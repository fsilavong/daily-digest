# HuggingFace Featured Papers Digest — 2026-05-20

## Video generation, editing, and multimodal evaluation

### CogOmniControl: Reasoning-Driven Controllable Video Generation via Creative Intent Cognition
https://arxiv.org/abs/2605.19995
- CogOmniControl factorizes controllable video generation into two stages: creative intent cognition and generation, aiming at sparse or abstract production inputs such as storyboard sketches and clay-render conditions.[1](./citations/1.md)
- The system trains a specialized CogVLM on authentic anime production data to translate sparse cues into dense reasoning output, then aligns CogOmniDiT to those reasoning outputs with reinforcement learning.[1](./citations/1.md)
- It also uses the CogVLM to plan evaluators and support Best-of-N selection, turning the system into a closed-loop framework.[1](./citations/1.md)
- The paper reports that the model surpasses existing open-source models on CogReasonBench and CogControlBench, two benchmarks built from professional workflow data with genuine creative intent.[1](./citations/1.md)

### Aurora: Unified Video Editing with a Tool-Using Agent
https://arxiv.org/abs/2605.18748
- Aurora pairs a tool-augmented VLM agent with a unified video diffusion transformer so that raw user requests can be converted into structured edit plans for text, source video, reference images, and spatial grounding.[2](./citations/2.md)
- The agent is trained with supervised data for complete edit planning and reference-image selection, plus preference pairs for robust tool use and instruction refinement.[2](./citations/2.md)
- The new AgentEdit-Bench targets agent-enhanced video editing under textual and visual underspecification.[2](./citations/2.md)
- Experiments on AgentEdit-Bench and two existing video editing benchmarks show improvements over instruction-only baselines, and the VLM agent transfers to compatible frozen video editing models.[2](./citations/2.md)

### Artifact-Bench: Evaluating MLLMs on Detecting and Assessing the Artifacts of AI-Generated Videos
https://arxiv.org/abs/2605.18984
- Artifact-Bench evaluates MLLMs on artifact detection and analysis for AI-generated video, motivated by failures such as temporal inconsistencies, structural distortions, and semantic incoherence.[3](./citations/3.md)
- It introduces a three-level taxonomy spanning photorealistic, animated, and CG-style videos, and defines three tasks: real-vs-AI classification, pairwise realism comparison, and fine-grained artifact identification.[3](./citations/3.md)
- In tests on 19 leading MLLMs, many models performed near random or below random in difficult settings.[3](./citations/3.md)
- The benchmark also finds misalignment between MLLM judgments and human perceptual preferences, limiting their reliability as general evaluators of video realism.[3](./citations/3.md)

### MSAVBench: Towards Comprehensive and Reliable Evaluation of Multi-Shot Audio-Video Generation
https://arxiv.org/abs/2605.20183
- MSAVBench is presented as the first comprehensive benchmark and adaptive hybrid evaluation framework for multi-shot audio-video generation.[4](./citations/4.md)
- It spans four dimensions—video, audio, shot, and reference—covers up to 15 shots, and includes challenging non-realistic scenarios.[4](./citations/4.md)
- The evaluation framework adds adaptive self-correction for shot segmentation, instance-wise rubrics for subjective metrics, and tool-grounded evidence extraction for difficult judgments.[4](./citations/4.md)
- The paper reports 91.5% Spearman rank correlation with human judgments and finds that current models still struggle with director-level control and fine-grained audio-visual synchronization.[4](./citations/4.md)

### Echo-Forcing: A Scene Memory Framework for Interactive Long Video Generation
https://arxiv.org/abs/2605.16003
- Echo-Forcing targets interactive long video generation, where prompt switching, old-scene forgetting, and historical scene recall are harder than single-prompt extension.[5](./citations/5.md)
- The method is training-free and introduces hierarchical temporal memory, scene recall frames, and difference-aware memory decay to manage bounded cache budgets.[5](./citations/5.md)
- It claims support for smooth transitions, hard cuts, and long-range scene recall, while decoupling stable anchors, compressed history, and recent windows.[5](./citations/5.md)
- On VBench-Long, the paper reports the best overall performance for both long-video generation and interactive video generation settings.[5](./citations/5.md)

## Reasoning, RLVR, and long-context training

