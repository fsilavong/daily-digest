# HuggingFace featured papers digest — 2026-05-15

## Reasoning and agentic training

### Achieving Gold-Medal-Level Olympiad Reasoning via Simple and Unified Scaling
https://arxiv.org/abs/2605.13301

- The paper proposes a simple recipe for turning a post-trained reasoning backbone into an olympiad-level solver: reverse-perplexity curriculum SFT, then a two-stage RL pipeline, then test-time scaling [1](./citations/1.md).
- The authors say the SFT stage uses about 340K sub-8K-token trajectories, followed by 200 RL steps, on a 30B-A3B backbone [1](./citations/1.md).
- The resulting SU-01 model reportedly supports stable reasoning on trajectories over 100K tokens and reaches gold-medal-level performance on IMO/IPhO-style competitions, including IMO 2025/USAMO 2026 and IPhO 2024/2025 [1](./citations/1.md).
- The abstract also claims strong transfer of scientific reasoning beyond mathematics and physics, but gives no detailed breakdown in the snippet [1](./citations/1.md).

### Self-Distilled Agentic Reinforcement Learning
https://arxiv.org/abs/2605.15155

- This work adapts on-policy self-distillation to multi-turn agents by treating it as a gated auxiliary objective while keeping RL as the main optimization backbone [2](./citations/2.md).
- The method maps detached token-level signals into a sigmoid gate, strengthening distillation for teacher-endorsed positive-gap tokens and attenuating negative teacher rejections [2](./citations/2.md).
- Across Qwen2.5 and Qwen3 on ALFWorld, WebShop, and Search-QA, the authors report gains over GRPO of +9.4% on ALFWorld, +7.0% on Search-QA, and +10.2% on WebShop-Acc [2](./citations/2.md).
- The abstract emphasizes that naive GRPO+OPSD is unstable, while SDAR consistently outperforms hybrid RL–OPSD baselines across scales [2](./citations/2.md).

### Orchard: An Open-Source Agentic Modeling Framework
https://arxiv.org/abs/2605.15040

- Orchard is presented as an open-source framework for scalable agentic modeling, centered on Orchard Env, a lightweight environment service for sandbox lifecycle management across domains and pipeline stages [3](./citations/3.md).
- The paper offers three recipes: Orchard-SWE for coding agents, Orchard-GUI for computer-use agents, and Orchard-Claw for personal assistant agents [3](./citations/3.md).
- Orchard-SWE uses 107K distilled trajectories plus credit-assignment SFT and Balanced Adaptive Rollout RL; starting from Qwen3-30B-A3B-Thinking it reaches 64.3% on SWE-bench Verified after SFT and 67.5% after SFT+RL [3](./citations/3.md).
- Orchard-GUI and Orchard-Claw are reported to achieve 74.1%/67.0%/64.0% on WebVoyager/Online-Mind2Web/DeepShop and 59.6% pass@3 on Claw-Eval, respectively, supporting the claim that a reusable environment layer can scale agent data and evaluation [3](./citations/3.md).

### WildClawBench: A Benchmark for Real-World, Long-Horizon Agent Evaluation
https://arxiv.org/abs/2605.10912

- WildClawBench is a native-runtime benchmark of 60 human-authored bilingual multimodal tasks that execute in real CLI harnesses rather than synthetic sandboxes [4](./citations/4.md).
- Tasks average roughly 8 minutes of wall-clock time and over 20 tool calls, and are graded with deterministic checks, environment-state auditing, and LLM/VLM semantic verification [4](./citations/4.md).
- Across 19 frontier models, the best result is Claude Opus 4.7 at 62.2% overall under OpenClaw, with all others below 60%; the same model can shift by up to 18 points when the harness changes [4](./citations/4.md).
- The benchmark is positioned as evidence that long-horizon native-runtime agent evaluation remains unsolved for current frontier models [4](./citations/4.md).

## Multimodal memory and visual reasoning

### MemEye: A Visual-Centric Evaluation Framework for Multimodal Agent Memory
https://arxiv.org/abs/2605.15128

