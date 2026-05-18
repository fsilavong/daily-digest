# HuggingFace Featured Papers Digest — 2026-05-18

## Agents and multimodal procedures

### MMSkills: Towards Multimodal Skills for General Visual Agents
https://arxiv.org/abs/2605.13527
- Reframes reusable skills for visual agents as **multimodal procedural knowledge**, arguing that visual reuse depends on both the operation and the ability to recognize state, interpret visual progress/failure, and decide next steps [1](./citations/1.md).
- Introduces **MMSkills**, where each skill package combines a textual procedure with runtime state cards and multi-view keyframes, and a **trajectory-to-skill generator** that turns public non-evaluation trajectories into reusable multimodal skills through workflow grouping, procedure induction, visual grounding, and auditing [1](./citations/1.md).
- Uses a **branch-loaded multimodal skill agent** that inspects selected state cards and keyframes in a temporary branch before distilling them into structured guidance for the main agent [1](./citations/1.md).
- Reports that experiments across GUI and game-based visual-agent benchmarks improve both frontier and smaller multimodal agents, suggesting multimodal procedural knowledge complements model-internal priors [1](./citations/1.md).

### PAGER: Bridging the Semantic-Execution Gap in Point-Precise Geometric GUI Control
https://arxiv.org/abs/2605.15963
- Targets **precision-sensitive GUI tasks** where actions must land on exact points in continuous canvas space, unlike tolerant region-based GUI interaction [2](./citations/2.md).
- Introduces **PAGE Bench** with 4,906 problems and over 224K process-supervised, pixel-level GUI actions, explicitly covering geometry-aware verification and dependency-driven error propagation [2](./citations/2.md).
- Proposes **PAGER**, a topology-aware agent that combines dependency-structured planning, pixel-level execution, executable action grammar from pixel-grounded supervised tuning, and precision-aligned reinforcement learning with state-conditioned geometric feedback [2](./citations/2.md).
- Highlights a large **semantic-execution gap**: general multimodal models can exceed 88% action-type accuracy but remain below 6% task success; PAGER reaches 4.1x higher task success than the strongest evaluated general baseline and raises step success above 62% [2](./citations/2.md).

### ReactiveGWM: Steering NPC in Reactive Game World Models
https://arxiv.org/abs/2605.15256
- Argues that current game world models are player-centric and often treat NPCs as background pixels, so they behave like passive renderers rather than interactive simulation engines [3](./citations/3.md).
- Introduces **ReactiveGWM**, which decouples player controls from NPC behaviors, injecting player actions through a lightweight additive bias while grounding high-level NPC responses such as offense, control, and defense through cross-attention modules [3](./citations/3.md).
- Claims the cross-attention modules learn a game-agnostic representation of interactive logic, enabling zero-shot strategy transfer into off-the-shelf world models of different games without domain-specific retraining [3](./citations/3.md).
- Evaluated on two Street Fighter games, the method preserves player controllability while improving prompt-aligned NPC strategy adherence [3](./citations/3.md).

## Reasoning and optimization

### Nudging Beyond the Comfort Zone: Efficient Strategy-Guided Exploration for RLVR
https://arxiv.org/abs/2605.15726
- Frames RLVR as being limited by exploration, since policy improvement can only happen on sampled trajectories and brute-force rollout scaling is expensive [4](./citations/4.md).
- Proposes **NudgeRL**, which adds **strategy nudging**: lightweight strategy-level contexts condition each rollout to induce diverse reasoning trajectories without oracle supervision [4](./citations/4.md).
- Uses a unified objective that separates inter-context and intra-context reward components and adds a distillation term to transfer discovered behaviors back to the base policy [4](./citations/4.md).
- Reports stronger results than standard GRPO with up to 8x larger rollout budgets, and better average performance than an oracle-guided RL baseline across five math benchmarks [4](./citations/4.md).

### Learning from Failures: Correction-Oriented Policy Optimization with Verifiable Rewards
https://arxiv.org/abs/2605.14539
- Targets RLVR’s sparse binary rewards and weak credit assignment by converting on-policy failed trajectories into **correction-oriented supervision** without external signals [5](./citations/5.md).
- Proposes **CIPO**, which jointly optimizes correction samples derived from the model’s own failed attempts with the standard RLVR objective [5](./citations/5.md).
- Claims the method explicitly improves self-correction ability while increasing learning effectiveness [5](./citations/5.md).
- Reports consistent gains over strong baselines on 11 benchmarks spanning mathematical reasoning and code generation, with stronger pass@K improvements indicating more intrinsic reasoning capacity rather than just probability reshuffling [5](./citations/5.md).

