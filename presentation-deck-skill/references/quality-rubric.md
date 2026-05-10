# Quality Rubric

Use this checklist before finalizing the generated presentation.

Treat this as a pass/fix checklist, not a scoring essay. Fix any failed item before delivering the code.

## Architecture & Code Quality

Pass when:
- The output is a web-native deck that matches the requested environment: self-contained HTML by default, or app-native components when requested.
- Global styles use CSS variables for colors and typography to allow easy theming.
- The Javascript is strictly limited to slide navigation logic (no heavy frameworks or simulated lifecycles).
- It looks like a presentation (16:9 aspect ratio or full viewport sections), not a scrolling website.

Fix when:
- The code assumes external libraries (`npm install`, external JS CDNs) are present without being asked.
- Images rely on broken or placeholder URLs instead of using CSS abstractions or inline SVGs where possible.
- The presentation requires scrolling vertically within a single slide to see all content.

## Narrative & Pacing

Pass when:
- The presentation has a clear arc (e.g., Problem -> Solution -> Proof -> Ask).
- Slide titles are "Conclusion-First" statements, not generic labels.
- There is strictly "One Idea Per Slide".
- The sequence alternates between claim, evidence, interpretation, and decision instead of becoming a gallery of unrelated charts.

Fix when:
- A slide tries to explain the market size, the product features, and the team all at once.
- The narrative feels like a data dump rather than a persuasive argument.
- Titles are lazy (e.g., "Overview", "Metrics").

## Visual Density & Hierarchy

Pass when:
- The most important number or phrase on the slide is instantly recognizable from across the room.
- Font sizes use scalable viewport units (`vw`, `vh`, `clamp()`).
- Bullet points are either completely eliminated in favor of grid layouts, or strictly limited to 3 short lines.

Fix when:
- A slide contains more than 40 words of body text.
- Standard HTML `<ul>` and `<li>` elements are used to create "walls of text".
- Charts are overly complex and impossible to read quickly (rely on CSS abstract charts instead).
- Contrast fails the squint test (e.g., light gray text on a white background).

## Evidence & Data Integrity

Pass when:
- Important claims have supporting evidence, source notes, or explicit assumptions.
- Chart values, axes, labels, and time windows are accurate to the provided data.
- The slide simplifies presentation without changing the meaning of the data.
- Unverified claims are softened or marked as assumptions.

Fix when:
- A number appears without a source and the audience would reasonably ask where it came from.
- A chart is only decorative but appears to represent real data.
- The title overclaims relative to the evidence shown.
- Data source, segment, cohort, or time window ambiguity could change the interpretation.

## Language Fit

Pass when:
- Visible slide copy follows the user's requested or implied language.
- Chinese decks read like natural presentation Chinese, not translated English.
- Technical identifiers such as table names, query IDs, metric IDs, product names, and code snippets remain stable when needed.
- Chinese titles are rewritten as concise claims, not literal translations of English slide titles.
- Chinese punctuation, source labels, chart labels, legends, and units are consistent across slides.
- Data labels use natural Chinese terms such as `来源：`, `假设：`, `样本：`, `同比`, `环比`, `近 30 天`, and `n=`.

Fix when:
- A Chinese request produces an English deck without being asked.
- Labels, source notes, and navigation text mix languages without a clear reason.
- Chinese copy becomes too long for the slide because it was translated mechanically instead of rewritten for presentation density.
- Slide chrome says `Research brief`, `Source`, `Finding`, `Decision`, or `Ask` in an otherwise Chinese deck.
- Full-width Chinese punctuation appears inside code/query identifiers, or ASCII punctuation appears in normal Chinese prose without reason.
- Large Chinese headings use Latin-only display-font assumptions or aggressive negative tracking.
