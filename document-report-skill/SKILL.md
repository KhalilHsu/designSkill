---
name: document-report-skill
description: "用于生成或改写中文/多语言报告、研究报告、数据分析摘要、投资 memo、白皮书、技术规格和 PDF/HTML 文档。Use for source-aware report writing with evidence, tables, citations, structure, and quality checks."
---

# Document & Report Skill

Use this skill when the user asks to generate, restructure, or polish a long-form report, memo, whitepaper, research document, technical specification, or PDF-ready source artifact. Default visible report language to the user's prompt language unless they ask otherwise. The goal is not just "nice formatting"; the report must help a real reader understand the conclusion, trust the evidence, and know what to do next.

This skill uses progressive disclosure. Do not load every reference by default. First identify the document type, target format, and data sources, then read only the references that are needed.

## Output Contract

- Prefer Markdown for portable report source and HTML for print/PDF-ready visual reports.
- Do not generate raw PDF binaries unless another explicit PDF/DOCX skill or project pipeline is requested.
- Keep source provenance visible: data source, time window, method, assumptions, missing evidence, and citation style.
- For Chinese prompts, produce Chinese report copy, headings, labels, captions, source notes, table labels, and footnotes by default.
- Preserve product names, dataset names, query IDs, metric IDs, filenames, URLs, and code identifiers exactly.
- If evidence is missing, mark the gap. Do not invent citations, numbers, publication titles, authors, charts, datasets, or benchmark values.

## Minimum Rules

Apply these rules even if no reference file is loaded:

1. Identify report type, audience, source status, output format, and expected length before drafting.
2. Build a claim/evidence map internally; unsupported claims must be removed, softened, or labeled `待补证据` / `假设` / `示意`.
3. For Chinese output, use Chinese section headings, labels, captions, source notes, table labels, and punctuation.
4. For data-table products, preserve table names, view names, query IDs, field names, metric IDs, filters, date ranges, and calculation definitions.
5. Choose the shortest useful artifact: brief summary, memo, full report, or print-ready HTML.
6. Run the quality gate before final output; fix issues directly instead of merely listing them.

## Runtime Integration Notes

- The host product should log which references were loaded for each report run.
- If the base model does not reliably follow reference routing, the host should force-load `data-table-integration.md`, `evidence-methodology.md`, and `quality-rubric.md` for data-table reports.
- If the user asks for a full PDF/HTML report, also force-load `document-structure.md`, `typography-readability.md`, `layout-grids.md`, and `implementation-patterns.md`.
- Use the same task suite across models when evaluating this skill: quick summary, executive memo, data report, full HTML report, existing-report rewrite, and missing-evidence handling.


## Core Workflow

1. Classify the report job:
   - Infer archetype: executive memo, research report, consulting/market report, investment memo, technical specification, business/data report, whitepaper, status report, or policy/compliance report.
   - Infer audience, visible language, decision the reader needs to make, final format, and expected depth.
   - Read `references/report-archetypes.md` when the report type or structure needs routing.
   - Ask only when ambiguity would materially change the output, such as sourced research vs. illustrative draft, investment memo vs. market overview, Markdown vs. print-ready HTML, or public whitepaper vs. internal brief.

2. Build an evidence map before drafting:
   - List the core claims the report needs to make.
   - Attach supporting evidence to each claim: source document, URL, dataset, query result, chart input, interview quote, screenshot, or explicit user assumption.
   - Mark unsupported claims as `待补证据`, `假设`, or `示意`, then remove, soften, or label them.
   - Read `references/evidence-methodology.md` for source hierarchy, citation style, and unsupported-claim handling.

3. Resolve data-table context when present:
   - If the host product exposes a table, view, chart, query, dashboard, uploaded CSV/XLSX, or selected rows, treat it as primary evidence.
   - Capture source handles before writing: table/view/query name, filters, selected columns, metric definitions, time window, row count, and user-provided assumptions.
   - Read `references/data-table-integration.md` when the report is generated from product data.

4. Choose output scope:
   - Brief summary: 300-800 Chinese characters or 3-6 bullets for quick analysis.
   - Executive memo: 800-1,500 Chinese characters with decision, evidence, risk, and next step.
   - Standard report: 1,500-4,000 Chinese characters with sections and source notes.
   - Full report or print-ready HTML: use only when the user asks for depth, publishing, PDF, whitepaper, or board/client-ready output.

