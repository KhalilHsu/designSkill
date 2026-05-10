---
name: presentation-deck-skill
description: Use when generating web-native pitch decks, research decks, board updates, or data storytelling presentations for AI/database products. Turns analysis, metrics, source material, and user goals into browser-based HTML/CSS/JS decks by establishing audience, narrative arc, evidence mapping, one-idea-per-slide structure, and accurate chart presentation.
---

# Presentation Deck Skill

Use this skill when the user asks to generate a pitch deck, research deck, board update, customer briefing, or data storytelling presentation that runs in a browser. The goal is to turn analysis, database outputs, metrics, screenshots, and source material into a high-signal web deck with clear narrative flow, strong visual hierarchy, accurate evidence, and no bullet-point fatigue.

The technical output target is a web environment. Do not generate `.pptx` files or depend on PowerPoint/Google Slides unless specifically asked. Do not use external presentation frameworks like Marp, Reveal.js, or Spectacle unless specifically asked. Instead, build a web-native slide experience using HTML, CSS, and minimal JS for navigation.

This is a data/business storytelling skill, not a generic "pretty HTML slides" skill. The deck must explain what the audience should believe, what evidence supports it, and where that evidence came from. Visual style matters, but it is secondary to storyline, chart integrity, source traceability, and slide pacing.

This skill uses progressive disclosure. Do not load every reference by default. First identify the audience, presentation goal, and technical output format, then read only the references that are needed.

## Core Workflow

1. Clarify the audience and goal:
   - Is this a VC pitch, a sales deck, an internal board update, or an educational keynote?
   - What is the ONE main takeaway the audience should remember?
   - What source material exists: database export, SQL result, metrics table, analysis memo, screenshots, research notes, or rough claims?
   - Confirm the desired output: web-native HTML/CSS/JS slide deck, React components with slide behavior, or just a detailed textual outline.
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
