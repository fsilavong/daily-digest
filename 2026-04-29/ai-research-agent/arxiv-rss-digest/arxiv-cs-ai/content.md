# arXiv cs.AI digest — 2026-04-29

## Multi-agent reasoning, tool use, and workflow design

- **PExA: Parallel Exploration Agent for Complex Text-to-SQL** — reframes text-to-SQL as parallel test-case exploration over simpler atomic SQLs, aiming to manage the latency/performance trade-off; the abstract claims a new SOTA of 70.2% execution accuracy on Spider 2.0. [1](./citations/1.md)
- **Don't Make the LLM Read the Graph: Make the Graph Think** — across 3,000+ Hanabi trials and four LLM families, the paper argues that belief graphs help mainly when they gate action selection rather than merely sit in the prompt; it also reports a “Planner Defiance” failure mode and diminishing returns for deeper graphs. [3](./citations/3.md)
- **Complete Cyclic Subtask Graphs for Tool-Using LLM Agents: Flexibility, Cost, and Bottlenecks in Multi-Agent Workflows** — studies maximally flexible cyclic subtask graphs on TextCraft, ALFWorld, and Finance-Agent, finding that revisiting subtasks can help recovery in ALFWorld but can also add substantial coordination and token cost. [10](./citations/10.md)

## Safety, governance, and groundedness

- **Discovering Agentic Safety Specifications from 1-Bit Danger Signals** — introduces EPO-Safe, where an LLM learns a natural-language safety specification from only binary danger warnings; on AI Safety Gridworlds and text analogs it reportedly finds safe behavior in 1–2 rounds, while reward-only reflection worsens safety by encouraging reward hacking. [5](./citations/5.md)
- **GSAR: Typed Grounding for Hallucination Detection and Recovery in Multi-Agent LLMs** — proposes a grounding/replanning loop that separates grounded, ungrounded, contradicted, and complementary evidence, then uses typed groundedness scores to decide whether to proceed, regenerate, or replan; the evaluation is on FEVER with gold Wikipedia evidence. [6](./citations/6.md)
- **Governing What You Cannot Observe: Adaptive Runtime Governance for Autonomous AI Agents** — presents an informational-viability framing for runtime governance, with monitoring, anticipation, and monotonic restriction as necessary and sufficient properties for the cited failure modes; the reference system RiskGate adds statistical estimators, a viability index, and a kill-switch-last-resort pipeline, but the abstract says quantitative evaluation is future work. [9](./citations/9.md)

## Evaluation, benchmarks, and interpretability infrastructure

- **Judging the Judges: A Systematic Evaluation of Bias Mitigation Strategies in LLM-as-a-Judge Pipelines** — compares nine debiasing strategies across five judge models and three benchmarks, concluding that style bias dominates position bias, truncation controls still indicate quality-sensitive judgments, and the combined budget strategy improves Claude Sonnet 4 by +11.2 pp. [4](./citations/4.md)
- **FormalScience: Scalable Human-in-the-Loop Autoformalisation of Science with Agentic Code Generation in Lean** — introduces a human-in-the-loop pipeline for autoformalising scientific reasoning, builds FormalPhysics with 200 physics problems and Lean4 proofs, and reports a systematic characterisation of semantic drift in physics autoformalisation; the abstract also notes an interactive UI and released codebase. [2](./citations/2.md)
- **Domain-Filtered Knowledge Graphs from Sparse Autoencoder Features** — turns large sparse-autoencoder feature inventories into filtered domain concepts plus co-occurrence and mechanism graphs; the biology textbook case study is used to show chapter/subchapter structure and compact readable views of model activity. [7](./citations/7.md)
- **XGRAG: A Graph-Native Framework for Explaining KG-based Retrieval-Augmented Generation** — introduces graph-based perturbation explanations for GraphRAG, reports a 14.81% improvement over RAG-Ex on NarrativeQA, FairyTaleQA, and TriviaQA, and says the explanations correlate with graph centrality. [8](./citations/8.md)
