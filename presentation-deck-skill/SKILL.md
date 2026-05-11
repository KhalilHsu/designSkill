---
name: presentation-deck-skill
version: "2026-05-11"
description: "用于生成或改进浏览器原生演示文稿、pitch deck、研究 deck、董事会更新、销售/客户汇报和数据故事。Use when the requested deliverable is a presentation or slide deck, not a long-form report or general web page. Turns analysis, metrics, source material, and user goals into browser-based HTML/CSS/JS decks with audience decision flow, evidence mapping, one-idea-per-slide pacing, Chinese/English deck copy, and accurate chart/source presentation."
---

# Presentation Deck Skill

Use this skill when the user asks to generate a pitch deck, research deck, board update, customer briefing, or data storytelling presentation that runs in a browser. The goal is to turn analysis, database outputs, metrics, screenshots, and source material into a high-signal web deck with clear narrative flow, strong visual hierarchy, accurate evidence, and no bullet-point fatigue.

The technical output target is a web environment. Do not generate `.pptx` files or depend on PowerPoint/Google Slides unless specifically asked. Do not use external presentation frameworks like Marp, Reveal.js, or Spectacle unless specifically asked. Instead, build a web-native slide experience using HTML, CSS, and minimal JS for navigation.

This is a data/business storytelling skill, not a generic "pretty HTML slides" skill. The deck must explain what the audience should believe, what evidence supports it, and where that evidence came from. Visual style matters, but it is secondary to storyline, chart integrity, source traceability, and slide pacing.

This skill uses progressive disclosure. Do not load every reference by default. First identify the audience, presentation goal, and technical output format, then read only the references that are needed.

## Skill Boundary

Use this skill only when the output should behave like a presentation: discrete slides, sequential pacing, live/meeting audience flow, and one idea per slide.

- Use `document-report-skill` instead when the user wants a memo, long-form report, whitepaper, PDF-ready article, research writeup, or source-heavy reading document.
- Use `web-design-skill` instead when the user wants a normal web page, dashboard, product page, app screen, or interactive data view rather than slide pacing.
- If the user says "展示", "分享", or "汇报" without a format, infer from the deliverable: slide deck for live/meeting presentation, report for reading, web page for browsing/interaction. Ask only when this materially changes the result.

## Minimum Rules

Apply these even when no reference file is loaded:

1. Default visible deck copy to the user's prompt language, including titles, labels, controls, legends, source notes, and speaker-facing explanations.
2. For Chinese decks, use Chinese-capable font stacks first; never make Latin display fonts the primary style for Chinese text.
3. Build an evidence map before slide copy. Unsupported claims must be removed, softened, or labeled as `假设` / `示意`.
4. Choose a useful deck length before generating slides. If unspecified, use 5-7 slides for a short briefing, 8-12 for pitch/sales/customer decks, 6-10 for board/research updates, and add appendix slides only when the user asks for depth.
5. Enforce one idea per slide and fix slides that exceed presentation density instead of shrinking text until it fits.

## Core Workflow

1. Clarify the audience and goal:
   - Is this a VC pitch, a sales deck, an internal board update, or an educational keynote?
   - What is the ONE main takeaway the audience should remember?
   - What source material exists: database export, SQL result, metrics table, analysis memo, screenshots, research notes, or rough claims?
   - Confirm the desired output: web-native HTML/CSS/JS slide deck, React components with slide behavior, or just a detailed textual outline.
   - Confirm or infer target length: quick briefing, standard deck, or deep deck with appendix.
   - Match the deck copy language to the user's prompt language unless the user explicitly asks for another language.

2. Build the evidence map before writing slides:
   - List the core claims the deck needs to make.
   - For each claim, attach the supporting evidence: metric, query result, chart input, customer quote, screenshot, source document, or assumption.
   - Mark unsupported claims explicitly and either remove them, soften the wording, or ask for the missing source.

