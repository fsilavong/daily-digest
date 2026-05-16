# arXiv cs.AI Digest — 2026-05-16

Grouped source notes from unread RSS entries published on 2026-05-16. Each item below is grounded only in the RSS title and abstract.

## Agent orchestration, tool use, and workflow execution

### GraphBit: A Graph-based Agentic Framework for Non-Linear Agent Orchestration
- GraphBit targets the failure modes of prompted orchestration, namely hallucinated routing, infinite loops, and non-reproducible execution [1](./citations/1.md).
- It replaces prompted control with an engine-orchestrated directed acyclic graph, where agents are typed functions and a Rust-based engine governs routing, state transitions, and tool invocation [1](./citations/1.md).
- The framework adds parallel branch execution, conditional control flow over structured state predicates, configurable error recovery, and a three-tier memory design spanning ephemeral scratch space, structured state, and external connectors [1](./citations/1.md).
- On GAIA benchmark tasks spanning zero-tool, document-augmented, and web-enabled workflows, the abstract claims the highest accuracy at 67.6%, zero framework-induced hallucinations, the lowest latency overhead at 11.9 ms, and the highest throughput among six compared frameworks [1](./citations/1.md).
- Ablations reportedly show that each memory tier helps, with deterministic execution giving the largest gains on tool-intensive tasks [1](./citations/1.md).

### Model-Adaptive Tool Necessity Reveals the Knowing-Doing Gap in LLM Tool Use
- The paper argues that tool necessity should be defined relative to each model's empirical capability boundary, not as a model-agnostic property [2](./citations/2.md).
- Across four models on arithmetic and factual QA datasets, the abstract reports substantial mismatches between tool necessity and observed tool-call behavior, with mismatch rates of 26.5-54.0% and 30.8-41.8% [2](./citations/2.md).
- The authors decompose tool use into an internal cognition stage and an execution stage, then probe hidden states to study how necessity judgments become action [2](./citations/2.md).
- They report that both signals are often linearly decodable, but their probe directions become nearly orthogonal in the late-layer, last-token regime that drives next-token action, and that most mismatch concentrates in the cognition-to-action transition [2](./citations/2.md).
- The abstract frames this as a knowing-doing gap in LLM tool use [2](./citations/2.md).

### Good to Go: The LOOP Skill Engine That Hits 99% Success and Slashes Token Usage by 99% via One-Shot Recording and Deterministic Replay
- LOOP targets repetitive periodic agent tasks, where stochastic LLM behavior and repeated invocations make reliability and token cost difficult to control [3](./citations/3.md).
- The system records a first full LLM run, extracts a parameterized branch-free Loop Skill from the trajectory, and then deterministically replays later executions without calling the LLM [3](./citations/3.md).
- The abstract claims a combined 99% success rate and 99% token reduction, plus monthly token consumption reductions of 93.3%-99.98% and an 8.7x latency cut across periodic tasks from 5 minutes to 24 hours [3](./citations/3.md).
- It also claims proofs of replay determinism and write safety, and says the engine includes a multi-layer degradation strategy so tasks do not stall [3](./citations/3.md).
- The release is described as part of the buddyMe open-source agent framework [3](./citations/3.md).

### AgentTrap: Measuring Runtime Trust Failures in Third-Party Agent Skills
- AgentTrap studies third-party skills as a package ecosystem for LLM agents and treats malicious runtime behavior inside skills as a distinct security problem [4](./citations/4.md).
- The benchmark has 141 tasks, split into 91 malicious and 50 benign utility tasks, and covers 16 security-impact dimensions tied to agent-skill supply-chain threats [4](./citations/4.md).
- In the benchmark setup, the agent receives an ordinary user request, runs with installed skills that may embed malicious workflow elements, and is evaluated in a sandbox on full trajectories [4](./citations/4.md).
- The main finding is that models often finish the visible user task while also executing unsafe side effects hidden in the skill workflow, which the abstract presents as a runtime trust failure rather than a simple jailbreak [4](./citations/4.md).

## Long-horizon memory, grounding, and retrieval

### Grounded Continuation: A Linear-Time Runtime Verifier for LLM Conversations
- This paper addresses conversations where an utterance sounds plausible but depends on premises the dialogue has already abandoned, and it frames this as a context-manipulation attack surface [5](./citations/5.md).
- The verifier maintains an explicit dependency graph: an LLM classifies each turn into one of eight update operations drawn from four formalisms, and a symbolic engine tracks which claims depend on which evidence [5](./citations/5.md).
- Support checking reduces to graph traversal, while retraction propagates through the graph to identify exactly which conclusions lose support; the abstract emphasizes linear per-turn cost and a formal conflict-free guarantee [5](./citations/5.md).
- On LongMemEval-KU oracle (n=78), the verifier reaches 89.7% accuracy, slightly above an LLM-only baseline and a transcript-RAG baseline matched on retrieval budget; on LoCoMo's 60 official QA items it is described as competitive with retrieval-augmented baselines [5](./citations/5.md).
- The abstract also reports a 15-item stale-premise subset where the verifier reaches 100% accuracy, plus microsecond-level retraction checks [5](./citations/5.md).