- MemEye targets a gap in multimodal memory evaluation: many prior questions can be answered from captions or text traces, so the benchmark adds cases that require preserving fine-grained visual evidence and reasoning over changing visual states [5](./citations/5.md).
- The framework scores memory along two dimensions: the granularity of decisive visual evidence and the way retrieved evidence must be used, ranging from single evidence to evolutionary synthesis [5](./citations/5.md).
- The authors build a benchmark over 8 life-scenario tasks with validation gates for answerability, shortcut resistance, visual necessity, and reasoning structure [5](./citations/5.md).
- Evaluating 13 memory methods across 4 VLM backbones, the paper concludes that current systems still struggle to preserve fine visual detail and track state changes over time [5](./citations/5.md).

### MemLens: Benchmarking Multimodal Long-Term Memory in Large Vision-Language Models
https://arxiv.org/abs/2605.14906

- MEMLENS compares long-context LVLMs with memory-augmented agents on multimodal multi-session conversations that genuinely require visual evidence [6](./citations/6.md).
- The benchmark contains 789 questions spanning five abilities: information extraction, multi-session reasoning, temporal reasoning, knowledge update, and answer refusal, evaluated at 32K-256K context lengths [6](./citations/6.md).
- An image-ablation study shows that removing evidence images drops two frontier LVLMs below 2% accuracy on the 80.4% of questions whose evidence includes images, indicating that the task is not solvable from text alone [6](./citations/6.md).
- The evaluation of 27 LVLMs and 7 memory-augmented agents suggests that long-context models are better grounded in short contexts but degrade with length, while memory agents remain length-stable but lose visual fidelity under compression; multi-session reasoning keeps most systems below 30% [6](./citations/6.md).

### BOOKMARKS: Efficient Active Storyline Memory for Role-playing
https://arxiv.org/abs/2605.14169

- BOOKMARKS replaces recurrent summarization with a search-based memory framework that actively initializes, maintains, and updates reusable bookmarks for role-playing agents [9](./citations/9.md).
- A bookmark is defined as the answer to a question at a specific point in the storyline, and the system supports concept, behavior, and state searches with synchronization so the bookmarks can be updated as the story moves forward [9](./citations/9.md).
- The authors frame this as a way to retain task-specific details while avoiding unnecessary recomputation, contrasting it with compression-heavy profiling approaches [9](./citations/9.md).
- The abstract claims strong results on 85 characters from 16 artifacts, but does not provide detailed per-task scores in the snippet [9](./citations/9.md).

## Video generation, world models, and 3D editing

### Warp-as-History: Generalizable Camera-Controlled Video Generation from One Training Video
https://arxiv.org/abs/2605.15182

- Warp-as-History converts camera-induced warps into camera-warped pseudo-history, then feeds that into the model's visual-history pathway with positional alignment and visible-token selection [7](./citations/7.md).
- The method is explicitly training-free at inference: it requires no architectural modification or test-time optimization to expose zero-shot camera-following behavior in a frozen video generator [7](./citations/7.md).
- A lightweight offline LoRA finetune on only one camera-annotated video further improves adherence, quality, and motion dynamics, and the gains generalize to unseen videos [7](./citations/7.md).
- The abstract says experiments across diverse datasets confirm the approach, but the snippet does not include the specific metrics [7](./citations/7.md).

### SANA-WM: Efficient Minute-Scale World Modeling with Hybrid Linear Diffusion Transformer
https://arxiv.org/abs/2605.15178

- SANA-WM is a 2.6B-parameter open-source world model trained natively for one-minute generation, producing 720p minute-scale videos with camera control [8](./citations/8.md).
- Its architecture combines hybrid linear attention, dual-branch camera control, a two-stage generation pipeline, and a robust annotation pipeline for metric-scale 6-DoF pose labels [8](./citations/8.md).
- The paper emphasizes efficiency: training uses 213K public video clips, takes 15 days on 64 H100s, and inference can run one 60s clip on a single GPU; a distilled variant can denoise a 60s 720p clip in 34s on a single RTX 5090 with NVFP4 quantization [8](./citations/8.md).
- On its minute-scale benchmark, SANA-WM reports stronger action-following accuracy than prior open-source baselines and comparable visual quality at 36× higher throughput [8](./citations/8.md).

