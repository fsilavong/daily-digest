# Anthropic Research Digest

## Evaluating Claude’s bioinformatics research capabilities with BioMysteryBench
https://www.anthropic.com/research/Evaluating-Claude-For-Bioinformatics-With-BioMysteryBench

- Anthropic frames BioMysteryBench as a way to evaluate Claude on open-ended, real-world bioinformatics research tasks that are not well captured by existing science benchmarks.[1](./citations/1.md)
- The benchmark contains 99 expert-written bioinformatics questions built from real-world datasets, and Claude is run in a container with minimal canonical bioinformatics tools.
- The setup allows Claude to install tools via pip or conda and to access standard databases such as NCBI and Ensembl.[1](./citations/1.md)
- Tasks are graded on final answers rather than the exact analytical path, which makes the evaluation closer to the outcome of a research workflow.[1](./citations/1.md)
- Anthropic says the latest Claude generations have improved rapidly, that current models perform on par with human experts, and that the latest generations solved many problems a panel of human experts could not, sometimes using different strategies.[1](./citations/1.md)
- The post also acknowledges an important limitation: no benchmark perfectly solves biology evaluation, because valid methods can differ, noisy data leaves room for subjective research choices, and some tasks may not yet be answerable by humans.[1](./citations/1.md)

