# Chinese Long-Form Readability

Read this when choosing typography, spacing, and reading rhythm for Chinese reports or PDF-ready documents.

## Font Stacks

For browser/PDF rendering:

```css
--font-serif: "Noto Serif SC", "Source Han Serif SC", "Songti SC", "STSong", Georgia, serif;
--font-sans: "PingFang SC", "Microsoft YaHei", "Noto Sans SC", "Source Han Sans SC", system-ui, sans-serif;
--font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
```

- Research and whitepaper body: prefer Chinese serif when available.
- Dashboards, technical reports, and dense tables: prefer Chinese sans.
- Metadata, captions, table headers, and footnotes: use sans for legibility.
- Code, query IDs, table names, filenames: use mono only for those fragments.

## Chinese Reading Measures

- Body font: 15-18px for web, 10.5-12pt for PDF.
- Line height: 1.65-1.9 for long Chinese body text.
- Paragraph spacing: visible but not blog-like; avoid huge gaps between every paragraph.
- Main text width: about 34-42 Chinese characters per line for comfortable reading.
- Avoid full-width text blocks across large screens.

## Chinese Copy Rules

- Use natural Chinese punctuation: `，` `。` `：` `；` `（ ）`.
- Keep Arabic numerals for metrics and dates.
- Use Chinese units naturally: `万元`, `亿元`, `小时`, `近 30 天`, `2026 年 Q1`.
- Preserve dataset names, query IDs, metric IDs, table names, product names, and code identifiers.
- Avoid machine-translated academic phrases. Prefer clear, concrete Chinese.

## Orphans, Widows, And Page Breaks

- Do not leave a heading alone at the bottom of a page.
- Keep figure/table captions with the figure/table.
- Avoid splitting a short key takeaway block across pages.
- In HTML print CSS, use `break-inside: avoid` for figures, tables, callouts, and summary boxes.
