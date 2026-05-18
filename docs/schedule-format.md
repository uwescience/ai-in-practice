# Schedule Format Guide

The splash page supports two schedule display modes, toggled by a single key in
`book/schedule.yaml`.

---

## Modes

| Mode | `schedule_style` value | When to use |
|---|---|---|
| **Tentative Schedule** — overview table | `overview` | Before the event, when times are not yet finalised |
| **Schedule** — day-by-day tabs | `tabs` | Once the full agenda is ready |

---

## Switching modes

Edit the first line of `book/schedule.yaml`:

```yaml
schedule_style: overview   # "overview" or "tabs"
```

Then rebuild the site:

```bash
bash scripts/build_resources.sh
```

---

## Editing the splash page

> **Important:** Never edit `book/_build/html/index.html` directly — it is a
> build artifact and will be overwritten every time you run the build script.

All splash page changes must be made to the Jinja template:

```
{{ cookiecutter.repo_directory }}/index.html
```

This template is rendered by `cookiecutter` during the build and written to
`book/_build/html/index.html`. The schedule section in the template uses
`cookiecutter.schedule.schedule_style` to conditionally render the correct
heading and body content for each mode.

---

## Overview table content

The overview table content (tutorial topics and project work per day) is
currently hardcoded in the template. To update it, edit the relevant `<li>`
items inside the `{%- if cookiecutter.schedule.schedule_style == "overview" %}`
block in `{{ cookiecutter.repo_directory }}/index.html`.
