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

Name components and classes by role before styling them. The component names in code should match the inventory from `components-states.md`:

- Good: `TopNav`, `MetricStrip`, `SourceFilter`, `InsightTable`, `RecordMasthead`, `.pricing-card`, `.activity-feed`.
- Weak: `Box`, `Panel2`, `BlueCard`, `.fancy`, `.left`.

For repeated patterns, keep the base primitive clear and add role-specific variants only where the product behavior differs, such as `.card`, `.pricing-card`, `.metric-card`, and `.media-card`.

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
- Check existing project dependencies and component conventions before choosing primitives.
- Use existing design-system components when present.
- Simple components such as buttons, cards, badges, section headers, and static rows can be handwritten.
- Complex interactive components such as dialogs, dropdowns, popovers, comboboxes, tooltips, and full keyboard-managed tabs should use existing Radix UI, shadcn/ui, Headless UI, or project primitives when available.
- Do not assume Radix UI, shadcn/ui, Tailwind, or lucide-react are installed. If a dependency is not present and cannot be added, use a simpler native or static pattern instead of a fragile custom focus trap.

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

## Vanilla CSS And CSS Modules

When the project does not use Tailwind:

- Organize CSS in this order: tokens, base elements, layout primitives, components, states, responsive rules.
- Put reusable tokens in `:root`, a theme file, or the existing project token layer.
- Name classes by component role and structure, not visual decoration alone.
- Use state selectors such as `[data-state="loading"]`, `[aria-current="page"]`, `:hover`, `:focus-visible`, and `[disabled]`.
- Keep layout utilities sparse and intentional.
- Avoid recreating Tailwind as many one-off utility classes unless the project already follows a utility-first pattern.
- For CSS Modules, keep tokens global or imported from the project theme; keep module classes local to the component.

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

Use assets in this order:

- User-provided business data: image fields, avatars, product photos, covers, screenshots, media URLs.
- Existing project assets.
- Generated or explicitly stable external assets when appropriate for a demo or prototype.
- Styled CSS visuals, frames, and mock UI panels when real imagery is unavailable.
- Inline SVG icons only when useful and not better served by an existing icon library.

Do not reference nonexistent image paths. Do not use random external images for production-like output unless the user accepts that tradeoff.

## Data And Mocking

For data-backed products:

- Preserve the provided schema and business fields.
- Do not replace real data with generic sample records.
- Do not fake network requests to nonexistent APIs.
- If mock data is necessary for a standalone demo, keep it structured and close to the expected business data.
- Add loading, empty, or error states only when they are relevant to the requested UI or existing product flow.
- Unless the user asks for an interactive demo, model loading/empty/error as rendered state slices or externally supplied props, not internal timers or fake lifecycle flows.

## Final Verification

Before delivery:

- Confirm the page works at mobile and desktop widths.
- Confirm primary action is visible.
- Confirm text contrast is strong.
- Confirm layout does not rely on unavailable fonts or images.
- Confirm component states exist when relevant.
