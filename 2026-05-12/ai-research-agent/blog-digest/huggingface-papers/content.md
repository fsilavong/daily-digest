# HuggingFace Featured Papers Digest — 2026-05-12

## Reasoning, benchmarks, and evaluation

### Soohak: A Mathematician-Curated Benchmark for Evaluating Research-level Math Capabilities of LLMs
https://arxiv.org/abs/2605.09063
- Soohak introduces a 439-problem research-level math benchmark authored from scratch by 64 mathematicians, positioned as a harder target than olympiad-style reasoning benchmarks [1](./citations/1.md).
- It has a Challenge subset where frontier models still leave substantial headroom: Gemini-3-Pro reaches 30.4%, GPT-5 26.4%, and Claude-Opus-4.5 10.4% [1](./citations/1.md).
- The benchmark also includes a refusal subset aimed at detecting whether models can recognize ill-posed problems and pause instead of answering confidently; no model exceeds 50% there [1](./citations/1.md).
- Its release is delayed to avoid contamination, with public release planned for late 2026 and interim evaluations available on request [1](./citations/1.md).

### Geometry Conflict: Explaining and Controlling Forgetting in LLM Continual Post-Training
https://arxiv.org/abs/2605.09608
- The paper frames continual post-training forgetting as a state-relative update-integration failure, driven by misalignment between the covariance geometry of task updates and the evolving model state [2](./citations/2.md).
- It proposes Geometry-Conflict Wasserstein Merging (GCWM), a data-free update-integration method using Gaussian Wasserstein barycenters and geometry conflict gating [2](./citations/2.md).
- Across Qwen3 0.6B–14B in domain-continual and capability-continual settings, GCWM outperforms data-free baselines and improves both retention and final performance without replay data [2](./citations/2.md).
- The main claim is both explanatory and operational: geometry conflict identifies when updates interfere and also provides the control signal for merging them [2](./citations/2.md).

### Rebellious Student: Reversing Teacher Signals for Reasoning Exploration with Self-Distilled RLVR
https://arxiv.org/abs/2605.10781
- The method reverses the usual self-distillation signal: when the student succeeds on a path the teacher would not predict, those tokens are treated as evidence of self-driven reasoning rather than overwritten [3](./citations/3.md).
- It proposes RLRT, which augments GRPO by reinforcing those tokens on correct rollouts, casting this as a form of exploration grounded in the student’s own success [3](./citations/3.md).
- Across base, instruction-tuned, and thinking-tuned Qwen3 checkpoints, RLRT outperforms self-distillation and exploration baselines [3](./citations/3.md).
- The paper’s broader point is that information asymmetry can be a principled design axis for RLVR [3](./citations/3.md).

## Multimodal generation, video reasoning, and document automation

### Qwen-Image-2.0 Technical Report
https://arxiv.org/abs/2605.10730
- Qwen-Image-2.0 is presented as an omni-capable image generation foundation model that unifies high-fidelity generation and precise image editing in one framework [4](./citations/4.md).
- The system pairs Qwen3-VL with a Multimodal Diffusion Transformer and uses large-scale data curation plus a custom multi-stage training pipeline [4](./citations/4.md).
- It supports instructions up to 1K tokens and improves text rendering, multilingual typography, high-resolution photorealism, and complex prompt following [4](./citations/4.md).
- Human evaluations reportedly show substantial improvements over previous Qwen-Image models for both generation and editing [4](./citations/4.md).

### PaperFit: Vision-in-the-Loop Typesetting Optimization for Scientific Documents
https://arxiv.org/abs/2605.10341
- PaperFit formalizes visual typesetting optimization (VTO): turning a compilable LaTeX paper into a visually polished, page-budget-compliant PDF through iterative visual verification and source-level revision [5](./citations/5.md).
- The motivation is that compilable manuscripts can still have layout defects such as misplaced floats, overflowing equations, inconsistent table scaling, widow/orphan lines, and poor page balance [5](./citations/5.md).
- It introduces PaperFit, a vision-in-the-loop agent that renders pages, diagnoses defects, and applies constrained repairs, plus PaperFit-Bench with 200 papers, 10 venue templates, and 13 defect types [5](./citations/5.md).
- Experiments show large gains over baselines, supporting the claim that publication-ready typesetting needs visual closed-loop optimization [5](./citations/5.md).

