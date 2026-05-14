# HuggingFace Papers Digest — 2026-05-14

## Infrastructure and systems

### MinT: Managed Infrastructure for Training and Serving Millions of LLMs
https://arxiv.org/abs/2605.13779
- MinT is a managed infrastructure system for LoRA post-training and online serving that keeps the base model resident while moving adapter revisions through rollout, update, export, evaluation, serving, and rollback [1](./citations/1.md).
- The paper frames the setting as many trained policies over a small number of expensive base-model deployments, with distributed training, serving, scheduling, and data movement hidden behind a service interface [1](./citations/1.md).
- Reported system wins include adapter-only handoff reducing a measured step by 18.3x on a 4B dense model and 2.85x on a 30B MoE, plus concurrent multi-policy GRPO shortening wall time without increasing peak memory [1](./citations/1.md).
- The scale-out claim is million-scale addressable catalogs, with single-engine sweeps through 100K and thousand-adapter active waves at cluster scale [1](./citations/1.md).

### Orthrus: Memory-Efficient Parallel Token Generation via Dual-View Diffusion
https://arxiv.org/abs/2605.12825
- Orthrus augments a frozen LLM with a lightweight trainable module to create a parallel diffusion view alongside the standard autoregressive view [11](./citations/11.md).
- Both views share the same high-fidelity KV cache, and an exact consensus mechanism is used to keep inference lossless [11](./citations/11.md).
- The reported result is up to a 7.8x speedup with O(1) memory cache overhead and minimal parameter additions [11](./citations/11.md).

### Results and Retrospective Analysis of the CODS 2025 AssetOpsBench Challenge
https://arxiv.org/abs/2605.08518
- This is a competition retrospective that combines rank sheets, submission logs, team registrations, winner reports, and verified source trees to explain what the challenge actually rewarded [8](./citations/8.md).
- The public planning leaderboard saturates at 72.73%, while public/private correlation is moderate for planning but negative for execution, so hidden evaluation changed the ranking story [8](./citations/8.md).
- The authors argue that successful execution systems mostly improved guardrails such as response selection, contamination cleanup, fallback, and context control rather than introducing novel agent architectures [8](./citations/8.md).

## Reasoning, agents, and learning from interaction

### Many-Shot CoT-ICL: Making In-Context Learning Truly Learn
https://arxiv.org/abs/2605.13511
- The paper studies many-shot chain-of-thought in-context learning and argues that standard many-shot rules do not transfer cleanly to reasoning tasks [5](./citations/5.md).
- It reports setting-dependent scaling: more CoT demonstrations help reasoning-oriented LLMs more reliably than non-reasoning LLMs, and similarity-based retrieval is weaker for reasoning because semantic similarity does not predict procedural compatibility [5](./citations/5.md).
- A new ordering method, Curvilinear Demonstration Selection, yields up to a 5.42 percentage-point gain on geometry with 64 demonstrations [5](./citations/5.md).
- The framing is that many-shot CoT-ICL behaves more like in-context test-time learning than scaled pattern matching [5](./citations/5.md).

### Revisiting DAgger in the Era of LLM-Agents
https://arxiv.org/abs/2605.12913
- The paper revisits DAgger for multi-turn LM agents by mixing student and teacher policies at the turn level, then training on teacher-labeled trajectories [6](./citations/6.md).
- Its motivation is to reduce covariate shift from off-policy teacher trajectories while still getting dense supervision that RL with sparse rewards does not provide [6](./citations/6.md).
- On SWE-bench Verified, the DAgger-style setup improves over the strongest post-training baseline by +3.9 points at 4B and +3.6 points at 8B [6](./citations/6.md).
- The reported 4B and 8B agents reach 27.3% and 29.8%, respectively, with the 8B model surpassing SWE-Gym-32B and nearing stronger 32B-scale agents [6](./citations/6.md).

### HAGE: Harnessing Agentic Memory via RL-Driven Weighted Graph Evolution
https://arxiv.org/abs/2605.09942
- HAGE replaces static lookup-style memory retrieval with query-conditioned traversal over a unified weighted multi-relational memory graph [13](./citations/13.md).
- It uses an LLM-based classifier for relational intent plus a routing network that modulates edge-embedding dimensions before traversal scoring [13](./citations/13.md).
- The claimed effect is better prioritization of useful relational paths and suppression of noisy or weakly relevant connections, improving long-horizon reasoning accuracy with a favorable accuracy-efficiency trade-off [13](./citations/13.md).

## Multimodal generation and editing

### AnyFlow: Any-Step Video Diffusion Model with On-Policy Flow Map Distillation
https://arxiv.org/abs/2605.13724
- AnyFlow is presented as the first any-step video diffusion distillation framework based on flow maps, designed to optimize the full ODE sampling trajectory rather than only a few fixed sampling steps [2](./citations/2.md).
- The method shifts the distillation target from endpoint consistency mapping to flow-map transition learning over arbitrary intervals, and introduces Flow Map Backward Simulation to decompose Euler rollouts into shortcut transitions [2](./citations/2.md).
- The claimed benefit is reduced test-time error from discretization and exposure bias, with experiments across bidirectional and causal architectures from 1.3B to 14B parameters showing parity or better than consistency-based counterparts in the few-step regime while scaling with sampling budgets [2](./citations/2.md).

