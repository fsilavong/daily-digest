# NVIDIA Generative AI Blog Digest

## How to Build In-Vehicle AI Agents with NVIDIA: From Cloud to Car
Source: https://developer.nvidia.com/blog/how-to-build-in-vehicle-ai-agents-with-nvidia-from-cloud-to-car/

- The post argues that in-vehicle assistants are shifting from fixed command-response systems to agentic, multimodal AI that can reason, plan, act, and adapt to evolving context across a trip [1](./citations/1.md).
- It says modern in-vehicle assistants should combine LLMs, VLMs, and speech models to support conversational interaction with memory, multimodal inputs across voice/vision/telemetry, and proactive assistance rather than simple command matching [1](./citations/1.md).
- The post frames production deployment as a real systems problem because vehicle assistants must satisfy low latency, privacy, and safety constraints while integrating with cloud agents and external services [1](./citations/1.md).
- It lists on-device requirements for a production agentic assistant as: 7B+ local models, multimodal inputs, under-500 ms response time, over 30 tokens/sec decode throughput, and edge-first privacy [1](./citations/1.md).
- It presents three deployment paths: an AI box add-on built on DRIVE AGX for existing IVI systems, a DRIVE AGX Thor multi-domain AI computer for unified AV and cabin AI, and a central car computer pairing DRIVE AGX with MediaTek Dimensity AX [1](./citations/1.md).
- The edge/cloud hybrid section says many tasks need cloud inference for large models and web APIs, and highlights agent orchestration plus context sharing as key requirements for a seamless experience [1](./citations/1.md).

## Building for the Rising Complexity of Agentic Systems with Extreme Co-Design
Source: https://developer.nvidia.com/blog/building-for-the-rising-complexity-of-agentic-systems-with-extreme-co-design/

- The post claims the agentic phase of generative AI changes workload shape: agents call tools, spawn sub-agents, retain memory, manage context, and choose when they are done, which drives highly variable token, latency, and context demands [2](./citations/2.md).
- It distinguishes simple chat, chat-with-tools, and agentic systems, arguing that tool calling and especially chained agent behavior make the workload structurally probabilistic rather than linear [2](./citations/2.md).
- It describes a standard agent architecture with a primary agent, sub-agents, file-system statefulness, and summarization/compaction as context-management techniques [2](./citations/2.md).
- It cites Anthropic’s estimate that multi-agent systems can consume up to 15x more tokens than standard chat, and uses a 33-minute Claude Code session as an example where 283 inference requests, 58 main-agent turns, and 225 sub-agent invocations pushed context from 15K to 156K tokens before compaction [2](./citations/2.md).
- It argues that prompt caching, cache-hit management, and long-context infrastructure are central economics issues; it says a 95% cache hit rate can reduce input processing cost by about 85%, and that coding agents often sustain 95-98% cache hit rates when tool output stays small [2](./citations/2.md).
- It connects these workload patterns to NVIDIA infrastructure claims around high-bandwidth memory, NVIDIA CMX, NVLink 6, ConnectX-9, BlueField-4, Spectrum-X, and Vera Rubin NVL72 as ways to keep long-prefix context economical and low-latency [2](./citations/2.md).
