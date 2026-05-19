# HuggingFace Featured Papers Digest — 2026-05-19

## Research automation and agents

### AI for Auto-Research: Roadmap & User Guide
https://arxiv.org/abs/2605.18661
- AI-assisted research is described as crossing a threshold: fully automated systems can generate papers for as little as $15, and long-horizon agents can execute experiments, draft manuscripts, and simulate critique with minimal human input [1](./citations/1.md).
- The paper argues the main integrity problem is that frontier LLMs still fabricate results, miss hidden errors, and fail to judge novelty reliably under scientific pressure; it organizes the research lifecycle into creation, writing, validation, and dissemination [1](./citations/1.md).
- The abstract claims AI is strongest for structured, retrieval-grounded, and tool-mediated tasks, but fragile for novel ideas, research-level experiments, and scientific judgment; the authors conclude human-governed collaboration remains the most credible deployment paradigm [1](./citations/1.md).
- It also reports a taxonomy, benchmark suite, tool inventory, design principles, and practitioner playbook maintained on the project page [1](./citations/1.md).

### Model-Adaptive Tool Necessity Reveals the Knowing-Doing Gap in LLM Tool Use
https://arxiv.org/abs/2605.14038
- The paper introduces a model-adaptive definition of tool necessity grounded in each model's empirical performance, instead of treating tool need as model-agnostic or only human/judge annotated [2](./citations/2.md).
- Across four models on arithmetic and factual QA, the observed tool-call behavior mismatched the model-adaptive necessity definition by 26.5-54.0% and 30.8-41.8%, respectively [2](./citations/2.md).
- The authors decompose tool use into an internal cognition stage and an execution stage, finding that both are often linearly decodable but their probe directions become nearly orthogonal in the late-layer, last-token regime that drives the next-token action [2](./citations/2.md).
- They conclude the main failure is in the cognition-to-action transition, framing it as a knowing-doing gap in LLM tool use [2](./citations/2.md).

### Agent Bazaar: Enabling Economic Alignment in Multi-Agent Marketplaces
https://arxiv.org/abs/2605.17698
- The paper frames economic alignment as the ability of agentic systems to preserve market stability and integrity, and introduces the Agent Bazaar simulation framework to study it [3](./citations/3.md).
- It identifies two failure modes: algorithmic instability in a B2C market where firms amplify price volatility until collapse, and Sybil deception in a C2C market where one deceptive agent controls multiple seller identities and floods the market with fraud [3](./citations/3.md).
- Frontier and open-weight models largely fail to self-regulate, with failure severity varying by model rather than size; the paper proposes Stabilizing Firms and Skeptical Guardians as economically aligned harnesses, but notes they remain fragile under harder conditions [3](./citations/3.md).
- A 9B model trained with REINFORCE++ and an adaptive curriculum outperforms all evaluated frontier and open-weight models, and the authors introduce Economic Alignment Score as a 4-component metric aggregating stability, integrity, welfare, and profitability [3](./citations/3.md).

## Reasoning efficiency and early exit

### Stop When Reasoning Converges: Semantic-Preserving Early Exit for Reasoning Models
https://arxiv.org/abs/2605.17672
- The paper argues that large reasoning models often overthink by continuing to generate after a solution has stabilized, wasting tokens and latency [4](./citations/4.md).
- It proposes PUMA, a plug-and-play framework that combines a lightweight Redundancy Detector with answer-level verification to identify semantically redundant candidate exits while preserving a coherent reasoning prefix [4](./citations/4.md).
- Across five reasoning models and five benchmarks, PUMA achieves 26.2% average token reduction while preserving accuracy and retained chain-of-thought quality [4](./citations/4.md).
- The abstract also reports additional evidence in code generation, zero-shot vision-language reasoning, and learned stopping-policy internalization, suggesting reasoning-level redundancy is transferable and learnable [4](./citations/4.md).

## Multimodal generation and video systems

### KVPO: ODE-Native GRPO for Autoregressive Video Alignment via KV Semantic Exploration
https://arxiv.org/abs/2605.14278
- KVPO targets alignment of streaming autoregressive video generators with human preferences, criticizing existing RL methods for using noise-based exploration and SDE-based surrogate policies that mismatch deterministic ODE dynamics [5](./citations/5.md).
- It introduces causal-semantic exploration by routing variation through the historical KV cache, so branches stay on the data manifold while remaining semantically diverse [5](./citations/5.md).
- For policy modeling, it uses a velocity-field surrogate policy based on Trajectory Velocity Energy, which scores branch likelihood in flow-matching velocity space and supports a reward-weighted contrastive objective aligned with the native ODE formulation [5](./citations/5.md).
- Experiments on multiple distilled autoregressive video generators show gains in visual quality, motion quality, and text-video alignment for both short-video and long-video settings [5](./citations/5.md).

