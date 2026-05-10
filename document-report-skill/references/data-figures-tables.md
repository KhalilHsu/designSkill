# Chinese Data, Figures, Tables, And Citations

Read this when the report includes charts, tables, figures, citations, or source notes.

## Figure And Table Labels

For Chinese reports, use localized labels:

- `图 1：月度收入趋势`
- `表 2：样本分布`
- `来源：warehouse.orders，2026 年 1-3 月`
- `注：仅包含付费企业账户。`

Do not use `Figure`, `Table`, `Source`, or `Note` in an otherwise Chinese report unless the user requests bilingual output.

## Data Integrity

- Every important chart/table should state source, time window, segment, and calculation口径 when relevant.
- Do not round away the meaning of a metric.
- If values are illustrative, say so explicitly: `示意数据，不代表真实业务结论。`
- Keep technical handles unchanged: `weekly_active_accounts`, `warehouse.orders`, `metric_id`.

## Table Design

- Chinese table headers should be short and concrete.
- Avoid dense paragraph text inside table cells.
- Right-align numeric columns where comparison matters.
- Keep units in headers when possible: `收入（万元）`, `耗时（小时）`.
- Add notes below the table for口径, not inside every cell.

## Citation Style

Use one consistent citation style:

- Footnote-style for formal PDF reports.
- Inline source notes for business reports.
- End reference list for research/whitepaper reports.

Preserve URLs and publication names exactly. Translate the explanation, not the identifier.