### EvolveMem:Self-Evolving Memory Architecture via AutoResearch for LLM Agents
- EvolveMem argues that long-term memory systems are frozen at deployment even though stored content changes, so the retrieval mechanism should co-evolve with the memory itself [6](./citations/6.md).
- It exposes the full retrieval configuration as a structured action space optimized by an LLM-powered diagnosis module that reads failure logs, proposes configuration changes, and uses guarded revert-on-regression and explore-on-stagnation safeguards [6](./citations/6.md).
- The abstract describes this as an AutoResearch process in which the system iteratively researches its own architecture and discovers effective retrieval strategies, including new configuration dimensions not in the original action space [6](./citations/6.md).
- Reported gains include 25.7% relative improvement over the strongest baseline on LoCoMo, 18.9% relative improvement over the strongest baseline on MemBench, and 78.0% relative improvement over the minimal baseline on LoCoMo [6](./citations/6.md).
- The abstract says the evolved configurations transfer positively across benchmarks rather than catastrophically [6](./citations/6.md).

### COREKG: Coreset-Guided Personalized Summarization of Knowledge Graphs
- COREKG addresses large knowledge graphs that are unwieldy for question answering and visualization, and it emphasizes personalized summaries based on user query patterns [7](./citations/7.md).
- The method adapts coreset theory and uses sensitivity-based importance sampling to select a subset of triples that approximates the full graph with bounded approximation error [7](./citations/7.md).
- The abstract says the summaries are constructed independently for each user according to query behavior, with the goal of smaller storage and runtime [7](./citations/7.md).
- Evaluation on Freebase, WikiData, and DBpedia is reported to beat GLIMPSE, PPR, iSummary, PEGASUS, and APEX^2 on query-answering accuracy and structural coverage while using only a tiny fraction of the original graph [7](./citations/7.md).

## Benchmarks for discovery, robustness, and evaluation under state shift

### PolitNuggets: Benchmarking Agentic Discovery of Long-Tail Political Facts
- PolitNuggets targets the under-evaluated problem of agentic discovery and synthesis of long-tail facts from dispersed sources [8](./citations/8.md).
- It is a multilingual benchmark built from political biographies for 400 global elites and covers more than 10,000 political facts [8](./citations/8.md).
- The authors standardize evaluation with an optimized multi-agent system and introduce FactNet, an evidence-conditional protocol that scores discovery, fine-grained accuracy, and efficiency [8](./citations/8.md).
- The abstract says current systems often struggle with fine-grained details and vary substantially in efficiency, and it highlights short-context extraction, multilingual robustness, and reliable tool use as important capabilities [8](./citations/8.md).

### ClawForge: Generating Executable Interactive Benchmarks for Command-Line Agents
- ClawForge addresses the gap between scalable benchmark construction and realistic workflow evaluation for interactive command-line agents [9](./citations/9.md).
- The framework compiles scenario templates, grounded slots, initialized state, reference trajectories, and validators into reproducible task specifications, and it evaluates agents over persistent workflow surfaces using normalized end state and observable side effects instead of exact trajectory matching [9](./citations/9.md).
- The instantiated ClawForge-Bench contains 17 scenarios across 6 ability categories [9](./citations/9.md).
- Across seven frontier models, the abstract reports that the best model reaches only 45.3% strict accuracy, wrong-state replacement stays below 17% for all models, and performance differs sharply depending on whether the agent inspects existing state before acting [9](./citations/9.md).
- The authors say many failures are near-miss closures rather than early breakdowns, and that models exhibit different failure styles under state conflict [9](./citations/9.md).

### GAMBIT: A Three-Mode Benchmark for Adversarial Robustness in Multi-Agent LLM Collectives
- GAMBIT studies adaptive adversaries in multi-agent systems, where a single deceptive agent can nullify collective gains and evade deployed defenses [10](./citations/10.md).
- The benchmark has three evaluation modes and two independent scores for imposter detectors, with the first two modes testing zero-shot detection under distribution shift and a third recalibration mode testing adaptation from just 20 labeled examples [10](./citations/10.md).
- The release includes 27,804 labeled instances spanning 240 co-evolved imposter strategies, built around chess as the reasoning substrate and Gemini 3.1 Pro for agents [10](./citations/10.md).
- The abstract claims an adaptive imposter that collapses task performance while staying nearly undetectable, and says zero-shot evaluation can be misleading because detectors with similar zero-shot scores differ by 8x on few-shot adaptation while the meta-learned variant converges 20x faster [10](./citations/10.md).
