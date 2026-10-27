# Quality gate and evaluation cases

## Content and hierarchy

- [ ] Descriptive title and clear opening purpose / conclusion / action.
- [ ] Existing numbers, citations, quotations, qualifications and source meaning preserved.
- [ ] Normal prose carries explanation; only 1–3 main points dominate visually.
- [ ] Selective emphasis; card only for bounded facts; steps and tables have semantic value.
- [ ] Necessary risks and caveats visible, not hidden in extra controls.

## Formal QA

- [ ] Word uses semantic styles, black titles/headings and required paper/margins.
- [ ] Long tables have suitable column widths and repeated headers; rows are not clipped.
- [ ] No orphan headings, font substitution errors, missing CJK glyphs, overflowing figures or unwanted blank half-pages.
- [ ] **Every DOCX/PDF page rendered to image and visually inspected** before describing visual QA as passed.

## Online QA

- [ ] Check HTML at 360px, 768px and desktop; no page-level horizontal overflow.
- [ ] Escaped HTML content, semantic heading order, accessible table headers, visible keyboard focus.
- [ ] Markdown supports copy/paste without external CSS or fake buttons.
- [ ] Any interactive HTML choice has real selection, submit and tailored feedback; paper variants explicitly static.

## Behavioral evaluation prompts

1. "写一段100字的项目进展说明" → short memo, no forced table or six headings.
2. "制作跨部门 AI PRD" → opening decision, concrete process, true comparisons, risks and acceptance criteria.
3. "优化我的毕业论文排版" → school template, citations and figure numbering trump these generic design tokens.
4. "导出飞书和 PDF 两份" → content parity, platform-adapted visual rules, not screenshot duplication.
5. "已有 DOCX 只整理间距" → preserve wording and revision metadata; edit only spacing.
6. "插入选择题" → HTML interactive; PDF/Word/Markdown honest static fallback.
7. "现在无法运行文档渲染器" → acknowledge inability to verify visual polish.

Static tests confirm schema and text parity, not actual visual correctness. Keep **unit tests** separate from **rendered page review** in completion reporting.
