# AI Research Digest — 2026-04-29

```audio
src: ./assets/narration.mp3
title: Listen
```

## Agent collaboration, recursion, and workflow design

- Recursive multi-agent systems are moving toward latent-space coordination rather than pure text chaining: RecursiveMAS uses a RecursiveLink module for latent thought generation and cross-agent state transfer, plus an inner-outer loop to co-optimize the whole system across recursion rounds [1](./blog-digest/huggingface-papers/content.md).
- On benchmarked collaboration, RecursiveMAS reports average gains of 8.3%, 1.2x-2.4x speedup, and 34.6%-75.6% token reduction across math, science, medicine, search, and code tasks, suggesting recursion is being treated as a scaling lever for agent efficiency as much as capability [1](./blog-digest/huggingface-papers/content.md).
- Parallel exploration remains a strong design pattern for tool-using agents: PExA reframes text-to-SQL as parallel test-case exploration over simpler atomic SQLs and claims 70.2% execution accuracy on Spider 2.0 [2](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Workflow structure itself is now a research target, with cyclic subtask graphs studied as a way to revisit subtasks for recovery in ALFWorld, while also exposing coordination and token-cost bottlenecks in TextCraft and Finance-Agent [3](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- SkillSynth pushes the same idea into terminal tasks by sampling executable paths from a scenario-mediated skill graph, then using a multi-agent harness to synthesize training instances for terminal-agent development [4](./blog-digest/huggingface-papers/content.md).
- TCOD addresses multi-turn agent training by applying a temporal curriculum that starts with short trajectories and expands to longer ones to reduce compounding error and trajectory-level KL instability, with up to 18-point gains over vanilla OPD on ALFWorld, WebShop, and ScienceWorld [5](./blog-digest/huggingface-papers/content.md).
- Co-Director applies hierarchical multi-agent control to video storytelling, using a bandit to choose creative directions and a local multimodal self-refinement loop to reduce semantic and identity drift in chained generation [6](./blog-digest/huggingface-papers/content.md).

## Safety, guardrails, and runtime governance

- Discovering agentic safety specifications from 1-bit danger signals suggests that binary danger warnings can be enough for an LLM to infer a usable natural-language safety spec, with EPO-Safe finding safe behavior in 1–2 rounds on AI Safety Gridworlds and text analogs [7](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The same safety line warns that reward-only reflection can backfire by encouraging reward hacking, which makes the distinction between safety learning and reward maximization more than theoretical [7](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- GSAR tackles hallucination recovery in multi-agent LLMs by separating grounded, ungrounded, contradicted, and complementary evidence, then using typed groundedness scores to decide whether to proceed, regenerate, or replan [8](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Adaptive runtime governance is also being formalized: RiskGate frames monitoring, anticipation, and monotonic restriction as viability properties for autonomous agents and adds a viability index plus a kill-switch-last-resort pipeline, though quantitative evaluation is still future work [9](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- BARRED shows a synthetic-data path to custom guardrails, using asymmetric debate over dimension-decomposed policy coverage to train smaller models that reportedly outperform proprietary LLMs and dedicated guardrail systems [10](./blog-digest/huggingface-papers/content.md).

## Evaluation, benchmarks, and judge reliability

- LLM-as-a-judge pipelines appear more fragile than many users assume: a systematic comparison of nine debiasing strategies across five judge models and three benchmarks finds style bias dominates position bias, while combined budget control yields the best reported lift, including +11.2 points for Claude Sonnet 4 [11](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- AutoResearchBench makes scientific literature discovery itself into the benchmark, splitting work into Deep Research and Wide Research and showing that even strong models still score only 9.39% and 9.31% respectively, which points to a large gap in autonomous scholarly search [12](./blog-digest/huggingface-papers/content.md).
- DV-World broadens agent evaluation beyond sandboxed demos into real-world visualization work, spanning spreadsheet manipulation, artifact adaptation, and user-simulator interaction, and reports that state-of-the-art models remain under 50% overall [13](./blog-digest/huggingface-papers/content.md).
- FormalScience applies human-in-the-loop autoformalization to science, releases FormalPhysics with 200 physics problems and Lean4 proofs, and highlights semantic drift as a systematic failure mode in physics formalization [14](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Knowledge graphs, sparse features, and explainability

- Domain-Filtered Knowledge Graphs from Sparse Autoencoder Features turns large sparse-autoencoder feature inventories into filtered domain concepts and co-occurrence or mechanism graphs, with a biology-textbook case study showing chapter and subchapter structure in a readable form [15](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- XGRAG makes GraphRAG explanations graph-native by using perturbation-based explanations that reportedly improve over RAG-Ex by 14.81% on NarrativeQA, FairyTaleQA, and TriviaQA, and the explanation quality correlates with graph centrality [16](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Don't Make the LLM Read the Graph: Make the Graph Think argues that belief graphs matter most when they gate action selection rather than simply sit in the prompt, based on 3,000+ Hanabi trials across four LLM families [17](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The same Hanabi study reports a Planner Defiance failure mode and diminishing returns from deeper graphs, suggesting there is a practical limit to how much symbolic structure helps if the agent does not actually use it [17](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Multimodal generation, editing, and post-training

- Refinement via Regeneration reframes unified multimodal image refinement as conditional regeneration rather than editing, enlarging the modification space while still conditioning on the target prompt and semantic tokens of the initial image [18](./blog-digest/huggingface-papers/content.md).
- The reported gains for that approach are substantial, with improvements on Geneval, DPGBench, and UniGenBench++ all moving materially upward relative to prior baselines [18](./blog-digest/huggingface-papers/content.md).
- Meta-CoT improves image editing by decomposing tasks into task/target/understanding triplets and five meta-tasks, then adding a CoT-Editing Consistency Reward to align behavior with chain-of-thought reasoning [19](./blog-digest/huggingface-papers/content.md).
- Mutual Forcing targets fast autoregressive audio-video character generation with a two-stage training recipe and a shared-weight few-step/multi-step self-distillation setup that claims baseline-level quality in only 4 to 8 sampling steps [20](./blog-digest/huggingface-papers/content.md).
- IAM adds identity awareness to motion synthesis by jointly modeling body morphology, motion dynamics, and multimodal identity cues, with gains in motion realism and motion-identity consistency on motion capture and in-the-wild data [21](./blog-digest/huggingface-papers/content.md).
- A Systematic Post-Train Framework for Video Generation treats deployment as a post-training problem, combining supervised fine-tuning, video-tailored GRPO RLHF, prompt enhancement, and inference optimization to improve quality, coherence, and controllability under sampling-cost constraints [22](./blog-digest/huggingface-papers/content.md).
- MAIC-UI moves in the opposite direction from pure generation by giving educators a zero-code way to create and iteratively edit interactive STEM courseware, with sub-10-second updates and reported gains in learnability and classroom STEM outcomes [23](./blog-digest/huggingface-papers/content.md).

## Audio, dialogue, and spoken interaction

- Step-Audio-R1.5 criticizes verified-reward reinforcement learning for audio reasoning as a verifiable-reward trap, arguing that it over-optimizes discrete correctness at the expense of spoken interaction quality [24](./blog-digest/huggingface-papers/content.md).
- Its alternative is reinforcement learning from human feedback for audio reasoning, aiming to keep analytical reasoning strong while improving long-turn dialogue and prosody in immersive speech settings [24](./blog-digest/huggingface-papers/content.md).
