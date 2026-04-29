# Anthropic Alignment Digest

## Poisoning Fine-tuning Datasets of Constitutional Classifiers
https://alignment.anthropic.com/2026/backdooring-classifiers/

- The paper studies how many poisoned examples are needed to install a backdoor in a constitutional classifier via fine-tuning data poisoning, while keeping robustness loss small enough that red-teamers may not notice [1](./citations/1.md).
- In the default bio-harm classifier setup, about 32 poisoned training examples were sufficient to install a backdoor regardless of training-set size [1](./citations/1.md).
- Backdoor insertion usually reduced robustness when the training set had no prompt injections, but adding correctly labeled prompt-injection examples or “almost-backdoors” often reduced or masked that robustness drop [1](./citations/1.md).
- The authors report replication on Anthropic’s internal CBRN constitutional classifier: backdoors took between 32 and 128 poisoned examples, and the robustness decrease was likely too small to block deployment [1](./citations/1.md).
- Methodologically, they fine-tune Qwen3 8B with LoRA, sweep training-set sizes of roughly 33K, 16.5K, and 8K examples, and poison examples by prepending a fixed trigger phrase while relabeling harmful examples as harmless [1](./citations/1.md).
- The main caveat is that the trigger resembles a prompt injection, so the robustness-preserving effect of prompt-injection augmentation may depend on trigger choice [1](./citations/1.md).
- Why it matters: the work suggests a small insider-poisoning budget may be enough to create a classifier backdoor that survives standard robustness review [1](./citations/1.md).

## Introspection Adapters
https://alignment.anthropic.com/2026/introspection-adapters/

- The paper introduces introspection adapters (IA): a single LoRA adapter trained to make fine-tuned LLMs describe learned behaviors in natural language [2](./citations/2.md).
- Training happens in two phases: first, many models are fine-tuned from a common base model on researcher-selected behaviors; second, the shared IA is trained across those models so it can elicit a description of the implanted behavior when queried [2](./citations/2.md).
- The reported thesis is broader generalization than prior “Diff Interpretation Tuning”: the IA generalizes to models fine-tuned in different ways, not just one narrow fine-tuning regime [2](./citations/2.md).
- The authors say IA achieves state-of-the-art performance on AuditBench, a benchmark of 56 models with implanted behaviors, and can detect encrypted fine-tuning API attacks [2](./citations/2.md).
- They also state that IA performance improves with model scale and training-data diversity [2](./citations/2.md).
- The limitation noted in the source text is implicit rather than quantified here: the method depends on having known behaviors to generate labeled model-behavior pairs during training [2](./citations/2.md).
- Why it matters: IA gives a natural-language auditing interface for frontier-model behavior inspection and appears to generalize across different fine-tuning procedures [2](./citations/2.md).