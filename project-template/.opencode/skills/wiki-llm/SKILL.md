---
name: wiki-llm
description: Explains the compounding LLM wiki pattern: raw sources, structured markdown wiki pages, index/log maintenance, and cited answers from local knowledge.
---

# Wiki LLM

A wiki turns repeated research into a durable local knowledge base. Compile once, maintain carefully, and answer from structured pages instead of re-reading raw sources every time.

## Layout

Recommended project paths:

- `data-place/raw/`: immutable source files.
- `data-place/wiki/index.md`: catalog of wiki pages.
- `data-place/wiki/log.md`: chronological maintenance log.
- `data-place/wiki/sources/`: source summaries.
- `data-place/wiki/concepts/`: evolving concepts.
- `data-place/wiki/entities/`: people, systems, organizations, or objects.

## Workflow

For ingest, read raw source, summarize it, extract concepts/entities, cross-link pages, update index, and append log.

For query, read index first, then relevant pages, and cite local wiki pages in the answer.