### VGGT-Edit: Feed-forward Native 3D Scene Editing with Residual Field Prediction
https://arxiv.org/abs/2605.15186

- VGGT-Edit is a feed-forward framework for text-conditioned native 3D scene editing, designed to avoid the blurry textures and geometry inconsistencies of 2D-lifting pipelines [10](./citations/10.md).
- The method uses depth-synchronized text injection for instruction grounding and a residual transformation head that predicts 3D geometric displacements while preserving background stability [10](./citations/10.md).
- The authors also introduce DeltaScene, a large-scale dataset generated with automated 3D agreement filtering to improve ground-truth quality [10](./citations/10.md).
- The abstract claims substantially better sharpness, multi-view consistency, and near-instant inference versus 2D-lifting baselines [10](./citations/10.md).

### ATLAS: Agentic or Latent Visual Reasoning? One Word is Enough for Both
https://arxiv.org/abs/2605.15198

- ATLAS proposes a single discrete functional token that serves both as an agentic operation and as a latent visual reasoning unit [11](./citations/11.md).
- The token requires no visual supervision, remains a normal vocabulary token, and can be generated through next-token prediction, letting the method stay compatible with standard SFT and RL [11](./citations/11.md).
- To address sparse functional-token usage in RL, the paper adds Latent-Anchored GRPO, which anchors functional tokens with a statically weighted auxiliary objective for stronger gradients [11](./citations/11.md).
- The abstract claims superior performance on challenging benchmarks with better interpretability, but no exact benchmark names or numbers are provided in the snippet [11](./citations/11.md).

## Optimization, model merging, and diffusion

### Darwin Family: MRI-Trust-Weighted Evolutionary Merging for Training-Free Scaling of Language-Model Reasoning
https://arxiv.org/abs/2605.14386

- Darwin Family explores training-free evolutionary merging of LLMs through gradient-free weight-space recombination rather than additional post-training [12](./citations/12.md).
- The framework includes a 14-dimensional adaptive merge genome, MRI-Trust Fusion for balancing layer-importance signals with evolutionary search, and an Architecture Mapper for cross-architecture breeding [12](./citations/12.md).
- The flagship Darwin-27B-Opus is reported to reach 86.9% on GPQA Diamond and rank #6 among 1,252 evaluated models, outperforming its fully trained foundation model without gradient-based training [12](./citations/12.md).
- The abstract further claims improvements across 4B–35B scales and support for recursive multi-generation evolution, including merging Transformer and Mamba components [12](./citations/12.md).

### DiffusionOPD: A Unified Perspective of On-Policy Distillation in Diffusion Models
https://arxiv.org/abs/2605.15055

- DiffusionOPD reframes multi-task diffusion-model training as online policy distillation, with task-specific teachers distilled into a unified student along the student's own rollout trajectories [13](./citations/13.md).
- The authors extend OPD from discrete tokens to continuous-state Markov processes and derive a closed-form per-step KL objective that unifies stochastic SDE and deterministic ODE refinement via mean-matching [13](./citations/13.md).
- The abstract claims the analytic gradient has lower variance and better generality than PPO-style policy gradients [13](./citations/13.md).
- Experiments reportedly show better training efficiency and final performance than multi-reward RL and cascade RL, with state-of-the-art results on all evaluated benchmarks [13](./citations/13.md).

## Surveys and broader framing

### Beyond Individual Intelligence: Surveying Collaboration, Failure Attribution, and Self-Evolution in LLM-based Multi-Agent Systems
https://arxiv.org/abs/2605.14892

- This survey organizes multi-agent systems around a four-stage LIFE progression: lay the capability foundation, integrate agents through collaboration, find faults through attribution, and evolve through autonomous self-improvement [14](./citations/14.md).
- It argues that existing surveys split individual capability, collaboration, and self-evolution into separate topics, whereas this paper emphasizes the causal dependencies between those stages [14](./citations/14.md).
- The survey contributes taxonomies, boundary-specific open problems, and a cross-stage research agenda for closed-loop multi-agent systems that can diagnose failures and reorganize themselves [14](./citations/14.md).
- This is a synthesis paper rather than an empirical result paper, so its value is mainly in framing and categorization [14](./citations/14.md).
