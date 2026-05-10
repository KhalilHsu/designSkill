---
name: web-design-skill
description: Use when creating or improving high-quality web pages, landing pages, product pages, web app screens, dashboards, marketing pages, documentation pages, or interactive frontend UI. Produces polished, responsive, accessible HTML/CSS, React, or Next.js code by first defining a visual direction, design tokens, layout composition, components, interactions, and a quality rubric.
---

# Web Design Skill

Use this skill when the user asks to generate, redesign, polish, or implement a web page or web UI. The goal is production-quality code with a clear visual point of view, not generic template output.

This skill uses progressive disclosure. Do not load every reference by default. First identify the page type, data source, stack, and main design problem, then read only the references that are needed.

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
- Use brand references as archetypes, not as default tokens.
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
