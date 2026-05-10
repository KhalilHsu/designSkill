# Quality Rubric

Use this before finalizing a generated web page.

Treat this as a pass/fix checklist, not a scoring essay. Fix any failed item that affects the requested output.

## Data And Inputs

Pass when:

- The page uses provided business data, schema, records, fields, and media where available.
- The layout follows the data shape and user task.
- Missing fields are handled without fabricating precise facts.

Fix when:

- Real data was replaced with generic mock content.
- The implementation invents API endpoints, fields, dependencies, or local asset paths.
- A data-heavy page was forced into a generic marketing layout.

## Visual Direction

Pass when:

- The page has a clear visual idea.
- Tokens, layout, and components support the same mood.
- It does not feel like a default template.

Fix when:

- It uses generic white/purple SaaS styling.
- Every section looks interchangeable.
- Decorative elements do not support the content.

## Hierarchy

Pass when:

- The primary message or task is immediately clear.
- Text sizes and weights create obvious priority.
- CTAs are placed and styled intentionally.

Fix when:

- All cards have equal weight.
- The hero has no visual anchor.
- The page depends on long paragraphs to explain itself.

## System Coherence

Pass when:

- Spacing follows a scale.
- Radii are consistent.
- Surfaces and shadows follow one model.
- Color roles are stable.

Fix when:

- Each component has unrelated values.
- Accent colors are used randomly.
- Shadows and borders are mixed without purpose.

## Craft

Pass when:

- Details such as hover, focus, active, disabled, empty, and loading states are present when relevant.
- Typography has tuned line-height and tracking.
- Imagery or mock visuals feel intentional.

Fix when:

- Buttons and cards look browser-default.
- Inputs lack labels or focus states.
- Mock content is implausible.

## Responsiveness

Pass when:

- Mobile layout is deliberately reorganized.
- Text remains readable.
- Hit targets are usable.
- Wide layouts do not become stretched.

Fix when:

- Desktop columns simply shrink until unreadable.
- Large hero text overflows.
- Tables or cards break the viewport.

## Accessibility

Pass when:

- Semantic HTML is used.
- Contrast is adequate.
- Focus states are visible.
- Reduced motion is respected.

Fix when:

- Clickable divs replace native controls.
- Low-contrast muted text is used for important content.
- Focus outlines are removed.

## Language Fit

Pass when:

- Page copy follows the user's requested or implied language.
- Tone matches the target audience and page type.
- Proper nouns, product names, brand names, and technical terms are preserved correctly.
- Chinese copy reads naturally when the prompt is Chinese.
- Chinese UI labels, buttons, empty states, table headers, chart labels, and source notes are also localized.
- Chinese punctuation, units, and date/number labels feel native to the page context.

Fix when:

- A Chinese request produces an English page without being asked.
- Copy sounds machine-translated.
- Product terminology is inconsistent across sections.
- Interface labels use a different language from the main page without reason.
- Buttons or nav labels remain English because the implementation stack is English.
- Chinese text overflows because the layout assumed English word length and line breaks.
- Technical identifiers were translated and became unstable.

## Code Quality

Pass when:

- The code is runnable.
- Tokens are reusable.
- Components are named by role.
- Styles are maintainable.
- Dependencies and component libraries are present or explicitly added.

Fix when:

- One-off values dominate.
- The implementation references missing assets.
- The implementation assumes unavailable component libraries or icon packages.
- The implementation fakes API calls.
- Layout depends on fragile fixed heights or absolute positioning.

## Minimum Bar

Do not deliver until:

- The page has a named visual direction.
- The design token set is coherent.
- Provided business data is used when available.
- The main layout works on desktop and mobile.
- Interactive elements have visible states.
- Complex components respect existing project dependencies or use a simpler reliable pattern.
- There are no broken image paths, fake APIs, or assumed missing dependencies.
- The result is better than a generic template.
