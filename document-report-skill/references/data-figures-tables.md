# Chinese Data, Figures, Tables, And Citations

Read this when the report includes charts, tables, figures, citations, or source notes.

## Figure Or Table Decision

- Use charts for trends, distribution, composition, comparison, and anomalies.
- Use tables for exact values, repeated comparable records, scenario matrices, risk registers, source lists, and requirements.
- Use prose or bullets for reasoning, recommendations, and one-off facts.
- If a table cell becomes a paragraph, the section probably should be prose plus a smaller table.

## Figure And Table Labels

For Chinese reports, use localized labels:

- `图 1：月度收入趋势`
- `表 2：样本分布`
- `来源：warehouse.orders，2026 年 1-3 月`
- `注：仅包含付费企业账户。`

Do not use `Figure`, `Table`, `Source`, or `Note` in an otherwise Chinese report unless the user requests bilingual output.

## Data Integrity

- Every important chart/table should state source, time window, segment, and calculation method when relevant.
- Do not round away the meaning of a metric.
- If values are illustrative, say so explicitly: `示意数据，不代表真实业务结论。`
- Keep technical handles unchanged: `weekly_active_accounts`, `warehouse.orders`, `metric_id`.
- For comparisons, show baseline/current, absolute change, and percentage change only when all three are meaningful.
- For forecasts, label scenario, assumption, and confidence level.
- Never create a chart from invented values. If the user gave no data, describe the chart specification instead.

## Table Design

- Chinese table headers should be short and concrete.
- Avoid dense paragraph text inside table cells.
- Right-align numeric columns where comparison matters.
- Keep units in headers when possible: `收入（万元）`, `耗时（小时）`.
- Add notes below the table for口径, not inside every cell.
- Keep status/severity columns compact.
- Use consistent decimal precision across comparable numeric columns.
- Use `—` or `暂无数据` only when the meaning is clear; do not mix missing, zero, and not applicable.

## Chart Writing

- Give charts conclusion-first captions: `图 2：企业客户续约收入连续 3 个季度贡献主要增长`.
- Mention what changed, not just what the axis says.
- Explain anomalies near the chart.
- Keep the text interpretation close to the chart; do not force readers to connect it across sections.

## Citation Style

Use one consistent citation style:

- Footnote-style for formal PDF reports.
- Inline source notes for business reports.
- End reference list for research/whitepaper reports.

Preserve URLs and publication names exactly. Translate the explanation, not the identifier.

## Source Note Templates

```markdown
来源：公司 2025 年年报；作者整理。
注：收入按人民币计，未包含一次性处置收益。
口径：仅统计 2026 年 1-3 月活跃企业账户。
```
