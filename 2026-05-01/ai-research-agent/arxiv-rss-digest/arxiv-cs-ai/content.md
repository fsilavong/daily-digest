# arXiv cs.AI digest — 2026-05-01

## Production LLM operations and migration

- **When Your LLM Reaches End-of-Life: A Framework for Confident Model Migration in Production Systems** — production LLM migration framework using Bayesian calibration of automated metrics against human judgments; demonstrated on a commercial QA system with 5.3M monthly interactions across six regions, evaluating correctness, refusal behavior, and stylistic adherence to identify replacement models [1](./citations/1.md).

## Autonomous agents, orchestration, and verification

- **End-to-end autonomous scientific discovery on a real optical platform** — LLM-based agentic system for end-to-end discovery on a real optical platform; combines nonlinear research phases, Meta-Trace memory, and a dual-layer architecture, and claims autonomous reproduction of a transmission-matrix experiment plus experimental validation of an optical bilinear interaction in an open-ended study [2](./citations/2.md).
- **Think it, Run it: Autonomous ML pipeline generation via self-healing multi-agent AI** — five-agent system for end-to-end ML pipeline generation from datasets and NL goals, covering profiling, intent parsing, microservice recommendation, DAG construction, and execution; evaluated on 150 ML tasks and reports 84.7% pipeline success with self-healing and code-grounded RAG components [3](./citations/3.md).
- **TRUST: A Framework for Decentralized AI Service v.0.1** — decentralized verification framework for LRMs and MAS with HDAGs, DAAN causal attribution, and stake-weighted multi-tier consensus; reports 72.4% accuracy across LLMs and benchmarks, resilience against 20% corruption, and 60% token savings for DAAN [4](./citations/4.md).
- **Step-level Optimization for Efficient Computer-use Agents** — event-driven cascade for computer-use agents that runs a small policy by default and escalates only on detected risk; uses a Stuck Monitor and Milestone Monitor to reduce always-on frontier-model inference, but the abstract does not give benchmark numbers [5](./citations/5.md).
- **Reinforced Agent: Inference-Time Feedback for Tool-Calling Agents** — inserts a reviewer agent into the execution loop before tool calls, shifting from post-hoc evaluation to proactive mitigation; introduces Helpfulness-Harmfulness metrics and reports gains on BFCL and Tau2-Bench, including +5.5% irrelevance detection and +7.1% on multi-turn tasks [7](./citations/7.md).

## Search, extraction, and retrieval systems

- **Web2BigTable: A Bi-Level Multi-Agent LLM System for Internet-Scale Information Search and Extraction** — bi-level multi-agent web-to-table framework with an upper-level orchestrator, parallel worker agents, and a closed-loop run--verify--reflect process with persistent memory; sets new state of the art on WideSearch and generalises to XBench-DeepSearch [6](./citations/6.md).
- **NeocorRAG: Less Irrelevant Information, More Explicit Evidence, and More Effective Recall via Evidence Chains** — RAG framework focused on retrieval quality via Evidence Chains and a new Recall Conversion Rate metric; uses activated search and constrained decoding, and reports SOTA on HotpotQA, 2WikiMultiHopQA, MuSiQue, and NQ while consuming under 20% of comparable token budgets [10](./citations/10.md).

## Knowledge graphs, temporal knowledge, and biomedical graphs

- **OptimusKG: Unifying biomedical knowledge in a modern multimodal graph** — large biomedical labeled property graph spanning molecular, anatomical, clinical, and environmental domains; includes 190,531 nodes and 21.8M edges, with PaperQA3 supporting 70.0% of sampled edges and no evidence for 83.4% of sampled false edges [8](./citations/8.md).
- **Not All Memories Age the Same: Autodiscovery of Adaptive Decay in Knowledge Graphs** — replaces uniform temporal decay with a hierarchical decay surface driven by velocity and volatility, learned through survival analysis; validated on Wikipedia articles and Synthea patient records, and reports that uniform decay performs 18x worse than no temporal weighting [9](./citations/9.md).