3. Build the Narrative Arc before writing slides:
   - **Crucial:** Do not just start listing features. Use the "Audience Decision Flow" approach. What questions is the audience asking in their head, and in what order?
   - If generating a Pitch Deck, structure around standard VC questions (Problem, Solution, Market, Traction, Team, Ask).
   - Read `references/narrative-structure.md` to design the story arc.

4. Enforce "One Idea Per Slide":
   - Break down the narrative. If a slide has three distinct points, it should probably be three slides.
   - Read `references/slide-composition.md` for slide archetypes (Hero, Big Number, Split, Matrix).

5. Design the Visual Hierarchy and Charts:
   - Use massive text for key metrics.
   - Summarize data into "Conclusion-First" charts (e.g., instead of "Q3 Revenue", use "Q3 Revenue Doubled YoY").
   - Keep chart values accurate. Simplify the visual form, not the underlying data.
   - Read `references/typography-hierarchy.md` and `references/visual-assets-charts.md`.

6. Output the Deck (Web-Native):
   - Generate the code using HTML, CSS (like Tailwind or Vanilla), and JS to create a web-based slide viewer interface (e.g., full-viewport sections, CSS scroll-snapping, or JS-based left/right arrow navigation).
   - Ensure the aspect ratio mimics standard slides (typically 16:9).
   - Read `references/implementation-patterns.md` for specific web-native slide syntax.

7. Final Quality Check:
   - Read `references/quality-rubric.md`.
   - Fix slides with more than 40 words, weak titles, unsupported claims, muddy data visualization, or broken web layouts.

## Reference Routing

Read references based on the current presentation design phase:

- Source boundaries and external inspiration for this skill: read `references/source-notes.md`.
- Overall story arc, investor Q&A flow, data-claim sequencing, pacing, and structure: read `references/narrative-structure.md`.
- Visual theme, color palettes, and typographic mood: read `references/style-archetypes.md`.
- Slide layout, avoiding bullet fatigue, single-idea focus: read `references/slide-composition.md`.
- Font scaling, high-contrast text, minimal reading effort: read `references/typography-hierarchy.md`.
- Data visualization, diagrams, metrics display: read `references/visual-assets-charts.md`.
- Code generation (web-native HTML/CSS/JS slide architectures): read `references/implementation-patterns.md`.
- Final check against presentation anti-patterns: read `references/quality-rubric.md`.

## Language Behavior

- Default all visible deck copy to the user's prompt language.
- If the user asks in Chinese, generate Chinese titles, body copy, labels, notes, controls, and source explanations by default.
- Preserve explicit brand names, product names, dataset names, table names, query IDs, metrics IDs, code snippets, and proper nouns in the language or notation provided.
- If the user requests a bilingual deck, define the language structure deliberately instead of mixing languages casually.
- Avoid literal machine translation. Write natural presentation copy for the selected audience and language.
- For Chinese decks, use Chinese punctuation in prose and UI labels: `，` `。` `：` `；` `（ ）`. Keep ASCII punctuation inside code, URLs, query IDs, filenames, and technical identifiers.
- For Chinese data slides, use natural labels and units such as `来源：`, `假设：`, `样本：`, `同比`, `环比`, `近 30 天`, `万元`, and `n=`.
- For Chinese typography, prefer the font guidance in `references/typography-hierarchy.md` before applying any Latin font recommendations from style archetypes.

## Anti-Patterns

- Do not generate a scrolling article, dashboard, or landing page and call it a deck.
- Do not turn a presentation into a report by filling slides with paragraphs, footnotes, and dense tables.
- Do not use generic slide titles such as `Overview`, `Metrics`, `背景`, or `数据分析` when a conclusion title is possible.
- Do not invent numbers, citations, source tables, customer quotes, market sizes, or chart values.
- Do not hide missing evidence behind confident pitch language.
- Do not mix English slide chrome into a Chinese deck unless the user asked for bilingual output.
- Do not rely on Latin-only display fonts for Chinese copy; the fallback glyphs will make the visual system accidental.
- Do not produce 20-30 slides by default. Expand only when the source material and user goal justify it.
