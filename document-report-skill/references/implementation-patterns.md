# Chinese Report Implementation Patterns

Read this when outputting Markdown, HTML, or PDF-ready report artifacts. Do not generate raw `.pdf` binaries directly. Instead, generate the source code (Markdown or HTML) that renders beautifully into a PDF.

## 1. Markdown (The Data Science / Pandoc Workflow)

Use Markdown when the user wants portable source text or is using an automated pipeline such as Pandoc or `convert-markdown`.

- Include YAML frontmatter when targeting Pandoc/PDF metadata.
- Use Chinese headings and captions.
- Place source notes directly under figures/tables.

Example:

```markdown
---
title: 2026 年人工智能行业白皮书
author: Data Team
date: 2026-05-10
geometry: margin=2cm
---

## 3. 核心发现

> 核心结论：企业客户收入增长主要来自续约扩张，而不是新增客户。

图 1：企业客户 ARR 趋势

来源：warehouse.revenue，2026 年 Q1-Q3。
```

## 2. HTML For PDF (The Paged.js / WeasyPrint Workflow)

When the user wants a highly styled whitepaper that can be printed to PDF, generate a single-file HTML document using print-aware CSS.

- **Structure:** Use semantic HTML (`<article>`, `<section>`, `<figure>`, `<aside>`).
- **Typography:** Use the Chinese font stacks from `typography-readability.md`.
- **Print support:** Use CSS Paged Media for page geometry when the output targets paged PDF tools. Add `@media print` rules for browser print behavior.
- **Paged.js:** If the user wants browser-based pagination with running headers, generated TOCs, or page counters, Paged.js is a useful option. Avoid external CDN dependencies for offline, internal, or dependency-free reports unless the user approves them.
- **No app chrome:** A report artifact should look like a document, not a SaaS dashboard. Avoid decorative nav bars, marketing hero sections, and interactive controls unless the user asked for a web report.

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>研究报告</title>
  <style>
    /* Insert CSS from layout-grids.md and typography-readability.md here */
  </style>
</head>
<body>
  <div class="cover-page">
    <h1>2026 数据基础设施报告</h1>
    <p>作者：研究团队</p>
  </div>

  <section class="chapter">
    <h2>1. 摘要</h2>
    <p>核心发现如下...</p>
  </section>
</body>
</html>
```

## 3. Data Report Markdown Pattern

Use this pattern when the user gives data or asks for operational reporting:

```markdown
## 摘要

核心结论：近 30 天企业客户收入增长主要来自存量扩张。

## 关键指标

| 指标 | 当前 | 上期 | 变化 |
| --- | ---: | ---: | ---: |
| 净收入留存率 | 118% | 112% | +6pp |

来源：warehouse.revenue，2026 年 4 月。

## 变化原因

1. 续约合同扩张贡献最大。
2. 新增客户数稳定，但客单价未显著提升。

## 建议

优先复盘续约扩张场景，并把销售剧本拆成可复制动作。
```

## 4. Print CSS Checklist

For print/PDF-ready HTML:

- define `@page` size and margins
- set comfortable body measure
- use `break-inside: avoid` for figures, tables, callouts, and code blocks
- use `break-after: avoid` for headings
- keep captions and source notes adjacent to their figure/table
- hide non-print controls under `@media print`
- test long tables, long headings, and narrow mobile widths if the artifact is also a web page

## 5. LaTeX

Only use LaTeX when the user asks for it or the project already has a LaTeX pipeline. Chinese LaTeX needs explicit CJK handling (e.g., `ctex` package or XeLaTeX); do not assume a Latin-only template works.

## 6. Binary DOCX/PDF Handoff

If the user explicitly wants `.docx` or `.pdf`:

- Use this skill for report architecture, evidence, writing, citations, tables/figures, and style intent.
- Use a dedicated DOCX/PDF skill or existing project pipeline for binary construction and visual render QA.
- Preserve this skill's evidence and language rules in the downstream artifact.

## 7. Output Safety

- Do not invent citations, URLs, datasets, or authors.
- Mark missing data as assumptions or placeholders.
- Preserve technical identifiers exactly.
- Remove placeholder text before delivery unless the placeholder is intentionally labeled as missing input.
