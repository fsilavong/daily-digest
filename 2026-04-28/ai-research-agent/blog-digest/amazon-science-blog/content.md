# Amazon Science Blog Digest

## How catastrophic is your LLM?
https://www.amazon.science/blog/how-catastrophic-is-your-llm

- The post introduces C3LLM, a framework for certifying catastrophic conversational risks in LLMs by modeling conversations as multiturn dialogues on a graph where nodes are prompts and edges encode semantic relationships between prompts [1](./citations/1.md).
- It says the framework shifts evaluation away from single-score red-teaming toward statistical certification of attack success rates across large conversation spaces [1](./citations/1.md).
- It defines several threat-model sampling regimes: Random Node with Jailbreak (RNwJ) for independently sampled prompts, Graph Path vanilla (GPv) for graph-following sequences, Graph Path harmful target constraint (GPh) for sequences whose final query comes from a harmful target set, and Adaptive with Rejection (AwR) for adaptive attacker steering [1](./citations/1.md).
- The framework labels model responses with a separate ChatGPT-based judging mechanism and then uses Clopper-Pearson confidence intervals to compute lower and upper bounds on attack success rates [1](./citations/1.md).
- In the study described, UIUC researchers applied C3LLM to frontier proprietary models including Claude-Sonnet-4 and Nova Premier, plus open-weights models; the post reports that catastrophic risks are nontrivial across the evaluated models and that Nova Premier and Claude-Sonnet-4 are safer than Mistral-Large and DeepSeek-R1 in those tests [1](./citations/1.md).
- The post highlights a cybercrime result where DeepSeek-R1 reaches a certified lower bound above 70% under RNwJ distributions, and notes Nova Premier’s low risk is largely attributed to built-in guardrails blocking potentially unsafe content [1](./citations/1.md).
- The authors say C3LLM is open sourced for reproducibility and to support more principled safety studies [1](./citations/1.md).
