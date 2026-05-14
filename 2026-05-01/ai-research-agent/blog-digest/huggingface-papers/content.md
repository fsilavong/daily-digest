# HuggingFace Featured Papers Digest — 2026-05-01

## Agents, scientific infrastructure, and productivity

### Heterogeneous Scientific Foundation Model Collaboration
https://arxiv.org/abs/2604.27351
- Eywa extends language-centric agent systems to scientific foundation models by adding a language-model-based reasoning interface over non-linguistic modalities, so domain-specific predictive models can participate in higher-level decision making [1](./citations/1.md).
- It can be used as a drop-in single-agent pipeline (EywaAgent), swapped into multi-agent systems as specialized agents (EywaMAS), or coordinated by a planner in EywaOrchestra [1](./citations/1.md).
- The paper evaluates across physical, life, and social sciences and reports improved performance on structured, domain-specific data while reducing reliance on language-only reasoning [1](./citations/1.md).

### Intern-Atlas: A Methodological Evolution Graph as Research Infrastructure for AI Scientists
https://arxiv.org/abs/2604.28158
- Intern-Atlas targets the gap in document-centric research infrastructure by explicitly modeling methodological evolution, lineage, and bottlenecks rather than only citation links [3](./citations/3.md).
- The graph is built from 1,030,314 papers and 9,410,201 semantically typed, verbatim-grounded edges, with a self-guided temporal tree search for tracing evolution chains [3](./citations/3.md).
- The authors report strong alignment with expert-curated evolution chains and show downstream use for idea evaluation and automated idea generation [3](./citations/3.md).

### Synthetic Computers at Scale for Long-Horizon Productivity Simulation
https://arxiv.org/abs/2604.28181
- The method creates synthetic computer environments with realistic folder hierarchies and content-rich artifacts, then runs long-horizon simulations on them to generate productivity data [4](./citations/4.md).
- In the setup, one agent creates month-scale productivity objectives and another acts as the user across the computer, navigating files, coordinating with collaborators, and producing deliverables [4](./citations/4.md).
- Preliminary experiments on 1,000 synthetic computers ran for over 8 hours per simulation and averaged more than 2,000 turns; the resulting experiential signals improved in-domain and out-of-domain productivity evaluations [4](./citations/4.md).

### The Last Human-Written Paper: Agent-Native Research Artifacts
https://arxiv.org/abs/2604.24658
- ARA reframes papers as machine-executable research packages with four layers: scientific logic, executable code/specifications, an exploration graph of failures, and evidence grounding every claim in raw outputs [10](./citations/10.md).
- The system includes a live research manager, a compiler from legacy papers/repos into ARAs, and an ARA-native review process focused on objective checks [10](./citations/10.md).
- Reported results on PaperBench and RE-Bench show higher QA accuracy and reproduction success, and the preserved failure traces help but can also constrain later exploration [10](./citations/10.md).

## Visual generation, video, and embodied simulation

### Visual Generation in the New Era: An Evolution from Atomic Mapping to Agentic World Modeling
https://arxiv.org/abs/2604.28185
- This is a roadmap paper arguing that visual generation should move from appearance synthesis toward structure-, dynamics-, and causality-grounded generation [2](./citations/2.md).
- It proposes a five-level taxonomy: Atomic Generation, Conditional Generation, In-Context Generation, Agentic Generation, and World-Modeling Generation [2](./citations/2.md).
- The paper argues current evaluation overstates progress because perceptual metrics can miss structural, temporal, and causal failures, and it reviews technical drivers such as flow matching, post-training, reward modeling, and sampling acceleration [2](./citations/2.md).

### Representation Fréchet Loss for Visual Generation
https://arxiv.org/abs/2604.28190
- The paper argues Fréchet Distance can be optimized as a training objective in representation space by decoupling population size from gradient batch size, calling the method FD-loss [6](./citations/6.md).
- Post-training with FD-loss improves visual quality across representation spaces; in Inception space, a one-step generator reaches 0.72 FID on ImageNet 256x256 [6](./citations/6.md).
- FD-loss can convert multi-step generators into strong one-step generators without distillation or adversarial training, and the authors argue Inception FID can misrank sample quality, motivating a multi-representation metric, FDr^k [6](./citations/6.md).

