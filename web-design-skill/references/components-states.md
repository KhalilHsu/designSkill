# Components And States

Read this when choosing or implementing visible UI components. Use only states that match the requested product flow; do not add artificial async behavior just to show every possible state.

Output after reading:

- Component list.
- Component role names.
- Required states.
- Interaction affordances.
- Empty/loading/error handling when relevant.

## Component Inventory And Names

Before implementing, write a short component inventory in your own notes or implementation plan. Each component should have a role-based name, a purpose, and the states it needs.

Prefer names that describe the product job:

- `top-nav`, `account-switcher`, `source-filter`, `pricing-card`.
- `metric-strip`, `insight-table`, `activity-feed`, `record-masthead`.
- `hero-product-frame`, `feature-proof-card`, `testimonial-row`, `checkout-summary`.

Avoid vague or decoration-first names:

- `box`, `section1`, `blue-card`, `fancy-panel`, `left-column`.

Use generic primitives only when they are truly reusable across contexts, such as `button`, `badge`, `tabs`, `dialog`, or `empty-state`. For page-specific UI, attach the business or workflow role so the design stays tied to the product.

## Component Anatomy

Every component should define:

- Purpose.
- Surface.
- Text style.
- Spacing.
- Shape.
- Border/elevation.
- Icon/image behavior if relevant.
- States.

## Buttons

Button hierarchy:

- Primary: filled, highest contrast, one per local decision area.
- Secondary: outline or lower-contrast fill.
- Tertiary: text or ghost.
- Destructive: only for destructive actions.

States:

- Hover: visible but not jumpy.
- Focus-visible: strong enough for keyboard users.
- Active: tactile feedback.
- Disabled: visibly inactive and non-interactive.
- Loading: preserves size and communicates progress.

## Cards

Cards should group related content. Do not card everything.

Card variants:

- Plain content card.
- Elevated card.
- Accent card.
- Media card.
- Interactive card.
- Data card.

Interactive cards need hover and focus states. Static cards usually need no hover.

## Navigation

Navigation elements need:

- Current/active state.
- Hover state.
- Focus-visible state.
- Responsive collapse or wrapping behavior.
- Clear distinction between links and primary actions.

## Forms

Forms need:

- Labels.
- Placeholder only as supplemental guidance.
- Focus state.
- Error state.
- Disabled state.
- Helper text where useful.
- Adequate hit targets.

Avoid unlabeled inputs.

## Badges And Tags

Badges should communicate category, status, or metadata. Do not use badges as random decoration.

Use pill badges for soft metadata and rectangular badges for more utilitarian status.

## Tables And Data

For data-heavy UI:

- Keep row height and type compact but legible.
- Use alignment for scanability.
- Use color sparingly for status.
- Include hover/focus row states if interactive.
- Keep controls near the data they affect.

## Screenshots And Mockups

When showing a product:

- Put screenshots inside a deliberate frame.
- Use shadows or borders only if they clarify separation.
- Make fake UI content plausible.
- Avoid unreadable mini screenshots that add no information.

## Empty, Loading, And Error States

High-quality UI includes non-happy paths:

- Empty states explain what happened and the next action.
- Loading states preserve layout and avoid jarring shifts.
- Error states are visible, specific, and actionable.

For data-backed pages, base these states on the real product flow. Do not invent network failure states for a static or server-rendered view unless the product actually needs them.

Unless the user asks for an interactive demo, prefer static visual state slices or externally controlled state props over timers, fake async flows, or component lifecycle simulation.

Examples:

- Static markup: use attributes such as `data-state="loading"` or `aria-busy="true"` when rendering a state slice.
- React: prefer props such as `<Panel state="loading" />` or real product data flags over local `useState` plus `setTimeout`.
- Demo-only interactions: use simple state toggles only when the requested output needs the user to switch between states.
