---
name: web-design-skill
version: "2026-05-11"
description: "用于生成或改进网页、落地页、产品页、Web app screen、dashboard、文档页和交互式前端 UI。Use when the requested deliverable is a browsable web page or app UI, not a slide deck or long-form report. Produces polished, responsive, accessible HTML/CSS, React, or Next.js code by defining visual direction, design tokens, layout composition, components, interactions, data-aware structure, and quality checks."
---

# Web Design Skill

Use this skill when the user asks to generate, redesign, polish, or implement a web page or web UI. The goal is production-quality code with a clear visual point of view, not generic template output.

This skill uses progressive disclosure. Do not load every reference by default. First identify the page type, data source, stack, and main design problem, then read only the references that are needed.

## Skill Boundary

Use this skill when the output should be browsed, clicked, scanned, or operated as a web page/app UI.

- Use `presentation-deck-skill` instead when the user wants a slide deck, pitch deck, board update, meeting presentation, or sequential data story.
- Use `document-report-skill` instead when the user wants a memo, report, whitepaper, PDF-ready document, investment note, or long-form analysis artifact.
- For ambiguous requests like "把这些数据做成一个展示", route by surface: interactive/browsable page -> this skill; live/meeting slides -> presentation deck; reading/printing/shareable memo -> document report.
- Do not narrow this skill to one page family. It should stay general across landing pages, app screens, dashboards, data pages, and documentation pages while making the deliverable boundary explicit.

## Minimum Rules

Apply these even when no reference file is loaded:

1. Identify page/UI type, stack, data/source status, audience, and primary user task before implementation.
2. Preserve provided business fields, records, media, labels, filters, table names, view names, query IDs, metric IDs, date ranges, and metric definitions; do not replace them with generic mock content.
3. Default visible copy to the user's prompt language and use Chinese-capable font stacks for Chinese UI.
4. Choose layout from content/data shape instead of forcing a default dashboard, SaaS landing page, or card grid.
5. Run the quality gate before final output and fix weak hierarchy, missing states, poor contrast, fake data access, broken assets, and brittle responsive behavior.

## Core Workflow

1. Clarify the target when ambiguity would materially change the result:
   - If page type, technical stack, content, audience, or constraints are missing and cannot be safely inferred, ask 1-3 concise questions.
   - Prefer short choice-based questions, but do not block on clarification when a reasonable default can be chosen.
   - If proceeding with assumptions, state them briefly before implementation.
   - Confirm the technical stack: plain HTML/CSS, React, Next.js, Tailwind, or existing project conventions.
   - Identify the primary audience, required content, data source, and desired visual direction.

2. Identify data and assets before layout:
   - Prefer user-provided business data, schema, records, fields, images, and existing project assets over invented content.
   - Do not invent API calls, dependencies, local image paths, or business fields that are not provided or present in the project.
   - If data shape matters, read `references/data-driven-generation.md` before choosing layout.
   - Only create mock content when the user asks for a demo, no real data exists, or placeholders are needed to preview the design.

3. Choose a visual direction before writing code.
   - If the user gave a style, honor it.
   - If not, pick a fitting direction and state it briefly in implementation notes.
   - Keep aesthetic language such as premium, cinematic, editorial, playful, calm, precise, or expressive, but translate it into visible choices in layout, typography, color, imagery, and density.
   - Read `references/style-archetypes.md` when selecting or combining visual styles.

4. Define design tokens before composing the UI.
   - Colors: canvas, surfaces, text, borders, accents, semantic states.
   - Typography: display, headings, body, labels, captions, line-height, letter spacing.
   - Spacing: base unit, section rhythm, grid gap, component padding.
   - Shape and elevation: radii, borders, shadows, surface layering.
   - Read `references/visual-systems.md` and `references/typography-color.md` when token choices matter.

5. Build information hierarchy and layout composition.
   - Establish primary message or task.
   - Create a clear top-to-bottom rhythm.
   - Use contained, full-bleed, split, grid, and card layouts intentionally.
   - Read `references/layout-composition.md` for page structure decisions.

6. Implement components with real states.
   - Buttons, nav, cards, forms, badges, tabs, tables, screenshots, empty states, or content blocks as appropriate.
   - Name components by their product role before implementing them, such as `pricing-card`, `source-filter`, `insight-table`, or `top-nav`.
   - Include hover, focus, active, disabled, loading, and responsive states when relevant.
   - Read `references/components-states.md` and `references/interaction-motion.md` when interaction detail matters.

7. Make it responsive and accessible.
   - Use semantic HTML.
   - Preserve keyboard focus.
   - Meet contrast requirements.
   - Respect reduced-motion preferences.
   - Read `references/responsive-accessibility.md` for constraints.

8. Output working code.
   - Follow existing project conventions if editing a repo.
   - Prefer CSS variables or design tokens over one-off hard-coded values.
   - Do not rely on unavailable brand fonts, image assets, component libraries, or API endpoints.
   - Read `references/implementation-patterns.md` for code structure.

9. Self-check before finalizing.
   - Read `references/quality-rubric.md`.
   - Fix obvious template feel, weak hierarchy, inconsistent spacing, missing states, poor contrast, brittle responsive behavior, fake data access, missing dependencies, or broken assets.

## Reference Routing

Read references based on the current design problem:

