# Quality Rubric

Use this before finalizing a generated web page.

## Visual Direction

Score high when:

- The page has a clear visual idea.
- Tokens, layout, and components support the same mood.
- It does not feel like a default template.

Fix when:

- It uses generic white/purple SaaS styling.
- Every section looks interchangeable.
- Decorative elements do not support the content.

## Hierarchy

Score high when:

- The primary message or task is immediately clear.
- Text sizes and weights create obvious priority.
- CTAs are placed and styled intentionally.

Fix when:

- All cards have equal weight.
- The hero has no visual anchor.
- The page depends on long paragraphs to explain itself.

## System Coherence

Score high when:

- Spacing follows a scale.
- Radii are consistent.
- Surfaces and shadows follow one model.
- Color roles are stable.

Fix when:

- Each component has unrelated values.
- Accent colors are used randomly.
- Shadows and borders are mixed without purpose.

## Craft

Score high when:

- Details such as hover, focus, active, disabled, empty, and loading states are present when relevant.
- Typography has tuned line-height and tracking.
- Imagery or mock visuals feel intentional.

Fix when:

- Buttons and cards look browser-default.
- Inputs lack labels or focus states.
- Mock content is implausible.

## Responsiveness

Score high when:

- Mobile layout is deliberately reorganized.
- Text remains readable.
- Hit targets are usable.
- Wide layouts do not become stretched.

Fix when:

- Desktop columns simply shrink until unreadable.
- Large hero text overflows.
- Tables or cards break the viewport.

## Accessibility

Score high when:

- Semantic HTML is used.
- Contrast is adequate.
- Focus states are visible.
- Reduced motion is respected.

Fix when:

- Clickable divs replace native controls.
- Low-contrast muted text is used for important content.
- Focus outlines are removed.

## Language Fit

Score high when:

- Page copy follows the user's requested or implied language.
- Tone matches the target audience and page type.
- Proper nouns, product names, brand names, and technical terms are preserved correctly.
- Chinese copy reads naturally when the prompt is Chinese.

Fix when:

- A Chinese request produces an English page without being asked.
- Copy sounds machine-translated.
- Product terminology is inconsistent across sections.
- Interface labels use a different language from the main page without reason.

## Code Quality

Score high when:

- The code is runnable.
- Tokens are reusable.
- Components are named by role.
- Styles are maintainable.

Fix when:

- One-off values dominate.
- The implementation references missing assets.
- Layout depends on fragile fixed heights or absolute positioning.

## Minimum Bar

Do not deliver until:

- The page has a named visual direction.
- The design token set is coherent.
- The main layout works on desktop and mobile.
- Interactive elements have visible states.
- The result is better than a generic template.