### Solvita: Enhancing Large Language Models for Competitive Programming via Agentic Evolution
https://arxiv.org/abs/2605.15301
- Presents **Solvita**, a stateless multi-agent competitive-programming system that replaces fixed retrieval with continuous learning over problem-solving and debugging experience without updating the base LLM weights [6](./citations/6.md).
- Organizes the loop into four specialized agents—Planner, Solver, Oracle, and Hacker—covering strategy selection, synthesis, certified supervision, and adversarial testing [6](./citations/6.md).
- Maintains trainable graph-structured knowledge networks per agent; outcome signals such as pass/fail results, certification quality, and discovered vulnerabilities update these networks through reinforcement learning [6](./citations/6.md).
- Reports state-of-the-art results across CodeContests, APPS, AetherCode, and live Codeforces rounds, outperforming existing multi-agent pipelines and nearly doubling single-pass baselines [6](./citations/6.md).

## Image generation, tokenization, and video

### InsightTok: Improving Text and Face Fidelity in Discrete Tokenization for Autoregressive Image Generation
https://arxiv.org/abs/2605.14333
- Identifies tokenizer compression as a bottleneck for discrete autoregressive image generation, especially for readable text and distinctive faces [7](./citations/7.md).
- Proposes **InsightTok**, which uses localized, content-aware perceptual losses to align tokenizer training with text legibility and facial fidelity rather than generic reconstruction alone [7](./citations/7.md).
- Uses a compact 16k codebook with 16x downsampling and reports improved text and face reconstruction without hurting general reconstruction quality [7](./citations/7.md).
- Says the gains transfer to autoregressive generation in **InsightAR**, producing clearer text and more faithful facial details [7](./citations/7.md).

### Flash-GRPO: Efficient Alignment for Video Diffusion via One-Step Policy Optimization
https://arxiv.org/abs/2605.15980
- Addresses the high cost of GRPO-style alignment for video diffusion models, where training a 14B model can require hundreds of GPU days [8](./citations/8.md).
- Introduces **Flash-GRPO**, a single-step training framework that claims better alignment quality than full trajectory training under low compute budgets [8](./citations/8.md).
- Its two core mechanisms are **iso-temporal grouping**, which removes timestep-confounded variance by enforcing prompt-wise temporal consistency, and **temporal gradient rectification**, which stabilizes gradient magnitudes across timesteps [8](./citations/8.md).
- Experiments across 1.3B to 14B models show substantial acceleration, stability improvements, and state-of-the-art alignment quality [8](./citations/8.md).

### FashionChameleon: Towards Real-Time and Interactive Human-Garment Video Customization
https://arxiv.org/abs/2605.15824
- Targets interactive garment-level video customization while preserving motion coherence, using only single-garment video data [9](./citations/9.md).
- Trains a teacher model with in-context learning on a single reference-garment pair, encouraging coherence during single-garment switching despite mismatched reference and garment images [9](./citations/9.md).
- Adds **Streaming Distillation with In-Context Learning** to improve extrapolation consistency, and a training-free **KV Cache Rescheduling** method with garment KV refresh, historical KV withdraw, and reference KV disentangle for interactive switching [9](./citations/9.md).
- Reports real-time generation at 23.8 FPS on a single GPU and 30–180x speedups over existing baselines [9](./citations/9.md).

## 3D, robotics, and geometry

### DexJoCo: A Benchmark and Toolkit for Task-Oriented Dexterous Manipulation on MuJoCo
https://arxiv.org/abs/2605.16257
- Provides **DexJoCo**, a benchmark/toolkit for task-oriented dexterous manipulation with 11 functionally grounded tasks covering tool-use, bimanual coordination, long-horizon execution, and reasoning [10](./citations/10.md).
- Includes a low-cost data collection system and 1.1K trajectories, plus domain randomization to test robustness [10](./citations/10.md).
- Benchmarks modern models under visual and dynamics randomization, multi-task training, and action-head adaptation, and reports important insights and limitations of current policies [10](./citations/10.md).
- The abstract emphasizes standardized evaluation for dexterous hands but does not provide the specific quantitative results in the snippet [10](./citations/10.md).

