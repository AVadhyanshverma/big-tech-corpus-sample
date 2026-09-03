---
license: mit
task_categories:
- text-generation
language:
- en
tags:
- web-crawl
- markdown
- big-tech
- corpus
size_categories:
- n<1K
---
# High-Fidelity Web Crawl Sample

This dataset contains a small, representative sample of our highly curated, domain-specific web corpus.

## What is this?
Unlike raw web dumps (e.g., Common Crawl), this data was extracted using a custom, Rust-based tiered scraping engine designed for modern AI and ML pipelines.

### Key Features
- **Pristine Markdown**: All HTML boilerplate (navbars, footers, ad banners, script tags, style blocks) has been stripped out at extraction time. You get only the core structural text.
- **Anti-Bot Evasion**: Crawled using Tier 1 TLS impersonation and Tier 3 headless browser escalation for JS-heavy or cloudflare-protected sites.
- **High Quality**: Every document in this sample has a minimum of 450 words, ensuring high-density context.
- **Rich Metadata**: Includes original URLs, page titles, word counts, and the fetch tier used to acquire the DOM.

## Data Format
The sample is provided in two highly compatible formats:
1. `sample.jsonl` - Standard JSON Lines format.
2. `sample.parquet` - Compressed columnar format optimized for Pandas, Polars, and Hugging Face `datasets`.

### Schema
- `domain` (string): The authoritative domain of the document.
- `url` (string): The exact URL crawled.
- `title` (string): The extracted page title.
- `markdown` (string): The cleaned, structural markdown content.
- `word_count` (int): Number of words in the markdown.
- `tier` (string): Extraction method (`http` for static, `browser` for JS-rendered).

## Licensing & Contact
This sample is provided for evaluation purposes. If you are interested in purchasing the full 22.5M+ token dataset or contracting a custom crawl for your target domains, please reach out.
