# Daily Digest

<div align="center">

### The AI research world moves fast. This keeps you up.

**20+ top labs · arXiv · Hugging Face — summarised into one daily brief, automatically.**

![Sources](https://img.shields.io/badge/sources-20%2B-blue?style=flat-square)
![Cadence](https://img.shields.io/badge/cadence-daily-green?style=flat-square)
![Powered by AI](https://img.shields.io/badge/powered%20by-AI-purple?style=flat-square)

**[📖 Read the latest digest →](https://unfoldoc.fly.dev/)**

<br/>

</div>

--- 

No more tab overload. No more FOMO. Every morning, `ai-research-agent` crawls the frontier — papers, blog posts, model releases — and lands a single, skimmable digest. 

![demo](demo.gif)

## High-Level Flow

```mermaid
flowchart LR
    A[Start daily research run]
    A --> C[Blog and publication digests]
    A --> D[arXiv feed digests]
    A --> E[Hugging Face papers digest]
    C --> F[Combine]
    D --> F
    E --> F
    F --> H[Summarise]
```

## Data Sources

### Blog and publication sources

- `openai-research`
- `anthropic-research`
- `anthropic-alignment`
- `deepmind-publications`
- `google-research-blog`
- `meta-ai-blog`
- `mistral-news`
- `xai-news`
- `cohere-blog`
- `ai2-research`
- `ai2-papers`
- `bair-blog`
- `princeton-agents`
- `stanford-hai-news`
- `ibm-research-blog`
- `microsoft-research-blog`
- `microsoft-research-publications`
- `amazon-science-blog`
- `nvidia-generative-ai-blog`
- `huggingface-papers` when enabled

### arXiv RSS feeds

- `arxiv-cs-ai`
- `arxiv-cs-cl`
- `arxiv-cs-lg`
- `arxiv-cs-ir`
- `arxiv-cs-ma`
- `arxiv-cs-se`
- `arxiv-cs-hc`
- `arxiv-stat-ml`
