# HuggingFace Featured Papers Digest — 2026-05-05

## Robotics, embodied reasoning, and control

### MolmoAct2: Action Reasoning Models for Real-world Deployment
https://arxiv.org/abs/2605.02881

- Fully open VLA action-reasoning model aimed at practical robot deployment, with a new VLM backbone (MolmoER), a new action tokenizer (OpenFAST), new datasets, and an adaptive-depth reasoning variant (MolmoThink) [1](./citations/1.md).
- Training and data claims are unusually concrete: MolmoER is trained on a 3.3M-sample corpus; MolmoAct2-BimanualYAM contributes 720 hours of teleoperated bimanual trajectories and is described as the largest open bimanual dataset to date [1](./citations/1.md).
- The paper reports a broad empirical study across 7 simulation and real-world benchmarks, with MolmoAct2 outperforming strong baselines including Pi-05; MolmoER is said to surpass GPT-5 and Gemini Robotics ER-1.5 on 13 embodied-reasoning benchmarks [1](./citations/1.md).
- Why it matters: this is the most directly deployment-oriented open VLA in the batch, combining model, tokenizer, data, and latency-aware reasoning improvements in one release [1](./citations/1.md).

## Agents, context learning, and evaluation

### From Context to Skills: Can Language Models Learn from Context Skillfully?
https://arxiv.org/abs/2604.27660

- Proposes Ctx2Skill, a self-evolving framework that discovers, refines, and selects context-specific natural-language skills without human supervision or external feedback [2](./citations/2.md).
- The mechanism is a multi-agent self-play loop: a Challenger generates probing tasks/rubrics, a Reasoner solves them using evolving skills, and a Judge returns binary feedback; Proposer and Generator agents mine failures into skill updates [2](./citations/2.md).
- Adds Cross-time Replay to avoid adversarial collapse and over-specialization by selecting the skill set that best balances representative cases for the Reasoner [2](./citations/2.md).
- Evaluated on four CL-bench context-learning tasks, with consistent solving-rate gains across backbone models [2](./citations/2.md).

### PhysicianBench: Evaluating LLM Agents in Real-World EHR Environments
https://arxiv.org/abs/2605.02240

- Introduces a benchmark for LLM agents in real EHR workflows rather than static knowledge or single-step actions, targeting long-horizon physician tasks [5](./citations/5.md).
- Contains 100 consultation-derived tasks reviewed by physicians, spanning 21 specialties and requiring an average of 27 tool calls per task inside a real EHR environment with commercial-vendor-style APIs [5](./citations/5.md).
- Uses 670 structured checkpoints with execution-grounded verification; tasks require retrieval across encounters, reasoning over heterogeneous clinical information, actions, and documentation [5](./citations/5.md).
- Results are stark: the best of 13 proprietary/open agents reaches 46% pass@1, while open-source models top out at 19% [5](./citations/5.md).

### AcademiClaw: When Students Set Challenges for AI Agents
https://arxiv.org/abs/2605.02661

- Bilingual benchmark of 80 long-horizon tasks sourced from university students’ real workflows, selected from 230 submissions and expert-reviewed [8](./citations/8.md).
- Tasks span 25+ domains, including olympiad-level math/linguistics, GPU-intensive reinforcement learning, and full-stack debugging; 16 tasks require CUDA execution [8](./citations/8.md).
- Evaluation runs in isolated Docker sandboxes with multi-dimensional rubrics plus a five-category safety audit [8](./citations/8.md).
- Best of six frontier models reaches only 55% pass rate, and the paper emphasizes capability boundaries and behavior differences beyond aggregate scores [8](./citations/8.md).

### T^2PO: Uncertainty-Guided Exploration Control for Stable Multi-Turn Agentic Reinforcement Learning
https://arxiv.org/abs/2605.02178

- Proposes Token- and Turn-level Policy Optimization (T^2PO), an uncertainty-aware method to stabilize multi-turn RL for reasoning LLMs by controlling low-information exploration [9](./citations/9.md).
- Token-level intervention triggers thinking when marginal uncertainty change falls below a threshold; turn-level resampling drops interactions that do not make exploration progress [9](./citations/9.md).
- Evaluated on WebShop, ALFWorld, and Search QA, where it improves training stability and performance while using exploration more efficiently [9](./citations/9.md).

## Multimodal, ocean, and visual grounding

### OceanPile: A Large-Scale Multimodal Ocean Corpus for Foundation Models
https://arxiv.org/abs/2605.00877

- Builds OceanPile as a multimodal corpus for ocean foundation models, addressing the field’s fragmented, noisy, weakly labeled data bottleneck [3](./citations/3.md).
- The package has three parts: OceanCorpus (sonar, underwater imagery, marine science visuals, scientific text), OceanInstruction (instruction data synthesized with a hierarchical Ocean Concept Knowledge Graph), and OceanBenchmark (manual evaluation set) [3](./citations/3.md).
- Includes a multi-stage quality-control pipeline for scientific validity and alignment across modalities [3](./citations/3.md).
- The abstract reports significant performance gains for models trained on the data and notes that all datasets are publicly released [3](./citations/3.md).

### Perceptual Flow Network for Visually Grounded Reasoning
https://arxiv.org/abs/2605.02730

- Proposes PFlowNet to reduce language bias and hallucination in LVLMs by decoupling perception from reasoning and avoiding rigid alignment to visual-expert priors [7](./citations/7.md).
- Uses multi-dimensional rewards plus vicinal geometric shaping via variational reinforcement learning to steer perceptual behavior while preserving visual reliability [7](./citations/7.md).
- Claims a provable performance guarantee and new SOTA on V* Bench (90.6%) and MME-RealWorld-lite (67.0%) [7](./citations/7.md).

## Generative modeling and efficiency

### Generative Modeling with Orbit-Space Particle Flow Matching
https://arxiv.org/abs/2605.02222

- Introduces OGPP, a particle-native flow-matching framework built around orbit-space canonicalization, index embeddings, and geometric probability paths with arc-length-aware terminal velocities [6](./citations/6.md).
- The motivation is that particle indexing inflates target variance under permutation symmetry, and that terminal velocity can encode geometric attributes such as normals [6](./citations/6.md).
- Reports large improvements on minimal-surface benchmarks, strong ShapeNet results with fewer steps and parameters, and competitive 3D reconstructions/normals on single-shape encoding [6](./citations/6.md).

### Motion-Aware Caching for Efficient Autoregressive Video Generation
https://arxiv.org/abs/2605.01725

- Proposes MotionCache, a motion-aware cache reuse strategy for autoregressive video generation that adapts update frequency by token using inter-frame differences as a proxy for motion [10](./citations/10.md).
- The paper argues that coarse chunk-level skipping misses high-motion pixels that need more denoising, while static pixels can be skipped more aggressively; it also gives a theoretical link between cache errors and residual instability [10](./citations/10.md).
- On SkyReels-V2 and MAGI-1, the abstract reports 6.28x and 1.64x speedups with only small VBench drops (1% and 0.01%) [10](./citations/10.md).

## Safety / preparedness

### Code World Model Preparedness Report
https://arxiv.org/abs/2605.00932

- Preparedness assessment for Meta’s Code World Model, focusing on domains in the Frontier AI Framework that could present catastrophic risks and on misaligned propensities [11](./citations/11.md).
- The report says CWM does not pose additional frontier risks beyond the current AI ecosystem and is therefore released as an open-weight model [11](./citations/11.md).