### WorldReasonBench: Human-Aligned Stress Testing of Video Generators as Future World-State Predictors
https://arxiv.org/abs/2605.10434
- WorldReasonBench reframes video generation evaluation as world-state prediction: given an initial state and an action, can a model generate a future video with physically, socially, logically, and informationally consistent state evolution [6](./citations/6.md).
- The benchmark contains 436 curated test cases with structured QA annotations spanning four reasoning dimensions and 22 subcategories [6](./citations/6.md).
- It also introduces WorldRewardBench, with roughly 6K expert-annotated pairs over 1.4K videos for pair-wise and point-wise reward-model evaluation [6](./citations/6.md).
- Results across modern video generators reveal a gap between visual plausibility and actual world reasoning, where videos can look convincing while failing dynamics, causality, or information preservation [6](./citations/6.md).

### CollabVR: Collaborative Video Reasoning with Vision-Language and Video Generation Models
https://arxiv.org/abs/2605.08735
- CollabVR couples a VLM with a VGM at step-level granularity: the VLM plans the next action, inspects the generated clip, and feeds diagnosis back into the next prompt [7](./citations/7.md).
- The motivation is to address long-horizon drift and mid-clip simulation errors that arise when VGMs reason only with short-horizon visual priors [7](./citations/7.md).
- On Gen-ViRe and VBVR-Bench, it improves open-source and closed-source VGMs over single-inference, Pass@k, and prior test-time scaling baselines at matched compute, with the biggest gains on hard tasks [7](./citations/7.md).
- The method is stackable with reasoning-fine-tuned VGMs, suggesting step-level VLM supervision is orthogonal to model-side fine-tuning [7](./citations/7.md).

## Agents, skills, memory, and self-improvement

### X-OmniClaw Technical Report: A Unified Mobile Agent for Multimodal Understanding and Interaction
https://arxiv.org/abs/2605.05765
- X-OmniClaw is a unified Android mobile agent for multimodal understanding and interaction, motivated by the need for personal agents that can handle complex, intuitive mobile tasks [8](./citations/8.md).
- Its architecture combines Omni Perception, Omni Memory, and Omni Action for unified multimodal ingress, personalized working/long-term memory, and hybrid grounding with XML metadata plus visual perception [8](./citations/8.md).
- The report also describes behavior cloning and trajectory replay for capturing navigation as reusable skills [8](./citations/8.md).
- Demonstrations across scenarios are presented as evidence that the system improves interaction efficiency and task reliability [8](./citations/8.md).

### G-Zero: Self-Play for Open-Ended Generation from Zero Data
https://arxiv.org/abs/2605.09959
- G-Zero is a verifier-free co-evolutionary framework for open-ended self-improvement, aimed at domains where proxy LLM judges create bottlenecks and reward hacking [9](./citations/9.md).
- Its central signal is Hint-δ, which measures the predictive shift between an unassisted response and a response conditioned on a self-generated hint [9](./citations/9.md).
- A Proposer model is trained to find the Generator’s blind spots, while the Generator internalizes the hint-guided improvements; the paper also states a best-iterate suboptimality guarantee for an idealized standard-DPO version under coverage and noise assumptions [9](./citations/9.md).
- The framework claims to derive supervision from internal distributional dynamics rather than external judges [9](./citations/9.md).

