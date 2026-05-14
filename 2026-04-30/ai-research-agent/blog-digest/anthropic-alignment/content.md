# Anthropic Alignment Digest

## Poisoning Fine-tuning Datasets of Constitutional Classifiers

Original URL: https://alignment.anthropic.com/2026/backdooring-classifiers/

- The post studies the conditions needed to install a backdoor in a constitutional classifier by poisoning the fine-tuning dataset, while trying to avoid a detectable loss in robustness [1](./citations/1.md).
- The authors’ tl;dr says that a small, constant number of poisoned examples is sufficient to install a backdoor, regardless of training set size [1](./citations/1.md).
- In their default setup, they report that about 32 poisoned training examples are enough to install a backdoor; on Anthropic’s internal CBRN constitutional classifier, they say the number is between 32 and 128 poisoned examples [1](./citations/1.md).
- Their main experiments use biological-harm classifiers based on Qwen3 8B with LoRA fine-tuning, and they sweep training-set sizes around 33K, 16.5K, and 8K examples [1](./citations/1.md).
- They report that backdooring tends to reduce robustness when the training set contains no prompt injections, but that adding prompt injections or mutated versions of the backdoor trigger phrase to some correctly labeled examples can make the robustness drop small enough that an insider could poison data without red-teamers noticing [1](./citations/1.md).
- Limitation/caveat: the trigger they use resembles a prompt injection, and they note that prompt-injection augmentation might not preserve robustness for a less prompt-injection-like trigger [1](./citations/1.md).
