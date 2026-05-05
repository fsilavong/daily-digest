# NVIDIA Generative AI Blog Digest

## Optimize Supply Chain Decision Systems Using NVIDIA cuOpt Agent Skills
- URL: https://developer.nvidia.com/blog/optimize-supply-chain-decision-systems-using-nvidia-cuopt-agent-skills/
- This post frames agentic AI as a way to let LLMs interpret supply-chain business questions in natural language, translate them into mathematical models, and solve them with GPU-accelerated optimization instead of weeks-long manual OR modeling. [1](./citations/1.md)
- The core mechanism is **agent skills**: an open format for extending agents with specialized knowledge and workflows. Here, cuOpt skills package optimization capabilities so the LLM can dynamically invoke production planning, inventory optimization, or route optimization functions with structured I/O schemas. [1](./citations/1.md)
- The referenced supply-chain workflow uses LangChain Deep Agents to spawn sub-agents; the orchestrator decomposes the request, while other sub-agents validate data, formulate the model, and call the cuOpt skill. [1](./citations/1.md)
- The post says cuOpt is GPU-accelerated and can solve LP, MIP, and routing problems orders of magnitude faster than CPU-based solvers. It also says the agent passes a structured payload containing decision variables, objective function, and constraints to the solver. [1](./citations/1.md)
- The supply-chain input data described includes demand forecasts, production capacity and unit costs, inventory holding costs and storage limits, transportation costs and lead times, plus business constraints such as SLAs or minimum production runs. The demo uses mock datasets, while production deployments would pull from planning systems. [1](./citations/1.md)
- The output is an actionable plan with optimized decision variables and summary metrics like total cost, capacity utilization, and constraint slack. The post presents the workflow as an extensible starting point for adding governance, reliability, and additional agent skills. [1](./citations/1.md)

## Notes on scope
- Only one unread item was returned from the latest source-page check, so the digest contains a single item section.