### LongLive-2.0: An NVFP4 Parallel Infrastructure for Long Video Generation
https://arxiv.org/abs/2605.18739
- LongLive-2.0 is an NVFP4-based parallel infrastructure for the full training and inference workflow of long video generation, aiming at speed and memory bottlenecks [6](./citations/6.md).
- For training, it introduces sequence-parallel autoregressive training via Balanced SP, which pairs clean-history and noisy-target temporal chunks per rank and combines this with NVFP4 precision to reduce memory and accelerate GEMMs [6](./citations/6.md).
- The system directly tunes a diffusion model into a long, multi-shot, interactive autoregressive diffusion model, and can later be converted to real-time generation with standalone LoRA weights [6](./citations/6.md).
- The abstract reports up to 2.15x training speedup and 1.84x inference speedup, with LongLive-2.0-5B reaching 45.7 FPS while maintaining strong benchmark performance [6](./citations/6.md).

### Lance: Unified Multimodal Modeling by Multi-Task Synergy
https://arxiv.org/abs/2605.18678
- Lance is a lightweight native unified model for multimodal understanding, generation, and editing across images and videos [7](./citations/7.md).
- It is trained from scratch with a dual-stream mixture-of-experts architecture over shared interleaved multimodal sequences, aiming to unify context learning while decoupling understanding and generation pathways [7](./citations/7.md).
- The authors add modality-aware rotary positional encoding and staged multi-task training with capability-oriented objectives and adaptive data scheduling to improve alignment across tasks [7](./citations/7.md).
- The abstract claims it outperforms existing open-source unified models in image and video generation while retaining strong multimodal understanding [7](./citations/7.md).

### LiteFrame: Efficient Vision Encoders Unlock Frame Scaling in Video LLMs
https://arxiv.org/abs/2605.17260
- LiteFrame addresses the latency bottleneck in long-form video LLMs by optimizing the vision encoder itself, rather than only reducing visual tokens after feature extraction [8](./citations/8.md).
- It uses Compressed Token Distillation to train a compact student encoder to predict information-dense, spatio-temporally compressed representations from a large teacher vision model [8](./citations/8.md).
- With Language Model Adaptation, LiteFrame establishes a new latency-accuracy Pareto frontier [8](./citations/8.md).
- Compared with InternVL3-8B, the abstract reports a 35% end-to-end latency reduction, 8x more frames processed, and improved average video understanding accuracy across multiple benchmarks [8](./citations/8.md).

## Context extension and model architecture

### EndPrompt: Efficient Long-Context Extension via Terminal Anchoring
https://arxiv.org/abs/2605.14589
- EndPrompt extends context windows using only short training sequences by preserving the original short context as an intact first segment and appending a brief terminal prompt near the target context length [9](./citations/9.md).
- This two-segment construction exposes both local and long-range relative distances without needing full-length inputs, preserving semantic continuity that chunk-based simulation lacks [9](./citations/9.md).
- The abstract says the method is grounded in RoPE and a Bernstein-inequality analysis, arguing that position interpolation imposes a smoothness constraint over attention [9](./citations/9.md).
- On LLaMA-family models extended from 8K to 64K, EndPrompt reaches an average RULER score of 76.03 and the highest average on LongBench, beating LCEG, LongLoRA, and full-length fine-tuning while using substantially less computation [9](./citations/9.md).

### Where Should Diffusion Enter a Language Model? Geometry-Guided Hidden-State Replacement
https://arxiv.org/abs/2605.14368
- DiHAL asks where diffusion should enter a pretrained transformer and proposes a geometry-guided hybrid that scores layers with geometry-based proxies to choose a diffusion-friendly hidden-state interface [10](./citations/10.md).
- Instead of replacing tokens directly, it replaces the lower transformer prefix with a diffusion bridge and reconstructs the selected-layer hidden state while retaining the upper layers and original LM head [10](./citations/10.md).
- On 8B-scale backbones, the abstract says the geometry score predicts effective shallow insertion layers under a fixed bridge-training protocol [10](./citations/10.md).
- It also reports improved hidden-state recovery over continuous diffusion baselines in a diagnostic comparison matched for diffusion/recovery training budget, suggesting hidden-state geometry can identify feasible replacement points [10](./citations/10.md).