- Data-driven pages, database records, generated pages, dashboards, score pages, profile/detail pages: read `references/data-driven-generation.md`.
- Visual direction, mood, brand feel, or avoiding generic templates: read `references/style-archetypes.md` and, if needed, `references/design-principles.md`.
- Tokens, surfaces, density, imagery model, radius, elevation: read `references/visual-systems.md`.
- Typography scale, font choice, color roles, contrast, gradients: read `references/typography-color.md`.
- Page structure, section order, hero, grids, app shells, dense layouts: read `references/layout-composition.md`.
- Buttons, cards, navigation, forms, tables, loading/empty/error states: read `references/components-states.md`.
- Hover, focus, active, loading motion, scroll behavior, reduced motion: read `references/interaction-motion.md`.
- Mobile behavior, semantic HTML, keyboard access, ARIA, contrast: read `references/responsive-accessibility.md`.
- Plain HTML/CSS, React, Next.js, Tailwind, dependency and asset handling: read `references/implementation-patterns.md`.
- Final check before delivery: read `references/quality-rubric.md`.
- Source provenance and brand abstraction history: read `references/source-notes.md` only when asked about where the design guidance came from.

## Language And Copy Rules

- Default page copy must follow the user's prompt language.
- If the user asks in Chinese, generate Chinese page content by default.
- If the user asks in English, generate English page content by default.
- Preserve explicit brand names, product names, technical terms, and proper nouns in the language provided by the user.
- Do not translate proper nouns unless the user asks.
- If the user requests a multilingual page, define the language structure explicitly.
- Do not default to English just because the implementation uses HTML, CSS, React, Next.js, or another English-heavy technical stack.
- Avoid machine-translated copy. Write natural copy for the selected language and audience.
- For Chinese UI, rewrite copy for Chinese scanning rhythm instead of translating English labels word-for-word.
- Use Chinese punctuation in Chinese copy: `，` `。` `：` `；` `（ ）`. Keep ASCII punctuation inside code, URLs, query IDs, filenames, and technical identifiers.
- Preserve common product/technical nouns when they are clearer in English, but explain the surrounding UI in Chinese.
- Keep Chinese button labels short and action-oriented, usually 2-6 characters when possible.
- For data-backed Chinese pages, use natural units and labels such as `万元`, `同比`, `环比`, `近 30 天`, `样本 n=`, and `来源：`.

## Style Selection Rules

- Do not copy a brand system verbatim unless explicitly asked.
- Use source references as archetypes, not as default tokens or public-facing attribution.
- Avoid default SaaS sameness: white page, purple CTA, generic cards, system font, no atmosphere.
- A page should have one dominant visual idea: precision, editorial calm, playful productivity, cinematic product focus, command-center utility, warm craft, or another coherent direction.
- More color is not automatically more designed. More restraint is not automatically more premium.
- Do not flatten aesthetic direction into fixed templates. Use aesthetic words as intent, then make visible design choices that express that intent.

## Output Standards

- Generate complete, runnable code for the requested stack.
- Include enough structure and sample content to judge the design.
- Prefer expressive but maintainable CSS.
- Avoid placeholder-only layouts unless the user specifically requests a wireframe.
- For frontend repo edits, run the available formatter/test/build commands when feasible.
- For data-backed products, preserve and use the provided business fields instead of replacing them with generic mock content.

## Anti-Patterns

- Do not solve report or deck requests by wrapping long text or slides in a generic web page.
- Do not invent APIs, datasets, image URLs, package dependencies, component libraries, or brand assets.
- Do not expose internal source-reference names in generated user-facing copy unless the user explicitly asks about provenance.
- Do not default every data request to a dashboard. Choose page structure from the data relationship and user task.
- Do not rely on Latin-only display fonts for Chinese UI.
- Do not ship static-only controls for an app UI when hover, focus, active, disabled, loading, empty, and error states are expected.

## Compact Example

User: `把 inventory_dashboard 视图做成一个好看的页面。`

Internal routing:
- Surface: browsable data page, not report or slide deck.
- Data handles: `inventory_dashboard`, selected filters, visible fields, metric IDs, refresh time, and any available row/media records.
- Required references: `data-driven-generation.md`, `style-archetypes.md`, `layout-composition.md`, `components-states.md`, `quality-rubric.md`.

Output shape:
- A compact web page or app screen with summary metrics, primary table/list/detail area, source/update metadata, filter/search states, empty/loading/error states, and responsive layout.
- Chinese UI copy by default when the user prompt is Chinese; preserve table/view/query identifiers exactly.

## Reference Map

- `references/design-principles.md`: universal principles distilled from the sources.
- `references/data-driven-generation.md`: choosing structure from business data, schema, fields, media, density, and relationships.
- `references/style-archetypes.md`: reusable visual directions derived from brand references.
- `references/visual-systems.md`: surfaces, space, shape, elevation, imagery, and density.
- `references/layout-composition.md`: page structure and section rhythm.
- `references/typography-color.md`: type scale, font pairing, color systems, contrast.
- `references/components-states.md`: component anatomy and state design.
- `references/interaction-motion.md`: hover, focus, loading, scroll, and motion.
- `references/responsive-accessibility.md`: responsive and accessibility requirements.
- `references/implementation-patterns.md`: HTML/CSS/React/Next.js implementation guidance.
- `references/quality-rubric.md`: final design and code quality checklist.
- `references/source-notes.md`: source-derived observations and how they were abstracted.
