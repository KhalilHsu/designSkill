# Components And States

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
