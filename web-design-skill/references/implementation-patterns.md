# Implementation Patterns

## General

Start with tokens:

```css
:root {
  --color-canvas: #f8f6f1;
  --color-surface: #ffffff;
  --color-text: #141414;
  --color-muted: #6b6760;
  --color-border: rgba(20, 20, 20, 0.12);
  --color-accent: #2457ff;
  --radius-card: 24px;
  --radius-control: 999px;
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-12: 48px;
  --space-16: 64px;
}
```

Do not scatter raw values everywhere after defining tokens.

## Plain HTML/CSS

For standalone pages:

- Include semantic HTML.
- Put global tokens at `:root`.
- Define base type styles.
- Define layout utilities sparingly.
- Define components after tokens.
- Include responsive media queries.
- Include reduced-motion handling.

## React

For React:

- Keep components small and named by role.
- Use props for repeated content blocks.
- Keep design tokens in CSS or theme files, not inline style objects by default.
- Avoid unnecessary memoization unless the existing codebase uses it or performance requires it.

## Next.js

For Next.js:

- Use server components unless interactivity is needed.
- Keep page structure clear.
- Use semantic sections.
- Use image optimization only when real assets exist.
- Avoid client components for static marketing content.

## Tailwind

When using Tailwind:

- Still establish a token-like system through CSS variables or theme config.
- Avoid long inconsistent class strings with one-off values.
- Use component extraction for repeated patterns.
- Do not default to standard purple SaaS styling.

## CSS Quality

Prefer:

- CSS variables.
- Fluid type with `clamp()`.
- Grid and flex used for their strengths.
- Logical grouping.
- Accessible focus states.
- Container max-widths.

Avoid:

- Absolute positioning for normal layout.
- Fixed heights for content-heavy sections.
- Overly specific selectors.
- Magic numbers without reason.
- Removing outlines without replacement.

## Asset Handling

If assets are missing:

- Build abstract CSS visuals.
- Use gradients, frames, and mock UI panels.
- Use inline SVG icons when useful.
- Do not reference nonexistent image paths.

## Final Verification

Before delivery:

- Confirm the page works at mobile and desktop widths.
- Confirm primary action is visible.
- Confirm text contrast is strong.
- Confirm layout does not rely on unavailable fonts or images.
- Confirm component states exist when relevant.