### Post-Trained MoE Can Skip Half Experts via Self-Distillation
https://arxiv.org/abs/2605.18643
- ZEDA converts post-trained static MoE models into dynamic ones using zero-expert self-distillation adaptation, aiming to reduce inference cost without training from scratch [11](./citations/11.md).
- The method injects parameter-free zero-output experts into each MoE layer and adapts the augmented model with two-stage self-distillation using the original MoE as a frozen teacher plus a group-level balancing loss [11](./citations/11.md).
- On Qwen3-30B-A3B and GLM-4.7-Flash across 11 benchmarks in math, code, and instruction following, ZEDA eliminates over 50% of expert FLOPs at marginal accuracy loss [11](./citations/11.md).
- It outperforms the strongest dynamic MoE baseline by 6.1 and 4.0 points on the two models and delivers about 1.20x end-to-end inference speedup [11](./citations/11.md).

### Measuring Maximum Activations in Open Large Language Models
https://arxiv.org/abs/2605.15572
- The paper measures maximum activation magnitudes in 27 checkpoints from 8 open model families using a unified pipeline over embeddings, hidden states, attention, MLP/MoE, SwiGLU gates, and final norm [12](./citations/12.md).
- It reports that global maxima vary by nearly four orders of magnitude at comparable parameter counts, with Qwen3.5 and MoE checkpoints in the 10^2 to 10^3 range and Gemma3-27B-it reaching about 7 x 10^5 [12](./citations/12.md).
- The abstract says MoE checkpoints show 14.0-23.4x lower peaks than matched dense counterparts, while the residual stream carries the global maximum in 22 of 24 checkpoints [12](./citations/12.md).
- A lightweight INT-8 sanity check finds the measured maxima co-vary with low-bit reconstruction error, motivating reporting maximum activation magnitude alongside open-weight releases [12](./citations/12.md).

### SNLP: Layer-Parallel Inference via Structured Newton Corrections
https://arxiv.org/abs/2605.17842
- SNLP reframes autoregressive layer execution as solving a nonlinear residual equation over the hidden-state trace, then approximates that solve with structured Newton-style updates [13](./citations/13.md).
- It introduces architecture-induced surrogate dynamics: Identity Newton for residual Transformers and HC Newton for mHC-style architectures, plus SNLP-aware regularization to make one or a few structured Newton iterations accurate [13](./citations/13.md).
- On nanochat-scale Transformers, SNLP regularization improves layer-parallel compatibility and also reduces standard sequential perplexity by 4.7%-23.4% [13](./citations/13.md).
- At inference, SNLP with layer fusion and chunkwise decomposition reaches 2.3x speedup on a 0.5B Nanochat model while improving PPL by 6.1%; the abstract notes limitations on off-the-shelf pretrained models and that exact convergence recovers sequential computation [13](./citations/13.md).

## Safety and steering

### Targeted Neuron Modulation via Contrastive Pair Search
https://arxiv.org/abs/2605.12290
- CNA identifies the 0.1% of MLP neurons whose activations most distinguish harmful from benign prompts, using only forward passes with no gradients or auxiliary training [14](./citations/14.md).
- In instruct models, ablating the discovered circuit reduces refusal rates by over 50% on a jailbreak benchmark while preserving fluency and non-degeneracy across all steering strengths [14](./citations/14.md).
- Across matched base and instruct models from Llama and Qwen families ranging from 1B to 72B, the authors find base models have similar late-layer discrimination structures, but steering those neurons produces content shifts rather than behavioral change [14](./citations/14.md).
- The paper argues neuron-level intervention can steer behavior reliably without the quality tradeoffs of residual-stream methods and suggests alignment fine-tuning transforms pre-existing discrimination structure into a sparse refusal gate [14](./citations/14.md).

## Low-signal note

### Geometric Phase Transition Enables Extreme Hippocampal Memory Capacity
https://arxiv.org/abs/2605.17199
- This item is a biology paper rather than an AI systems paper, but it is featured on the same digest day [15](./citations/15.md).
- The abstract claims superior spatial memory in food-caching chickadees is associated with a crystalline hippocampal population geometry, higher geometric stability and temporal coherence, and a >100-fold modeled capacity advantage over disorganized codes [15](./citations/15.md).
- It also reports a 169-fold representational redundancy as a geometric tax stabilizing the manifold against noise [15](./citations/15.md).
