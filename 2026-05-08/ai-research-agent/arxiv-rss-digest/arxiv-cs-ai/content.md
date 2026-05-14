# arXiv cs.AI Digest — 2026-05-08

## Inference, memory, and agent orchestration

### Parallel Prefix Verification for Speculative Generation
- PARSE proposes parallel prefix verification for speculative generation, aiming to move beyond token-level equivalence by verifying semantic-level prefixes in a single forward pass with a custom attention mask.[1](./citations/1.md)
- The abstract frames the key limitation of prior semantic/segment-level approaches as sequential verification overhead, and says PARSE directly identifies the maximal valid prefix without sequential checks.[1](./citations/1.md)
- Claimed gains are throughput improvements of 1.25× to 4.3× over the target model, or 1.6× to 4.5× when composed with EAGLE-3, with negligible accuracy degradation.[1](./citations/1.md)

### LongSeeker: Elastic Context Orchestration for Long-Horizon Search Agents
- LongSeeker is built around Context-ReAct, an agentic paradigm for elastic context orchestration that integrates reasoning, context management, and tool use in one loop.[2](./citations/2.md)
- The framework defines five operations — Skip, Compress, Rollback, Snippet, and Delete — to reshape working context as evidence becomes relevant, resolved, or unhelpful.[2](./citations/2.md)
- The abstract claims Compress is expressively complete, while the other operators offer efficiency and fidelity guarantees that reduce generation cost and hallucination risk.[2](./citations/2.md)
- On BrowseComp and BrowseComp-ZH, the abstract reports 61.5% and 62.5%, outperforming Tongyi DeepResearch and AgentFold on those benchmarks.[2](./citations/2.md)

### Storage Is Not Memory: A Retrieval-Centered Architecture for Agent Recall
- True Memory argues that extraction at ingestion is the wrong primitive for agent memory because discarded content cannot be recovered later, and instead centers a multi-stage retrieval pipeline over verbatim events.[3](./citations/3.md)
- The full system is described as a six-layer architecture running as a single SQLite file on commodity CPU, without an external database, vector index, graph store, or GPU.[3](./citations/3.md)
- Reported results include 93.0% on LoCoMo, 87.8% on LongMemEval, and 76.6% on BEAM-1M for True Memory Pro, with comparisons against several named baselines in the abstract.[3](./citations/3.md)
- The abstract also reports a 56-configuration ablation with a 1.3-point spread within the top-performing family.[3](./citations/3.md)

### Uno-Orchestra: Parsimonious Agent Routing via Selective Delegation
- Uno-Orchestra is a unified orchestration policy that jointly learns whether to decompose a task and which admissible model/primitive pair to dispatch to each subtask.[4](./citations/4.md)
- The abstract says the policy is trained from curated RL trajectories grounded in real worker interactions, rather than hand-engineered routing alone.[4](./citations/4.md)
- On a 13-benchmark suite spanning math, code, knowledge, long-context, and agentic tool use, the paper claims 77.0% macro pass@1, about 16% above the strongest workflow baseline, at roughly an order of magnitude lower per-query cost.[4](./citations/4.md)

## Safety, alignment, and robustness

### From Parameter Dynamics to Risk Scoring : Quantifying Sample-Level Safety Degradation in LLM Fine-tuning
- This paper argues that benign fine-tuning can cause parameters to drift toward danger-aligned directions, progressively eroding safety behaviors learned from preference examples.[5](./citations/5.md)
- Based on that mechanism, it proposes SQSD, a sample-level method that assigns continuous risk scores by measuring the projection difference of induced parameter updates between danger and safety directions.[5](./citations/5.md)
- The abstract claims the method works across multiple models and datasets and transfers across architectures, parameter scales, and parameter-efficient fine-tuning methods.[5](./citations/5.md)

### Efficiently Aligning Language Models with Online Natural Language Feedback
- The paper studies alignment in fuzzy domains where experts can provide high-quality feedback only for a small number of model outputs, using online natural language feedback.[6](./citations/6.md)
- The method iteratively optimizes proxy reward signals, stops at over-optimization, gathers fresh expert supervision, and updates the proxy reward; proxy models are built from LMs using in-context learning and fine-tuning.[6](./citations/6.md)
- The abstract reports data-efficiency gains on Qwen3-8B and Haiku 4.5, including recovery of up to 35% performance with 50x fewer expert samples via ICL for Qwen3-8B and 100% with 3x fewer samples via fine-tuning, plus similar gains for Haiku 4.5.[6](./citations/6.md)

### SoK: Robustness in Large Language Models against Jailbreak Attacks
- This SoK presents a taxonomy of jailbreak attacks and defenses and introduces Security Cube, a unified multi-dimensional evaluation framework.[7](./citations/7.md)
- The abstract says the authors benchmark 13 representative attacks and 5 defenses, and that narrow metrics such as attack success rate are inadequate for the multidimensional nature of LLM security.[7](./citations/7.md)
- The stated output is a literature comparison plus open challenges and research directions for stronger, more interpretable jailbreak robustness.[7](./citations/7.md)

### Pen-Strategist: A Reasoning Framework for Penetration Testing Strategy Formation and Analysis
- Pen-Strategist targets the strategy-formulation and tool-selection weaknesses of existing LLM-based pentesting agents.[8](./citations/8.md)
- The framework includes a domain-specific reasoning model for deriving pentesting strategies and a classifier that converts strategies into actionable steps; the abstract says the reasoning model is fine-tuned with reinforcement learning on a reasoning dataset with logical explanations.[8](./citations/8.md)
- Reported gains include an 87% improvement in strategy derivation over the baseline, a 47.5% improvement in subtask completion when integrated into PentestGPT, and an 18% gain on CTFKnow.[8](./citations/8.md)
- For step prediction, the abstract claims a semantic-based CNN outperforms commercial LLMs by 28% and improves execution stability.[8](./citations/8.md)

## Dialogue and structured prediction

### GEM: Graph-Enhanced Mixture-of-Experts with ReAct Agents for Dialogue State Tracking
- GEM combines a graph neural network, a finetuned T5-Small encoder-decoder, and ReAct agents under an intelligent router for dialogue state tracking.[9](./citations/9.md)
- The abstract frames the motivation as LLMs struggling with precise structured extraction in multi-domain conversations.[9](./citations/9.md)
- On MultiWOZ 2.2, the paper claims 65.19% Joint Goal Accuracy, above the cited end-to-end LLM baseline and several SOTA methods named in the abstract.[9](./citations/9.md)
