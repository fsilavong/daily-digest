# Amazon Science blog digest

## Isabelle/HOL: The proof assistant behind the Nitro Isolation Engine
URL: https://www.amazon.science/blog/isabelle-hol-the-proof-assistant-behind-the-nitro-isolation-engine
- Isabelle/HOL is presented as the proof assistant Amazon used to formally verify the Nitro Isolation Engine (NIE), described as the first formally verified cloud hypervisor, with the goal of providing AWS resources while protecting customer data [1](./citations/1.md).
- The post says Isabelle/HOL was chosen for a balance of expressiveness, automation, proof readability, and scalability; it supports higher-order logic, user-configurable parsing, type classes, locales, built-in automation, sledgehammer, counterexample finding, and code generation [1](./citations/1.md).
- For NIE, Amazon says it implemented a separation-logic layer on top of Isabelle/HOL, embedded a significant fragment of Rust, and verified specifications covering Graviton-5 architecture, Rust hypercalls, functional correctness, and security properties; the formal proof is described as about a quarter-million lines and reportedly ran in about half an hour on an off-the-shelf laptop [1](./citations/1.md).
- The post emphasizes that Isabelle/HOL has already been used in prior verification efforts such as seL4, WebAssembly semantics, Cogent, CRDT correctness, pure mathematics, and cryptographic protocols, but does not claim those projects are comparable in scale or purpose to NIE [1](./citations/1.md).
- Limitations/caveats: the article frames formal verification as useful because exhaustive testing is infeasible for critical software, but it does not claim verification removes all risk; it also notes Isabelle is free and open source [1](./citations/1.md).

## Customized Amazon Nova models improve molecular-property prediction in drug discovery
URL: https://www.amazon.science/blog/customized-amazon-nova-models-improve-molecular-property-prediction-in-drug-discovery
- Amazon reports that supervised fine-tuning (SFT) plus reinforcement fine-tuning (RFT) on Nova 2 Lite enabled one customized model to predict 11 molecular properties simultaneously, matching or outperforming separately trained multitask GNN models on 7 of the 11 properties [2](./citations/2.md).
- In the described experiments, general-purpose LLMs such as Claude Sonnet 4 and base Nova 2 Lite underperformed specialized GNNs by wide margins, with RMSE gaps ranging from 40% to more than 200% depending on the property; the fine-tuned model narrowed that gap substantially [2](./citations/2.md).
- Training data and setup: SFT used more than 55,000 labeled molecules across 11 properties; RFT was tested on 15,000 unseen molecules; the system prompt included chemistry concepts plus the target property definitions and value ranges [2](./citations/2.md).
- Reward design mattered: exponential-decay rewards and binary pass/fail rewards both had weaknesses, while Huber-loss-based rewards produced the best RFT result, including a 4.9% R² improvement over the supervised baseline and average performance within 5% of specialized GNNs by RMSE [2](./citations/2.md).
- The post says Nimbus Therapeutics deployed its custom Novus model on Amazon Bedrock and plans to extend it from molecular-property prediction toward molecular design and conversational reasoning; the article also notes drug discovery’s long timelines and high cost but does not present a new benchmark for clinical success [2](./citations/2.md).

## How Amazon uses agentic AI for vulnerability detection at global scale
URL: https://www.amazon.science/blog/how-amazon-uses-agentic-ai-for-vulnerability-detection-at-global-scale
- RuleForge is described as Amazon’s agentic-AI system for turning vulnerability disclosures into detection rules; the post says it generates rules 336% faster than manual methods while maintaining high precision [3](./citations/3.md).
- The workflow mirrors human security engineering: ingest and prioritize exploit proof-of-concept code, generate multiple candidate rules in parallel, evaluate them with a separate judge model, validate them against synthetic tests and traffic logs, and send surviving rules to human review before deployment [3](./citations/3.md).
- The post distinguishes sensitivity from specificity in the judge model and says domain-specific, negatively phrased prompts work better than generic confidence prompts; this separation reduced false positives by 67% while maintaining true positives [3](./citations/3.md).
- RuleForge is positioned against a growing CVE volume: the article cites more than 48,000 new CVEs in 2025 and argues that rule-generation automation is needed to keep pace with disclosure and defense [3](./citations/3.md).
- Caveat: humans remain the final approval gate, and the system is presented as augmenting—not replacing—analyst judgment; the article links to an arXiv paper for technical details [3](./citations/3.md).

## Verifying and optimizing post-quantum cryptography at Amazon
URL: https://www.amazon.science/blog/verifying-and-optimizing-post-quantum-cryptography-at-amazon
- Amazon describes mlkem-native as an open-source, formally verified, high-performance C implementation of ML-KEM that combines the simplicity of the reference implementation with research optimizations and formal verification [4](./citations/4.md).
- The implementation uses CBMC to verify memory safety and type safety at the C level, and HOL Light plus s2n-bignum to verify the hand-optimized assembly routines for AArch64 and x86_64; SLOTHY is used to superoptimize assembly while keeping proofs agnostic to instruction scheduling and register allocation [4](./citations/4.md).
- The modular design separates a frontend from hardware-specific backends, allowing optimized implementations for AArch64, x86_64, and RISC-V64 while keeping the frontend stable and maintainable [4](./citations/4.md).
- Performance results reported in the post show ML-KEM-768 operations per second increasing by factors of 2.0–2.4 on c7i and c7g EC2 instances after switching from the reference implementation to mlkem-native [4](./citations/4.md).
- Caveats and limitations: the article explicitly says formal verification is never absolute, and it publishes SOUNDNESS.md to map the assumptions, trusted-computing-base boundaries, and residual risks [4](./citations/4.md).

## Improving quality and robustness in LLM-based text-to-speech systems
URL: https://www.amazon.science/blog/improving-quality-and-robustness-in-llm-based-text-to-speech-systems
- Amazon says its LLM-based TTS work addresses three failure modes: accent leakage in polyglot voice cloning, limited expressiveness, and reliability issues such as hallucinated repetitions and truncation [5](./citations/5.md).
- For accent leakage, the post describes locale-specific data augmentation and LoRA fine-tuning so cloned voices can speak target languages with native-like pronunciation while preserving speaker identity [5](./citations/5.md).
- For expressiveness, the system uses classifier-free guidance to create synthetic reference audio with improved prosody; the article reports 5%–20% quality improvements across nine locales, with a table listing locale-by-locale gains [5](./citations/5.md).
- For robustness, the model adds chain-of-thought-style predictions of phoneme sequences and duration before generation, then applies guardrails, agentic regeneration, and data filtering to reduce critical errors to less than one second per hour on long-form text [5](./citations/5.md).
- Caveat: the article emphasizes these are production-oriented mitigations for autoregressive TTS failure modes rather than a claim that the system eliminates them entirely [5](./citations/5.md).