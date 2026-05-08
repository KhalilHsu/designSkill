# Interaction And Motion

## Interaction Principles

Interactions should clarify state and affordance. They should not be decorative noise.

## Hover

Good hover states:

- Slight surface shift.
- Border or shadow change.
- Text/accent color change.
- Small transform only when appropriate.

Avoid large movement on dense UI elements.

## Focus

Focus-visible must be obvious. Use an outline, ring, or strong border that fits the visual system.

Do not remove outlines unless replacing them with an accessible equivalent.

## Active And Pressed

Pressed states can use:

- Slight downward transform.
- Darkened fill.
- Reduced shadow.
- Inset highlight.

Keep active feedback quick.

## Loading

Use loading patterns based on task:

- Skeletons for content areas.
- Spinner for short isolated actions.
- Progress indicator for longer tasks.
- Disabled button with preserved width for submitting.

## Motion Timing

Default ranges:

- Micro interactions: 120-180ms.
- Surface transitions: 180-260ms.
- Page/section reveal: 300-600ms.

Use easing that feels physical, not linear.

## Page Motion

Meaningful page motion:

- Staggered content reveal.
- Subtle hero entrance.
- Scroll-linked background or visual anchor.
- Reduced-motion fallback.

Avoid animating large amounts of text or essential controls.

## Reduced Motion

Always include:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
```
