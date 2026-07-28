# Responsible AI

**Responsible AI** is the practice of designing, developing, deploying, and using AI systems in ways that identify, evaluate, and reduce potential risks and harms — while maximizing benefit — throughout the AI lifecycle.

There is no universal checklist that fits every project. Different projects carry different risks, stakeholders, and domains. These four questions serve as a lens you can apply to any project:

1. Who / what could be affected or harmed?
2. What could go wrong, or cause harm?
3. How likely is that harm, and how would we know?
4. What can we do to reduce that risk?

The goal isn't to eliminate all risk. It's to recognize what matters most in *your* context, and design for it from the start.


## Questions Across the AI/ML Lifecycle

![AI/ML Lifecycle](ai_lifecycle_figure.png)

| Stage | Guiding Questions | Example Risk / Harm |
|---|---|---|
| Framing the Research Problem as an ML Problem | •&nbsp;Should AI even be used for this problem?•&nbsp;Is it making the decision, supporting it, or assisting a human in the loop? | Reducing a complex outcome to a proxy that doesn't capture what you actually care about |
| Data Collection & Preparation | •&nbsp;Where does this data come from?•&nbsp;Do we have permission to use it?•&nbsp;Does it represent the people and scenarios the system will encounter? | A dataset reflects only part of the population it's meant to serve |
| Model Selection | •&nbsp;Which model is appropriate, not just which performs best?•&nbsp;Could explainability matter more than a small accuracy gain? | A black-box model is chosen when a simpler, interpretable one performs nearly as well |
| Model Training | •&nbsp;Could the model memorize sensitive data?•&nbsp;Could training introduce new bias?•&nbsp;How robust is it to shifts in data or environment? | A model learns a spurious shortcut (such as memorization) instead of the actual signal |
| Model Evaluation | •&nbsp;Does it perform equally well across subgroups, or only on average?•&nbsp;Has it been tested outside its training conditions?•&nbsp;Has it been audited? | High overall accuracy hides much higher error rates for one subgroup |
| Model Deployment | •&nbsp;Who is monitoring performance after launch?•&nbsp;Can a human review, override, or appeal a decision?•&nbsp;Who is accountable if it fails? | Accuracy degrades as real-world conditions drift from training data, unnoticed |
| Research Communication | •&nbsp;Are findings communicated honestly?•&nbsp;Would someone using your tool without talking to you understand its limitations? | A tool is described as more capable or certain than the evidence supports |

*Note: the lifecycle loops — what you learn from deployment and communication should reshape how you frame the next iteration.*

### A Note on Generative & Agentic AI

Generative and agentic systems (LLMs, autonomous agents, multi-step tool-using systems) don't map neatly onto a single lifecycle stage — the same run can touch several at once. A few risks worth knowing about if your project involves them:

- **Hallucination** — fluent, confident output that isn't factually grounded.
- **Goal misgeneralization** — an agent optimizes for what it was told rather than what was intended.
- **Unsupervised action-taking** — agents that call tools, write files, or take multi-step actions with limited human review in between steps.
- **Cascading errors** — a small mistake early in an agent's reasoning compounds across later steps.
- **Provenance / content authenticity** — knowing whether content was AI-generated, and being able to trace it back.

See NIST's [Generative AI Profile (NIST-AI-600-1)](https://www.nist.gov/itl/ai-risk-management-framework) for a more detailed treatment.

## Mitigation Techniques (Advanced)

| Risk Area | Relevant Stage(s) | Techniques |
|---|---|---|
| Privacy | Data, Training | •&nbsp;Differential Privacy (DP) •&nbsp;Federated Learning (FL) •&nbsp;Anonymization •&nbsp;Data minimization |
| Privacy | Evaluation, Deployment | •&nbsp;Membership inference,  Privacy Audits |
| Bias / Fairness | Data Preparation | •&nbsp;Reweighting •&nbsp;Resampling |
| Bias / Fairness | Training | •&nbsp;Fairness-constrained training (e.g., Fairlearn, AIF360) |
| Bias / Fairness | Evaluation, Deployment | •&nbsp;Threshold adjustment• &nbsp;Disaggregated (subgroup) evaluation |
| Explainability | Model Selection | •&nbsp;Inherently interpretable models (decision trees, linear/logistic models, GAMs) |
| Explainability | Evaluation | •&nbsp;LIME •&nbsp;SHAP •&nbsp; Feature importance |
| Robustness | Training | •&nbsp;Adversarial training •&nbsp;Data augmentation |
| Robustness | Evaluation | •&nbsp;Stress testing •&nbsp;Uncertainty quantification (Bayesian methods, ensembles, conformal prediction) |
| Robustness | Deployment | •&nbsp;Distribution shift / OOD detection •&nbsp;Production monitoring |
| Hallucination (GenAI) | Model Selection, Training | •&nbsp;Retrieval-Augmented Generation (RAG) •&nbsp;Calibrated refusal |
| Hallucination (GenAI) | Evaluation, Deployment | •&nbsp;Fact-verification •&nbsp;Watermarking / provenance |
| Accountability | Deployment, Communication | •&nbsp;Model cards •&nbsp;Datasheets •&nbsp;Audit trails•&nbsp;Human-in-the-loop review •&nbsp;Red-teaming |

## Glossary


- **Bias (algorithmic)** — Systematic errors in a model's output that disadvantage particular groups, often traceable to patterns in training data, labeling, or problem framing.

- **Calibration** — Whether a model's confidence in a prediction matches how often it's actually correct (a model that says "90% confident" should be right about 90% of the time).

- **Construct validity** — Whether the thing a model is trained to predict (the label) actually captures the real-world concept it's meant to represent.

