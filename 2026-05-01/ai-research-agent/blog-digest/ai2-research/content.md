# Ai2 Research Digest

## AstaBench update: New results, plus adoption from industry
Original URL: https://allenai.org/blog/astabench-update-spring-2026

- Ai2 reports a new AstaBench results round on more than 2.4K research problems, with the updated leaderboard now including stronger frontier models such as GPT-5.5 [1](./citations/1.md).
- The benchmark is meant to measure AI agent scientific research capability across four categories: literature finding/understanding, code writing/execution, dataset analysis, and end-to-end discovery workflows [1](./citations/1.md).
- The headline result is that performance improved, but unevenly: top scores rose most in Code & Execution and End-to-End Discovery, while gains were more modest in Data Analysis and Literature Understanding [1](./citations/1.md).
- Claude Opus 4.7 ranks first overall at 58.0%; GPT-5.5 reaches 52.9% and is the strongest non-Claude frontier run in this round; Gemini 3.1 Pro Preview and GPT-5.4 trail behind [1](./citations/1.md).
- The post emphasizes a persistent gap between strong component skills and full research workflows: even the best agents still struggle to complete end-to-end discovery reliably, and the scorer update is stricter about fabricated results and placeholder code [1](./citations/1.md).
- Adoption is broadening beyond Ai2, with mentions of UK AISI/Inspect Evals, Arcadia Impact, General Reasoning’s OpenReward integration, and external leaderboard submissions [1](./citations/1.md).

## OlmPool: How small architectural choices compound to undermine long context extension
Original URL: https://allenai.org/blog/olmpool

- Ai2 argues that long-context extension performance is driven primarily by architecture, not just data or recipe choices, and that common assumptions from Llama-family results do not transfer cleanly to other model families [2](./citations/2.md).
- The evidence comes from OlmPool, a controlled suite of 26 7B models pretrained on the same data and then extended to 64K context with the same procedure, varying only architectural choices [2](./citations/2.md).
- The four tested choices are QK normalization, grouped-query attention (GQA), sliding-window attention, and pretraining context length; each alone has a relatively modest effect, but combinations compound strongly [2](./citations/2.md).
- Across HELMET, RULER, and LongPPL, the post says short-context metrics do not predict long-context outcomes, and models that look similar on standard evaluations can diverge by more than 26 points on HELMET at 32K after extension [2](./citations/2.md).
- The largest single factor is the count of architectural constraints present: combining three or more of the four choices can reduce long-context scores by up to 47%, and that count explains more variation than treating the four factors separately [2](./citations/2.md).
- The release includes full checkpoints before and after extension, and Ai2 frames OlmPool as a resource for both better context-extension methods and broader study of early-pretraining phenomena [2](./citations/2.md).
