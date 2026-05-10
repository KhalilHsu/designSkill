# Slide Composition & Layouts

Read this to determine the structural grid of individual slides. A slide is not a document; it must be scannable in 3 seconds.

## The Golden Rule: One Idea Per Slide
If a slide contains a market size chart, a list of competitors, and a product screenshot, it is broken. Split it into three slides.

## Core Layout Archetypes

Do not invent complex, fragile DOM structures. Rely on these stable, high-impact archetypes:

### 1. The Hero / Title Slide
- **Use for:** Intros, section breaks, major announcements.
- **Structure:** Massive, vertically and horizontally centered text. High contrast background. Minimal or zero secondary text.

### 2. The Split (50/50 or 40/60)
- **Use for:** Comparing "Before vs. After", text explanation paired with a strong visual (screenshot, diagram).
- **Structure:** Two-column CSS Grid.
  - Left column: The punchy claim (H1) and minimal supporting text.
  - Right column: The visual evidence.

### 3. The Big Number (Metric Panel)
- **Use for:** Highlighting traction, market size, or key ROI.
- **Structure:** The number takes up 40% of the viewport height. The label is underneath. No other distracting elements.
- *Example:* "1.2M" (Huge) -> "Active Daily Users" (Small).

### 4. The Grid / Matrix (3 or 4 Columns)
- **Use for:** Value props, feature highlights, or pricing tiers.
- **Structure:** 3x1 or 2x2 CSS Grid. Each cell gets a simple icon/number, a short header, and exactly one sentence of text.

### 5. The "Full Bleed" Image/Quote
- **Use for:** Emotional impact, setting the scene, or ending the presentation.
- **Structure:** Background image covering the whole viewport (`background-size: cover`), with a dark overlay and a single, powerful centered quote.

## Anti-Patterns (Do NOT do this)

- **Bullet Point Fatigue:** Never use standard `<ul><li>` bullet lists with more than 3 items. Never nest bullets. If you have 5 points, use a Grid layout or make 5 separate slides.
- **Wall of Text:** No paragraph should exceed 3 lines on a slide.
- **Logo Soup:** If placing logos (clients/investors), align them strictly in a grid with equal visual weight. Do not randomly scatter them.
