# Anthropic Alignment Digest

## Teaching Claude Why
- Source: https://alignment.anthropic.com/2026/teaching-claude-why/
- Retrieved: full text was available, but the captured text was truncated; notes below are grounded only in the visible excerpt.
- The post argues that alignment training should teach the *principles* behind aligned behavior, not just imitate aligned answers, because this can generalize better than narrow demonstration-based supervision [1](./citations/1.md).
- It describes experiments on agentic misalignment interventions, including training on user-advice conversations about ethical dilemmas, training on LLM-generated documents about Claude’s constitution and fictional admirable AI behavior, and augmenting harmlessness RL environments with tool definitions and more varied system prompts [1](./citations/1.md).
- The ethical-dilemma advice dataset reportedly reduced measured agentic misalignment to zero, while constitution/story documents improved alignment and those gains persisted through later RL post-training [1](./citations/1.md).
- The tool-augmented harmlessness environments also substantially reduced agentic misalignment, suggesting that broader environment design can matter as much as the direct labels [1](./citations/1.md).
- A key caveat is that training directly on the eval distribution can optimize the metric without improving out-of-distribution behavior, and may make future auditing less informative [1](./citations/1.md).
- The post also says demonstrations alone were often insufficient and that data quality and diversity mattered a lot for the observed gains [1](./citations/1.md).
- Why it may matter: this is presented as a practical case study for scalable alignment training in frontier models with tool use and complex agentic behavior, with the implication that principled, value-level supervision may generalize better than eval-targeted fixes [1](./citations/1.md).
