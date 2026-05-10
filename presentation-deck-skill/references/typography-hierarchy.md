# Typography & Hierarchy for Chinese Presentations

Read this to choose fonts, sizes, spacing, and hierarchy for web-native slide decks. Optimize for Chinese users first. English and mixed-language content are secondary cases.

Presentation typography is about fast comprehension from a distance. For Chinese decks, clarity comes from short claims, strong weight contrast, stable line height, and careful mixed Chinese/Latin/numeric handling.

## Chinese-First Font Stacks

Default to local system fonts. Do not rely on external web fonts unless the implementation explicitly imports them and the loading behavior is acceptable.

### Data / SaaS / AI / Executive Deck

Use a clean Chinese sans-serif stack:

```css
--font-sans: "PingFang SC", "Microsoft YaHei", "Noto Sans SC", "Source Han Sans SC", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
--font-number: "DIN Alternate", "Avenir Next Condensed", "Arial Narrow", var(--font-sans);
--font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
```

Use for pitch decks, operating reviews, product narratives, AI/database demos, financial metric slides, and customer briefings.

### Research / Whitepaper / Policy Deck

Use a restrained serif/sans pairing:

```css
--font-serif: "Noto Serif SC", "Source Han Serif SC", "Songti SC", "STSong", Georgia, serif;
--font-sans: "PingFang SC", "Microsoft YaHei", "Noto Sans SC", system-ui, sans-serif;
```

Use serif for large editorial titles or body-light research slides. Use sans-serif for labels, source notes, tables, legends, and dense annotations.

### Technical / Console Deck

Use Chinese sans for prose and mono only for code/query blocks:

```css
--font-sans: "PingFang SC", "Microsoft YaHei", "Noto Sans SC", system-ui, sans-serif;
--font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
```

Do not render full Chinese slides in a monospace font. It usually feels crude and reduces readability.

## Avoid These Font Mistakes

- Do not choose English display fonts such as `Space Grotesk`, `Playfair Display`, or `Syne` as the main typography for Chinese copy. Chinese characters will fall back unpredictably.
- Do not import a Latin-only font and assume the Chinese deck is "styled"; most visible text will be rendered by fallback fonts.
- Do not mix more than two Chinese font families in one deck unless there is a clear typographic role.
- Do not use fake bold on thin Songti for large data slides; use a heavier sans-serif for high-impact numeric or business claims.

## Chinese Type Scale

Use viewport-aware sizing, but tune the ranges for Chinese density. Chinese text often occupies more visual weight than English at the same CSS size.

- **Hero Claim:** `clamp(3rem, 5.8vw, 6.8rem)` for 8-18 Chinese characters.
- **Slide Title:** `clamp(2rem, 4vw, 4.8rem)` for one conclusion sentence.
- **Section / Card Title:** `clamp(1.2rem, 1.9vw, 2.2rem)`.
- **Body / Support Copy:** `clamp(0.95rem, 1.35vw, 1.45rem)`.
- **Label / Legend:** `clamp(0.72rem, 0.9vw, 0.96rem)`.
- **Source Note / Fine Print:** `clamp(0.62rem, 0.78vw, 0.84rem)`.
- **Big Number:** `clamp(4rem, 9vw, 11rem)`, using `--font-number` when available.

For Chinese slides, shorten the text before shrinking the font. A slide title that needs a tiny font is probably not a slide title.

## Line Height

- Hero claim: `1.02` to `1.12`.
- Slide title: `1.08` to `1.18`.
- Body copy: `1.38` to `1.55`.
- Source notes: `1.45` to `1.65`.
- Dense tables: `1.3` to `1.45`.

Chinese headings usually need slightly more line height than English all-caps display text. Avoid `line-height: 0.9` for Chinese unless it is a single-line number or very short phrase.

## Letter Spacing

- Default Chinese `letter-spacing` should be `0`.
- Large Chinese headings may use at most `-0.01em`; avoid aggressive negative tracking.
- Small uppercase English labels can use `0.08em` to `0.16em`.
- Mixed Chinese/English labels should usually use `0` to avoid awkward spacing around Latin fragments.
- Never use `-0.04em` or lower on Chinese paragraphs or multi-line titles.

## Mixed Chinese, English, and Numbers

- Keep product names, table names, query IDs, metric IDs, and code snippets in their original notation.
- Add readable spacing in prose around Latin product names when it improves scanning: `LedgerLens 把数仓指标...`.
- Use tabular or condensed numeral styling for metrics when available.
- Large metric slides should pair the number with a short Chinese explanation:
  - Good: `64%` + `刷新工作量下降`
  - Weak: `64% efficiency improvement across workflow`
- Avoid translating technical identifiers: `data-query-id`, `weekly_active_accounts`, and `warehouse.orders` should remain stable.

## Chinese Slide Copy Density

Chinese can look compact but become cognitively dense quickly. Keep each slide to one conclusion.

- Hero slide: 1 headline + 1 short support sentence.
- Data slide: 1 conclusion + 1 chart + 1 source note.
- Matrix/table slide: 3-4 columns max, short cell text.
- Research slide: 1 finding + 2-3 evidence points.

Avoid mechanically translating English titles. Rewrite for Chinese presentation rhythm:

- Bad: `源链接的幻灯片削减刷新工作通过 64%`
- Good: `带来源的幻灯片让刷新工作量下降 64%`

## Source Notes and Captions

Source notes should be readable but quiet. Use Chinese labels when the deck is Chinese:

- `来源：pilot.time_study，n=12 个财务团队，2026 年 4 月。`
- `假设：仅纳入有备用电力、饮水设施和无障碍覆盖的分馆。`
- `证据地图：合成试点数据集；所有指标均为 skill 测试示意。`

Keep identifiers unchanged inside source notes. Translate the explanatory parts, not the data handles.

## Contrast and Weight

- Use strong contrast for Chinese body text; thin gray Chinese is harder to read than thin gray Latin text.
- Prefer off-white text on dark backgrounds: `#f8fafc`, `#f3f4f6`, or similar.
- Muted Chinese text should still be legible from a normal presentation distance.
- Use font weight, size, and spacing before adding decorative effects.

## The Chinese Squint Test

Step back from the screen. The audience should immediately read:

1. the main Chinese conclusion,
2. the most important number or comparison,
3. the evidence/source cue if trust matters.

If the viewer notices the template before the conclusion, simplify the typography.
