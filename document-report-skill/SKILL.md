---
name: document-report-skill
description: Use when generating long-form documents, whitepapers, research reports, or PDFs. Produces professional, academic, or corporate long-form content by first defining the document structure, enforcing readability rules, and structuring citations/data before outputting Markdown, HTML (for PDF printing), or LaTeX.
---

# Document & Report Skill

Use this skill when the user asks to generate a whitepaper, research report, technical specification, or PDF-ready document. The goal is deep-reading comfort, authoritative structure, and precise information hierarchy.

This skill uses progressive disclosure. Do not load every reference by default. First identify the document type, target format, and data sources, then read only the references that are needed.

## Core Workflow

1. Clarify the scope and format:
   - Is this an academic paper, a B2B marketing whitepaper, a technical audit, or a financial report?
   - What is the final rendering target? (Markdown for Pandoc/PDF, HTML with CSS Paged Media, LaTeX, or standard Markdown).

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
   - Generate the content. If using Markdown for PDF, ensure YAML frontmatter is present. If using HTML, utilize `@tailwindcss/typography` or print media queries.
   - Read `references/implementation-patterns.md`.

7. Final Quality Check:
   - Read `references/quality-rubric.md`.
   - Fix logical orphans/widows, inconsistent heading depths, or uncaptioned data.

## Reference Routing

Read references based on the current document generation phase:

- Outline, executive summary, chapters, and appendices: read `references/document-structure.md`.
- Line length, heading scale, serif vs sans-serif rules, reading flow: read `references/typography-readability.md`.
- Margin notes, page breaks, multi-column, print constraints: read `references/layout-grids.md`.
- Table formatting, figure captions, citation handling: read `references/data-figures-tables.md`.
- Markdown to PDF workflows, HTML print styles, Tailwind Prose: read `references/implementation-patterns.md`.
- Final check for professional document standards: read `references/quality-rubric.md`.
