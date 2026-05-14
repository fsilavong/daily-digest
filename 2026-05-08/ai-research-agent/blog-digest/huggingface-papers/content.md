# HuggingFace Featured Papers Digest — 2026-05-08

## Reasoning, long-context, and RL

### MiA-Signature: Approximating Global Activation for Long-Context Understanding
https://arxiv.org/abs/2605.06416
- MiA-Signature proposes a compressed representation of the global activation pattern induced by a query, motivated by a cognitive-science analogy to reportable conscious access and distributed activation [1](./citations/1.md).
- In LLM systems, it is instantiated with submodular selection of high-level concepts that cover the activated context space, with optional lightweight iterative updates using working memory [1](./citations/1.md).
- The paper reports that integrating MiA-Signatures into both RAG and agentic systems yields consistent gains across multiple long-context understanding tasks [1](./citations/1.md).

### Nonsense Helps: Prompt Space Perturbation Broadens Reasoning Exploration
https://arxiv.org/abs/2605.05566
- LoPE targets the zero-advantage problem in GRPO-style RL, where all sampled rollouts fail and relative advantage collapses to zero, wasting training signal [5](./citations/5.md).
- The method prepends stochastic Lorem Ipsum-like token sequences to prompts before resampling, arguing that task-irrelevant perturbations can unlock orthogonal reasoning pathways [5](./citations/5.md).
- Across 1.7B, 4B, and 7B models, LoPE outperforms resampling with the original prompts; the authors also note that other low-perplexity Latin-based random sequences work [5](./citations/5.md).

### A^2TGPO: Agentic Turn-Group Policy Optimization with Adaptive Turn-level Clipping
https://arxiv.org/abs/2605.06200
- A^2TGPO keeps Information Gain as an intrinsic process signal for agentic RL, but changes how it is normalized, accumulated, and clipped across turns [8](./citations/8.md).
- It introduces turn-group normalization, variance-rescaled discounted accumulation, and adaptive turn-level clipping to handle heterogeneous turn positions, depth-dependent advantage drift, and mismatched update ranges [8](./citations/8.md).
- The abstract positions it as a process-credit-assignment alternative to external process reward models or tree-based rollout methods [8](./citations/8.md).

### Can RL Teach Long-Horizon Reasoning to LLMs? Expressiveness Is Key
https://arxiv.org/abs/2605.06638
- ScaleLogic gives independent control over proof-planning depth and logical expressiveness, spanning implication-only logic through conjunction, disjunction, negation, and universal quantification [14](./citations/14.md).
- The authors report a power-law relationship between RL compute and reasoning depth, with the exponent increasing monotonically with expressiveness from 1.04 to 2.60 and R² > 0.99 [14](./citations/14.md).
- More expressive training settings transfer better to downstream math and general reasoning benchmarks, with gains up to +10.66 points and improved compute efficiency [14](./citations/14.md).

## Diffusion, image, and video generation

### MARBLE: Multi-Aspect Reward Balance for Diffusion RL
https://arxiv.org/abs/2605.06507
- MARBLE addresses multi-reward diffusion RL by moving from scalar weighted-sum reward aggregation to per-reward gradient computation and quadratic-programming-based harmonization [2](./citations/2.md).
- The method maintains independent advantage estimators per reward and adds an amortized formulation to reduce cost from K+1 backward passes to near single-reward baseline cost, plus EMA smoothing for balancing coefficients [2](./citations/2.md).
- On SD3.5 Medium with five rewards, it improves all reward dimensions simultaneously, makes the worst-aligned reward gradient cosine consistently positive, and runs at 0.97x baseline training speed [2](./citations/2.md).

### Continuous-Time Distribution Matching for Few-Step Diffusion Distillation
https://arxiv.org/abs/2605.06376
- CDM migrates DMD from discrete anchors to continuous optimization, motivated by artifacts and oversmoothing from sparse discrete-time supervision [3](./citations/3.md).
- It uses a dynamic continuous schedule of random length and a continuous-time alignment objective that matches off-trajectory latents extrapolated by the student velocity field [3](./citations/3.md).
- The paper claims competitive visual fidelity on SD3-Medium and Longcat-Image without auxiliary GAN or reward-model objectives [3](./citations/3.md).

### ReflectDrive-2: Reinforcement-Learning-Aligned Self-Editing for Discrete Diffusion Driving
https://arxiv.org/abs/2605.04647
- ReflectDrive-2 represents driving plans as discrete trajectory tokens and enables in-place AutoEdit revision without an auxiliary refinement network [10](./citations/10.md).
- Training combines structure-aware perturbation recovery with full decision-draft-reflect RL, where terminal driving reward is propagated through the full rollout [10](./citations/10.md).
- On NAVSIM, it reports 91.0 PDMS with camera-only input and 94.8 PDMS in best-of-6 oracle mode, at 31.8 ms average latency on NVIDIA Thor [10](./citations/10.md).

