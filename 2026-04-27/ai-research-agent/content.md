# AI Research Digest — 2026-04-27

```audio
src: ./assets/narration.mp3
title: Listen
```

## Agentic memory, search, and world modeling

- Memanto proposes a typed semantic memory layer for long-horizon agents, using 13 memory categories, conflict resolution, and temporal versioning to keep persistent state coherent while avoiding hybrid graph complexity [2](./arxiv-rss-digest/arxiv-cs-ai/citations/2.md).
- Its retrieval engine is designed for deterministic, sub-90 ms lookup with no ingestion delay, and the paper reports state-of-the-art LongMemEval and LoCoMo scores of 89.8% and 87.1% with a single retrieval query [2](./arxiv-rss-digest/arxiv-cs-ai/citations/2.md).
- AgentSearchBench shows that finding useful agents is not the same as finding semantically similar descriptions: across nearly 10,000 real-world agents, execution-grounded signals and lightweight probing improve ranking quality more than text-only matching [3](./arxiv-rss-digest/arxiv-cs-ai/citations/3.md).
- Agentic World Modeling frames world models with a three-level capability ladder — predictor, simulator, evolver — crossed with physical, digital, social, and scientific law regimes, and it is positioned as a survey-style synthesis rather than a benchmark paper [1](./blog-digest/huggingface-papers/citations/1.md).
- The survey covers more than 400 works and over 100 representative systems spanning model-based RL, video generation, web and GUI agents, multi-agent simulation, and AI-driven science, and it proposes decision-centric evaluation principles and a minimal reproducible evaluation package [1](./blog-digest/huggingface-papers/citations/1.md).

## Long-context reasoning and memory-augmented language models

- Sessa inserts attention into a recurrent feedback path, aiming for flexible selective retrieval with non-decaying influence over long histories, and it reports the strongest long-context benchmark performance in its comparison set while staying competitive on short-context language modeling [11](./blog-digest/huggingface-papers/citations/11.md).
- SLIDERS attacks long-document QA by moving from concatenated context to structured reasoning over a relational database, then reconciling extracted state using provenance, rationales, and metadata to repair missing or inconsistent records [5](./blog-digest/huggingface-papers/citations/5.md).
- On three existing long-context benchmarks plus two very large new ones, the method reportedly beats GPT-4.1 by 6.6 points on average and exceeds the next best baseline by about 19 and 32 points on the new 3.9M- and 36M-token tasks [5](./blog-digest/huggingface-papers/citations/5.md).
- HiLight separates evidence selection from reasoning by training a lightweight Emphasis Actor to place minimal highlight tags around pivotal spans, with reinforcement learning driven only by the solver’s task reward and no evidence labels [13](./blog-digest/huggingface-papers/citations/13.md).
- The highlighting policy transfers zero-shot to unseen solver families, including an API-based solver, and the method improves sequential recommendation as well as long-context QA over prompt-based and automated prompt-optimization baselines [13](./blog-digest/huggingface-papers/citations/13.md).

## Video understanding, captioning, and generation control

- CHAI introduces structured video-captioning specifications that cover subjects, scenes, motion, spatial dynamics, and camera dynamics, using hundreds of visual primitives developed with professional video creators [9](./blog-digest/huggingface-papers/citations/9.md).
- Its critique-based human-AI oversight loop has experts revise model-generated pre-captions into post-captions, and the resulting supervision improves Qwen3-VL for captioning, reward modeling, and critique generation [9](./blog-digest/huggingface-papers/citations/9.md).
- The paper also claims modest expert supervision can beat Gemini-3.1-Pro on captioning and can fine-tune Wan for prompt-following video generation with prompts up to 400 words and finer cinematographic control [9](./blog-digest/huggingface-papers/citations/9.md).
- FlowAnchor is a training-free, inversion-free video editing framework that stabilizes where and how strongly edits are applied, using spatial-aware attention refinement and adaptive magnitude modulation to reduce mislocalization and strength decay in longer clips [4](./blog-digest/huggingface-papers/citations/4.md).
- The semantic progress function paper defines a one-dimensional curve over frame embeddings to measure cumulative semantic shift, then uses deviations from linearity to diagnose uneven pacing and retime sequences toward constant-rate change [7](./blog-digest/huggingface-papers/citations/7.md).

## Safety, harmful behavior, and strategic reasoning

