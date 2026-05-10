---
name: document-report-skill
description: Use when generating long-form documents, Chinese or multilingual reports, whitepapers, research reports, business/data reports, technical specifications, or PDF-ready artifacts. Produces professional, readable, source-aware reports by defining structure, audience, visible language, evidence, citations/data, and print/web rendering before outputting Markdown, HTML, or LaTeX.
---

# Document & Report Skill

Use this skill when the user asks to generate a whitepaper, research report, technical specification, business analysis, data report, or PDF-ready document. Default visible report language to the user's prompt language unless they ask otherwise. The goal is deep-reading comfort, authoritative structure, precise information hierarchy, and clear evidence handling.

This skill uses progressive disclosure. Do not load every reference by default. First identify the document type, target format, and data sources, then read only the references that are needed.

## Core Workflow

1. Resolve scope and format:
   - Infer the document type, audience, visible language, final rendering target, and evidence sources from the prompt when possible.
   - Ask only when ambiguity would materially change the report, such as academic paper vs. business memo, Markdown vs. PDF-ready HTML, or sourced analysis vs. illustrative draft.
   - If the user asks in Chinese, default visible report content to Chinese.
   - Track the data sources, citations, screenshots, tables, assumptions, and missing evidence that support the report.

2. Establish the Document Skeleton:
   - Define the front matter (Title, Abstract/Executive Summary), Table of Contents, Main Sections, and Appendices/References.
   - Read `references/document-structure.md` for authoritative scaffolding.

3. Enforce Deep-Reading Typography:
   - Optimize line length (measure), line height (leading), and paragraph spacing.
   - Maintain strict heading hierarchies (H1 to H4).
   - Read `references/typography-readability.md`.

4. Integrate Data, Tables, and Citations:
   - Ensure all charts, tables, and figures have proper numbering and captions (e.g., *Figure 1: Market Growth*).
   - Maintain a consistent citation log or footnote style if requested.
   - Read `references/data-figures-tables.md`.

5. Design the Grid and Layout (if rendering to PDF/Print):
   - Utilize wide margins for notes, multi-column layouts for density, and proper page breaks.
   - Read `references/layout-grids.md`.

6. Output the Document:
   - Generate the content. If using Markdown for Pandoc/PDF metadata, include YAML frontmatter. If using HTML, use readable document CSS and print-aware rules.
   - Read `references/implementation-patterns.md`.

7. Final Quality Check:
   - Read `references/quality-rubric.md`.
   - Fix logical orphans/widows, inconsistent heading depths, uncaptioned data, English labels in Chinese reports, or unsupported claims.

## Reference Routing

Read references based on the current document generation phase:

- Outline, executive summary, chapters, and appendices: read `references/document-structure.md`.
- Line length, heading scale, serif vs sans-serif rules, reading flow: read `references/typography-readability.md`.
- Margin notes, page breaks, multi-column, print constraints: read `references/layout-grids.md`.
- Table formatting, figure captions, citation handling: read `references/data-figures-tables.md`.
- Markdown to PDF workflows, HTML print styles, Tailwind Prose: read `references/implementation-patterns.md`.
- Final check for professional document standards: read `references/quality-rubric.md`.

## Language Behavior

- Default visible report content to the user's prompt language.
- If the user asks in Chinese, write Chinese titles, section headings, body copy, captions, table labels, source notes, and footnotes by default.
- Preserve product names, dataset names, table names, query IDs, metric IDs, filenames, URLs, and code identifiers.
- Use Chinese punctuation, natural Chinese units, and Chinese source labels in Chinese reports.
- Avoid machine-translated prose. Rewrite for Chinese long-form reading rhythm.
