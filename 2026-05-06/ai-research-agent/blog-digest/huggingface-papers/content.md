# HuggingFace Featured Papers Digest — 2026-05-06

## Reasoning, alignment, and agents

### Beyond SFT-to-RL: Pre-alignment via Black-Box On-Policy Distillation for Multimodal RL
https://arxiv.org/abs/2604.28123

- PRISM inserts an explicit distribution-alignment stage between SFT and RLVR to mitigate the drift that standard SFT can introduce in large multimodal models, especially where perception and reasoning errors compound.[1](./citations/1.md)
- The alignment stage is framed as black-box on-policy distillation with an MoE discriminator that separates perception and reasoning signals, and it does not require teacher logits.[1](./citations/1.md)
- The paper says 1.26M public demonstrations are enough for broad SFT initialization, but alignment needs higher-fidelity data; it adds 113K Gemini 3 Flash demonstrations with dense visual grounding and step-by-step reasoning on hard unsolved problems.[1](./citations/1.md)
- On Qwen3-VL, PRISM improves downstream RLVR performance across GRPO, DAPO, and GSPO, raising average accuracy by +4.4 points on 4B and +6.0 points on 8B over the SFT-to-RLVR baseline.[1](./citations/1.md)

### HeavySkill: Heavy Thinking as the Inner Skill in Agentic Harness
https://arxiv.org/abs/2605.02396

- HeavySkill argues that “heavy thinking” is not just an orchestration-time execution unit, but an internalized skill in the model parameters that helps solve complex tasks.[3](./citations/3.md)
- The identified pattern is a two-stage pipeline: parallel reasoning followed by summarization, and it can operate underneath any agentic harness.[3](./citations/3.md)
- In the reported empirical study, this inner skill outperforms Best-of-N, and stronger LLMs can approach Pass@N performance.[3](./citations/3.md)
- The paper claims the depth and width of heavy thinking can be scaled via reinforcement learning, suggesting a path toward models that internalize more of the orchestration logic.[3](./citations/3.md)

### Reinforcement Learning for LLM-based Multi-Agent Systems through Orchestration Traces
https://arxiv.org/abs/2605.02801

- The paper defines orchestration traces as temporal interaction graphs that include spawning, delegation, communication, tool use, return, aggregation, and stopping events.[8](./citations/8.md)
- It organizes RL for multi-agent systems along three axes: reward families, credit/signal attachment points, and five orchestration sub-decisions (spawn, delegate, communicate, aggregate, stop).[8](./citations/8.md)
- The authors note that explicit counterfactual message-level credit is sparse in their curated pool, and they found no explicit RL training method for the stopping decision as of May 4, 2026.[8](./citations/8.md)
- The paper is partly a survey-and-taxonomy artifact, with a curated pool, exclusion log, and replayable trace schema released in a public repository.[8](./citations/8.md)

### OpenSeeker-v2: Pushing the Limits of Search Agents with Informative and High-Difficulty Trajectories
https://arxiv.org/abs/2605.04036

- OpenSeeker-v2 claims that a simple SFT recipe, when trained on informative and high-difficulty trajectories, can be surprisingly strong for frontier search agents.[10](./citations/10.md)
- The data recipe combines a larger knowledge graph, a larger tool set, and strict low-step filtering; the model is trained on only 10.6K data points.[10](./citations/10.md)
- It reports SOTA results on four benchmarks for 30B ReAct agents: 46.0% BrowseComp, 58.1% BrowseComp-ZH, 34.6% Humanity's Last Exam, and 78.0% xbench, exceeding Tongyi DeepResearch’s reported numbers on all four.[10](./citations/10.md)
- The authors emphasize that this is the first SOTA search agent at this model scale and paradigm from a purely academic team using only SFT.[10](./citations/10.md)

### Healthcare AI GYM for Medical Agents
https://arxiv.org/abs/2605.02943

