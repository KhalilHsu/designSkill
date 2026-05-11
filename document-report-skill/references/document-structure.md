# Chinese Report Structure

Read this before drafting long-form Chinese reports, whitepapers, research reports, or PDF-ready documents.

## Default Chinese Report Skeleton

Use this skeleton as a base, then adjust with `report-archetypes.md`:

1. 标题页 / Title block
2. 摘要 / Executive Summary
3. 目录
4. 背景、问题与读者决策
5. 方法与数据来源
6. 核心发现
7. 分析与论证
8. 风险、假设与限制
9. 建议、决策或下一步
10. 附录、数据口径、参考资料

Do not include every section mechanically. Remove sections that do not serve the report type.

For business reports, keep the executive summary concrete: conclusion, evidence, impact, recommendation.

For research reports, keep methods and limitations visible. Do not hide weak evidence inside polished prose.

For investment memos, include thesis, business quality, valuation, risk, variant view, and decision. Separate facts from interpretation.

For technical specifications, replace the generic analysis chapters with goals, non-goals, requirements, architecture, interfaces, constraints, edge cases, and acceptance checks.

## Chinese Heading Style

- Use numbered headings when the report is formal: `1. 背景`, `1.1 数据来源`.
- Use short descriptive headings, not vague labels.
- Avoid translated headings such as `市场洞察概览` when a specific claim is available.
- Keep heading depth to H1-H3 unless the document is truly technical.
- Prefer claim-led headings when they improve scanning: `3.2 续约扩张是收入增长的主因`.
- Keep repeated heading patterns consistent across chapters.

## Summary Blocks

Use summary blocks to make long Chinese documents scannable:

- `核心结论：`
- `关键证据：`
- `影响：`
- `建议：`
- `风险提示：`

Each block should be short enough to quote.

## Front Matter

Use front matter deliberately:

- Public report: title, subtitle, author/team, date, version, confidentiality or distribution note if needed.
- Internal memo: title, owner, decision needed, due date, audience, source status.
- Technical spec: status, owner, reviewers, related tickets/docs, version.
- Research report: abstract, keywords/tags if useful, methodology summary.

## Appendices

Move dense materials to appendices:

- raw tables
- query notes
- source list
- definitions
- methodology details
- alternate scenarios
- omitted evidence or unresolved questions
