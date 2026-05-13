# HuggingFace Featured AI Papers Digest — 2026-05-13

## Memory, agents, and privacy

### δ-mem: Efficient Online Memory for Large Language Models
https://arxiv.org/abs/2605.12357

- δ-mem adds a compact online associative-memory state to a frozen full-attention backbone, instead of expanding context windows or replacing the backbone.[1](./citations/1.md)
- The method compresses past information into a fixed-size state matrix updated by delta-rule learning, then uses readout to generate low-rank corrections to attention during generation.[1](./citations/1.md)
- Reported results show an average score of 1.10× the frozen backbone and 1.15× the strongest non-δ-mem memory baseline, with larger gains on memory-heavy tasks such as 1.31× on MemoryAgentBench and 1.20× on LoCoMo.[1](./citations/1.md)
- The abstract emphasizes that these gains come while largely preserving general capabilities, suggesting a lightweight path to long-term memory for assistants and agents.[1](./citations/1.md)

### MemPrivacy: Privacy-Preserving Personalized Memory Management for Edge-Cloud Agents
https://arxiv.org/abs/2605.09530

- MemPrivacy targets edge-cloud personalized memory, where cloud-side memory management can expose sensitive user information and naive masking can destroy task-relevant semantics.[2](./citations/2.md)
- The framework identifies privacy-sensitive spans on device, replaces them with semantically structured type-aware placeholders for cloud processing, and restores original values locally when needed.[2](./citations/2.md)
- The authors introduce MemPrivacy-Bench with 200 users and over 52k privacy instances, plus a four-level privacy taxonomy for configurable protection policies.[2](./citations/2.md)
- According to the abstract, MemPrivacy surpasses strong general-purpose models such as GPT-5.2 and Gemini-3.1-Pro on privacy information extraction, reduces inference latency, and keeps utility loss within 1.6% across multiple memory systems.[2](./citations/2.md)

### Agent-ValueBench: A Comprehensive Benchmark for Evaluating Agent Values
https://arxiv.org/abs/2605.10365

- Agent-ValueBench is presented as the first benchmark focused on agent values rather than text-only LLM values.[3](./citations/3.md)
- It contains 394 executable environments across 16 domains, with 4,335 value-conflict tasks spanning 28 value systems and 332 dimensions; each instance is co-synthesized and curated by professional psychologists.[3](./citations/3.md)
- The benchmark uses two pole-aligned golden trajectories per task and a trajectory-level rubric-based judge, then evaluates 14 frontier proprietary and open-weight models across 4 mainstream harnesses.[3](./citations/3.md)
- The abstract reports a “Value Tide” pattern of cross-model homogeneity under interpretable counter-currents, and says values bend non-additively under harness pull and more decisively under embedded skills.[3](./citations/3.md)

### MCP-Cosmos: World Model-Augmented Agents for Complex Task Execution in MCP Environments
https://arxiv.org/abs/2605.09131

- MCP-Cosmos combines MCP, world models, and agents so that a “Bring Your Own World Model” strategy can simulate state transitions and refine plans before execution.[4](./citations/4.md)
- The paper evaluates ReAct and SPIRAL with two planning models and three representative world models on 20+ MCP-Bench tasks.[4](./citations/4.md)
- The abstract reports improvements in environment interaction KPIs such as tool success rate and tool parameter accuracy, and introduces an Execution Quality metric.[4](./citations/4.md)

## Reasoning, post-training, and optimization

### RubricEM: Meta-RL with Rubric-guided Policy Decomposition beyond Verifiable Rewards
https://arxiv.org/abs/2605.10899

- RubricEM targets deep research agents whose outputs are long-form reports and whose trajectories cannot be supervised by verifiable rewards alone.[5](./citations/5.md)
- The framework makes trajectories stage-aware using self-generated rubrics, then uses Stage-Structured GRPO to provide denser semantic feedback for planning, evidence gathering, review, and synthesis.[5](./citations/5.md)
- It also trains a reflection meta-policy that distills judged trajectories into reusable rubric-grounded guidance for future attempts.[5](./citations/5.md)
- The abstract states that RubricEM-8B performs strongly across four long-form research benchmarks, outperforming comparable open models and approaching proprietary deep-research systems.[5](./citations/5.md)

