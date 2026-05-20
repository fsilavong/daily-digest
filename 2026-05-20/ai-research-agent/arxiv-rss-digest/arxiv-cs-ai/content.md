# arXiv cs.AI Digest — 2026-05-20

## Agentic systems, orchestration, and delegation

### AgentNLQ: A General-Purpose Agent for Natural Language to SQL
- Proposes a multi-agent NL2SQL method for converting natural language to SQL, aimed at closing the gap between current LLMs and human SQL writers [1](./citations/1.md).
- The method uses a semantically enriched schema representation and incorporates user-provided business rules to improve query generation [1](./citations/1.md).
- The abstract claims 78.1% semantic accuracy on the BIRD benchmark and says the approach generalizes across domains and datasets, including BIRD-SQL [1](./citations/1.md).

### DecisionBench: A Benchmark for Emergent Delegation in Long-Horizon Agentic Workflows
- Introduces DecisionBench, a benchmark substrate for emergent delegation in long-horizon workflows, with tasks from GAIA, tau-bench, and BFCL multi-turn [2](./citations/2.md).
- The substrate includes 11 peer models across 7 vendor families, a `call_model` delegation interface, an optional `read_profile` channel, and metrics for quality, cost, latency, delegation rate, routing fidelity, vendor self-preference, and counterfactual delegation ceiling [2](./citations/2.md).
- In a sweep over 23,375 task instances, the abstract says quality stays statistically similar across awareness conditions, while routing fidelity-at-1 varies widely and a counterfactual ceiling suggests 15–31 percentage points of headroom [2](./citations/2.md).

### ContextFlow: Hierarchical Task-State Alignment for Long-Horizon Embodied Agents
- Frames long-horizon embodied agent failure as task-state misalignment, where planning, monitoring, memory, and execution no longer support the same next-step decision [3](./citations/3.md).
- ContextFlow represents stages as explicit contracts, turns runtime observations into evidence packets, and applies scoped updates such as continue, refine, transfer, promote, and repair [3](./citations/3.md).
- The abstract describes experiments and demonstration traces showing how the framework diagnoses and mitigates recurring task-state failures, but gives no numeric results [3](./citations/3.md).

## Retrieval, grounding, and personalized context selection

### Embedding by Elicitation: Dynamic Representations for Bayesian Optimization of System Prompts
- Studies aggregate-feedback optimization of system prompts when only scalar scores are available, not per-example labels or critiques [4](./citations/4.md).
- ReElicit uses an LLM to elicit a compact feature space from task descriptions, past prompts, and scores, then applies a Gaussian-process surrogate and acquisition function to select target feature vectors [4](./citations/4.md).
- The abstract says re-eliciting the feature space as evaluations arrive makes the representation adapt over time, and that the method performs best among representative aggregate-only baselines on ten prompt-optimization tasks with a 30-evaluation budget [4](./citations/4.md).

### Query-Conditioned Graph Retrieval for Contextualized LLM Reasoning in Personalized Wearable Data
- Proposes Wearable As Graph (WAG), a graph-based retrieval framework for query-adaptive reasoning over long-term, multimodal wearable data [5](./citations/5.md).
- WAG builds a personalized knowledge graph, retrieves a query-conditioned subgraph, and combines global relationships from hierarchical Bayesian modeling with local short-term deviations; a query openness signal controls retrieval breadth [5](./citations/5.md).
- The abstract reports evaluation on more than 10,000 data-grounded queries from real-world wearable datasets and an approximately 70% win rate over baseline and standard RAG methods [5](./citations/5.md).

### STAR: Semantic-Tuned and Tail-Adaptive Retriever for Graph-Augmented Generation
- Targets GraphRAG retrieval for multi-hop QA, arguing that sparse semantic information causes Semantic Shortcut Bias and Long-Tail Path Bias in existing retrievers [6](./citations/6.md).
- STAR combines token-level interaction learning with path-weighted contrastive learning, using cross-attention, hard path mining, and tail-adaptive path weighting [6](./citations/6.md).
- The abstract claims average retrieval gains of 1.8% and LLM QA improvements of 2.2% across benchmark datasets [6](./citations/6.md).

### ClusterRAG: Cluster-Based Collaborative Filtering for Personalized Retrieval-Augmented Generation
- Presents ClusterRAG for personalized RAG, motivated by high retrieval cost and the benefit of collaborative signals from similar users [7](./citations/7.md).
- The method clusters users by profile documents, then retrieves at both cluster and document levels using cluster similarity and fine-grained ranking [7](./citations/7.md).
- On the LaMP benchmark, the abstract says using both the target user’s profile and top similar users’ profiles gives the best performance across tasks and works with different retrievers, rankers, and language models [7](./citations/7.md).

## Privacy, safety, and robust action control

### POLAR-Bench: A Diagnostic Benchmark for Privacy-Utility Trade-offs in LLM Agents
- Introduces POLAR-Bench, a policy-aware adversarial benchmark where a trusted model with a privacy policy converses with a third-party model that probes for task-relevant and protected attributes [8](./citations/8.md).
- The benchmark spans 10 domains and 7,852 samples and measures privacy and utility under varying policy dimensions and attack strategies [8](./citations/8.md).
- The abstract reports that frontier models withhold over 99% of protected attributes, while smaller open-weight 1–30B models perform much worse, with the weakest leaking over half [8](./citations/8.md).

### Hallucination as Exploit: Evidence-Carrying Multimodal Agents
- Treats hallucination in multimodal agents as an authorization failure when a false visual claim causes a privileged action to appear permitted [9](./citations/9.md).
- ECA decomposes each tool call into action-critical predicates, obtains typed certificates from constrained DOM/OCR/AX verifiers, and uses a deterministic gate to authorize only supported privileges [9](./citations/9.md).
- The abstract reports that targeted hardening reduces gate bypass from 15% to 1.3%, and that ECA achieves 0% unsafe-action rate on a 200-task end-to-end pipeline and a 120-task browser proof-of-concept [9](./citations/9.md).
- It also says naive agents and prompt-only defenses remain vulnerable under the HACR audit, while oracle-certificate replay and neural judge baselines are used as sanity checks [9](./citations/9.md).

## Hallucination benchmarking and evaluation

### HalluWorld: A Controlled Benchmark for Hallucination via Reference World Models
- Introduces HalluWorld, a benchmark based on an explicit reference-world formulation where a claim is hallucinated if it is false with respect to the world [10](./citations/10.md).
- The benchmark uses synthetic and semi-synthetic environments where the reference world is fully specified, the model view is controlled, and labels are generated automatically [10](./citations/10.md).
- HalluWorld spans gridworlds, chess, and terminal tasks, and the abstract reports that frontier models are near-solved on direct perceptual hallucination but still struggle with multi-step state tracking, causal forward simulation, and abstention in terminal settings [10](./citations/10.md).
- The abstract argues these failures point to distinct hallucination modes rather than a single capability gap [10](./citations/10.md).
