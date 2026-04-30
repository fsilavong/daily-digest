# arXiv cs.MA digest — 2026-04-30

## Onchain agent reliability and operating controls

- **Operating-Layer Controls for Onchain Language-Model Agents Under Real Capital** — The abstract centers on reliability for autonomous language-model agents that translate user mandates into validated tool actions under real capital, using the DX Terminal Pro deployment as the evidence base [1](./citations/1.md).
- The deployment description is unusually concrete: 21 days, 3,505 user-funded agents, real ETH trading in a bounded onchain market, 7.5M agent invocations, about 300K onchain actions, about $20M in volume, more than 5,000 ETH deployed, roughly 70B inference tokens, and 99.9% settlement success for policy-valid submitted transactions [1](./citations/1.md).
- The authors attribute reliability to the operating layer around the model rather than the base model alone, naming prompt compilation, typed controls, policy validation, execution guards, memory design, and trace-level observability [1](./citations/1.md).
- Pre-launch testing reportedly exposed failures that text-only benchmarks rarely measure, including fabricated trading rules, fee paralysis, numeric anchoring, cadence trading, and misread tokenomics; targeted harness changes reduced fabricated sell rules from 57% to 3%, reduced fee-led observations from 32.5% to below 10%, and increased capital deployment from 42.9% to 78.0% in an affected test population [1](./citations/1.md).
- The abstract’s main takeaway is that capital-managing agents should be evaluated across the full path from user mandate to prompt, validated action, and settlement [1](./citations/1.md).
