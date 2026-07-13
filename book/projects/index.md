# Project Work

This page describes the purpose of the projects, how project time is structured, and how to scope a project that fits in the time available.

```{image} ../img/projects-montage.png
:alt: picture of people interacting during hackweek project work
:class: bg-primary mb-1
:width: 700px
:align: center
```

## How project time is structured

Each day includes a few hours of dedicated project time. Here is a rough budget:

- **Monday afternoon:** Project consulting (optional)
- **Tuesday afternoon:** Project scoping and setup
- **Wednesday:** Extended project work with instructor consultations
- **Thursday:** Extended project work, focus on results and reproducibility
- **Friday morning:** Finalize results, prepare short presentation
- **Friday afternoon:** Project showcase

In total, you should expect roughly 15 hours of hands-on project time across the week. Although this sounds like a lot, the time will go by quickly, so we will be available to help you scope your work accordingly.


## Framing your project on the AI research lifecycle

The AI in Practice Summer Institute is organized around the AI research lifecycle: the stages a research project moves through from problem framing to results and reproducibility. A well-scoped workshop project usually focuses on moving one or two steps along this lifecycle. Or, you may wish to dive deeply into a single phase based on new things you learn during the tutorials.

In practice, the flow through the stages is rarely linear and it involves a lot of iteration. In fact, sometimes it is worthwhile going backwards: for example, training is done in conjunction with evaluation, or we can realize the way we have annotated the data is not helpful for training, and we can go back and revisit the data preparation step.

<svg width="100%" viewBox="0 0 680 200" role="img" xmlns="http://www.w3.org/2000/svg">
  <title>AI research lifecycle with iteration</title>
  <desc>Six iterative stages: Frame the question, Prepare the data, Train the model, Evaluate the performance, Deploy in practice, Share the results. Bidirectional arrows between adjacent stages indicate local iteration; a dashed return arrow indicates the overall cycle.</desc>
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
  <rect class="stage" x="5" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="55" y="61" text-anchor="middle" dominant-baseline="central">Frame</text>
  <text class="sub" x="55" y="81" text-anchor="middle" dominant-baseline="central">the question</text>
  <line class="connector" x1="105" y1="70" x2="119" y2="70" marker-start="url(#arrow)" marker-end="url(#arrow)"/>
  <rect class="stage" x="119" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="169" y="61" text-anchor="middle" dominant-baseline="central">Prepare</text>
  <text class="sub" x="169" y="81" text-anchor="middle" dominant-baseline="central">the data</text>
  <line class="connector" x1="219" y1="70" x2="233" y2="70" marker-start="url(#arrow)" marker-end="url(#arrow)"/>
  <rect class="stage" x="233" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="283" y="61" text-anchor="middle" dominant-baseline="central">Train</text>
  <text class="sub" x="283" y="81" text-anchor="middle" dominant-baseline="central">the model</text>
  <line class="connector" x1="333" y1="70" x2="347" y2="70" marker-start="url(#arrow)" marker-end="url(#arrow)"/>
  <rect class="stage" x="347" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="397" y="61" text-anchor="middle" dominant-baseline="central">Evaluate</text>
  <text class="sub" x="397" y="81" text-anchor="middle" dominant-baseline="central">the performance</text>
  <line class="connector" x1="447" y1="70" x2="461" y2="70" marker-start="url(#arrow)" marker-end="url(#arrow)"/>
  <rect class="stage" x="461" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="511" y="61" text-anchor="middle" dominant-baseline="central">Deploy</text>
  <text class="sub" x="511" y="81" text-anchor="middle" dominant-baseline="central">in practice</text>
  <line class="connector" x1="561" y1="70" x2="575" y2="70" marker-start="url(#arrow)" marker-end="url(#arrow)"/>
  <rect class="stage" x="575" y="40" width="100" height="60" rx="8" stroke-width="0.5"/>
  <text class="title" x="625" y="61" text-anchor="middle" dominant-baseline="central">Share</text>
  <text class="sub" x="625" y="81" text-anchor="middle" dominant-baseline="central">the results</text>
  <path class="connector" d="M 625 100 C 625 165, 55 165, 55 100" stroke-dasharray="4 4" marker-end="url(#arrow)"/>
  <text class="caption" x="340" y="185" text-anchor="middle">Iterate throughout — stages inform each other</text>
</svg>

### Example projects framed by lifecycle position

| **Starting fresh** | **Working prototype** | **Mature project** |
|---|---|---|
| Frame a research question and train a baseline model on a small labeled dataset using transfer learning. | Design an evaluation protocol for an existing model, and reorganize your data (training, validation, held-out sets) and code to generate appropriate metrics. | Generate a reproducible example and documentation so that a new researcher can use your model on their own data. |
| *Frame → Prepare → Model* | *Evaluate → Interpret* | *Share* |

### Choosing your scope

These questions will help you narrow in on a scope of work for the projects:

- Where along the AI project lifecycle is my current work so far? 
- What stage of the lifecycle will benefit most from tutorials and instructor support?
- What stage of work do I often neglect due to lack of time? 

As you are forming your ideas we encourage you to also reflect on your learning goals for the week. These might include:

- Learning how to set up new types of models and determine whether they are suitable for your research tasks.
- Reorganizing your data into a new format so that it is easier to use in various ML models.
- Working with a new dataset you want to integrate into your training or testing.
- Transferring your workflow from your laptop to the cloud so you can be more efficient with computational resources.

### Signs your scope is too large

- Your plan requires data you don't have yet.
- Your plan requires labeling data during the workshop.
- Your plan has more than 3 distinct stages ("first I'll do X, then Y, then Z, then W...").
- You can't describe what "done" looks like in one specific sentence.
- Your plan assumes everything works on the first try.
- You're planning to train a model from scratch on a large dataset.

One way you can reduce scope is to temporarily fix some of the earlier stages as inputs. For example, even if you have an imperfect dataset, you could start with it as it is, and focus on model tuning so you can make progress in a new area of work. Or, if the data you want to work with are not readily available, you could select a publicly-available dataset that is similar, just so you can gain the necessary experience.

## Writing Exercises

Before the Institute, we suggest writing a one-sentence description of what you want to have accomplished in the project, and a one-sentence description of what you hope to learn, by the end of the Institute. Try to make both sentences as concrete and observable as possible. Below are some examples.

### Project Scoping Examples

**Well-scoped:**
- "I will produce a working fine-tuning pipeline that takes my labeled dataset, trains a model, and produces evaluation plots on a held-out validation set."
- "I will build a comparison table showing accuracy and training time for three different transfer learning strategies on my classification task."
- "I will make a reproducible notebook that extracts embeddings from my domain data using a pretrained model, and clusters and visualizes them."

**Poorly-scoped:**
- "I hope to make progress on my dissertation."
- "I will explore whether AI can help with my research."
- "I plan to work on foundation models."

### Learning Goal Examples

**Well-scoped:**

- "I want to learn how to fine-tune a foundation model on my labeled dataset using the Hugging Face transformers library."
- "I want to learn how to extract embeddings from a pretrained vision model and use them as features in a downstream classifier."
- "I want to learn how to move a training workflow from my laptop to Hyak."

**Poorly-scoped:**

- "I want to learn AI."
- "I want to become an expert in transformers."
- "I want to understand how neural networks work." 

