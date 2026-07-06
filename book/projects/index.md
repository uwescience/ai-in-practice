# Project Work

This page describes the purpose of the projects, how project time is structured, and how to scope a project that fits in the time available.

```{image} ../img/projects-montage.png
:alt: picture of people interacting during hackweek project work
:class: bg-primary mb-1
:width: 700px
:align: center
```

## How project time is structured

Days 2–5 include several hours of dedicated project time. Here is a rough budget:

- **Tuesday afternoon:** Project scoping and setup
- **Wednesday:** Extended project work with instructor consultations
- **Thursday:** Extended project work, focus on results and reproducibility
- **Friday morning:** Finalize results, prepare short presentation
- **Friday afternoon:** Project showcase

In total, you should expect roughly 15 hours of hands-on project time across the week. Although this sounds like a lot, the time will go by quickly, so we will be available to help you scope your work accordingly.


## Framing your project on the AI research lifecycle

The AI in Practice Summer Institute is organized around the AI research lifecycle: the stages a research project moves through from problem framing to results and reproducibility. A well-scoped workshop project usually focuses on moving one or two steps along this lifecycle. Or, you may wish to dive deeply into a single phase based on new things you learn during the tutorials.


<svg width="100%" viewBox="0 0 680 200" role="img" xmlns="http://www.w3.org/2000/svg">
  <title>AI research lifecycle</title>
  <desc>Six iterative stages of the AI research lifecycle: Frame the question, Prepare the data, Model, Evaluate, Interpret, and Share reproducibly. A dashed return arrow indicates that projects cycle through stages as understanding develops.</desc>
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
  </defs>
  <style>
    .stage { fill: #EEEDFE; stroke: #534AB7; }
    .title { font-family: system-ui, sans-serif; font-size: 14px; font-weight: 500; fill: #26215C; }
    .sub { font-family: system-ui, sans-serif; font-size: 12px; fill: #3C3489; }
    .connector { stroke: #73726c; stroke-width: 1.5; fill: none; }
    .caption { font-family: system-ui, sans-serif; font-size: 12px; fill: #73726c; }
  </style>
  <rect class="stage" x="10" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="60" y="62" text-anchor="middle" dominant-baseline="central">Frame</text>
  <text class="sub" x="60" y="82" text-anchor="middle" dominant-baseline="central">The question</text>
  <line class="connector" x1="110" y1="70" x2="121" y2="70" marker-end="url(#arrow)"/>
  <rect class="stage" x="122" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="172" y="62" text-anchor="middle" dominant-baseline="central">Prepare</text>
  <text class="sub" x="172" y="82" text-anchor="middle" dominant-baseline="central">The data</text>
  <line class="connector" x1="222" y1="70" x2="233" y2="70" marker-end="url(#arrow)"/>
  <rect class="stage" x="234" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="284" y="62" text-anchor="middle" dominant-baseline="central">Model</text>
  <text class="sub" x="284" y="82" text-anchor="middle" dominant-baseline="central">Train &amp; tune</text>
  <line class="connector" x1="334" y1="70" x2="345" y2="70" marker-end="url(#arrow)"/>
  <rect class="stage" x="346" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="396" y="62" text-anchor="middle" dominant-baseline="central">Evaluate</text>
  <text class="sub" x="396" y="82" text-anchor="middle" dominant-baseline="central">Measure fit</text>
  <line class="connector" x1="446" y1="70" x2="457" y2="70" marker-end="url(#arrow)"/>
  <rect class="stage" x="458" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="508" y="62" text-anchor="middle" dominant-baseline="central">Interpret</text>
  <text class="sub" x="508" y="82" text-anchor="middle" dominant-baseline="central">Explain</text>
  <line class="connector" x1="558" y1="70" x2="569" y2="70" marker-end="url(#arrow)"/>
  <rect class="stage" x="570" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="620" y="62" text-anchor="middle" dominant-baseline="central">Share</text>
  <text class="sub" x="620" y="82" text-anchor="middle" dominant-baseline="central">Reproducibly</text>
  <path class="connector" d="M 620 100 C 620 165, 60 165, 60 100" stroke-dasharray="4 4" marker-end="url(#arrow)"/>
  <text class="caption" x="340" y="185" text-anchor="middle">Iterate as understanding grows</text>
</svg>


### Example projects framed by lifecycle position

| **Starting fresh** | **Working prototype** | **Mature project** |
|---|---|---|
| Frame a research question and train a baseline model on a small labeled dataset using transfer learning. | Build a proper evaluation pipeline for an existing model: held-out test sets, appropriate metrics, honest performance estimates. | Bring an existing codebase up to reproducibility standards with documentation and a methods write-up. |
| *Frame → Prepare → Model* | *Evaluate → Interpret* | *Share* |

### Choosing your scope

These questions will help you narrow in on a scope of work for the projects:

- Where along the AI project lifecycle is my current work so far? 
- What stage of the lifecycle will benefit most from tutorials and instructor support?
- What stage of work do I often neglect due to lack of time? 

### Signs your scope is too large

- Your plan requires data you don't have yet.
- Your plan requires labeling data during the workshop.
- Your plan has more than 3 distinct stages ("first I'll do X, then Y, then Z, then W...").
- You can't describe what "done" looks like in one specific sentence.
- Your plan assumes everything works on the first try.
- You're planning to train a model from scratch on a large dataset.

One way you can reduce scope is to temporarily fix some of the earlier stages as inputs. For example, even if you have an imperfect dataset, you could start with it as it is, and focus on model tuning so you can make progress in a new area of work.

### Scoping Exercise

Before the Institute, we suggest writing a one-sentence description of what you want to have by Friday afternoon. Try to make it as concrete and observable as possible.

**Well scoped examples:**
- "I will produce a working fine-tuning pipeline that takes my labeled dataset, trains a model, and produces evaluation plots on a held-out test set."
- "I will build a comparison table showing accuracy and training time for three different transfer learning strategies on my classification task."
- "I will make a reproducible notebook that extracts embeddings from my domain data using a pretrained model and clusters them, with a visualization."

**Poorly scoped examples:**
- "I hope to make progress on my dissertation."
- "I will explore whether AI can help with my research."
- "I plan to learn about foundation models."


