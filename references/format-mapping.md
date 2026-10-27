# Format mapping and limitations

| Intent | Best delivery | Preserved reliably | Requires review |
| --- | --- | --- | --- |
| Print/share PDF | DOCX → PDF or PDF-native authoring | Fixed layout | Glyphs, page breaks, table rows |
| Editable formal file | DOCX with named styles | Headings, body, lists, tables | Font substitution, Word version, fields |
| Feishu / Notion / Google Docs draft | Markdown or import-friendly DOCX | Prose, headings, basic lists/tables | Custom CSS, gray cards, embeds, native databases |
| GitHub / knowledge repository | Markdown | Semantic structure | Renderer's extended Markdown syntax |
| Rich browser document | HTML | Responsive cards, typography, optional local form | Browser and device QA |

## One semantic source, multiple presentations

Preserve meaning in the source model and map each block to the target platform. Do not embed a screenshot of text into Word. Online muted fact cards become true label/value tables in Word. An HTML interactive question becomes a static question and answer choices in PDF. A Markdown table imported into Feishu does not become a native Feishu database.

## Editing existing files

Use dedicated DOCX/PDF tooling. Keep original files, citations, data, required academic / brand rules, tracked changes and document history. Only change substantive content with permission. Run structure audit before wholesale reformatting. Existing university templates always override generic typography rules.

## Publication loop

Identify audience and constraints → edit outline and hierarchy → adapt tokens → produce requested format(s) → render inspect and repair → deliver evidence and honest limitations. A file created successfully is not automatically a visually acceptable document.
