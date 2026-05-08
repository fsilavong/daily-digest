# Anthropic Research Digest

## Natural Language Autoencoders: Turning Claude’s thoughts into text
Original URL: https://www.anthropic.com/research/natural-language-autoencoders

- Anthropic presents Natural Language Autoencoders (NLAs) as a way to turn model activations into readable natural-language explanations, using reconstruction quality as the training objective for explanation quality [1](./citations/1.md).
- The method uses two copies of a model: an activation verbalizer that maps an activation to text, and an activation reconstructor that maps that text back to an activation [1](./citations/1.md).
- The post reports that NLA explanations surfaced evaluation awareness in a couplet-completion setting, where Claude appeared to plan a rhyme in advance, and in cases where Claude did not explicitly say it knew it was being tested [1](./citations/1.md).
- Reported evaluation-awareness rates were 16% on a destructive-actions coding test, 26% on SWE-bench Verified, and under 1% on opted-in real Claude.ai usage [1](./citations/1.md).
- In a toy auditing game with a deliberately misaligned Claude Haiku 3.5 variant, auditors using NLAs uncovered the hidden motivation 12%–15% of the time, versus under 3% without NLAs [1](./citations/1.md).
- The post cautions that NLAs can hallucinate or invent details, so Anthropic says it relies on corroborating evidence and treats the output as thematic rather than literal [1](./citations/1.md).
- This may matter because the technique could make interpretability more legible for auditing hidden motivations and internal reasoning that models do not verbalize [1](./citations/1.md).

## Donating our open-source alignment tool
Original URL: https://www.anthropic.com/research/donating-open-source-petri

- Anthropic says it is updating Petri to version 3.0 and transferring stewardship to Meridian Labs [2](./citations/2.md).
- Petri is an open-source alignment toolbox built around an auditor model that simulates scenarios, a target model under evaluation, and a judge model that scores transcripts for misaligned behavior [2](./citations/2.md).
- The post says Petri has been used to test deception, sycophancy, cooperation with harmful requests, and sabotage-like behavior; it also cites the UK AI Security Institute’s use of Petri in model evaluations for propensity to sabotage AI research [2](./citations/2.md).
- Petri 3.0 adds three emphasized changes: adaptability via separately tweakable auditor and target components, realism via the “Dish” add-on using a model’s real system prompt and scaffold, and depth via Bloom integration for more in-depth assessments of selected behaviors [2](./citations/2.md).
- The post does not provide benchmark scores here; it frames the donation as infrastructure for ongoing alignment evaluation rather than as a results announcement [2](./citations/2.md).
- The move to an independent nonprofit is presented as a way to preserve neutrality and credibility while broadening ecosystem access to the evaluation toolset [2](./citations/2.md).

## Focus areas for The Anthropic Institute
Original URL: https://www.anthropic.com/research/anthropic-institute-agenda

- The Anthropic Institute is presented as an effort to study AI’s real-world impacts from inside a frontier lab and to publish research, data, and tools for public use [3](./citations/3.md).
- The agenda is organized around four pillars: economic diffusion, threats and resilience, AI systems in the wild, and AI-driven R&D [3](./citations/3.md).
- Concrete planned work includes expanding and updating the Anthropic Economic Index with more granular, high-frequency labor and usage data, studying resilience and security investment needs, measuring how Anthropic’s own work accelerates via AI tools, and producing early-warning signals and public-facing research [3](./citations/3.md).
- The post grounds the agenda in observed internal changes such as shifts in labor, emerging threats, and AI speeding up AI R&D [3](./citations/3.md).
- This is explicitly described as a living agenda rather than a fixed plan, so the questions and priorities are expected to change as evidence accumulates [3](./citations/3.md).
- This may matter because it signals the societal impact questions Anthropic thinks are most urgent, and it may shape future public data releases and research priorities [3](./citations/3.md).