### Teaching Language Models to Think in Code
https://arxiv.org/abs/2605.07237

- ThinC reframes tool-integrated reasoning so that code itself acts as the reasoner, with only a brief natural-language planning step at the start.[6](./citations/6.md)
- The authors distill 12.2k code-centric trajectories from a teacher model and train ThinC-1.7B and ThinC-4B with supervised fine-tuning followed by reinforcement learning.[6](./citations/6.md)
- ThinC-4B is reported to outperform every TIR baseline on five competition-level math benchmarks and even surpass the much larger Qwen3-235B-A22B-Thinking.[6](./citations/6.md)
- The abstract claims 99.2% of final answers are grounded in interpreter output and that the model recovers reliably from code execution failures without intermediate natural-language reasoning.[6](./citations/6.md)

### LoopUS: Recasting Pretrained LLMs into Looped Latent Refinement Models
https://arxiv.org/abs/2605.11011

- LoopUS converts a pretrained LLM into a looped latent-refinement architecture through post-training, rather than training a recurrent model from scratch or doing a disruptive retrofit.[7](./citations/7.md)
- Its design includes block decomposition, an input-dependent selective gate, random deep supervision, and a confidence head for adaptive early exiting.[7](./citations/7.md)
- The abstract says the method improves reasoning-oriented performance without extending generated traces and without requiring recurrent training from scratch.[7](./citations/7.md)

### Beyond GRPO and On-Policy Distillation: An Empirical Sparse-to-Dense Reward Principle for Language-Model Post-Training
https://arxiv.org/abs/2605.12483

- The paper argues that sparse sequence-level reward should be used upstream on strong teacher models, while dense token-level supervision should be used downstream to compress behavior into the deployment model.[8](./citations/8.md)
- It compares GRPO-style sparse RL and OPD-style dense teacher supervision as different reward-density regimes, not separate recipes.[8](./citations/8.md)
- On verifiable math with Qwen3 and Llama models, the abstract reports that an RL-improved 8B teacher distilled through the dense bridge beats direct GRPO on the same 1.7B student, and that the bridge makes later student-side GRPO more effective.[8](./citations/8.md)
- The strongest pre-Stage 3 AIME endpoints are also reported for the canonical 8B/14B teachers after the bridge.[8](./citations/8.md)

### The Many Faces of On-Policy Distillation: Pitfalls, Mechanisms, and Fixes
https://arxiv.org/abs/2605.11182

- This study examines when on-policy distillation and on-policy self-distillation work, fail, and why, with emphasis on mixed results in reasoning and internalization settings.[9](./citations/9.md)
- The abstract says OPD on mathematics is highly sensitive to teacher choice and loss formulation, while OPSD fails in the tested settings because there is no instance-specific privileged information at test time.[9](./citations/9.md)
- It identifies three failure mechanisms: teacher-student distribution mismatch from student-generated prefixes, instability from biased TopK reverse-KL gradients, and an OPSD-specific limitation where the student learns a PI-free policy that aggregates PI-conditioned teachers.[9](./citations/9.md)
- Proposed fixes include stop-gradient TopK objectives, RLVR-adapted teachers, and SFT-stabilized students.[9](./citations/9.md)

### Beyond the Last Layer: Multi-Layer Representation Fusion for Visual Tokenization
https://arxiv.org/abs/2605.10780

- DRoRAE revisits representation autoencoders for visual tokenization by fusing all frozen vision-encoder layers instead of only using the last layer.[10](./citations/10.md)
- The method uses a lightweight fusion module with energy-constrained routing and incremental correction, then fine-tunes the decoder in a three-phase decoupled training scheme.[10](./citations/10.md)
- On ImageNet-256, the abstract reports rFID improving from 0.57 to 0.29 and generation FID improving from 1.74 to 1.65 with AutoGuidance, with gains transferring to text-to-image synthesis.[10](./citations/10.md)
- The paper also reports a log-linear scaling law (R^2 = 0.86) between fusion capacity and reconstruction quality, framing representation richness as a scalable dimension for visual tokenizers.[10](./citations/10.md)

