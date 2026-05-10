# Visual Systems

Read this to choose the visual system after the page job, data source, and visual direction are known.

Output after reading:

- Surface model.
- Density level.
- Shape/elevation language.
- Imagery or graphics strategy.
- Token groups needed by the implementation.

## Token Groups

Define tokens before styling components:

- Canvas: page-level background.
- Surface: cards, panels, nav, dialogs.
- Text: primary, secondary, muted, inverse.
- Border: subtle, strong, focus.
- Accent: primary action, links, decorative accents.
- Semantic: success, warning, danger, info.
- Shape: small, medium, large, pill.
- Elevation: none, subtle, raised, overlay.
- Spacing: base unit, section gap, container padding, element gap.

## Surfaces

Use two to four surface levels:

- Level 0: page canvas.
- Level 1: main content surface.
- Level 2: grouped cards or panels.
- Level 3: overlays, active states, inputs, nav.

Depth can come from color shifts, borders, shadows, or all three. Do not use heavy shadows when surface contrast already communicates depth.

## Color Temperature

Color temperature changes the page mood:

- Cool black/blue: technical, precise, powerful.
- Warm off-white/brown: human, editorial, premium.
- Bright white/multicolor: open, flexible, productive.
- Purple/blue gradients: collaborative, expressive, digital.

Do not mix warm luxury palettes with random neon accents unless there is a clear visual idea.

## Shape Language

Radii should be systematic:

- Sharp: serious, editorial, dense, technical.
- Small radius: utilitarian, app-like, controlled.
- Medium radius: friendly and modern.
- Large radius: soft, playful, product-marketing.
- Pill: actions, badges, filters, compact controls.

Avoid arbitrary radius values across components.

## Elevation

Choose one elevation model:

- Surface-based: depth through background color changes.
- Border-based: depth through subtle outlines and dividers.
- Shadow-based: depth through restrained shadows.
- Glow-based: only for dark, digital, or dramatic styles.

Use shadows sparingly. A page with every card floating usually feels cheap.

## Imagery And Graphics

Pick imagery behavior deliberately:

- Business data images: best when records include covers, avatars, screenshots, product photos, or media URLs.
- Product screenshots: best for software, dashboards, tools.
- Abstract graphics: best for atmosphere or complex concepts.
- Product photography: best for physical or premium products.
- Icons: best for scanning and repeated features.
- Gradient washes: best for hero atmosphere or section transition.

If assets are unavailable, create styled placeholders or CSS-built visuals that match the system rather than using broken image assumptions. Do not let fallback visuals override real business media.

## Density

Define density before layout:

- Spacious: large sections, wide gaps, few cards, premium feel.
- Comfortable: balanced cards, readable copy, most marketing pages.
- Compact: dense data, dashboards, tables, admin tools.

Do not use spacious marketing rhythm for a dense app UI, and do not use compact table rhythm for a brand landing page.
