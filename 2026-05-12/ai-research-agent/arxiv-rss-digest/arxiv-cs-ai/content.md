# arXiv cs.AI RSS Digest — 2026-05-12

## Reliability, calibration, and interpretability

### Where Reliability Lives in Vision-Language Models: A Mechanistic Study of Attention, Hidden States, and Causal Circuits
- The paper directly tests the idea that sharp attention maps indicate trustworthy vision-language model answers, and finds attention structure is a near-zero predictor of correctness across three open-weight VLM families: LLaVA-1.5, PaliGemma, and Qwen2-VL [1](./citations/1.md).
- The abstract says reliability becomes more legible later in the computation, with a single hidden-state linear probe reaching AUROC > 0.95 on POPE for two of the three families, and self-consistency at K=10 emerging as the strongest behavioral predictor it measures, albeit at 10x inference cost [1](./citations/1.md).
- Causal ablations expose a model-family split: late-fusion LLaVA concentrates reliability in a fragile late bottleneck, while early-fusion PaliGemma and Qwen2-VL distribute it more broadly and tolerate destruction of about half of the peak-layer hidden dimension with <= 1 pp degradation [1](./citations/1.md).
- The narrow takeaway is that, in 3–7B VLMs, reliability is read more reliably from hidden-state geometry, layer-wise margin formation, and sparse late-layer circuits than from attention-map sharpness [1](./citations/1.md).

### Consistency as a Testable Property: Statistical Methods to Evaluate AI Agent Reliability
- The paper proposes a measurement-science framework for AI agent reliability focused on consistency under semantically preserving perturbations, using U-statistics for output-level reliability and kernel-based metrics for trajectory-level stability [2](./citations/2.md).
- It emphasizes a distinction between an agent’s core capability and its execution robustness, arguing that small task-level variations can trigger complete strategy breakdowns even when the agent has the needed knowledge [2](./citations/2.md).
- Across three agentic benchmarks, trajectory-level consistency metrics are reported to be much more diagnostically sensitive than traditional pass@1 rates [2](./citations/2.md).

## Memory, tool use, and agent architecture

### MemQ: Integrating Q-Learning into Self-Evolving Memory Agents over Provenance DAGs
- MemQ targets episodic-memory agents that evaluate retrieval quality in isolation, arguing that this misses the dependency chains through which memories enable later memories [3](./citations/3.md).
- It applies TD($\lambda$) eligibility traces to memory Q-values and propagates credit backward through a provenance DAG that records which memories were retrieved when each new memory was created, with credit decaying as $(\gamma\lambda)^d$ by DAG depth [3](./citations/3.md).
- The abstract formalizes the setting as an Exogenous-Context MDP and reports the highest success rate on all six evaluated benchmarks in both generalization evaluation and runtime learning, with the largest gains on multi-step tasks that create deep provenance chains and the smallest on single-step classification [3](./citations/3.md).

### CoCoDA: Co-evolving Compositional DAG for Tool-Augmented Agents
- CoCoDA addresses the coupled problem of evolving a tool library and retrieving from it within a fixed context budget as the library grows [4](./citations/4.md).
- It represents tools as a compositional code DAG with typed signatures, descriptions, pre/post-conditions, and examples, and uses Typed DAG Retrieval to prune by symbolic signature unification, then rank, filter, and disambiguate candidates [4](./citations/4.md).
- At training time, successful trajectories are folded into validated composite tools and the planner is updated with a DAG-induced reward that credits composites by primitive expansion size [4](./citations/4.md).
- The abstract claims theoretical retrieval and co-evolution benefits and says an 8B student matches or exceeds a 32B teacher on GSM8K and MATH while improving over strong baselines across mathematical reasoning, tabular analysis, and code tasks [4](./citations/4.md).

