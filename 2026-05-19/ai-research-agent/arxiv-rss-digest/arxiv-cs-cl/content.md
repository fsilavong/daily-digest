# arXiv cs.CL digest for 2026-05-19

## Multi-agent LLM workflow debugging and refinement

### PROTEA: Offline Evaluation and Iterative Refinement for Multi-Agent LLM Workflows
- PROTEA targets multi-agent LLM workflows, which the abstract describes as systems with multiple role-specific LLM calls that can outperform single-prompt baselines but are hard to debug because subtle intermediate errors propagate through downstream nodes [1](./citations/1.md).
- The system provides offline, test-driven improvement: it executes a workflow, scores intermediate node outputs with configurable rubrics, and overlays per-node states and rationales on the workflow graph to localize likely bottlenecks [1](./citations/1.md).
- For workflows where supervision mainly comes from final-answer references, PROTEA adds backward node evaluation by generating candidate node-level expectations from the final-answer references and graph context, then comparing them with observed node outputs [1](./citations/1.md).
- It also supports targeted prompt revision by showing editable before/after comparisons and then automatically rerunning and re-evaluating the workflow to expose output changes and score trajectories in the same interface [1](./citations/1.md).
- The abstract reports gains in two production-adjacent workflows: document-inspection accuracy improved from 64.3% to 83.9%, and recommendation Hit@5 improved from 0.30 to 0.38 [1](./citations/1.md).
- In a formative study with six experienced LLM developers, participants valued graph-level localization, per-node rationales, and editable before/after prompt revisions [1](./citations/1.md).