### Unlocking Dense Metric Depth Estimation in VLMs
https://arxiv.org/abs/2605.15876
- Proposes **DepthVLM**, which attaches a lightweight depth head to a VLM backbone and trains with unified vision-text supervision to produce full-resolution depth maps in a single forward pass [11](./citations/11.md).
- Adds a unified indoor-outdoor metric depth benchmark in a VLM-compatible format [11](./citations/11.md).
- Claims the approach preserves multimodal capability while enabling native dense geometry prediction, avoiding external distillation error accumulation and inefficient per-pixel or coarse token outputs [11](./citations/11.md).
- Reports better performance than existing VLMs, higher inference efficiency, and gains on complex 3D spatial reasoning, with code and checkpoints promised for release [11](./citations/11.md).

### FFAvatar: Few-Shot, Feed-Forward, and Generalizable Avatar Reconstruction
https://arxiv.org/abs/2605.15320
- Presents **FFAvatar**, a feed-forward framework that reconstructs animatable 3D Gaussian head avatars from few-shot unposed portrait images in seconds [12](./citations/12.md).
- Fuses multiple source images into a canonical Gaussian representation via a Multi-View Query-Former and predicts FLAME parameters end-to-end from pixels, avoiding offline FLAME extraction [12](./citations/12.md).
- Uses a three-stage curriculum: large-scale monocular pretraining on over 1M identities, multi-view fine-tuning on 360-degree captures, and optional personalization within 500 optimization steps [12](./citations/12.md).
- Reports a 5.5 PSNR gain over LAM on NeRSemble, plus reconstruction in 2 seconds without personalization, 10 seconds with personalization, and 49 FPS animation on a single A100 [12](./citations/12.md).

### WorldAct: Activating Monolithic 3D Worlds into Interactive-Ready Object-Centric Scenes
https://arxiv.org/abs/2605.15843
- Converts static generated 3D worlds into editable, interaction-ready scenes by decomposing them into actionable objects and reconstructing object-level meshes with a residual background via 3D inpainting [13](./citations/13.md).
- Uses a multimodal agent to guide scene decomposition and identify actionable objects for object-level editing, collision-aware manipulation, and embodied task execution [13](./citations/13.md).
- The result is a path from monolithic generated worlds to more interactive scenes while preserving global coherence [13](./citations/13.md).
- The abstract reports improved interaction scenarios versus the original generated scenes but does not include quantitative metrics [13](./citations/13.md).

## Safety, robustness, and industrial decision support

### DiagnosticIQ: A Benchmark for LLM-Based Industrial Maintenance Action Recommendation from Symbolic Rules
https://arxiv.org/abs/2605.08614
- Introduces a benchmark of 6,690 expert-validated multiple-choice questions built from 118 rule-action pairs across 16 asset types, targeting the rule-to-action step in industrial maintenance [14](./citations/14.md).
- Supplies a symbolic-to-MCQA pipeline that normalizes rules to disjunctive normal form and uses embedding-based distractor sampling, plus five variants probing different failure modes [14](./citations/14.md).
- Benchmarks 29 LLMs and 4 embedding baselines, and includes a human evaluation of 9 practitioners to confirm the task requires specialist knowledge beyond operational experience [14](./citations/14.md).
- Reports that frontier models are tightly clustered, but are brittle under distractor expansion and condition inversion, indicating calibration and structural robustness remain the main deployment bottlenecks [14](./citations/14.md).

## Efficiency and compression

### HodgeCover: Higher-Order Topological Coverage Drives Compression of Sparse Mixture-of-Experts
https://arxiv.org/abs/2605.13997
- Argues that pairwise expert-similarity scores are structurally blind to higher-order mergeability in sparse MoE compression because some triples are jointly irreducible despite pairwise compatibility [15](./citations/15.md).
- Models the obstruction as the harmonic kernel of a simplicial Laplacian over a 2-complex whose edges encode KL merge barriers and faces encode triplet barriers [15](./citations/15.md).
- Proposes **HodgeCover**, which greedily covers harmonic-critical edges and triangle-critical faces, with a hybrid variant combined with standard weight pruning on survivors [15](./citations/15.md).
- Reports competitive or leading performance on three open-weight sparse MoE backbones under aggressive expert reduction, and claims the method uniquely balances retained mass across Hodge components [15](./citations/15.md).