## Multimodal generation and video

### SenseNova-U1: Unifying Multimodal Understanding and Generation with NEO-unify Architecture
https://arxiv.org/abs/2605.12500

- SenseNova-U1 proposes a native unified multimodal paradigm, arguing that understanding and generation should be treated as synergistic views of one process rather than separate systems.[11](./citations/11.md)
- The paper introduces two variants, SenseNova-U1-8B-MoT and SenseNova-U1-A3B-MoT, built on dense and mixture-of-experts understanding baselines.[11](./citations/11.md)
- The abstract claims the models rival top-tier understanding-only VLMs on text understanding, perception, reasoning, agentic decision-making, and spatial intelligence, while also performing strongly on any-to-image synthesis, infographic generation, and interleaved vision-language generation.[11](./citations/11.md)
- It additionally reports preliminary evidence for vision-language-action and world-model scenarios, and says the paper includes design, preprocessing, training, and inference details for community research.[11](./citations/11.md)

### CausalCine: Real-Time Autoregressive Generation for Multi-Shot Video Narratives
https://arxiv.org/abs/2605.12496

- CausalCine reframes multi-shot video generation as an online directing process rather than open-ended continuation of a single scene.[12](./citations/12.md)
- It introduces Content-Aware Memory Routing, which retrieves historical KV entries by attention-based relevance rather than temporal proximity, and reuses context without regenerating previous shots.[12](./citations/12.md)
- The pipeline trains a causal base model on native multi-shot sequences, then distills it into a few-step generator for real-time interactive generation.[12](./citations/12.md)
- The abstract says the approach outperforms autoregressive baselines and approaches bidirectional models while preserving streaming interactivity; a demo is available.[12](./citations/12.md)

## World models and simulation

### Do Enterprise Systems Need Learned World Models? The Importance of Context to Infer Dynamics
https://arxiv.org/abs/2605.12178

- The paper asks whether agents still need learned world models when environment transition rules can be read at inference time from configurable enterprise systems.[13](./citations/13.md)
- It proposes enterprise discovery agents that recover transition dynamics at runtime from system configuration instead of relying only on internalized models.[13](./citations/13.md)
- CascadeBench is introduced as a reasoning-focused benchmark for enterprise cascade prediction, paired with deployment-shift evaluation on synthetic environments.[13](./citations/13.md)
- The abstract says offline-trained world models can work in-distribution but degrade under changing dynamics, while discovery-based agents are more robust because they ground predictions in the current instance.[13](./citations/13.md)

### World Model for Robot Learning: A Comprehensive Survey
https://arxiv.org/abs/2605.00080

- This is a survey of world models from a robot-learning perspective, covering how they support policy learning, planning, simulation, evaluation, and data generation.[14](./citations/14.md)
- It connects robot world models with embodied applications such as navigation and autonomous driving, and summarizes representative datasets, benchmarks, and evaluation protocols.[14](./citations/14.md)
- The abstract positions the survey as a synthesis of fragmented literature and says an accompanying GitHub repository will be maintained and regularly updated.[14](./citations/14.md)

### LychSim: A Controllable and Interactive Simulation Framework for Vision Research
https://arxiv.org/abs/2605.12449

- LychSim is a controllable simulation framework built on Unreal Engine 5, intended to lower the technical barrier for simulation-based vision research.[15](./citations/15.md)
- Its key components are a streamlined Python API, a procedural pipeline with diverse OOD visual challenges and rich 2D/3D ground truth, and native MCP integration for closed-loop reasoning agents.[15](./citations/15.md)
- The abstract also mentions scene-level procedural rules and object-level pose alignments for semantically aligned 3D ground truths and automated scene modification.[15](./citations/15.md)
- Demonstrated uses include synthetic data generation, adversarial examiners for RL, and language-driven scene layout generation; the framework is promised for public release.[15](./citations/15.md)