### Process Rewards with Learned Reliability
https://arxiv.org/abs/2605.15529
- BetaPRM extends process reward models by predicting both step success probability and the reliability of that prediction, rather than outputting only a single step score.[6](./citations/6.md)
- It learns a Beta belief from Monte Carlo continuation supervision via a Beta-Binomial likelihood, instead of regressing to the finite-sample success ratio as a point estimate.[6](./citations/6.md)
- The learned reliability signal is used in Adaptive Computation Allocation for PRM-guided Best-of-N reasoning, spending more compute on uncertain prefixes and stopping when a high-reward solution is reliable.[6](./citations/6.md)
- Across four backbones and four reasoning benchmarks, the method improves Best-of-N selection and the accuracy-token tradeoff, reducing token usage by up to 33.57% while improving final-answer accuracy.[6](./citations/6.md)

### CEPO: RLVR Self-Distillation using Contrastive Evidence Policy Optimization
https://arxiv.org/abs/2605.19436
- CEPO addresses RLVR self-distillation by comparing whether the correct answer favors a token while the wrong answer disfavors it, aiming to isolate genuine reasoning steps from filler.[7](./citations/7.md)
- The wrong-answer teacher is built from rejected rollouts already in the batch, so the method adds no extra sampling cost.[7](./citations/7.md)
- The paper claims CEPO preserves structural safety guarantees from prior work while sharpening credit at decisive tokens and vanishing at filler positions.[7](./citations/7.md)
- It reports average accuracy gains over GRPO on five multimodal math reasoning benchmarks at 2B and 4B scale, while distribution-matching self-distillation baselines fall below the untrained baseline.[7](./citations/7.md)

### Anti-Self-Distillation for Reasoning RL via Pointwise Mutual Information
https://arxiv.org/abs/2605.11609
- AntiSD argues that on-policy self-distillation can fail in math reasoning because privileged context inflates confidence on implied tokens and suppresses deliberation tokens such as “Wait,” “Let,” and “Maybe.”[8](./citations/8.md)
- The method ascends a divergence between student and teacher instead of descending it, reversing the per-token sign, and uses an entropy-triggered gate to disable the term once teacher entropy collapses.[8](./citations/8.md)
- It is presented as a drop-in replacement for default self-distillation.[8](./citations/8.md)
- Across five models from 4B to 30B parameters, AntiSD reaches GRPO-level accuracy in 2 to 10 times fewer training steps and improves final accuracy by up to 11.5 points.[8](./citations/8.md)

### GoLongRL: Capability-Oriented Long Context Reinforcement Learning with Multitask Alignment
https://arxiv.org/abs/2605.19577
- GoLongRL is a fully open-source post-training recipe for long-context RLVR that emphasizes capability-oriented data construction rather than increasingly complex retrieval paths.[9](./citations/9.md)
- The authors release 23K RLVR samples, the full construction pipeline, and training code; the data spans 9 task types paired with their natural evaluation metrics.[9](./citations/9.md)
- The dataset mixes curated open-source samples and synthetic QA pairs generated from real source documents such as books, academic papers, and multi-turn dialogues.[9](./citations/9.md)
- Under vanilla GRPO, the dataset outperforms the closed-source QwenLong-L1.5 dataset, and a Qwen3-30B-A3B model trained on it reaches long-context performance comparable to DeepSeek-R1-0528 and Qwen3-235B-A22B-Thinking-2507.[9](./citations/9.md)
- TMN-Reweight is introduced to align heterogeneous rewards across tasks and improve average performance over vanilla GRPO.[9](./citations/9.md)

## Agents, automation, and evaluation infrastructure

### AutoResearchClaw: Self-Reinforcing Autonomous Research with Human-AI Collaboration
https://arxiv.org/abs/2605.20025
- AutoResearchClaw is a multi-agent autonomous research pipeline built around structured debate, self-healing execution, verifiable reporting, human-in-the-loop collaboration, and cross-run evolution.[10](./citations/10.md)
- The system uses a Pivot/Refine loop to turn execution failures into information and claims to prevent fabricated numbers and hallucinated citations via verifiable result reporting.[10](./citations/10.md)
- Human collaboration is explicitly modeled through seven intervention modes, ranging from full autonomy to step-by-step oversight.[10](./citations/10.md)
- On ARC-Bench, a 25-topic experiment-stage benchmark, the system outperforms AI Scientist v2 by 54.7%, and the ablation suggests targeted collaboration at high-leverage decision points is best.[10](./citations/10.md)

