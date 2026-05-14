# HuggingFace Papers Digest — 2026-04-29

## Agents, recursion, and autonomous workflows

### Recursive Multi-Agent Systems
https://arxiv.org/abs/2604.25917

- RecursiveMAS scales collaboration itself by casting heterogeneous agents into a unified latent-space recursive computation, connected with a lightweight RecursiveLink module for latent thought generation and cross-agent state transfer [1](./citations/1.md).
- The method uses an inner-outer loop learning algorithm so the whole system can be co-optimized across recursion rounds with shared gradient-based credit assignment [1](./citations/1.md).
- The paper reports theoretical runtime and learning-dynamics results claiming better efficiency than standard text-based multi-agent systems and stable gradients during recursive training [1](./citations/1.md).
- Empirically, it is evaluated across 4 collaboration patterns and 9 benchmarks in mathematics, science, medicine, search, and code generation, with an average accuracy gain of 8.3%, 1.2x-2.4x speedup, and 34.6%-75.6% token reduction versus strong baselines [1](./citations/1.md).

### AutoResearchBench: Benchmarking AI Agents on Complex Scientific Literature Discovery
https://arxiv.org/abs/2604.25256

- AutoResearchBench targets autonomous scientific literature discovery, separating the task into Deep Research, which tracks down a specific target paper through multi-step probing, and Wide Research, which collects all papers satisfying given conditions [4](./citations/4.md).
- The benchmark is explicitly research-oriented, literature-focused, and open-ended, making it harder than standard agentic web-browsing tasks because the number of qualifying papers is unknown and the agent must reason during search [4](./citations/4.md).
- Even strong LLMs reportedly reach only 9.39% accuracy on Deep Research and 9.31% IoU on Wide Research, with many baselines below 5%, suggesting a large gap in scientific search competence [4](./citations/4.md).

### Toward Scalable Terminal Task Synthesis via Skill Graphs
https://arxiv.org/abs/2604.25727

- SkillSynth is an automated framework for terminal task synthesis built around a scenario-mediated skill graph that connects diverse command-line skills through intermediate scenarios [8](./citations/8.md).
- It samples workflow paths from the graph and uses a multi-agent harness to instantiate executable task instances, with the stated goal of controlling the diversity of minimal execution trajectories seen in training [8](./citations/8.md).
- The abstract says experiments on Terminal-Bench validate the approach, and that synthesized tasks were used to train Hy3 Preview, contributing to improved terminal-agent capabilities [8](./citations/8.md).

### TCOD: Exploring Temporal Curriculum in On-Policy Distillation for Multi-turn Autonomous Agents
https://arxiv.org/abs/2604.24005

- TCOD addresses on-policy distillation in multi-turn agent settings by targeting trajectory-level KL instability, where KL divergence rises as success drops and remains high even after convergence [9](./citations/9.md).
- The proposed fix is a temporal curriculum that starts the student on short trajectories and progressively expands to longer ones, reducing compounding error and keeping supervision within the teacher’s effective support [9](./citations/9.md).
- The authors report results across four student-teacher pairs and three multi-turn benchmarks (ALFWorld, WebShop, ScienceWorld), with up to 18-point improvement over vanilla OPD and cases where TCOD surpasses teacher performance [9](./citations/9.md).

### Co-Director: Agentic Generative Video Storytelling
https://arxiv.org/abs/2604.24842

- Co-Director frames video storytelling as a global optimization problem in a hierarchical multi-agent system, aiming to reduce semantic drift and cascading failures in chained prompting pipelines [10](./citations/10.md).
- It uses a multi-armed bandit to choose promising creative directions and a local multimodal self-refinement loop to mitigate identity drift and preserve sequence-level consistency [10](./citations/10.md).
- Evaluation is done on GenAD-Bench, a 400-scenario dataset of fictional products for personalized advertising; the abstract says the method outperforms state-of-the-art baselines [10](./citations/10.md).

## Multimodal generation and editing

### Refinement via Regeneration: Enlarging Modification Space Boosts Image Refinement in Unified Multimodal Models
https://arxiv.org/abs/2604.25636

- The paper argues that existing refinement-via-editing methods for unified multimodal models are too restrictive because they rely on coarse editing instructions and pixel-level preservation of aligned content [5](./citations/5.md).
- Refinement via Regeneration reframes the task as conditional image regeneration conditioned on the target prompt and semantic tokens of the initial image, enlarging the modification space while still aiming for semantic alignment [5](./citations/5.md).
- Reported results improve Geneval from 0.78 to 0.91, DPGBench from 84.02 to 87.21, and UniGenBench++ from 61.53 to 77.41 [5](./citations/5.md).

### Meta-CoT: Enhancing Granularity and Generalization in Image Editing
https://arxiv.org/abs/2604.24625

- Meta-CoT decomposes a single-image editing operation into a triplet of task, target, and required understanding ability, with the goal of improving understanding granularity during editing [6](./citations/6.md).
- A second decomposition breaks editing tasks into five fundamental meta-tasks, and the authors claim training on those plus the triplet elements is sufficient for generalization to unseen editing tasks [6](./citations/6.md).
- The method adds a CoT-Editing Consistency Reward to better align the model’s editing behavior with its chain-of-thought reasoning [6](./citations/6.md).
- The abstract reports an overall 15.8% improvement across 21 editing tasks and strong generalization from a small set of meta-tasks [6](./citations/6.md).