### Dynamic Skill Lifecycle Management for Agentic Reinforcement Learning
https://arxiv.org/abs/2605.10923
- SLIM treats the active external skill set as a dynamic optimization variable rather than assuming skills only accumulate or are fully absorbed into policy [10](./citations/10.md).
- It estimates each skill’s marginal contribution with leave-one-skill-out validation and then retains, retires, or expands skills accordingly [10](./citations/10.md).
- Experiments report an average 7.1 percentage point improvement across ALFWorld and SearchQA over the best baselines [10](./citations/10.md).
- The main takeaway is that some skills remain valuable externally even after policy learning, so skill retention and policy learning are not mutually exclusive [10](./citations/10.md).

### Mela: Test-Time Memory Consolidation based on Transformation Hypothesis
https://arxiv.org/abs/2605.10537
- Mela imports memory consolidation ideas from neuroscience via a Hierarchical Memory Module with low-frequency, gist-level and high-frequency, episodic sub-modules [11](./citations/11.md).
- The final memory output is reconstructed from both representations, and MemStack distributes memory features across early decoder layers without adding tokens [11](./citations/11.md).
- In language modeling experiments, Mela outperforms Transformer baselines across model sizes [11](./citations/11.md).
- With pretrained context length fixed at 4K, it maintains performance on much longer contexts where Transformer baselines degrade [11](./citations/11.md).

## Efficiency and 3D generation

### Model Merging Scaling Laws in Large Language Models
https://arxiv.org/abs/2509.24244
- The paper studies empirical scaling laws for model merging using cross-entropy and reports a compact power law relating model size and expert number [12](./citations/12.md).
- The law holds in-domain and cross-domain, across architectures and merge methods including Average, TA, TIES, and DARE [12](./citations/12.md).
- It captures two regularities: most gains arrive early, and variability shrinks as more experts are added [12](./citations/12.md).
- The result is positioned as a planning tool for deciding how many experts to merge and when to stop adding them [12](./citations/12.md).

### Make Each Token Count: Towards Improving Long-Context Performance with KV Cache Eviction
https://arxiv.org/abs/2605.09649
- The paper argues that full-cache attention is not always optimal in long contexts because irrelevant tokens can dilute attention away from useful evidence [13](./citations/13.md).
- It proposes a global retention-based KV eviction method with lightweight retention gates and a shared final scoring projection to calibrate utility across layers and heads [13](./citations/13.md).
- The method allows tokens from different layers, heads, and modalities to compete for cache capacity under one global policy [13](./citations/13.md).
- Across long-context language, vision-language reasoning, and multi-turn dialogue benchmarks, it substantially reduces KV memory while matching or surpassing full-cache inference [13](./citations/13.md).

### Pixal3D: Pixel-Aligned 3D Generation from Images
https://arxiv.org/abs/2605.10922
- Pixal3D proposes pixel-aligned 3D generation, directly generating 3D in the input view rather than in canonical pose, to improve fidelity to the source image [14](./citations/14.md).
- It uses pixel back-projection conditioning to lift multi-scale image features into a 3D feature volume and establish direct pixel-to-3D correspondence [14](./citations/14.md).
- The paper claims the approach scales, improves fidelity toward reconstruction-level quality, and naturally extends to multi-view generation by aggregating feature volumes [14](./citations/14.md).
- It is also presented as beneficial for scene synthesis and modular object-separated 3D scene generation [14](./citations/14.md).

## Multimodal alignment and reward design

### Auto-Rubric as Reward: From Implicit Preferences to Explicit Multimodal Generative Criteria
https://arxiv.org/abs/2605.08354
- ARR reframes reward modeling as explicit, criteria-based decomposition: before pairwise comparison, a VLM externalizes prompt-specific rubrics from its internal preference knowledge [15](./citations/15.md).
- This structured decomposition is intended to reduce evaluation biases such as positional bias and to support zero-shot deployment and few-shot conditioning [15](./citations/15.md).
- For training, Rubric Policy Optimization (RPO) distills the rubric-based evaluation into a binary reward, replacing opaque scalar regression with rubric-conditioned preference decisions [15](./citations/15.md).
- On text-to-image generation and image editing benchmarks, ARR-RPO outperforms pairwise reward models and VLM judges [15](./citations/15.md).
