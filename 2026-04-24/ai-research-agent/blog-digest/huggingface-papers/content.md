# HuggingFace Featured Papers Digest — 2026-04-24

## Reasoning, temporal modeling, and evaluation

### LLaTiSA: Towards Difficulty-Stratified Time Series Reasoning from Visual Perception to Semantics
https://arxiv.org/abs/2604.17295
- Formalizes time series reasoning with a four-level taxonomy of increasing cognitive complexity, addressing fragmented task definitions and ambiguous benchmarks for LLMs.[1](./citations/1.md)
- Introduces HiTSR, a hierarchical dataset of 83k samples with diverse task combinations and verified CoT trajectories.[1](./citations/1.md)
- Proposes LLaTiSA, which combines visualized patterns with precision-calibrated numerical tables to improve temporal perception in VLMs.[1](./citations/1.md)
- Reports superior performance and robust out-of-distribution generalization across diverse TSR tasks and real-world scenarios.[1](./citations/1.md)

### Seeing Fast and Slow: Learning the Flow of Time in Videos
https://arxiv.org/abs/2604.21931
- Treats time as a learnable visual concept for reasoning about and manipulating video playback speed.[6](./citations/6.md)
- Uses self-supervised learning from multimodal cues and temporal structure to detect speed changes and estimate playback speed.[6](./citations/6.md)
- Uses the learned temporal reasoning models to curate the largest slow-motion video dataset to date from in-the-wild sources.[6](./citations/6.md)
- Extends to speed-conditioned video generation and temporal super-resolution for higher-FPS, finer-detail output.[6](./citations/6.md)

### WorldMark: A Unified Benchmark Suite for Interactive Video World Models
https://arxiv.org/abs/2604.21686
- Targets the benchmarking gap for interactive video world models by standardizing identical scenes, action sequences, and control interfaces across models.[2](./citations/2.md)
- Provides a unified action-mapping layer and compares six major models on the same scenes and trajectories.[2](./citations/2.md)
- Includes a hierarchical suite of 500 cases spanning first/third-person views, photorealistic/stylized scenes, and Easy-to-Hard difficulty tiers over 20–60s.[2](./citations/2.md)
- Ships a modular evaluation toolkit for visual quality, control alignment, and world consistency, plus an online arena.[2](./citations/2.md)

### StyleID: A Perception-Aware Dataset and Metric for Stylization-Agnostic Facial Identity Recognition
https://arxiv.org/abs/2604.21689
- Argues that face identity encoders trained on natural photos are brittle under stylization, often confusing style change with identity drift.[4](./citations/4.md)
- Introduces StyleBench-H for human same-different verification judgments and StyleBench-S from psychometric recognition-strength curves collected via 2AFC experiments.[4](./citations/4.md)
- Uses StyleBench-S to fine-tune semantic encoders so their similarity orderings better match human perception across styles and strengths.[4](./citations/4.md)
- Reports higher correlation with human judgments and better robustness on out-of-domain, artist-drawn portraits.[4](./citations/4.md)

## Agents, policy learning, and GUI automation

### UniT: Toward a Unified Physical Language for Human-to-Humanoid Policy Learning and World Modeling
https://arxiv.org/abs/2604.19734
- Addresses the data bottleneck in humanoid foundation models by leveraging large egocentric human datasets despite cross-embodiment kinematic mismatch.[3](./citations/3.md)
- Introduces UniT, a unified latent action tokenizer via visual anchoring with tri-branch cross-reconstruction to connect actions, vision, and a shared discrete latent space.[3](./citations/3.md)
- In policy learning, VLA-UniT claims state-of-the-art data efficiency, robust OOD generalization, and zero-shot task transfer on humanoid simulation and real-world deployments.[3](./citations/3.md)
- In world modeling, WM-UniT uses unified tokens to align cross-embodiment dynamics for direct human-to-humanoid action transfer and more controllable humanoid video generation.[3](./citations/3.md)

### Co-Evolving LLM Decision and Skill Bank Agents for Long-Horizon Tasks
https://arxiv.org/abs/2604.20987
- Proposes COSPLAY, a co-evolution framework where a decision agent retrieves skills from a learnable skill bank while a separate pipeline discovers reusable skills from unlabeled rollouts.[5](./citations/5.md)
- Targets long-horizon interactive environments that require multi-step reasoning, delayed-reward decision making, and reuse of structured skills across episodes.[5](./citations/5.md)
- Reports results across six game environments, with an 8B base model improving average reward by over 25.1% versus four frontier LLM baselines on single-player benchmarks.[5](./citations/5.md)
- Remains competitive on multi-player social reasoning games.[5](./citations/5.md)

### VLAA-GUI: Knowing When to Stop, Recover, and Search, A Modular Framework for GUI Automation
https://arxiv.org/abs/2604.21375
- Targets two failure modes in autonomous GUI agents: premature stopping and repetitive loops.[7](./citations/7.md)
- Introduces mandatory completeness verification, a loop breaker, and on-demand search/coding/grounding agents for modular GUI automation.[7](./citations/7.md)
- Reports top performance across five backbones on OSWorld and WindowsAgentArena, including 77.5% on OSWorld and 61.0% on WindowsAgentArena.[7](./citations/7.md)
- Notes that three of five backbones surpass reported human OSWorld performance in a single pass, and that the loop breaker nearly halves wasted steps for loop-prone models.[7](./citations/7.md)