### Edit-Compass & EditReward-Compass: A Unified Benchmark for Image Editing and Reward Modeling
https://arxiv.org/abs/2605.13062
- Edit-Compass is a benchmark for image editing with 2,388 annotated instances across six progressively challenging task categories [3](./citations/3.md).
- The benchmark explicitly covers world knowledge reasoning, visual reasoning, and multi-image editing, and uses structured reasoning with fine-grained scoring rubrics rather than coarse evaluation [3](./citations/3.md).
- EditReward-Compass complements it with 2,251 preference pairs meant to simulate realistic reward-modeling scenarios during RL optimization [3](./citations/3.md).

### Qwen-Image-VAE-2.0 Technical Report
https://arxiv.org/abs/2605.13565
- Qwen-Image-VAE-2.0 is a high-compression VAE suite aimed at improving both reconstruction fidelity and diffusability [4](./citations/4.md).
- The report attributes the gains to Global Skip Connections, expanded latent channels, billion-image scale training, synthetic rendering for text-rich scenarios, and an enhanced semantic alignment strategy for high-dimensional latents [4](./citations/4.md).
- It reports state-of-the-art reconstruction on public benchmarks and says downstream DiT experiments show faster convergence than existing high-compression baselines [4](./citations/4.md).
- A new benchmark, OmniDoc-TokenBench, is introduced for text-rich document evaluation with OCR-based metrics [4](./citations/4.md).

### PresentAgent-2: Towards Generalist Multimodal Presentation Agents
https://arxiv.org/abs/2605.11363
- PresentAgent-2 is an agentic framework that turns an open-ended user query into a presentation video by summarizing the topic, researching presentation-friendly sources, and collecting multimodal resources such as text, images, GIFs, and videos [7](./citations/7.md).
- It then builds slides, generates mode-specific scripts, and composes slides, audio, and dynamic media into a finished presentation video [7](./citations/7.md).
- The framework supports Single Presentation, Discussion, and Interaction modes, and the authors built a multimodal benchmark for these scenarios with criteria for content quality, media relevance, dynamic media use, dialogue naturalness, and interaction grounding [7](./citations/7.md).

## Long-context and scalable generation

### Training Long-Context Vision-Language Models Effectively with Generalization Beyond 128K Context
https://arxiv.org/abs/2605.13831
- The paper studies long-context continued pre-training for LVLMs, extending a 7B model from 32K to 128K with ablations on long-document data [9](./citations/9.md).
- It finds long-document VQA is more effective than OCR transcription, balanced length distributions outperform target-length-only data, and retrieval remains the main bottleneck [9](./citations/9.md).
- The resulting MMProLong model improves long-document VQA by 7.1% and generalizes beyond its 128K training window to 256K and 512K contexts without additional training [9](./citations/9.md).
- The reported generalization also extends to webpage multimodal needle retrieval, long-context vision-text compression, and long-video understanding [9](./citations/9.md).

### Asymmetric Flow Models
https://arxiv.org/abs/2605.12964
- AsymFlow uses a rank-asymmetric velocity parameterization that restricts noise prediction to a low-rank subspace while keeping data prediction full-dimensional [10](./citations/10.md).
- The paper says this recovers the full-dimensional velocity analytically without changing network architecture or training/sampling procedures [10](./citations/10.md).
- On ImageNet 256x256, the model reaches a leading 1.57 FID, and a pixel-space model finetuned from FLUX.2 klein 9B is reported as new state of the art for pixel text-to-image generation on HPSv3, DPG-Bench, and GenEval [10](./citations/10.md).
- The main significance is a route for finetuning pretrained latent flow models into pixel-space models while preserving high-level semantics and structure [10](./citations/10.md).

### The DAWN of World-Action Interactive Models
https://arxiv.org/abs/2605.11550
- DAWN instantiates World-Action Interactive Models for autonomous driving by coupling a World Predictor with a World-Conditioned Action Denoiser [12](./citations/12.md).
- The model recursively refines both the world hypothesis and the action hypothesis during inference, using a compact semantic latent space rather than full pixel-space rollout [12](./citations/12.md).
- The paper reports strong planning performance and favorable safety-related results across multiple autonomous driving benchmarks [12](./citations/12.md).

## Robotics and embodied data generation

### RoboEvolve: Co-Evolving Planner-Simulator for Robotic Manipulation with Limited Data
https://arxiv.org/abs/2605.13775
- RoboEvolve couples a VLM planner and a VGM simulator in a co-evolutionary loop, operating purely on unlabeled seed images [14](./citations/14.md).
- Its training scheme uses daytime exploration for grounded behavioral discovery and nighttime consolidation to mine near-miss failures, with an autonomous curriculum that scales from atomic actions to complex tasks [14](./citations/14.md).
- The paper reports +30 absolute points on base planners, +48% simulator success on average, and beating fully supervised baselines with only 500 unlabeled seeds [14](./citations/14.md).
- It also claims robust continual learning without catastrophic forgetting [14](./citations/14.md).

## Evaluation and diagnostics for agent behavior

### AgentLens: Revealing The Lucky Pass Problem in SWE-Agent Evaluation
https://arxiv.org/abs/2605.12925
- AgentLens argues that pass/fail-only SWE-agent evaluation hides process quality differences between principled solutions and trial-and-error trajectories [15](./citations/15.md).
- The study analyzes 2,614 OpenHands trajectories on 60 SWE-bench Verified tasks and identifies a “Lucky Pass” pattern in 10.7% of passing trajectories, including regression cycles, blind retries, missing verification, and disordered exploration/implementation/verification [15](./citations/15.md).
- It releases AgentLens-Bench with 1,815 annotated trajectories and 47 task-level PTA references, plus a process-level quality score that can move some models by up to five rank positions compared with pass rate alone [15](./citations/15.md).
