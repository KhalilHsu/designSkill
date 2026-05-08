---
name: web-design-skill
description: Use when creating or improving high-quality web pages, landing pages, product pages, web app screens, dashboards, marketing pages, documentation pages, or interactive frontend UI. Produces polished, responsive, accessible HTML/CSS, React, or Next.js code by first defining a visual direction, design tokens, layout composition, components, interactions, and a quality rubric.
---

# Web Design Skill

Use this skill when the user asks to generate, redesign, polish, or implement a web page or web UI. The goal is production-quality code with a clear visual point of view, not generic template output.

## Core Workflow

1. Clarify the target only when needed:
   - Page or screen type.
   - Audience and tone.
   - Required content.
   - Technical stack: plain HTML/CSS, React, Next.js, Tailwind, or existing project conventions.
   - Desired visual direction, if provided.

2. Choose a visual direction before writing code.
   - If the user gave a style, honor it.
   - If not, pick a fitting direction and state it briefly in implementation notes.
   - Read `references/style-archetypes.md` when selecting or combining visual styles.

3. Define design tokens before composing the UI.
   - Colors: canvas, surfaces, text, borders, accents, semantic states.
   - Typography: display, headings, body, labels, captions, line-height, letter spacing.
   - Spacing: base unit, section rhythm, grid gap, component padding.
   - Shape and elevation: radii, borders, shadows, surface layering.
   - Read `references/visual-systems.md` and `references/typography-color.md` when token choices matter.

4. Build information hierarchy and layout composition.
   - Establish primary message or task.
   - Create a clear top-to-bottom rhythm.
   - Use contained, full-bleed, split, grid, and card layouts intentionally.
   - Read `references/layout-composition.md` for page structure decisions.

5. Implement components with real states.
   - Buttons, nav, cards, forms, badges, tabs, tables, screenshots, empty states, or content blocks as appropriate.
   - Include hover, focus, active, disabled, loading, and responsive states when relevant.
   - Read `references/components-states.md` and `references/interaction-motion.md` when interaction detail matters.

6. Make it responsive and accessible.
   - Use semantic HTML.
   - Preserve keyboard focus.
   - Meet contrast requirements.
   - Respect reduced-motion preferences.
   - Read `references/responsive-accessibility.md` for constraints.

7. Output working code.
   - Follow existing project conventions if editing a repo.
   - Prefer CSS variables or design tokens over one-off hard-coded values.
   - Do not rely on unavailable brand fonts or image assets unless provided.
   - Read `references/implementation-patterns.md` for code structure.

8. Self-check before finalizing.
   - Read `references/quality-rubric.md`.
   - Fix obvious template feel, weak hierarchy, inconsistent spacing, missing states, poor contrast, or brittle responsive behavior.

## Language And Copy Rules

- Default page copy must follow the user's prompt language.
- If the user asks in Chinese, generate Chinese page content by default.
- If the user asks in English, generate English page content by default.
- Preserve explicit brand names, product names, technical terms, and proper nouns in the language provided by the user.
- Do not translate proper nouns unless the user asks.
- If the user requests a multilingual page, define the language structure explicitly.
- Do not default to English just because the implementation uses HTML, CSS, React, Next.js, or another English-heavy technical stack.
- Avoid machine-translated copy. Write natural copy for the selected language and audience.

## Style Selection Rules

- Do not copy a brand system verbatim unless explicitly asked.
- Use brand references as archetypes, not as default tokens.
- Avoid default SaaS sameness: white page, purple CTA, generic cards, system font, no atmosphere.
- A page should have one dominant visual idea: precision, editorial calm, playful productivity, cinematic product focus, command-center utility, warm craft, or another coherent direction.
- More color is not automatically more designed. More restraint is not automatically more premium.

## Output Standards

- Generate complete, runnable code for the requested stack.
- Include enough structure and sample content to judge the design.
- Prefer expressive but maintainable CSS.
- Avoid placeholder-only layouts unless the user specifically requests a wireframe.
- For frontend repo edits, run the available formatter/test/build commands when feasible.

## Reference Map

- `references/design-principles.md`: universal principles distilled from the sources.
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