### TIDE-Bench: Task-Aware and Diagnostic Evaluation of Tool-Integrated Reasoning
- TIDE-Bench is presented as a unified benchmark for tool-integrated reasoning that addresses dataset quality, task diversity, diagnostics, and evaluation efficiency [9](./citations/9.md).
- It combines standard math and knowledge QA with two new tasks: a tool-grounded experimental design task and a dynamic interactive task [9](./citations/9.md).
- The evaluation protocol jointly measures final answer quality, process reliability, tool-use efficiency, and inference cost, and the benchmark filters low-discrimination instances to reduce evaluation cost [9](./citations/9.md).
- The abstract says experiments on multiple foundation models and TIR methods reveal persistent bottlenecks in tool grounding [9](./citations/9.md).

### Consistency as a Testable Property: Statistical Methods to Evaluate AI Agent Reliability
- In addition to reliability metrics, the paper frames consistency as a testable property of agent trajectories under perturbations, giving a statistical lens on where agents diverge [2](./citations/2.md).

## In-context learning and circuit-level mechanism studies

### Belief or Circuitry? Causal Evidence for In-Context Graph Learning
- The paper studies in-context learning on a toy graph random-walk task with two competing graph structures to test whether models copy local transitions or infer latent structure [5](./citations/5.md).
- PCA reconstruction suggests that at intermediate mixture ratios both graph topologies are encoded simultaneously in orthogonal principal subspaces, which the authors say is hard to reconcile with purely local transition copying [5](./citations/5.md).
- Residual-stream activation patching and graph-difference steering are used as causal interventions: late-layer patching almost fully transfers the clean graph preference, and linear steering moves predictions in the intended direction but fails under norm-matched and label-shuffled controls [5](./citations/5.md).
- The abstract’s interpretation is a dual-mechanism account in which structure inference and induction circuits operate in parallel [5](./citations/5.md).

## Safety, grounding, and evaluation of agents in environment-facing settings

### The Attacker in the Mirror: Breaking Self-Consistency in Safety via Anchored Bipolicy Self-Play
- The paper argues that standard self-play red teaming can converge to behaviors that include trivial always-refuse strategies and oracle-like defenders, limiting practical applicability [6](./citations/6.md).
- It claims that when attacker and defender share and update the same base model, the dynamics collapse to self-consistency, meaning attacks do not exert adversarial pressure on the defender [6](./citations/6.md).
- Anchored Bipolicy Self-Play uses distinct role-specific LoRA adapters on top of a frozen base model to preserve stable optimization while keeping attacker and defender separated [6](./citations/6.md).
- The abstract reports up to 100x greater parameter efficiency than finetuning and improved safety on Qwen2.5-{3B, 7B,14B}-IT models without loss of reasoning ability [6](./citations/6.md).

### When Agents Overtrust Environmental Evidence: An Extensible Agentic Framework for Benchmarking Evidence-Grounding Defects in LLM Agents
- EnvTrustBench targets a failure mode the authors call an evidence-grounding defect, where an agent treats an environment-facing claim as sufficient evidence for action without reconciling it against current evidence [7](./citations/7.md).
- The framework generates the workspace, objective, and validation oracle, executes the agent, records the action-observation trajectory and final state, and then applies the oracle to decide whether the run followed a false path under the true environment state [7](./citations/7.md).
- The abstract reports evaluation across 6 LLM backbones, 5 scaffolds, 55 generated cases, and 11 task scenarios expanded through five feedback-guided generation iterations [7](./citations/7.md).
- Its main takeaway is that EGDs consistently emerge across operational workflows, making environmental grounding a core reliability and security problem [7](./citations/7.md).

## Neuro-symbolic reasoning over structured knowledge

### LLM-Guided Monte Carlo Tree Search over Knowledge Graphs: Composing Mechanistic Explanations for Drug-Disease Pairs
- TESSERA tackles multi-step explanation extraction from knowledge graphs, where candidate paths proliferate with depth and credit assignment becomes difficult [8](./citations/8.md).
- The framework uses LLMs only for local discriminative judgment, while the knowledge graph constrains the hypothesis space and Monte Carlo Tree Search handles long-horizon search with backpropagated credit [8](./citations/8.md).
- The abstract says the LLM plays two roles: a prior policy for exploration and a comparative state evaluator for reward signals [8](./citations/8.md).
- Evaluation on drug mechanism elucidation across two knowledge graphs reportedly shows fidelity to curated biology while also surfacing coherent alternative mechanisms [8](./citations/8.md).
