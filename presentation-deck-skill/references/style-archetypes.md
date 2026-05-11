# Presentation Style Archetypes

Read this when the user asks for a specific visual style, "vibe", or theme for their presentation. Do not mix archetypes; stick strictly to one visual language to ensure a cohesive deck.

Choose style from audience, evidence density, and decision context. Do not choose style only from personal taste. A VC pitch can tolerate more contrast and personality; a board or research deck needs calmer evidence density; a customer deck needs product clarity.

If the user does not specify a style, default to **Data Executive Clean** for board/research decks and **High-Contrast Startup** for fundraising or launch decks.

Translate these archetypes into concrete CSS variables (Tokens) in the `:root` of the generated HTML.

## Chinese Typography Guardrail

The font examples below describe Latin mood only. For Chinese or mixed Chinese/English decks, read `typography-hierarchy.md` and use Chinese-capable stacks as the primary typography. Express the archetype through weight, spacing, contrast, layout, and color instead of relying on Latin-only display fonts.

## 1. High-Contrast Startup
Use for fundraising, product launches, and category-creation decks where the deck needs to feel decisive and memorable.
- **Mood:** Energetic, opinionated, slightly raw, high contrast.
- **Color Tokens:**
  - `--bg`: `#0f172a` (Very dark slate/navy) OR `#ffffff` (Pure white).
  - `--text-main`: `#f8fafc` (on dark) OR `#000000` (on light).
  - `--text-muted`: `#94a3b8` (on dark) OR `#64748b` (on light).
  - `--accent`: A highly saturated neon (e.g., `#3b82f6` Blue, `#f97316` Orange, or `#10b981` Emerald).
- **Typography:**
  - Headers: Heavy, tight geometric sans-serif (e.g., `Space Grotesk`, `Syne`, or `Clash Display`).
  - Body: Highly readable sans-serif.
  - Chinese decks: use the Chinese sans stack from `typography-hierarchy.md`; keep the high-contrast mood through heavier weights, short titles, and decisive color.
- **Visuals:** Hard borders, bold geometric shapes, large metric moments, and decisive contrast. Keep decorative effects secondary to the main claim.

## 2. Editorial Authority
Use for research briefings, thesis decks, market maps, and whitepaper-style presentations.
- **Mood:** Quiet, expensive, confident, spacious.
- **Color Tokens:**
  - `--bg`: `#fdfbf7` (Warm off-white, paper-like) or `#1a1a1a` (Charcoal).
  - `--text-main`: `#2c2c2c` (Soft black).
  - `--text-muted`: `#8a8a8a`.
  - `--accent`: Deep, muted tones (e.g., `#4a5568` Slate, `#713f12` Deep Brown, or `#064e3b` Forest Green).
- **Typography:**
  - Headers: Elegant Serif with high contrast between thick and thin strokes (e.g., `Playfair Display`, `Merriweather`, or `Lora`).
  - Body: Refined, light sans-serif (e.g., `Lato`, `Montserrat`) with generous line-height (`1.6`).
  - Chinese decks: use `Noto Serif SC`, `Source Han Serif SC`, `Songti SC`, or `STSong` only for large editorial titles; keep labels, charts, and dense notes in Chinese sans.
- **Visuals:** Generous negative space, thin rules, numbered sections, pull quotes, source notes, and carefully framed charts.

## 3. Data Executive Clean
Use for board updates, operating reviews, customer ROI decks, and investor updates where credibility matters more than personality.
- **Mood:** Trustworthy, data-dense, objective, structural.
- **Color Tokens:**
  - `--bg`: `#ffffff` (Pure white).
  - `--text-main`: `#111827` (Very dark gray).
  - `--text-muted`: `#4b5563`.
  - `--accent`: Corporate Blue (`#0ea5e9`) or Trustworthy Navy (`#1e3a8a`).
- **Typography:**
  - Headers: Classic, sturdy sans-serif (e.g., `Helvetica Neue`, `Arial`, or `Open Sans`).
  - Body: Same as headers, or a very readable serif (e.g., `Georgia`).
  - Chinese decks: use the Chinese sans stack and numeric stack from `typography-hierarchy.md`.
- **Visuals:** Clean grid lines, subtle dividers, restrained color, clear tables, precise chart labels, and visible source/caveat treatment.

## 4. Technical Console
Use for deep-tech demos, developer audiences, security, infrastructure, data tooling, and AI engineering narratives.
- **Mood:** Nocturnal, technical, intense, code-centric.
- **Color Tokens:**
  - `--bg`: `#000000` (Pure black).
  - `--text-main`: `#10b981` (Terminal Green) or `#f59e0b` (Amber).
  - `--text-muted`: `#047857` (Dimmer green).
  - `--accent`: `#ffffff` (White for extreme highlights) or `#ef4444` (Error Red).
- **Typography:**
  - Headers & Body: Monospace fonts ONLY (e.g., `Fira Code`, `JetBrains Mono`, `Courier New`).
  - Chinese decks: use monospace only for code/query fragments. Use Chinese sans for claims, labels, and explanation text.
- **Visuals:** Code panels, query snippets, terminal-like evidence blocks, trace diagrams, and high-contrast borders. Avoid making every slide look like a fake terminal if the evidence is business data.

## Implementation Note for AI
When applying a style, ensure the CSS `:root` variables follow the chosen archetype's color palette. If importing web fonts, keep the deck usable while fonts load and avoid making the font choice the main design idea.
