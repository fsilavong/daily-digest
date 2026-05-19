# arXiv cs.AI digest for 2026-05-19

## Agentic reasoning, self-improvement, and research workflows

- **ICRL: Learning to Internalize Self-Critique with Reinforcement Learning** — proposes jointly training a solver and critic from a shared backbone so critique-induced success becomes unassisted solver ability, rather than disappearing when critique is removed. On agentic and mathematical reasoning tasks with Qwen3-4B and Qwen3-8B, it reports average gains of 6.4 points over GRPO on agentic tasks and 7.0 points on mathematical reasoning; the learned 8B critic is reported as comparable to 32B critics while using fewer tokens [1](./citations/1.md).

- **Argus: Evidence Assembly for Scalable Deep Research Agents** — treats deep research as assembling complementary evidence pieces instead of pushing one long trajectory or duplicating parallel rollouts. A Searcher gathers evidence traces while a Navigator maintains a shared evidence graph, dispatches missing work, and synthesizes source-traced answers; with a 35B-A3B MoE backbone it reports gains of 5.5 points with one Searcher and 12.7 points with 8 parallel Searchers, and 86.2 on BrowseComp with 64 Searchers [5](./citations/5.md).

## Coding agents and benchmark design

- **Context Pruning for Coding Agents via Multi-Rubric Latent Reasoning** — argues that single-score learned pruning collapses distinct kinds of code relevance. LaMR splits relevance into semantic evidence and dependency support, uses dedicated CRFs plus a mixture-of-experts gate, and derives supervision from AST-based program analysis; on SWE-Bench Verified, SWE-QA, LCC, and LongCodeQA it wins 12 of 16 head-to-head multi-turn comparisons, saves up to 31% more tokens, and improves Exact Match by up to +3.5 [2](./citations/2.md).

- **PBT-Bench: Benchmarking AI Agents on Property-Based Testing** — introduces a benchmark meant to isolate property-based testing skill: infer a semantic invariant from documentation, then build a Hypothesis strategy that makes random search hit the bug. The benchmark contains 100 curated problems across 40 real Python libraries, with 365 semantic bugs total; across eight LLMs, PBT-guided prompting raises bug recall to 42.1%–83.4% versus 31.4%–76.7% for open-ended prompting, though the scaffold can hurt some strong models [4](./citations/4.md).

## Multi-agent routing and structured control

- **STAR: Failure-Aware Markovian Routing for Multi-Agent Spatiotemporal Reasoning** — externalizes specialist routing as a state-conditioned transition policy over agent, task type, and typed execution status. The paper emphasizes distinct failure modes such as malformed outputs, missing dependencies, and tool-query mismatches, and reports improvements across three spatiotemporal benchmarks and eight backbones, especially when execution deviates from the nominal path [6](./citations/6.md).

## Root cause analysis and observability

- **TopoEvo: A Topology-Aware Self-Evolving Multi-Agent Framework for Root Cause Analysis in Microservices** — targets microservice RCA under noisy multimodal observability, cascading failures, and topology drift from autoscaling or rolling updates. It combines multimodal alignment, vector quantization into auditable symptom tokens, hypothesis-evidence-test reasoning, and a self-evolving memory/adaptation mechanism to maintain robustness under drift [3](./citations/3.md).

## Retrieval, grounding, and verification

- **Does RAG Know When Retrieval Is Wrong? Diagnosing Context Compliance under Knowledge Conflict** — studies the context-compliance regime in RAG, where retrieved context overrides parametric knowledge even when it conflicts. It introduces Context-Driven Decomposition as an inference-time belief-decomposition probe and intervention, and reports adversarial gains and robustness patterns on Epi-Scale, TruthfulQA misconception injection, and cross-model reruns [8](./citations/8.md).

- **Falkor-IRAC: Graph-Constrained Generation for Verified Legal Reasoning in Indian Judicial AI** — argues that legal reasoning needs constrained symbolic structure rather than similarity search. The system grounds generation in an IRAC knowledge graph, validates answers through a Verifier Agent, flags doctrinal conflicts explicitly, and reports proof-of-concept validation on 51 Supreme Court judgments while leaving vector-only RAG comparisons for future work [7](./citations/7.md).