### SwiftI2V: Efficient High-Resolution Image-to-Video Generation via Conditional Segment-wise Generation
https://arxiv.org/abs/2605.06356
- SwiftI2V is a two-stage high-resolution I2V framework: first generate a low-resolution motion reference, then perform strongly image-conditioned 2K synthesis guided by that motion [11](./citations/11.md).
- Its Conditional Segment-wise Generation bounds token use by synthesizing videos segment-by-segment, and bidirectional contextual interaction is used within each segment to improve coherence and fidelity [11](./citations/11.md).
- On VBench-I2V at 2K resolution, it matches end-to-end baselines while reducing GPU-time by 202x and is described as practical on a single H800 or RTX 4090 [11](./citations/11.md).

## Agents, tooling, and self-improving systems

### Auto Research with Specialist Agents Develops Effective and Non-Trivial Training Recipes
https://arxiv.org/abs/2605.05724
- The paper frames auto research as an auditable closed loop of hypotheses, code edits, evaluator-owned outcomes, and lineage feedback, rather than a generated paper or checkpoint [6](./citations/6.md).
- Specialist agents partition recipe space and use failures like crashes, budget overruns, and accuracy-gate misses as later program-level edits instead of one-shot suggestions [6](./citations/6.md).
- Across 1,197 headline-run trials plus 600 control trials, the loop improves Parameter Golf validation bpb by 0.81%, NanoChat-D12 CORE by 38.7%, and CIFAR-10 Airbench96 wallclock by 4.59% [6](./citations/6.md).

### SkillOS: Learning Skill Curation for Self-Evolving Agents
https://arxiv.org/abs/2605.06614
- SkillOS trains a skill curator with experience-driven RL while keeping an executor frozen; the curator updates an external SkillRepo from accumulated experience [13](./citations/13.md).
- The reward design uses grouped task streams so earlier trajectories update the repo and later related tasks evaluate whether those updates help [13](./citations/13.md).
- The abstract claims consistent gains over memory-free and strong memory-based baselines on multi-turn agentic tasks and single-turn reasoning tasks, with more targeted skill use and richer Markdown skill files over time [13](./citations/13.md).

### When to Trust Imagination: Adaptive Action Execution for World Action Models
https://arxiv.org/abs/2605.06222
- FFDC is a lightweight verifier for world action models that estimates whether the remaining action rollout can still be trusted by jointly reasoning over predicted future actions, predicted visual dynamics, real observations, and language instructions [9](./citations/9.md).
- The method adaptively chooses chunk sizes: execute longer when prediction and reality stay consistent, and replan earlier when they diverge [9](./citations/9.md).
- On RoboTwin it reduces WAM forward passes by 69.10% and execution time by 34.02% while improving success rate by 2.54%; in real-world experiments the reported success gain is 35% [9](./citations/9.md).

## Representation learning and architecture

### TabEmbed: Benchmarking and Learning Generalist Embeddings for Tabular Understanding
https://arxiv.org/abs/2605.04962
- TabBench is introduced as a benchmark for evaluating tabular understanding in embedding models, covering both classification and retrieval-style tasks [7](./citations/7.md).
- TabEmbed unifies tabular classification and retrieval in a shared embedding space via contrastive learning and positive-aware hard negative mining [7](./citations/7.md).
- The paper says TabEmbed significantly outperforms state-of-the-art text embedding models on TabBench, establishing a new baseline for universal tabular representation learning [7](./citations/7.md).

### UniPool: A Globally Shared Expert Pool for Mixture-of-Experts
https://arxiv.org/abs/2605.06665
- UniPool replaces per-layer expert ownership with a single shared expert pool accessed by independent per-layer routers, treating expert capacity as a global budget [12](./citations/12.md).
- It adds a pool-level auxiliary loss and NormRouter to stabilize shared-pool routing and balance utilization [12](./citations/12.md).
- Across five LLaMA-architecture scales trained on 30B Pile tokens, it improves validation loss and perplexity over matched MoE baselines, with validation loss reductions up to 0.0386 and reduced-pool variants using 41.6% to 66.7% of the expert budget still matching or beating layer-wise MoE [12](./citations/12.md).

### Continuous Latent Diffusion Language Model
https://arxiv.org/abs/2605.06548
- Cola DLM is a hierarchical latent diffusion language model that first learns a text-to-latent mapping with a Text VAE, then models a global semantic prior in continuous latent space with a block-causal DiT, then decodes text conditionally [4](./citations/4.md).
- The authors frame diffusion as latent prior transport rather than token-level observation recovery, aiming to separate global semantic organization from local textual realization [4](./citations/4.md).
- They report experiments across 4 research questions, 8 benchmarks, matched ~2B autoregressive and LLaDA baselines, and scaling curves up to ~2000 EFLOPs, concluding that hierarchical continuous latent prior modeling is a principled alternative to token-level language modeling [4](./citations/4.md).

## Social and behavioral representations

### The Granularity Axis: A Micro-to-Macro Latent Direction for Social Roles in Language Models
https://arxiv.org/abs/2605.06196
- The paper defines a contrast-based Granularity Axis from macro- versus micro-role hidden states and argues that social-role granularity is a dominant latent dimension in prompted behavior [15](./citations/15.md).
- In Qwen3-8B, the axis aligns with PC1 at cosine 0.972 and explains 52.6% of variance; the paper uses 75 roles across five granularity levels and 91,200 role-conditioned responses [15](./citations/15.md).
- The axis transfers to Llama-3.1-8B-Instruct and is causally manipulable via activation steering, which shifts response granularity in the predicted direction [15](./citations/15.md).