- Healthcare AI GYM is a gymnasium-compatible environment for medical agents spanning 10 clinical domains, 3.6K+ tasks, 135 tools, and 828K medical passages.[15](./citations/15.md)
- The study finds a failure mode where multi-turn agentic structure collapses into verbose single-turn monologues, with length growth and reduced tool use during training.[15](./citations/15.md)
- Vanilla GRPO can reach strong final accuracy on some benchmarks, but the paper reports instability with oscillating response lengths and slow convergence.[15](./citations/15.md)
- TT-OPD, a turn-level truncated on-policy distillation method, achieves the best performance on 10 of 18 benchmarks and averages +3.9 pp over the non-RL baseline while preserving multi-turn tool use.[15](./citations/15.md)

## Multimodal and perception

### X2SAM: Any Segmentation in Images and Videos
https://arxiv.org/abs/2605.00891

- X2SAM is presented as a unified segmentation MLLM that extends any-segmentation from images to videos.[2](./citations/2.md)
- It couples an LLM with a Mask Memory module to keep guided vision features for temporally consistent video mask generation, and it works with conversational instructions plus visual prompts.[2](./citations/2.md)
- The model is described as supporting open-vocabulary, referring, reasoning, grounded conversation generation, interactive, and visual grounded segmentation across both image and video inputs.[2](./citations/2.md)
- The paper also introduces the V-VGD benchmark for segmenting object tracks in videos from interactive visual prompts, and says X2SAM remains competitive on image segmentation while preserving chat ability.[2](./citations/2.md)

### SVGS: Enhancing Gaussian Splatting Using Primitives with Spatially Varying Colors
https://arxiv.org/abs/2411.18966

- SVGS modifies Gaussian primitives to use spatially varying colors and opacity, aiming to improve representation capacity in Gaussian Splatting.[5](./citations/5.md)
- The implementation variants include bilinear interpolation, movable kernels, and tiny neural networks as spatially varying functions.[5](./citations/5.md)
- The paper reports that all three functions outperform the baseline, with movable kernels achieving the best novel-view synthesis results on multiple datasets.[5](./citations/5.md)
- The claimed motivation is compactness and stronger handling of scenes with complex textures but relatively simple geometry.[5](./citations/5.md)

### SplAttN: Bridging 2D and 3D with Gaussian Soft Splatting and Attention for Point Cloud Completion
https://arxiv.org/abs/2605.01466

- SplAttN replaces hard projection with differentiable Gaussian splatting to produce a dense, continuous image-plane representation for cross-modal point cloud completion.[14](./citations/14.md)
- The authors name the failure mode of standard hard projection “Cross-Modal Entropy Collapse,” where sparse support blocks visual prior propagation.[14](./citations/14.md)
- The method is reported to achieve SOTA on PCN and ShapeNet-55/34, and the KITTI benchmark is used as a stress test for multi-modal reliance.[14](./citations/14.md)
- In the counterfactual evaluation, baselines degrade into unimodal template retrievers when vision is removed, while SplAttN remains dependent on visual cues.[14](./citations/14.md)

## Evaluation, benchmarks, and domain tasks

### Workspace-Bench 1.0: Benchmarking AI Agents on Workspace Tasks with Large-Scale File Dependencies
https://arxiv.org/abs/2605.03596

- Workspace-Bench targets “workspace learning,” where agents must reason over explicit and implicit dependencies among heterogeneous files in a workspace.[6](./citations/6.md)
- The benchmark includes 5 worker profiles, 74 file types, 20,476 files up to 20GB, 388 tasks, and 7,399 rubrics that require cross-file retrieval and adaptive decision-making.[6](./citations/6.md)
- Workspace-Bench-Lite is a 100-task subset intended to preserve distribution while cutting evaluation cost by about 70%.[6](./citations/6.md)
- The reported results show current agents remain unreliable: best agent harness/model performance is 68.7%, below the human score of 80.7%, and average agent performance is 47.4%.[6](./citations/6.md)

### SymptomAI: Towards a Conversational AI Agent for Everyday Symptom Assessment
https://arxiv.org/abs/2605.04012

- SymptomAI is deployed through the Fitbit app as end-to-end conversational agents for patient interviewing and differential diagnosis, with 13,917 randomized participants interacting with five AI agents.[7](./citations/7.md)
- In a blinded randomized comparison, SymptomAI differential diagnoses were significantly more accurate than diagnoses from independent clinicians given the same dialogue (OR = 2.47, p < 0.001).[7](./citations/7.md)
- A dedicated symptom interview strategy that elicits more information before diagnosing performs substantially better than baseline user-guided conversations.[7](./citations/7.md)
- The authors note a limitation of self-reported ground truth, but argue the results support complete symptom interviews over the default consumer-LLM pattern.[7](./citations/7.md)

