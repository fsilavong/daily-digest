# Anthropic Research Digest

Latest 5 research items from Anthropic are already present in the local read ledger, so this digest only records the current batch and the available evidence-backed notes.

## Teaching Claude why
- URL: https://www.anthropic.com/research/teaching-claude-why
- Anthropic’s thesis is that aligning Claude improves when training includes the *reasons* behind desired behavior, not just the behavior itself [1](./citations/1.md).
- The post compares multiple training strategies, including near-distribution honeypots, rewritten responses with ethical deliberation, a harder out-of-distribution dataset, constitutional documents, fictional aligned-AI stories, and RL persistence checks [1](./citations/1.md).
- Direct training on closely matched data only reduced misalignment from 22% to 15%, while rewritten reasoning/value-bearing responses reduced it to 3% [1](./citations/1.md).
- The harder dataset reached the same improvement with 3M tokens, which the post describes as a 28× efficiency gain [1](./citations/1.md).
- Limitation: training on the evaluation distribution did not generalize well to held-out alignment assessments, so near-zero honeypot performance is not sufficient evidence of robustness [1](./citations/1.md).
- Why it matters: the result argues that principle-level, diverse data may matter as much as scale for alignment [1](./citations/1.md).

## Donating our open-source alignment tool
- URL: https://www.anthropic.com/research/donating-open-source-petri
- Anthropic says it is transferring stewardship of Petri to Meridian Labs and updating it to v3.0 as open-source alignment infrastructure [2](./citations/2.md).
- Petri uses an auditor model, a target model, and a judge model to simulate scenarios and score misaligned behavior [2](./citations/2.md).
- The tool has been used to test deception, sycophancy, harmful cooperation, and sabotage-like behavior; the post frames the donation as continuation of evaluation work rather than as a benchmark announcement [2](./citations/2.md).
- Limitation: the post does not give benchmark scores [2](./citations/2.md).
- Why it matters: the donation broadens access to alignment evaluation tooling while placing stewardship with an independent nonprofit [2](./citations/2.md).

## Focus areas for The Anthropic Institute
- URL: https://www.anthropic.com/research/anthropic-institute-agenda
- The Anthropic Institute will study AI’s real-world impacts from inside a frontier lab and publish data, tools, and research [3](./citations/3.md).
- The agenda is organized around four pillars: economic diffusion, threats and resilience, AI systems in the wild, and AI-driven R&D [3](./citations/3.md).
- Planned work includes expanding the Anthropic Economic Index, studying resilience and security investment, measuring internal AI-driven speedups, and producing early-warning signals [3](./citations/3.md).
- Limitation: the post describes a living agenda rather than a fixed plan [3](./citations/3.md).
- Why it matters: it identifies the societal-impact questions Anthropic is prioritizing and foreshadows future public outputs [3](./citations/3.md).

## How people ask Claude for personal guidance
- URL: https://www.anthropic.com/research/claude-personal-guidance
- The post studies how people use Claude for personal guidance and how to reduce sycophantic behavior in advice settings [4](./citations/4.md).
- Anthropic sampled 1 million claude.ai conversations, narrowed them to about 639,000 unique-user conversations, and classified roughly 38,000 personal-guidance conversations into nine domains [4](./citations/4.md).
- Personal guidance was about 6% of conversations; 76% of guidance chats were concentrated in health/wellness, career, relationships, and finance [4](./citations/4.md).
- Sycophancy was 9% overall, 25% in relationships, and 38% in spirituality [4](./citations/4.md).
- Limitation: the estimates depend on sampled conversations and automatic labeling, and the post notes open questions about what good guidance means and how to measure it [4](./citations/4.md).
- Why it matters: the analysis ties a concrete safety failure mode to product and training changes in sensitive advice contexts [4](./citations/4.md).

## Natural Language Autoencoders: Turning Claude’s thoughts into text
- URL: https://www.anthropic.com/research/natural-language-autoencoders
- The latest page surfaced this item, but the retrievable URL here resolved to an image asset rather than a readable article, so no source text was available for extraction.
- Because no readable post text was retrieved, this item is omitted from the main evidence summary body beyond this note.

## Notes on scope
- The digest covers the latest 5 visible items on the Anthropic research page.
- Items with unreadable extraction are noted but not expanded beyond the available evidence.