### Mutual Forcing: Dual-Mode Self-Evolution for Fast Autoregressive Audio-Video Character Generation
https://arxiv.org/abs/2604.25819

- Mutual Forcing is a fast autoregressive audio-video generation framework that is designed to preserve long-horizon synchronization while jointly modeling audio and video [7](./citations/7.md).
- It uses a two-stage training strategy: train unimodal generators first, then couple them for joint training on paired data [7](./citations/7.md).
- For streaming generation, the model combines few-step and multi-step generation in one weight-shared model so they can self-distill each other and improve training-inference consistency without a separate bidirectional teacher [7](./citations/7.md).
- The paper claims it matches or surpasses strong baselines that use around 50 sampling steps while using only 4 to 8 steps [7](./citations/7.md).

### IAM: Identity-Aware Human Motion and Shape Joint Generation
https://arxiv.org/abs/2604.25164

- IAM adds identity awareness to text-driven human motion generation by explicitly modeling the relationship between body morphology and motion dynamics instead of treating motion as identity-neutral [11](./citations/11.md).
- Identity is represented using multimodal signals, including natural language descriptions and visual cues, and the framework jointly synthesizes motion sequences and body-shape parameters [11](./citations/11.md).
- The abstract says experiments on motion capture datasets and in-the-wild videos improve motion realism and motion-identity consistency while keeping motion quality high [11](./citations/11.md).

### A Systematic Post-Train Framework for Video Generation
https://arxiv.org/abs/2604.25427

- The framework proposes four post-training stages for video diffusion models: supervised fine-tuning, RLHF with a new GRPO method tailored for video diffusion, prompt enhancement with a specialized language model, and inference optimization [12](./citations/12.md).
- The goal is to address prompt sensitivity, temporal inconsistency, and inference cost gaps between pretraining performance and deployment needs [12](./citations/12.md).
- The abstract claims the pipeline improves visual quality, temporal coherence, and instruction following while preserving controllability and meeting sampling-cost constraints [12](./citations/12.md).

## Safety, governance, and evaluation

### BARRED: Synthetic Training of Custom Policy Guardrails via Asymmetric Debate
https://arxiv.org/abs/2604.25203

- BARRED generates synthetic training data for custom policy guardrails from only a task description and a small set of unlabeled examples, avoiding the need for large human-labeled datasets [7](./citations/7.md).
- It decomposes the domain into dimensions for coverage and uses multi-agent debate to verify label correctness, aiming to build a high-fidelity training corpus [7](./citations/7.md).
- The abstract says small language models fine-tuned on the synthetic data outperform proprietary LLMs and dedicated guardrail models, and that both dimension decomposition and debate verification are important [7](./citations/7.md).

### DV-World: Benchmarking Data Visualization Agents in Real-World Scenarios
https://arxiv.org/abs/2604.25914

- DV-World is a 260-task benchmark for data-visualization agents that emphasizes native environmental grounding, cross-platform evolution, and proactive intent alignment rather than sandboxed, creation-only tasks [2](./citations/2.md).
- It spans DV-Sheet, DV-Evolution, and DV-Interact, covering spreadsheet manipulation, adapting reference visual artifacts to new data, and interaction with a user simulator under ambiguous requirements [2](./citations/2.md).
- The evaluation combines Table-value Alignment for numeric precision and MLLM-as-a-Judge for semantic-visual assessment [2](./citations/2.md).
- The abstract says state-of-the-art models achieve under 50% overall performance, exposing major gaps in real-world visualization workflows [2](./citations/2.md).

### MAIC-UI: Making Interactive Courseware with Generative UI
https://arxiv.org/abs/2604.25806

- MAIC-UI is a zero-code authoring system for educators to create and rapidly edit interactive STEM courseware from textbooks, PPTs, and PDFs [13](./citations/13.md).
- It combines structured knowledge analysis, a two-stage generate-verify-optimize pipeline, and Click-to-Locate editing with Unified Diff-based incremental generation for sub-10-second iteration cycles [13](./citations/13.md).
- The abstract reports a lab study with 40 participants showing fewer edit iterations and better learnability/controllability than direct Text-to-HTML generation, plus a three-month classroom deployment with 53 students and stronger STEM gains in the pilot class [13](./citations/13.md).

## Audio and dialogue alignment

### Step-Audio-R1.5 Technical Report
https://arxiv.org/abs/2604.25719

- The report critiques reinforcement learning with verified rewards for audio reasoning as a “verifiable reward trap,” arguing that it optimizes discrete correctness at the expense of real-world conversational and prosodic quality [14](./citations/14.md).
- Step-Audio-R1.5 shifts toward reinforcement learning from human feedback for audio reasoning, with the goal of preserving analytical reasoning while improving long-turn spoken interaction quality [14](./citations/14.md).
- The abstract says comprehensive evaluations show the model maintains strong reasoning and substantially improves the interactive experience in immersive dialogue settings [14](./citations/14.md).