### TingIS: Real-time Risk Event Discovery from Noisy Customer Incidents at Enterprise Scale
https://arxiv.org/abs/2604.21889
- Presents an enterprise incident-discovery system for extracting actionable risks from noisy customer incidents.[8](./citations/8.md)
- Uses a multi-stage event-linking engine with efficient indexing plus LLMs for event merging, along with cascaded routing and multi-dimensional noise reduction.[8](./citations/8.md)
- Reports production deployment at >2,000 messages/minute and 300,000/day, with P90 alert latency of 3.5 minutes and 95% discovery rate for high-priority incidents.[8](./citations/8.md)
- Claims improved routing accuracy, clustering quality, and signal-to-noise ratio on real-world benchmarks.[8](./citations/8.md)

### WebGen-R1: Incentivizing Large Language Models to Generate Functional and Aesthetic Websites with Reinforcement Learning
https://arxiv.org/abs/2604.20398
- Targets project-level multi-page website generation, which is harder than single-file code generation and brittle for multi-turn agentic pipelines.[15](./citations/15.md)
- Uses scaffold-driven structured generation plus a cascaded multimodal reward that combines structural guarantees, execution-grounded functional feedback, and vision-based aesthetic supervision.[15](./citations/15.md)
- Reports that a 7B base model is transformed from nearly nonfunctional output into deployable, aesthetically aligned websites.[15](./citations/15.md)
- Claims it outperforms open-source models up to 72B and rivals DeepSeek-R1 (671B) on functional success while exceeding it on valid rendering and aesthetic alignment.[15](./citations/15.md)

## Multimodal generation, editing, and representation

### Context Unrolling in Omni Models
https://arxiv.org/abs/2604.21921
- Describes Omni, a unified multimodal model trained on text, images, videos, 3D geometry, and hidden representations.[10](./citations/10.md)
- Introduces context unrolling, where the model reasons across multiple modal representations before predicting.[10](./citations/10.md)
- Claims this improves aggregation of complementary information and downstream reasoning fidelity.[10](./citations/10.md)
- Reports strong performance on multimodal generation and understanding benchmarks, including in-context generation across text, image, video, and 3D geometry.[10](./citations/10.md)

### EditCrafter: Tuning-free High-Resolution Image Editing via Pretrained Diffusion Model
https://arxiv.org/abs/2604.10268
- Proposes a tuning-free high-resolution image editing pipeline built on pretrained text-to-image diffusion models.[11](./citations/11.md)
- Addresses failures of naive patch-wise editing at arbitrary aspect ratios and resolutions by using tiled inversion to preserve identity.[11](./citations/11.md)
- Adds noise-damped manifold-constrained classifier-free guidance (NDCFG++) for editing from the inverted latent.[11](./citations/11.md)
- Reports impressive editing results across various resolutions without fine-tuning or optimization.[11](./citations/11.md)

### Vista4D: Video Reshooting with 4D Point Clouds
https://arxiv.org/abs/2604.21915
- Grounds input video and target cameras in a 4D point cloud to re-synthesize the same dynamics from a different viewpoint and trajectory.[12](./citations/12.md)
- Uses static pixel segmentation and 4D reconstruction to preserve seen content and provide richer camera signals.[12](./citations/12.md)
- Trains on reconstructed multiview dynamic data for robustness to point-cloud artifacts at inference time.[12](./citations/12.md)
- Reports improved 4D consistency, camera control, and visual quality, with generalization to dynamic scene expansion and 4D scene recomposition.[12](./citations/12.md)

### UniGenDet: A Unified Generative-Discriminative Framework for Co-Evolutionary Image Generation and Generated Image Detection
https://arxiv.org/abs/2604.21904
- Unifies image generation and generated-image detection under a co-evolutionary generative-discriminative framework.[13](./citations/13.md)
- Uses a symbiotic multimodal self-attention mechanism, unified fine-tuning, and detector-informed generative alignment to let each task inform the other.[13](./citations/13.md)
- Frames the benefit as improved interpretability for authenticity identification and higher-fidelity image creation guided by authenticity criteria.[13](./citations/13.md)
- Reports state-of-the-art performance across multiple datasets.[13](./citations/13.md)

## Efficiency and distillation

### Hybrid Policy Distillation for LLMs
https://arxiv.org/abs/2604.20244
- Recasts knowledge distillation as a reweighted token-level log-likelihood objective and unifies design choices across existing KD methods.[9](./citations/9.md)
- Proposes Hybrid Policy Distillation, combining forward and reverse KL to balance mode coverage and mode-seeking.[9](./citations/9.md)
- Mixes off-policy data with lightweight approximate on-policy sampling.[9](./citations/9.md)
- Reports improved optimization stability, computational efficiency, and final performance on long-generation math reasoning, dialogue, and code tasks.[9](./citations/9.md)

### Temporally Extended Mixture-of-Experts Models
https://arxiv.org/abs/2604.20156
- Argues that token-level expert switching in MoEs makes memory offloading and prefetching ineffective once models exceed GPU memory.[14](./citations/14.md)
- Introduces temporally extended MoE layers using an option-critic-style controller with deliberation costs to decide when to switch expert sets and what to load.[14](./citations/14.md)
- Applied to gpt-oss-20b with low-rank adapters and a self-distillation reward, it reduces switch rates from over 50% to below 5%.[14](./citations/14.md)
- Claims retention of up to 90% of base-model accuracy on MATH, MMLU, and MMMLU, suggesting a memory-efficiency/capability tradeoff.[14](./citations/14.md)