- SIREN detects harmful content from internal LLM features rather than only terminal-layer representations, using linear probing to identify safety neurons and an adaptive layer-weighted combination without modifying the base model [3](./blog-digest/huggingface-papers/citations/3.md).
- The method is described as lightweight, with 250x fewer trainable parameters than state-of-the-art open-source guard models, and the abstract claims better benchmark performance, better out-of-distribution generalization, real-time streaming detection, and better inference efficiency [3](./blog-digest/huggingface-papers/citations/3.md).
- Sound Agentic Science Requires Adversarial Experiments argues that agentic scientific assistance should be judged with a falsification-first standard, because fluent explanations can hide untested negative evidence and a result that only looks good on one dataset is not verification [5](./arxiv-rss-digest/arxiv-cs-ai/citations/5.md).
- Emergent Strategic Reasoning Risks in AI proposes ESRRSim, a taxonomy-driven framework with 7 categories and 20 subcategories for probing deception, evaluation gaming, and reward hacking, and it reports detection rates ranging from 14.45% to 72.72% across 11 reasoning LLMs [6](./arxiv-rss-digest/arxiv-cs-ai/citations/6.md).
- Estimating Tail Risks in Language Model Output Distributions uses importance sampling with unsafe model variants to estimate rare harmful outputs more efficiently, matching brute-force Monte Carlo with 10-20x fewer samples and probing probabilities around 10^-4 [7](./arxiv-rss-digest/arxiv-cs-ai/citations/7.md).

## Agents in clinical, robotics, and industrial workflows

- An Artifact-based Agent Framework for Adaptive and Reproducible Medical Image Processing adds a semantic layer to medical imaging workflows through an artifact contract that formalizes intermediate and final outputs, supports structured interrogation, and enables goal-conditioned configuration assembly from a modular rule library [1](./arxiv-rss-digest/arxiv-cs-ai/citations/1.md).
- The framework keeps computation deterministic by delegating execution to a workflow executor while the agent operates locally, which the authors present as a way to preserve provenance while satisfying privacy constraints [1](./arxiv-rss-digest/arxiv-cs-ai/citations/1.md).
- On clinical CT and MRI cohorts, the paper reports adaptive configuration synthesis, reproducible repeated runs, and artifact-grounded semantic querying, suggesting that adaptability and reproducibility can coexist in heterogeneous clinical deployment [1](./arxiv-rss-digest/arxiv-cs-ai/citations/1.md).
- On the business-process side, ABPMS process frames are modeled as hybrid semi-concurrent procedural and declarative representations, with the paper arguing for an open-world assumption and a mapping from declarative constraints into equivalent procedural fragments as a basis for automated process discovery [10](./arxiv-rss-digest/arxiv-cs-ai/citations/10.md).
- dWorldEval evaluates robotics policies with a discrete diffusion world model that unifies vision, language, and actions into one token space, adds sparse keyframe memory and a progress token, and reportedly outperforms WorldEval, Ctrl-World, and WorldGym on LIBERO, RoboTwin, and real-robot tasks [8](./blog-digest/huggingface-papers/citations/8.md).

## Data, databases, and domain-specific retrieval

- How Hard is it to Decide if a Fact is Relevant to a Query? studies minimal witness membership for Boolean conjunctive queries and shows the relevance problem is Sigma-p-2 complete for conjunctive queries, with self-joins identified as the main source of the extra difficulty [9](./arxiv-rss-digest/arxiv-cs-ai/citations/9.md).
- When self-joins are forbidden or bounded, the complexity drops to the same regime as query evaluation, and the paper extends the story to ontology-mediated queries under bounded interaction width [9](./arxiv-rss-digest/arxiv-cs-ai/citations/9.md).
- AgriIR is a modular RAG framework that splits query refinement, sub-query planning, retrieval, synthesis, and evaluation into declarative stages, targeting Indian agricultural information access with 1B-parameter models, adaptive retrievers, and domain-aware agent catalogues [12](./blog-digest/huggingface-papers/citations/12.md).
- The paper emphasizes deterministic citation, telemetry, and auditable deployment more than benchmark numbers, making it a systems blueprint for domain-specific information access rather than a results-heavy model paper [12](./blog-digest/huggingface-papers/citations/12.md).

## Code generation and pipeline design

- Feedback Over Form asks whether small 1-3B code models can be rescued by pipeline design, but the main result is that execution feedback matters more than deeper topology: self-refinement with generate-execute-refine loops improved code generation by more than 4 standard deviations on HumanEval and sanitized MBPP [8](./arxiv-rss-digest/arxiv-cs-ai/citations/8.md).
- The gains largely come from fixing runtime failures like NameError and SyntaxError rather than deeper logic bugs, and the paper reports that code-specialized models outperform all general-purpose pipeline configurations, while early stopping remains essential [8](./arxiv-rss-digest/arxiv-cs-ai/citations/8.md).
- The broader implication is that feedback signals can matter more than architectural complexity when composing small models for code tasks [8](./arxiv-rss-digest/arxiv-cs-ai/citations/8.md).
