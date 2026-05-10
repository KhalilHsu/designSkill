# Data-Driven Generation

Read this when the page is generated from user data, database records, score objects, business schemas, or existing product content.

## Goal

Use the data shape to decide structure. Do not force every dataset into a generic landing page, card grid, or dashboard template.

After reading this file, choose:

- Primary page job: explain, compare, monitor, edit, browse, sell, summarize, or inspect.
- Data anchor: the field or record that should dominate the first screen.
- Layout mode: detail page, list/grid, dashboard, report, timeline, gallery, comparison, or app shell.
- Media strategy: use provided images/media first, then project assets, then generated/stable external assets, then CSS/mock visuals.

## Data Source Rules

- Prefer user-provided records, schema, field names, images, files, and existing project data.
- Keep real business terms. Do not rename fields into generic marketing labels unless the user asks.
- Do not invent API endpoints, database calls, or fields.
- Do not replace real data with `MOCK_DATA` when real data exists.
- Use mock data only for demos, missing previews, or explicit placeholders. Mock data must mirror the likely business schema.

## Field-To-Layout Selectors

Use these as selectors, not templates:

- Repeated records with shared fields: consider table, grid, kanban, directory, list, or map.
- A single rich record: consider profile, product detail, score report, media article, case study, or inspection page.
- Time fields: consider timeline, activity feed, changelog, calendar grouping, or trend sections.
- Numeric fields: consider KPI strip, scorecard, chart, comparison, ranking, or threshold states.
- Category/status fields: consider filters, tabs, grouped sections, badges, or segmented controls.
- Image/media fields: consider gallery, hero media, editorial cards, product showcase, or visual comparison.
- Long text fields: consider article layout, expandable sections, summary-first detail, or annotation panels.
- Relationships between records: consider master-detail, related items, graph-like grouping, nested sections, or comparison matrix.
- Location fields: consider map/list pairing, region filters, or location cards.

## Density Selection

- High-density operational data: favor compact spacing, tables, filters, sticky controls, and strong alignment.
- Medium-density product/content data: favor cards, grouped sections, detail panels, and visible hierarchy.
- Low-density story or brand data: favor spacious rhythm, larger media, stronger typography, and fewer competing modules.

Density is chosen from the task and data, not from taste alone.

## First Screen

The first screen should answer:

- What record, collection, score, or workflow is this?
- What is the most important value, status, or message?
- What can the user inspect or do next?

For data pages, the hero does not need to be a marketing hero. It can be a summary header, score panel, record masthead, product visual, dashboard header, or focused work area.

## Missing Or Partial Data

When useful fields are missing:

- Do not fabricate precise facts.
- Use layout that still works with sparse records.
- Show unavailable fields as absent, not fake.
- Prefer neutral labels such as "Not provided" only when the UI needs an explicit value.
- Keep empty states useful and tied to the user's next action.

## Data Integrity Checks

Before finalizing:

- The page structure follows the provided data shape.
- Real fields are used where available.
- Images and media come from provided data or known assets when possible.
- No fake API request or nonexistent local asset path was introduced.
- The page still works if optional fields are missing.