### PatRe: A Full-Stage Office Action and Rebuttal Generation Benchmark for Patent Examination
https://arxiv.org/abs/2605.03571

- PatRe models the full patent examination lifecycle, including Office Action generation and applicant rebuttal, rather than treating patent examination as static classification or extraction.[4](./citations/4.md)
- The benchmark contains 480 real-world cases and supports both oracle and retrieval-simulated evaluation settings.[4](./citations/4.md)
- The paper reports differences between proprietary and open-source models, plus asymmetries between examiner-side analysis and applicant-side rebuttal.[4](./citations/4.md)
- Its main significance is that it turns patent examination into a multi-turn justification-and-response task for evaluating legal and technical reasoning.[4](./citations/4.md)

### A Benchmark for Interactive World Models with a Unified Action Generation Framework
https://arxiv.org/abs/2605.03941

- iWorld-Bench is a benchmark for training and testing interactive world models on abilities such as distance perception and memory.[9](./citations/9.md)
- The dataset uses 330K video clips, from which 2.1K high-quality samples are selected, spanning varied perspectives, weather, and scenes.[9](./citations/9.md)
- The Action Generation Framework unifies evaluation across different interaction modalities and creates six task types, yielding 4.9K test samples.[9](./citations/9.md)
- The authors evaluate 14 representative world models and present a public leaderboard at iWorld-Bench.com.[9](./citations/9.md)

### ESARBench: A Benchmark for Agentic UAV Embodied Search and Rescue
https://arxiv.org/abs/2605.01371

- ESARBench defines embodied search and rescue for UAV agents as autonomous exploration, clue identification, and victim-location reasoning in complex environments.[13](./citations/13.md)
- The benchmark uses Unreal Engine 5 and AirSim to create four photorealistic open environments mapped from real GIS data, along with 600 rescue-style tasks.[13](./citations/13.md)
- The paper evaluates traditional heuristics and MLLM-based ObjectNav baselines and finds bottlenecks in spatial memory, aerial adaptation, and the search-efficiency vs. flight-safety trade-off.[13](./citations/13.md)
- It positions ESARBench as a realistic benchmark for embodied aerial decision-making in rescue scenarios.[13](./citations/13.md)

## Other domain-specific results

### The TTS-STT Flywheel: Synthetic Entity-Dense Audio Closes the Indic ASR Gap Where Commercial and Open-Source Systems Fail
https://arxiv.org/abs/2605.03073

- On a synthesized entity-dense Telugu test set, the open-source Whisper Telugu baseline reaches EHR 0.027 and Deepgram Nova-3 reaches 0.16.[11](./citations/11.md)
- The proposed TTS↔STT flywheel synthesizes about 22K entity-dense Indic-English code-mix utterances at under $50 marginal cost, then fine-tunes with LoRA to reach EHR 0.473 on the held-out test.[11](./citations/11.md)
- The paper reports a native-human-recorded sanity check with n=20 Telugu speakers, where beta-Te reaches EHR 0.516 on native audio versus 0.473 on synthesized audio.[11](./citations/11.md)
- It also reports language-conditional behavior: the recipe helps Telugu and some other languages, but underperforms on Hindi where Deepgram already has substantial entity coverage.[11](./citations/11.md)

### TCDA: Thread-Constrained Discourse-Aware Modeling for Conversational Sentiment Quadruple Analysis
https://arxiv.org/abs/2605.01717

- TCDA combines a Thread-Constrained Directed Acyclic Graph with Discourse-Aware Rotary Position Embedding to model conversational sentiment quadruple analysis.[12](./citations/12.md)
- The graph component is described as filtering cross-thread noise, preserving global connectivity through root anchoring, and incorporating dialogue temporal order.[12](./citations/12.md)
- The embedding component is intended to separate token-level syntactic order from utterance-level progression and mitigate distance dilution.[12](./citations/12.md)
- The paper reports state-of-the-art results on two benchmark datasets.[12](./citations/12.md)
