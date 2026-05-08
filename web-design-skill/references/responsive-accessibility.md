# Responsive And Accessibility

## Responsive Behavior

Design mobile and desktop deliberately:

- Desktop can use wide grids, split layouts, and large visual anchors.
- Tablet often needs reduced columns and tighter hero visuals.
- Mobile needs reordered content, shorter line lengths, larger hit areas, and simplified navigation.

Do not only shrink desktop.

## Breakpoint Guidance

Common breakpoints:

- Mobile: under 640px.
- Tablet: 640-1024px.
- Desktop: above 1024px.
- Wide: above 1280px.

Use content-based breakpoints when possible.

## Mobile Priorities

On mobile:

- Keep primary message visible quickly.
- Stack columns.
- Reduce section gaps.
- Convert wide tables into cards or horizontal scroll only when necessary.
- Keep buttons and inputs at least 44px tall.

## Semantic HTML

Use semantic elements:

- `header`
- `nav`
- `main`
- `section`
- `article`
- `aside`
- `footer`
- `button`
- `form`
- `label`

Do not use clickable `div`s when a `button` or `a` is correct.

## Keyboard Access

Ensure:

- Interactive elements are keyboard reachable.
- Focus order matches visual order.
- Focus states are visible.
- Menus, tabs, and dialogs follow expected keyboard behavior when implemented.

## Contrast

Check contrast for:

- Body text.
- Muted text.
- Button labels.
- Links.
- Focus rings.
- Error messages.

Dark themes often need brighter secondary text than expected.

## Motion And Accessibility

Respect `prefers-reduced-motion`. Avoid motion that is required to understand content.

## ARIA

Use ARIA only when native HTML is insufficient. Incorrect ARIA is worse than no ARIA.

Use:

- `aria-label` for icon-only controls.
- `aria-current` for active navigation.
- `aria-expanded` for disclosure controls.
- `aria-describedby` for helper/error text.
