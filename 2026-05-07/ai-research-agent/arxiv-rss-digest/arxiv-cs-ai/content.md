# arXiv cs.AI digest for 2026-05-07

## Context management and long-horizon agents

### LCM: Lossless Context Management
Lossless Context Management (LCM) is presented as a deterministic architecture for LLM memory that outperforms Claude Code on long-context tasks [1](./citations/1.md). The abstract says the LCM-augmented coding agent Volt, benchmarked with Opus 4.6, scores higher than Claude Code on OOLONG at every context length from 32K to 1M tokens [1](./citations/1.md).

The method decomposes symbolic recursion into two engine-managed pieces: recursive context compression and recursive task partitioning [1](./citations/1.md). The trade-off is explicit: reduced flexibility in exchange for termination guarantees, zero-cost continuity on short tasks, and lossless retrieval of prior state [1](./citations/1.md).

### When Context Hurts: The Crossover Effect of Knowledge Transfer on Multi-Agent Design Exploration
This paper challenges the assumption that more context is always better in agent orchestration [6](./citations/6.md). Across 10 tasks, 7 context-injection conditions, and more than 2,700 runs, the same artifact type can either improve design exploration up to 20× tradeoff coverage or reduce it by as much as 46% [6](./citations/6.md).

A key predictor is baseline exploration without context, which correlates strongly with whether context helps or hurts (Pearson r = -0.82, p < 0.001) [6](./citations/6.md). The abstract also distinguishes natural convergence driven by training-data priors from induced convergence driven by explicit instructions [6](./citations/6.md).

## Neuro-symbolic reasoning and structured representation

### ANDRE: An Attention-based Neuro-symbolic Differentiable Rule Extractor
ANDRE is a differentiable ILP framework for learning first-order logic programs in noisy and probabilistic settings [3](./citations/3.md). It replaces predefined rule templates and fuzzy logical operators with attention-driven conjunction and disjunction operators that approximate logical min-max semantics [3](./citations/3.md).

The paper claims competitive or superior performance on classical ILP benchmarks, large-scale knowledge bases, and synthetic datasets with probabilistic predicates and noisy supervision, while also recovering correct symbolic rules under uncertainty [3](./citations/3.md). It is described as robust to moderate label noise and substantially better than existing differentiable ILP methods in rule extraction quality and stability [3](./citations/3.md).

### Temporal Reasoning Is Not the Bottleneck: A Probabilistic Inconsistency Framework for Neuro-Symbolic QA
The abstract argues that the bottleneck in temporal QA is not temporal reasoning itself, but unstructured text-to-event representation [4](./citations/4.md). The proposed neuro-symbolic QA framework uses a Probabilistic Inconsistency Signal (PIS) to separate perceptual errors from reasoning failures, and it lifts text into event graphs plus interval constraints before symbolic reasoning [4](./citations/4.md).

Reported results include perfect 1.0 accuracy (4000/4000) and zero false positives/negatives on temporal arithmetic benchmarks when correct structural representations are provided [4](./citations/4.md). On broader noise-injected QA settings, the system maintains 75.1% accuracy and enables deterministic step-level failure localization [4](./citations/4.md).

## Multi-agent benchmarks, evaluation, and calibration

### Agent Island: A Saturation- and Contamination-Resistant Benchmark from Multiagent Games
Agent Island is a multiplayer environment where language-model agents compete through cooperation, conflict, and persuasion [5](./citations/5.md). The benchmark is designed to mitigate saturation and contamination by keeping the game dynamic and by pitting agents against other adaptive agents rather than a fixed task set [5](./citations/5.md).

The authors rank players with a Bayesian Plackett-Luce model and report results from 999 games involving 49 unique models, where openai/gpt-5.5 has the highest posterior mean skill at 5.64 [5](./citations/5.md). The release also includes game logs for behavioral analysis, including an observed same-provider voting preference of 8.3 percentage points [5](./citations/5.md).

### Deployment-Relevant Alignment Cannot Be Inferred from Model-Level Evaluation Alone
This paper argues that deployment-relevant alignment cannot be inferred from model-level scores alone and should be indexed to the level where evidence is collected: model, response, interaction, or deployment [7](./citations/7.md). The abstract frames common benchmark practice as insufficient for claims about deployed alignment [7](./citations/7.md).

A benchmark audit of eleven alignment benchmarks, extended to sixteen, finds that user-facing verification support is absent across all examined benchmarks and that process steerability is nearly absent [7](./citations/7.md). A blinded cross-model stress test further shows that the same verification scaffold can help one frontier model to ceiling while leaving another unchanged, making scaffold efficacy model-dependent [7](./citations/7.md).

### AuditRepairBench: A Paired-Execution Trace Corpus for Evaluator-Channel Ranking Instability in Agent Repair
AuditRepairBench targets leaderboard instability in agent repair caused by methods that consult evaluator-derived signal during candidate selection [8](./citations/8.md). The corpus contains 576,000 registered cells, 96,000 of them executed, and is framed around evaluator-channel-blocking ranking instability [8](./citations/8.md).

The abstract reports validation on an 80-case channel-surgery subset and says screening-guided blinding patches reduce rank displacement by 55--74% with fewer than 50 lines of code [8](./citations/8.md). A lighter AuditRepairBench-Lite configuration is described as preserving the leaderboard at Kendall τ = 0.88 under twenty-four GPU-hours [8](./citations/8.md).

## Safety, red-teaming, and deployment controls for agents

### AgentTrust: Runtime Safety Evaluation and Interception for AI Agent Tool Use
AgentTrust is a runtime safety layer that intercepts agent tool calls before execution and returns one of four verdicts: allow, warn, block, or review [9](./citations/9.md). It is aimed at unsafe side effects from file operations, shell commands, HTTP requests, and database queries [9](./citations/9.md).

The system combines shell deobfuscation normalization, SafeFix suggestions, RiskChain detection, and a cache-aware LLM-as-Judge for ambiguous inputs [9](./citations/9.md). The abstract reports 95.0% verdict accuracy on the internal benchmark and 96.7% on a 630-scenario benchmark under a patched ruleset, with about 93% accuracy on shell-obfuscated payloads [9](./citations/9.md).

### DecodingTrust-Agent Platform (DTap): A Controllable and Interactive Red-Teaming Platform for AI Agents
DTap is introduced as a controllable and interactive red-teaming platform for AI agents, spanning 14 real-world domains and more than 50 simulation environments [10](./citations/10.md). The abstract names Google Workspace, Paypal, and Slack as examples of replicated systems [10](./citations/10.md).

The paper also introduces DTap-Red, an autonomous red-teaming agent that explores prompt, tool, skill, environment, and combined injection vectors [10](./citations/10.md). Using it, the authors build DTap-Bench, a dataset with verifiable judges for attack outcomes, and say the platform reveals systematic vulnerability patterns across agents and policies [10](./citations/10.md).

## Surgical decision support

### Actionable Real-Time Modeling of Surgical Team Dynamics via Time-Expanded Interaction Graphs
This paper models surgical team dynamics with time-expanded interaction graphs, where team members are time-indexed nodes and communication exchanges become directed edges [2](./citations/2.md). The stated goal is to go beyond visual workflow signals and capture intraoperative team interactions over time [2](./citations/2.md).

The model predicts procedural efficiency as deviation from expected duration, is designed for real-time deployment, and supports counterfactual analysis over communication structure and behavioral variables [2](./citations/2.md). The abstract says experiments on recorded surgical procedures improve early identification of prolonged interventions and yield coherent, actionable explanations [2](./citations/2.md).
