# arXiv cs.AI digest — 2026-05-09

## Safety policy, governance, and authorization

### Understanding Annotator Safety Policy with Interpretability
- Annotator Policy Models (APMs) learn annotators' internal safety policies from labeling behavior alone, so annotator reasoning can be compared without extra annotation burden [1](./citations/1.md).
- The abstract frames disagreement as coming from operational failures, policy ambiguity, or value pluralism; the paper positions APMs as a way to distinguish those sources [1](./citations/1.md).
- Reported validation claims include >80% policy-model accuracy and faithful counterfactual prediction, with applications to surfacing policy ambiguity and demographic differences in safety priorities [1](./citations/1.md).

### Partial Evidence Bench: Benchmarking Authorization-Limited Evidence in Agentic Systems
- Partial Evidence Bench targets the failure mode where an agent can be correctly access-controlled yet still answer as if it has complete evidence [2](./citations/2.md).
- The benchmark includes due diligence, compliance audit, and security incident response tasks, with 72 tasks total plus ACL-partitioned corpora and oracle completeness annotations [2](./citations/2.md).
- Baselines suggest silent filtering is unsafe, while explicit fail-and-report behavior avoids unsafe completeness without making the task trivial [2](./citations/2.md).

### Authorization Propagation in Multi-Agent AI Systems: Identity Governance as Infrastructure
- The paper defines authorization propagation as a workflow-level property in multi-agent systems where non-human principals retrieve, delegate, and synthesize across changing boundaries [6](./citations/6.md).
- It argues the issue is distinct from prompt injection and not fully handled by RBAC, ABAC, or ReBAC [6](./citations/6.md).
- The abstract identifies transitive delegation, aggregation inference, and temporal validity as the three sub-problems, and argues identity governance should be treated as infrastructure [6](./citations/6.md).

### The Geopolitics of AI Safety: A Causal Analysis of Regional LLM Bias
- This study uses a probabilistic graphical model and Pearl's do-operator to isolate the causal effect of injecting a cultural demographic into a prompt [5](./citations/5.md).
- It compares seven instruction-tuned models from the US, Europe, UAE, China, and India on ToxiGen and BOLD [5](./citations/5.md).
- The abstract claims observational fairness metrics can overestimate demographic bias because they do not account for context toxicity, and that causal refusal rates differ across model origins [5](./citations/5.md).

## Agentic retrieval and reasoning systems

### Agentic Retrieval-Augmented Generation for Financial Document Question Answering
- FinAgent-RAG is an agentic RAG framework for financial QA over tables, narratives, and footnotes in corporate filings [3](./citations/3.md).
- Its three named components are a Contrastive Financial Retriever, a Program-of-Thought module that emits executable Python for arithmetic, and an Adaptive Strategy Router that allocates compute by question complexity [3](./citations/3.md).
- The paper reports 76.81% on FinQA, 78.46% on ConvFinQA, and 74.96% on TAT-QA, plus a 41.3% API cost reduction on FinQA [3](./citations/3.md).

### AgenticRAG: Agentic Retrieval for Enterprise Knowledge Bases
- AgenticRAG adds a lightweight harness over enterprise search so the LLM can search, find, open, and summarize iteratively instead of relying on a fixed retrieval candidate set [7](./citations/7.md).
- The abstract reports gains on BRIGHT, WixQA, and FinanceBench, including 49.6% recall@1 on BRIGHT and 92% answer correctness on FinanceBench [7](./citations/7.md).
- The main shift is from single-shot retrieval to agentic tool use; the abstract says that change accounts for the largest ablation gain [7](./citations/7.md).

### Text-Graph Synergy: A Bidirectional Verification and Completion Framework for RAG
- TGS-RAG combines Graph-to-Text verification with Text-to-Graph completion to address the abstract's "Information Island" problem between unstructured text and structured graphs [10](./citations/10.md).
- The abstract says Graph-to-Text uses Global Voting over visited graph nodes to re-rank textual evidence, while Text-to-Graph uses Memory-based Orphan Entity Bridging to resurrect previously pruned reasoning paths [10](./citations/10.md).
- The paper reports strong results on multiple multi-hop reasoning benchmarks, with a claimed balance between retrieval precision and computational efficiency [10](./citations/10.md).

## State compression and test-time control

### From History to State: Constant-Context Skill Learning for LLM Agents
- Constant-context skill learning moves recurring procedures into task-family modules so inference conditions only on the current observation and a compact state block [4](./citations/4.md).
- A deterministic tracker renders the state block from task progress and provides aligned subgoal rewards for step-level SFT and online RL [4](./citations/4.md).
- Reported results include 89.6% unseen success on ALFWorld, 76.8% success on WebShop, and 66.4% unseen success on SciWorld with Qwen3-8B, plus a 2--7× reduction in prompt tokens per turn versus controlled ReAct baselines [4](./citations/4.md).

### BitCal-TTS: Bit-Calibrated Test-Time Scaling for Quantized Reasoning Models
- BitCal-TTS addresses the mismatch between quantized inference and adaptive test-time compute allocation, focusing on greedy 4-bit reasoning models [9](./citations/9.md).
- The controller uses token-level uncertainty proxies, reasoning-trace stability, bit-conditioned confidence rescaling, and a bit-aware post-marker confirmation horizon for GSM8K-style outputs [9](./citations/9.md).
- On small GSM8K shards with Qwen2.5 Instruct models, the abstract reports modest accuracy gains and lower premature-stop rates at 7B and 14B scales, while explicitly noting limited statistical power [9](./citations/9.md).

## Self-play and scientific QA

### SPARK: Self-Play with Asymmetric Reward from Knowledge Graphs
- SPARK builds a unified knowledge graph from multi-document scientific literature and uses it to ground self-play question generation and reward computation [8](./citations/8.md).
- A single small vision-language model alternates between Proposer and Solver roles under information asymmetry against the fixed KG [8](./citations/8.md).
- The abstract claims SPARK outperforms flat-corpus self-play baselines, with larger gains as hop count increases [8](./citations/8.md).