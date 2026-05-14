# NVIDIA Generative AI Blog Digest

## Improving Bash Generation in Small Language Models with Grammar-Constrained Decoding

URL: https://developer.nvidia.com/blog/improving-bash-generation-in-small-language-models-with-grammar-constrained-decoding/

- The post frames Bash as a high-value target for agentic systems because shell commands are executable actions that can read files, mutate workspaces, open network connections, and chain tools together.[1](./citations/1.md)
- It describes constrained decoding as modifying autoregressive sampling by applying a grammar before token selection, often blocking invalid tokens; the post points to PICARD as an earlier SQL example of the same idea.[1](./citations/1.md)
- NVIDIA AI Red Team used an experimental pipeline that generates Bash grammars from structured command evidence with `grammargen`, then applies them during decoding with `llguidance` and checks outputs with `tree-sitter-bash` before execution.[1](./citations/1.md)
- On 13 small language models evaluated across 299 tasks, grammar-constrained decoding improved average pass rate from 62.5% to 75.2%.[1](./citations/1.md)
- The strongest reported uplift was for Qwen3-0.6B, which rose from 16.7% to 59.2% pass rate.[1](./citations/1.md)
- The post notes a limitation: Tier 4 shell-construct tasks saw little benefit, with constrained retry averaging 69.0% versus 69.4% native, because the grammar was either too restrictive or too permissive for chaining, backgrounding, and loops.[1](./citations/1.md)
- The post also reports regressions: across 3,887 paired model-task results, constrained retry preserved 2,248 native passes, fixed 676 failures, regressed 181 passes, and left 782 failures unresolved.[1](./citations/1.md)

## Streaming Tokens and Tools: Multi-Turn Agentic Harness Support in NVIDIA Dynamo

URL: https://developer.nvidia.com/blog/streaming-tokens-and-tools-multi-turn-agentic-harness-support-in-nvidia-dynamo/

- The post argues that agentic inference must preserve structured multi-turn interactions: assistant turns can interleave reasoning and tool calls, and subsequent user turns need those results returned to model context in a way that preserves the right reasoning replay policy.[2](./citations/2.md)
- NVIDIA Dynamo added harness-facing support to harden parser coverage, improve streaming behavior, and extract parser layers into reusable crates; the post says these changes build on the serving-architecture work from an earlier Dynamo post focused on frontend, router, and KV cache management.[2](./citations/2.md)
- For reproduction, the post recommends the Anthropic-compatible API plus `--strip-anthropic-preamble` and `--enable-streaming-tool-dispatch`; on workers it uses `--dyn-tool-call-parser` and `--dyn-reasoning-parser` to reconstruct model-specific tool and reasoning blocks.[2](./citations/2.md)
- A concrete caching result is reported on a Dynamo NVIDIA B200 deployment with a 52K-token prompt: a stable prefix hit 168 ms TTFT, a varying session header raised TTFT to 912 ms, and stripping the header brought TTFT back to 169 ms.[2](./citations/2.md)
- The post says the unstable header therefore costs 744 ms per request and is about a 5× slowdown relative to the stripped-prefix case.[2](./citations/2.md)
- A major correctness issue was that reasoning and tool-call segments could be reconstructed in the wrong order or dropped too aggressively across turns; the post says PR #7358 fixed this by making reasoning parsing ownership explicit and by trusting backend structured reasoning when available.[2](./citations/2.md)
- The post provides a streaming example in which the event sequence is `message_start`, `content_block_start type=thinking`, a stream of thinking deltas, then `content_block_start type=text`, then `content_block_start type=tool_use`, and finally `message_stop` with `stop_reason=tool_use`.[2](./citations/2.md)
- The post validates the behavior against a Nemotron-3-Super-120B-A12B-NVFP4 deployment on 4×B200 with TP=4, using the `nemotron_deci` reasoning parser and the `qwen3_coder` tool-call parser.[2](./citations/2.md)