- **Data governance** — Practices around how data is sourced, stored, used, and maintained, covering privacy, consent, representation, and quality.

- **Differential Privacy (DP)** — A mathematical framework for adding calibrated noise to data or model outputs so that no individual record can be confidently identified.

- **Distribution shift** — When the data a model encounters after deployment differs statistically from the data it was trained on.

- **Explainability / Interpretability** — The degree to which a person can understand why a model produced a particular output.

- **Fairness (algorithmic)** — A model performing comparably, or equitably, across different demographic or contextual subgroups. Note: there are multiple mathematical definitions of fairness, and they can conflict with one another.

- **Federated Learning (FL)** — A training approach where a model learns across decentralized datasets (e.g., multiple hospitals or devices) without the raw data ever leaving its original location.

- **Hallucination** — When a generative AI model produces output that is fluent and confident but factually incorrect or unsupported by its training data or sources.

- **Human-in-the-loop** — A system design where a person can review, override, or intervene in a model's decision before it takes effect.

- **Membership inference** — An attack or test that determines whether a specific individual's data was used to train a model.

- **Out-of-distribution (OOD) detection** — Techniques for identifying when an input differs significantly from the data a model was trained on, so it can be flagged rather than acted on blindly.

- **Proxy** — A measurable variable used as a stand-in for a real-world concept that can't be directly observed (e.g., "arrest" as a proxy for "crime committed").

- **Robustness** — A model's ability to maintain reliable performance under new, unexpected, or adversarial conditions.

- **Shortcut learning** — When a model learns a spurious correlation that happens to predict well on training data but doesn't reflect the actual signal of interest.

- **Goal misgeneralization** — a model or agent pursues a proxy objective rather than the intended goal, often invisibly until deployment.
- **Provenance** — the ability to trace content or a decision back to its source (e.g., confirming it was AI-generated).
- **Proxy** — a measurable stand-in for a real-world concept that can't be directly observed.



## References
**Frameworks**
- NIST, *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*, 2023 — nist.gov/itl/ai-risk-management-framework
- NIST, *Generative AI Profile (NIST-AI-600-1)*, 2024 — companion to AI RMF, covers hallucination, provenance, agentic risk
- *EU Artificial Intelligence Act* — artificialintelligenceact.eu

**Foundational Texts**
- Barocas, Hardt & Narayanan, *Fairness and Machine Learning* — free online at fairmlbook.org
- Molnar, *Interpretable Machine Learning* — free online at christophm.github.io/interpretable-ml-book
- Dwork & Roth, *The Algorithmic Foundations of Differential Privacy* — foundational text; Desfontaines, *"Ted Is Writing Things"* (desfontain.es) for an accessible, regularly updated treatment
- Christian, *The Alignment Problem* — accessible, holistic book spanning fairness, safety, and trustworthy AI
- Liang et al., *"Holistic Evaluation of Language Models"* (HELM), Stanford CRFM, 2022
- Chan et al., *"Harms from Increasingly Agentic AI Systems,"* FAccT 2023

**Further Readings**
- *Fairness* — Kleinberg, Mullainathan & Raghavan, *"Inherent Trade-Offs in the Fair Determination of Risk Scores,"* ITCS 2017; Kearns, Neel, Roth & Wu, *"Preventing Fairness Gerrymandering: Auditing and Learning for Subgroup Fairness,"* ICML 2018; Verma & Rubin, *"Fairness Definitions Explained,"* FairWare 2018; Hardt, Price & Srebro, *"Equality of Opportunity in Supervised Learning,"* NeurIPS 2016
- *Privacy* — Shokri et al., *"Membership Inference Attacks against Machine Learning Models,"* IEEE S&P 2017; Abadi et al., *"Deep Learning with Differential Privacy,"* CCS 2016 (DP-SGD)
- *Robustness* — Carlini et al., *"On Evaluating Adversarial Robustness,"* 2019
- *Explainability* — Ribeiro, Singh & Guestrin, *"'Why Should I Trust You?'"* (LIME), KDD 2016; Lundberg & Lee, *"A Unified Approach to Interpreting Model Predictions"* (SHAP), NeurIPS 2017; Wachter, Mittelstadt & Russell, *"Counterfactual Explanations Without Opening the Black Box,"* Harvard JOLT 2018
- *Accountability* — Raji et al., *"Closing the AI Accountability Gap,"* FAT* 2020
- *Generative & Agentic AI* — Casper et al., *"Open Problems and Fundamental Limitations of RLHF,"* 2023; Wei, Haghtalab & Steinhardt, *"Jailbroken: How Does LLM Safety Training Fail?,"* NeurIPS 2023; *"Alignment of Language Agents,"* 2021

**Toolkits**
- *Fairness* — Fairlearn (fairlearn.org), AI Fairness 360 (aif360.res.ibm.com)
- *Privacy* — Opacus (opacus.ai), OpenDP (opendp.org), TensorFlow Privacy (github.com/tensorflow/privacy)
- *Robustness* — RobustBench (robustbench.github.io), Adversarial Robustness Toolbox (github.com/Trusted-AI/adversarial-robustness-toolbox)
- *Explainability* — Captum (captum.ai), InterpretML (interpret.ml)
- *Documentation & Governance* — Model Cards Toolkit (Google), Datasheets for Datasets templates

**Case Study Repositories**
- AI Incident Database — incidentdatabase.ai
- AIAAIC Repository — aiaaic.org

**Others**
- Trustworthy Machine Learning — trustworthy-machine-learning.github.io
- Stanford AI Index Report (annual) — aiindex.stanford.edu
- ACM FAccT Conference proceedings — facctconference.org
- AI Snake Oil (Narayanan & Kapoor) — aisnakeoil.com