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

## 3. LaTeX

Only use LaTeX when the user asks for it or the project already has a LaTeX pipeline. Chinese LaTeX needs explicit CJK handling (e.g., `ctex` package or XeLaTeX); do not assume a Latin-only template works.

## 4. Output Safety

- Do not invent citations, URLs, datasets, or authors.
- Mark missing data as assumptions or placeholders.
- Preserve technical identifiers exactly.