5. Design the skeleton around reader decisions:
   - Define title, subtitle, summary, table of contents, main chapters, method/source section, risks/limitations, recommendations, appendix, and references.
   - Put the conclusion near the front for business-facing reports.
   - Keep methods and limitations visible for research, technical, or public-facing reports.
   - Read `references/document-structure.md`.

6. Convert evidence into analysis:
   - Prefer claim -> evidence -> interpretation -> implication.
   - Use tables for comparable records, charts for patterns/trends, and prose for reasoning.
   - Avoid dumping all data into the body; move dense support into appendices.
   - Read `references/data-figures-tables.md` when using metrics, tables, charts, source notes, or citations.

7. Set the reading and layout system:
   - Choose Chinese serif/sans, heading scale, line length, paragraph rhythm, table density, and callout style based on archetype.
   - For print/PDF-ready HTML, define page size, margins, break rules, figure/table keep-together behavior, running headers, and page numbers.
   - Read `references/typography-readability.md` and `references/layout-grids.md`.

8. Generate the artifact:
   - For Markdown, include YAML frontmatter when useful and keep captions/source notes close to figures/tables.
   - For HTML, produce a single-file semantic document with print-aware CSS and no unnecessary external dependencies.
   - For DOCX/PDF binary output, hand off to a dedicated document/PDF skill if available; this skill should still provide structure, content, and visual source rules.
   - Read `references/implementation-patterns.md`.

9. Run the report quality gate:
   - Read `references/quality-rubric.md`.
   - Check decision usefulness, evidence traceability, natural Chinese, heading hierarchy, source labels, table/chart captions, print behavior, and unsupported claims.
   - Fix the artifact before finalizing; do not merely report the issue.

10. If asked to iterate an existing report:
   - Preserve the user-provided facts and source material.
   - First diagnose structure, evidence, readability, layout, and citation problems.
   - Edit the smallest scope that materially improves the report unless the user asked for a full rewrite.

## Reference Routing

Read references based on the current document generation phase:

- Report type routing, audience, chapter pattern, and deliverable shape: read `references/report-archetypes.md`.
- Evidence map, source hierarchy, methodology, assumptions, and citation policy: read `references/evidence-methodology.md`.
- Data-table product context, query/view provenance, metric definitions, and source labels: read `references/data-table-integration.md`.
- Outline, executive summary, chapters, and appendices: read `references/document-structure.md`.
- Line length, heading scale, serif vs. sans-serif rules, and reading flow: read `references/typography-readability.md`.
- Margin notes, page breaks, multi-column, page furniture, and print constraints: read `references/layout-grids.md`.
- Table formatting, figure captions, chart usage, source notes, and citation handling: read `references/data-figures-tables.md`.
- Markdown, HTML, print CSS, and source artifact patterns: read `references/implementation-patterns.md`.
- Final check for professional report standards: read `references/quality-rubric.md`.

## Language Behavior

- Default visible report content to the user's prompt language.
- If the user asks in Chinese, write Chinese titles, section headings, body copy, captions, table labels, source notes, and footnotes by default.
- Preserve product names, dataset names, table names, query IDs, metric IDs, filenames, URLs, and code identifiers.
- Use Chinese punctuation, natural Chinese units, and Chinese source labels in Chinese reports.
- Avoid machine-translated prose. Rewrite for Chinese long-form reading rhythm.

## Anti-Patterns

- Do not hide missing evidence behind confident prose.
- Do not generate decorative report layouts that make long reading harder.
- Do not use `Figure`, `Table`, `Source`, or `Note` labels inside a Chinese-only report unless the user asked for bilingual output.
- Do not turn every section into a table. Use tables only for repeated comparable records.
- Do not mix memo, whitepaper, and academic-paper structures without a deliberate reason.
- Do not leave placeholder citations, fake URLs, tool tokens, lorem ipsum, or unexplained illustrative data.
- Do not replace analysis with uniform bullet lists when paragraphs are needed for reasoning.
- Do not leak English reasoning text, hidden chain-of-thought style prose, or model self-talk into the final report.
- Do not make every section the same length; let section depth follow evidence density and reader need.

## Compact Example

User: `根据 sales_q2 表做一页中文经营摘要。`

Internal routing:
- Archetype: business/data report.
- Scope: executive memo, not full report.
- Evidence handles: `sales_q2`, selected filters, date range, revenue fields, region fields.
- Required references: `data-table-integration.md`, `evidence-methodology.md`, `data-figures-tables.md`, `quality-rubric.md`.

Output shape:
- `核心结论：...`
- `关键证据：表 sales_q2，时间范围...，口径...`
- `变化原因：...`
- `风险/待补证据：...`
- `建议：...`