### Co-Evolving Policy Distillation
https://arxiv.org/abs/2604.27083
- CoPD is proposed as a way to consolidate multiple expert capabilities while reducing the capability loss seen in mixed RLVR or sequential RLVR-then-OPD pipelines [7](./citations/7.md).
- The key idea is to train experts in parallel and apply OPD during ongoing RLVR, with experts serving as mutual teachers so the distillation is bidirectional [7](./citations/7.md).
- Experiments reportedly integrate text, image, and video reasoning into one model and outperform mixed RLVR, MOPD, and even domain-specific experts [7](./citations/7.md).

### ExoActor: Exocentric Video Generation as Generalizable Interactive Humanoid Control
https://arxiv.org/abs/2604.27711
- ExoActor uses third-person video generation as a unified interface for modeling interaction dynamics between robot, environment, and task-relevant objects [8](./citations/8.md).
- The generated video is converted into executable humanoid behavior via human-motion estimation and a general motion controller [8](./citations/8.md).
- The authors report an end-to-end system that generalizes to new scenarios without additional real-world data collection, while noting current limitations and future directions [8](./citations/8.md).

### World2Minecraft: Occupancy-Driven Simulated Scenes Construction
https://arxiv.org/abs/2604.27578
- World2Minecraft converts real-world scenes into structured Minecraft environments using 3D semantic occupancy prediction, aiming to reduce contamination and improve flexibility in embodied simulation [9](./citations/9.md).
- The paper introduces MinecraftOcc, a dataset with 100,165 images from 156 indoor scenes, created through a low-cost automated occupancy data pipeline [9](./citations/9.md).
- Experiments show the dataset complements existing data and is challenging for current SOTA occupancy models; reconstructed scenes support tasks like VLN [9](./citations/9.md).

### MoCapAnything V2: End-to-End Motion Capture for Arbitrary Skeletons
https://arxiv.org/abs/2604.28130
- The paper replaces the traditional factorized Video-to-Pose plus non-differentiable IK pipeline with a fully end-to-end model where both stages are learnable and jointly optimized [11](./citations/11.md).
- It resolves pose-to-rotation ambiguity by conditioning on a reference pose-rotation pair from the target asset, which defines the coordinate system for rotation prediction [11](./citations/11.md).
- On Truebones Zoo and Objaverse, the method reduces rotation error from about 17 degrees to about 10 degrees, reaches 6.54 degrees on unseen skeletons, and runs about 20x faster than mesh-based pipelines [11](./citations/11.md).

### PhyCo: Learning Controllable Physical Priors for Generative Motion
https://arxiv.org/abs/2604.28169
- PhyCo aims to add continuous, interpretable physical control to video generation so outputs better respect friction, restitution, deformation, and force [12](./citations/12.md).
- It combines a 100K+ simulation-video dataset, physics-supervised fine-tuning with a ControlNet conditioned on physical property maps, and VLM-guided reward optimization [12](./citations/12.md).
- On Physics-IQ, it improves physical realism over strong baselines, and human studies report clearer control over physical attributes without simulator or geometry reconstruction at inference [12](./citations/12.md).

## Multimodal interaction and website generation

### InteractWeb-Bench: Can Multimodal Agent Escape Blind Execution in Interactive Website Generation?
https://arxiv.org/abs/2604.27419
- InteractWeb-Bench is a multimodal interactive benchmark for website generation under non-expert, low-code user conditions, designed around the failure mode the authors call blind execution [5](./citations/5.md).
- It introduces four user-agent types, persona-driven perturbations, and requirement-engineering-inspired ambiguity/redundancy/contradiction to simulate messy instructions [5](./citations/5.md).
- The benchmark’s action space includes Clarify, Implement, Verify, and Submit; experiments show frontier MLLM agents still remain trapped in blind execution [5](./citations/5.md).
