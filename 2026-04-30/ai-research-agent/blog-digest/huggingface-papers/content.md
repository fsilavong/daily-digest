# HuggingFace Featured Papers Digest — 2026-04-30

## Multimodal agents and world modeling

### GLM-5V-Turbo: Toward a Native Foundation Model for Multimodal Agents
https://arxiv.org/abs/2604.26752
- The paper frames multimodal perception as a core part of reasoning, planning, tool use, and execution for agents, rather than as a separate interface to a language model. It positions GLM-5V-Turbo as a step toward a native foundation model for multimodal agents. [1](./citations/1.md)
- The development report says the model improves across model design, multimodal training, reinforcement learning, toolchain expansion, and integration with agent frameworks. [1](./citations/1.md)
- Reported outcomes include strong performance in multimodal coding, visual tool use, and framework-based agentic tasks, while preserving competitive text-only coding capability. [1](./citations/1.md)
- The abstract emphasizes practical lessons for building multimodal agents, especially multimodal perception, hierarchical optimization, and end-to-end verification. [1](./citations/1.md)

### Unified 4D World Action Modeling from Video Priors with Asynchronous Denoising
https://arxiv.org/abs/2604.26694
- X-WAM is presented as a unified 4D world model that combines real-time robotic action execution with high-fidelity 4D world synthesis in one framework, addressing prior unified world models that only modeled 2D pixel space. [2](./citations/2.md)
- The method predicts multi-view RGB-D videos and uses a lightweight structural adaptation that replicates the final few blocks of a pretrained Diffusion Transformer into a dedicated depth branch for future spatial reconstruction. [2](./citations/2.md)
- Asynchronous Noise Sampling (ANS) is introduced to jointly optimize generation quality and action decoding efficiency; it uses fewer steps for action decoding while reserving the full denoising sequence for high-fidelity video. [2](./citations/2.md)
- Pretrained on over 5,800 hours of robotic data, X-WAM reports 79.2% average success on RoboCasa and 90.7% on RoboTwin 2.0, while also improving visual and geometric metrics for 4D reconstruction/generation. [2](./citations/2.md)

## Agents and workflow environments

### ClawGym: A Scalable Framework for Building Effective Claw Agents
https://arxiv.org/abs/2604.26904
- ClawGym targets Claw-style environments that require multi-step workflows over local files, tools, and persistent workspace states, arguing that development has lacked a systematic framework for synthetic training data and evaluation. [3](./citations/3.md)
- The dataset ClawGym-SynData contains 13.5K filtered tasks synthesized from persona-driven intents and skill-grounded operations, paired with realistic mock workspaces and hybrid verification. [3](./citations/3.md)
- The authors train ClawGym-Agents via supervised fine-tuning on black-box rollout trajectories and also explore reinforcement learning with parallelized rollouts across per-task sandboxes. [3](./citations/3.md)
- For evaluation, they build ClawGym-Bench with 200 instances filtered through automated checks plus human-LLM review; resources are planned for release on GitHub. [3](./citations/3.md)

## Efficiency and training systems

### Accelerating RL Post-Training Rollouts via System-Integrated Speculative Decoding
https://arxiv.org/abs/2604.26779
- The paper treats autoregressive rollout generation as a bottleneck in RL post-training for frontier language models and studies speculative decoding as a lossless acceleration primitive that preserves the target distribution. [4](./citations/4.md)
- The implementation is integrated into NeMo-RL with a vLLM backend, supporting synchronous and asynchronous pipelines and enabling speculation during RL rollouts. [4](./citations/4.md)
- The approach is reported to work with multiple speculation mechanisms, including pretrained MTP heads, small external draft models, and Eagle3-style techniques. [4](./citations/4.md)
- In an 8B reasoning post-training workload, synchronous RL rollout throughput improves by 1.8x; a simulator projects up to 2.5x end-to-end training speedup at 235B scale when combined with asynchronous RL. [4](./citations/4.md)

### Turning the TIDE: Cross-Architecture Distillation for Diffusion Large Language Models
https://arxiv.org/abs/2604.26951
- TIDE is presented as the first framework for cross-architecture distillation for diffusion large language models, where teacher and student differ in architecture, attention mechanism, and tokenizer. [5](./citations/5.md)
- Its three modular components are TIDAL, which modulates distillation strength across training progress and diffusion timestep; CompDemo, which improves teacher context under heavy masking; and Reverse CALM, a cross-tokenizer objective with bounded gradients and dual-end noise filtering. [5](./citations/5.md)
- Distilling 8B dense and 16B MoE teachers into a 0.6B student across two heterogeneous pipelines outperforms the baseline by an average of 1.53 points across eight benchmarks. [5](./citations/5.md)
- The abstract highlights especially strong code-generation gains, with HumanEval reaching 48.78 versus 32.3 for the AR baseline. [5](./citations/5.md)

### Diffusion Templates: A Unified Plugin Framework for Controllable Diffusion
https://arxiv.org/abs/2604.24351
- Diffusion Templates proposes a unified plugin framework that decouples base-model inference from controllable capability injection, aiming to replace fragmented backbone-specific control systems. [6](./citations/6.md)
- The framework has three parts: Template models map task inputs to an intermediate capability representation, a Template cache standardizes capability injection, and a Template pipeline loads and merges one or more caches into the diffusion runtime. [6](./citations/6.md)
- The abstraction is defined at the systems level, so heterogeneous carriers such as KV-Cache and LoRA can be supported under the same interface. [6](./citations/6.md)
- The authors build a model zoo spanning structural control, brightness/color adjustment, image editing, super-resolution, sharpness enhancement, aesthetic alignment, content reference, local inpainting, and age control, and say all resources will be open sourced. [6](./citations/6.md)

## Data, interpretation, and surveys

### FASH-iCNN: Making Editorial Fashion Identity Inspectable Through Multimodal CNN Probing
https://arxiv.org/abs/2604.26186
- FASH-iCNN is trained on 87,547 Vogue runway images across 15 fashion houses from 1991 to 2024 to make editorial fashion identity inspectable. [7](./citations/7.md)
- On clothing-only inputs, the model identifies the fashion house at 78.2% top-1 across 14 houses, the decade at 88.6% top-1, and the year at 58.3% top-1 across 34 years with a mean error of 2.2 years. [7](./citations/7.md)
- Probing the signal shows a sharp dissociation between color and texture: removing color costs 10.6 percentage points of house-identity accuracy, while removing texture costs 37.6 points. [7](./citations/7.md)
- The authors interpret texture and luminance as the primary carriers of editorial identity, and present the system as a way to surface which houses, eras, and color traditions are encoded in the prediction. [7](./citations/7.md)

### A Survey on LLM-based Conversational User Simulation
https://arxiv.org/abs/2604.24977
- This survey reviews recent progress in LLM-based conversational user simulation, motivated by the importance of synthetic user conversation for a range of applications. [8](./citations/8.md)
- It proposes a novel taxonomy covering user granularity and simulation objectives. [8](./citations/8.md)
- The paper also analyzes core techniques and evaluation methodologies and identifies open challenges to guide future research. [8](./citations/8.md)