### OmniGUI: Benchmarking GUI Agents in Omni-Modal Smartphone Environments
https://arxiv.org/abs/2605.18758
- OmniGUI is a step-level benchmark for GUI agents in omni-modal smartphone environments, where each action step includes interleaved images, audio, and video.[11](./citations/11.md)
- The dataset contains 709 expert-demonstrated episodes and 2,579 action steps across 29 applications, annotated with objective multimodal dependency levels.[11](./citations/11.md)
- The benchmark uses foundational omni-modal models as agent proxies because dedicated omni-modal GUI agent frameworks are still nascent.[11](./citations/11.md)
- Results show models are competent on visually static tasks but degrade sharply when synchronous temporal and auditory signals matter, with cross-modal interference from task-irrelevant environmental noise identified as a bottleneck.[11](./citations/11.md)

### OpenComputer: Verifiable Software Worlds for Computer-Use Agents
https://arxiv.org/abs/2605.19769
- OpenComputer builds verifiable software worlds for computer-use agents using app-specific state verifiers, a self-evolving verification layer, realistic task synthesis, and an auditable evaluation harness.[12](./citations/12.md)
- The current version covers 33 desktop applications and 1,000 finalized tasks across browsers, office tools, creative software, development environments, file managers, and communication apps.[12](./citations/12.md)
- The framework records full trajectories and computes partial-credit rewards, emphasizing auditable evaluation rather than only end-state success.[12](./citations/12.md)
- The paper reports that hard-coded verifiers align more closely with human adjudication than LLM-as-judge evaluation, and that frontier agents and open-source models still struggle with robust computer automation.[12](./citations/12.md)

## Multilingual documents and unified multimodal learning

### DocAtlas: Multilingual Document Understanding Across 80+ Languages
https://arxiv.org/abs/2605.12623
- DocAtlas constructs OCR datasets and benchmarks for 82 languages and 9 evaluation tasks, targeting low-resource multilingual document understanding.[13](./citations/13.md)
- It uses two annotation pipelines: differential rendering of native DOCX documents and synthetic LaTeX-based generation for right-to-left scripts, producing DocTag annotations for layout, text, and component types without learned annotators.[13](./citations/13.md)
- Evaluation of 16 state-of-the-art models shows persistent gaps for low-resource scripts.[13](./citations/13.md)
- DPO with rendering-derived ground truth as positive signal improves in-domain and out-of-domain accuracy without measurable base-language degradation, while supervised fine-tuning degrades out-of-domain performance by up to 21%.[13](./citations/13.md)

### Semantic Generative Tuning for Unified Multimodal Models
https://arxiv.org/abs/2605.18714
- Semantic Generative Tuning studies generative post-training for unified multimodal models, using hierarchical visual tasks as generative proxies to connect understanding and generation.[14](./citations/14.md)
- The paper argues that image segmentation is the best high-level proxy because it captures structural semantics without the texture distraction of low-level tasks.[14](./citations/14.md)
- SGT is described as a segmentation-based generative proxy that improves feature linear separability and visual-textual attention allocation.[14](./citations/14.md)
- Extensive evaluations are said to improve both multimodal comprehension and generative fidelity across mainstream benchmarks.[14](./citations/14.md)

## Other paper

### SceneCode: Executable World Programs for Editable Indoor Scenes with Articulated Objects
https://arxiv.org/abs/2605.19587
- SceneCode formulates physically interactable indoor scene synthesis as programmatic world generation, compiling natural-language prompts into executable indoor worlds rather than opaque meshes.[15](./citations/15.md)
- A room-level agentic backbone produces a structured house layout and per-object AssetRequests via a planner-designer-critic loop, then routes them through five code-generation strategies.[15](./citations/15.md)
- The resulting Blender Python programs are execution-repaired, compiled into simulation-ready assets, and exported as SDF, with a persistent scene-state registry linking requests, programs, geometry, and simulation assets.[15](./citations/15.md)
- The paper evaluates scene-level synthesis, object-level asset quality, human judgment, and downstream robot interaction, reporting better prompt faithfulness, cleaner mesh structure, and simulator-loadable articulation metadata.[15](./citations/15.md)
