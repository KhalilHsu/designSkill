# Data Table Product Integration

Read this when the report is generated from a table, spreadsheet, database view, query result, dashboard, chart, selected rows, or product-provided dataset.

## Source Handles

Before drafting, preserve the product's source handles:

- table name or dataset name
- view name, dashboard name, or chart name
- query ID, report ID, or metric ID
- selected columns and selected rows
- filters, segments, date range, and timezone
- row count and sampling rule
- metric definitions and calculation formulas
- user assumptions or manual overrides

Use these handles in source notes. Do not translate code-like identifiers.

## Source Note Patterns

```markdown
来源：表 sales_q2，视图 Enterprise Renewals，筛选条件：region = APAC，时间范围：2026 年 Q2。
口径：收入按 paid_amount_cny 汇总，排除 refunded = true 的订单。
注：本摘要仅基于当前筛选视图，不代表全量客户。
```

If the product exposes a query result:

```markdown
来源：query_id: rev_retention_2026_q2；字段：nrr, expansion_revenue, churned_arr。
```

## Data Access Behavior

- If data is already in context, use it directly and cite the table/query handle.
- If only a table name is provided, request or invoke the host product's data retrieval path before making numeric claims.
- If retrieval is unavailable, write a report outline or analysis plan and mark all numeric claims as `待补数据`.
- If the user selected a subset of rows, state that the report only covers the selection.

## Report Shape

For data-table products, default to the shortest useful artifact:

- Quick summary: key change, likely driver, risk, next action.
- Business memo: conclusion, evidence table, interpretation, recommendation.
- Full report: only when the user asks for export, PDF, client-ready output, board memo, or deep analysis.

## Common Failure Modes

- Treating filtered data as all data.
- Losing the table/view/query identifier in source notes.
- Inventing rows, totals, or time windows not present in the product data.
- Translating field names such as `net_revenue`, `account_id`, or `query_id`.
- Reporting a percentage change without baseline and current values.
