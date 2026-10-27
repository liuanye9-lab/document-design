---
name: document-design
description: Create, edit, audit, or transform readable professional documents across Word DOCX, PDF, Markdown, HTML, and Feishu/Notion-targeted content. Use for PRDs, SPECs, proposals, reports, research drafts, manuals, document templates, formatting cleanup, and cross-format publication. Apply cognitive-first information hierarchy, selective emphasis, whitespace, restrained containers, and platform-specific quality checks.
---

# Document Design · Lay

## Goal

Help a reader identify **the document's purpose, key conclusion, and next action** before absorbing detail. Adapt the visual treatment to the medium: a printed page is not a chat screen.

## Workflow

1. **Identify audience and job.** Who reads this, why, and what must they decide or do? Determine the publication platform and any institutional / brand rules. Ask one question only if its answer changes the result materially.
2. **Protect content.** For existing documents, preserve evidence, quotations, data, citations, numbering, formulas, tracked changes, and required formatting. Keep a source copy. Never invent claims or sources just to improve design.
3. **Structure the reading path.** Descriptive title → compact purpose / finding → explanation and evidence → appropriate facts, steps, or comparison → risk / caveat → action. Choose only structures that help that type of document.
4. **Route to output medium:**
   - **Formal DOCX/PDF:** use page settings, named paragraph styles, normal prose, real comparison tables, keep-with-next headings, widow/orphan controls, and visual page QA. Default callouts to ordinary prose with a bold cue, not gray boxes.
   - **Online Markdown/HTML/Feishu/Notion-targeted:** use a constrained reading width, generous paragraph rhythm, selective bold, and pale-gray blocks only for bounded objects. Do not imply that custom CSS or JavaScript survives Markdown imports.
5. **Generate from a common content model** when multiple formats are needed. For simple structured documents, write JSON using [the bundled sample](assets/example-document.json) and run the renderer below. For complex citations, tracked changes, native equations, forms, or supplied institutional templates, use appropriate document-specialist tools.
6. **Render → inspect → repair.** Every produced DOCX/PDF must be visually checked page by page; HTML requires responsive, keyboard and overflow QA; Markdown requires copy/paste compatibility. If inspection was blocked, report it honestly.

## Output principles

- **Lead with the matter, not a slogan.** State scope and the real conclusion. No artificial introductions or overdesigned cover pages.
- **Emphasis is selective.** Bold one consequential term or fact where helpful; leave explanation at normal weight.
- **Whitespace does the grouping.** Related paragraphs sit close; topic changes receive a larger gap. Do not generate a heading/card for every sentence.
- **Gray only for special bounded information.** A concise fact group or file is a valid card online; ordinary explanation stays white. Formal Word favors a structured table or a bold lead-in instead.
- **Lists describe distinct items; steps describe ordered dependencies; tables describe exact comparable fields.** Keep full reasoning as prose.
- **Black leads, gray assists; accents are rare.** Never use color as the sole bearer of meaning.
- **Interactions must work.** Only HTML can optionally offer actual single-choice submission and local feedback. Word/PDF/Markdown must show a static response form or list, not a fake button.
- **No one-size-fits-all template.** Memo, thesis, PRD, policy and handbook have different requirements; user templates and compliance rules take priority.

## Bundled renderer

```bash
python3 scripts/render_document.py assets/example-document.json --out ./output --formats md,html
python3 scripts/render_document.py assets/example-document.json --out ./output --formats docx,pdf
```

- HTML/Markdown only require Python standard library. DOCX additionally requires `python-docx`; PDF additionally requires LibreOffice/soffice.
- JSON `schema_version: 1` accepts `title`, `summary`, optional `subtitle`, `page_size: letter|a4`, `sections`, and semantic blocks: `paragraph`, `facts`, `steps`, `list`, `table`, `note`, `choice`.
- Inline `**important**` becomes bold. `==subtle==` becomes light-gray inline highlight in HTML and bold in Word/Markdown. Always escape untrusted HTML content.
- The script never overwrites generated outputs unless `--force` is passed. The renderer covers short-to-medium structured documents, not every complex document feature.

## Read on demand

- [Visual system](references/visual-system.md) — online and formal typography, spacing and semantics.
- [Format mapping](references/format-mapping.md) — publication modes and content fidelity limitations.
- [Quality checklist](references/quality-checklist.md) — manual review, regression and prompts.
- [Optional standing rule](assets/default-agent-rule.md) — merge into Codex `AGENTS.md` or Claude Code `CLAUDE.md` only when the user wants a default policy; preserve existing rules.

## Completion gate

Deliver the actual files and verification. Separate passing static tests from verified visual QA. Never claim this portable draft ZIP is already installed, or claim native platform interactions you have not confirmed.
