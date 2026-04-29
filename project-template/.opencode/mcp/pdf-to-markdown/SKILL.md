---
name: pdf-to-markdown-mcp
description: Project-local MCP server that converts PDFs to Markdown with Google Gemini or Ollama vision models. Use when a project agent needs PDF extraction with text, equations, tables, captions, and footnotes.
---

# PDF to Markdown MCP

This server converts local PDFs into clean Markdown. It keeps the public tool call small and moves provider/model/rendering settings into MCP config.

## Files

- `.opencode/mcp/pdf-to-markdown/mcp-server.py`
- `.opencode/mcp/pdf-to-markdown/tests/`

## Tool

```text
convert_pdf_to_markdown(pdf_path, extra_instructions=None)
```

Arguments:

- `pdf_path`: local PDF path.
- `extra_instructions`: optional task-specific guidance that cannot override the extraction contract.

All other settings come from environment variables configured in `opencode.json`:

- `PDF_TO_MD_PROVIDER`: `google` or `ollama`; default `google`.
- `PDF_TO_MD_MODEL`: provider model override.
- `PDF_TO_MD_PAGES`: optional page selector such as `1`, `1-3`, or `1,3,5-7`.
- `PDF_TO_MD_RENDER_DPI`: default `180`.
- `PDF_TO_MD_INCLUDE_PAGE_MARKERS`: default `true`.
- `PDF_TO_MD_COMPLETENESS_CHECK`: default `false`.
- `PDF_TO_MD_MAX_PAGES`: optional selected-page limit.
- `PDF_TO_MD_TIMEOUT_SECONDS`: default `120`.
- `GOOGLE_API_KEY`, `GEMINI_API_BASE_URL`, `OLLAMA_BASE_URL`: provider config.

## Run Manually

```bash
uv run .opencode/mcp/pdf-to-markdown/mcp-server.py
```

## Extraction Contract

The prompt requires all visible text in reading order, headings, body text, captions, labels, marginalia, footnotes, references, annotations, equations, and tables. It must not invent or summarize content. Use `[illegible]` where visible content cannot be read.

Equation style is normalized to `$...$` inline math and `$$...$$` display math. Tables use Markdown for simple tables and HTML for complex tables.

## Testing

```bash
uv run --with pytest --with 'mcp[cli]>=1.2.0' --with 'httpx>=0.27.0' --with 'pymupdf>=1.24.0' pytest .opencode/mcp/pdf-to-markdown/tests
```
