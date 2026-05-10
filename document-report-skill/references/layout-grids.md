# Chinese Report Layout And Print Grids

Read this when rendering a report to HTML/PDF or designing long-form page layout.

## Layout Principles

- Long Chinese reports need comfortable line length more than decorative page furniture.
- Use a constrained main column with optional side notes, not full-width paragraphs.
- Keep charts and tables close to the paragraph that interprets them.
- Use callout boxes for conclusions, assumptions, risks, and recommendations.

## Web Report Layout

Good default:

```css
.report {
  max-width: 980px;
  margin: 0 auto;
  padding: 48px 28px;
}
.body-text {
  max-width: 42em; /* Optimal for Chinese reading */
  line-height: 1.75;
}
figure, table, .callout {
  break-inside: avoid;
}
```

## PDF / Print Layout (CSS Paged Media)

When generating HTML destined for PDF, use CSS Paged Media (`@page`) for page size, margins, running headers, and page numbers when the renderer supports it. Combine it with `@media print` for browser print behavior such as hiding controls, adjusting colors, and improving page breaks.

```css
@page {
  size: A4;
  margin: 25mm 20mm 25mm 20mm;

  /* Page Numbers */
  @bottom-right {
    content: counter(page);
    font-family: var(--font-sans);
    font-size: 9pt;
    color: #666;
  }

  /* Running Header */
  @top-left {
    content: string(chapter);
    font-family: var(--font-sans);
    font-size: 9pt;
    color: #999;
  }
}

/* Force chapter titles to update the running header */
h2 {
  string-set: chapter content();
  break-before: page; /* Start new chapter on a new page */
}

/* Cover Page Rules */
.cover-page {
  page: cover;
  break-after: page;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  min-height: 80vh;
}

/* Prevent awkward breaks */
h1, h2, h3, h4 { break-after: avoid; }
figure, table, pre, .summary-box { break-inside: avoid; }
p { orphans: 2; widows: 2; }
```

## Chinese Page Furniture

- Header/footer can include report title, chapter name, page number, and confidentiality level (e.g., `机密 / Confidential`).
- Use Chinese labels: `目录`, `摘要`, `附录`, `参考资料`.
- Avoid English running headers in Chinese reports unless requested.
