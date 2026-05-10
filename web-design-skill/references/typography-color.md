# Typography And Color

Read this to choose type roles and color roles. These ranges are guidance, not mandatory defaults; adjust them to the content density, visual direction, and existing project system.

Output after reading:

- Type role list.
- Color role list.
- Accent usage rules.
- Contrast risks to check.

## Typography

Define type roles:

- Display: major hero statements.
- Heading large: section titles.
- Heading: card and panel titles.
- Body: primary reading text.
- Body small: supporting text.
- Label: controls, metadata, nav.
- Caption: fine print, annotations.

## Type Scale Guidance

For marketing or product pages:

- Display: 56-96px desktop, 40-56px mobile.
- Heading large: 36-56px desktop.
- Heading: 24-32px.
- Body: 16-20px.
- Caption/label: 12-14px.

For app or dashboard UI:

- Page title: 24-36px.
- Section title: 16-22px.
- Body/control: 14-16px.
- Metadata/caption: 11-13px.

## Font Selection

Choose fonts by role:

- Precise product: clean sans, tight headline tracking.
- Luxury/editorial: refined sans or restrained serif accent.
- Playful/productivity: geometric or friendly sans.
- Technical app: legible UI sans with strong numerals.
- Expressive brand: distinctive display plus practical body font.

If a brand font is unavailable, use a realistic substitute. Do not reference external fonts unless the implementation imports them.

### Chinese-First Font Selection

When the user writes in Chinese or the audience is primarily Chinese, choose Chinese-capable font stacks first:

```css
--font-sans: "PingFang SC", "Microsoft YaHei", "Noto Sans SC", "Source Han Sans SC", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
--font-serif: "Noto Serif SC", "Source Han Serif SC", "Songti SC", "STSong", Georgia, serif;
--font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
```

- Product, SaaS, dashboard, and database UI: use the sans stack.
- Editorial, report-like, or cultural pages: optionally use the serif stack for large headings, then sans for controls and metadata.
- Code, table names, query IDs, and file paths: use mono only for those fragments.
- Do not use Latin display fonts as the primary style for Chinese content; Chinese glyphs will fall back and the visual system will look accidental.

## Chinese Copy Density

Chinese UI often looks compact but can become dense quickly. Design for scanning:

- Hero headline: one clear Chinese claim, not a translated paragraph.
- Card text: one sentence or one short metric explanation.
- Button text: short verbs such as `查看详情`, `生成报告`, `保存视图`, `重新分析`.
- Metadata: prefer compact labels such as `来源：`, `更新时间：`, `样本：`, `口径：`.
- Empty states: state what happened and the next action; avoid decorative motivational copy.

## Letter Spacing

- Large sans-serif headings often benefit from slight negative tracking.
- Small labels may need slight positive tracking.
- Body text usually should not be tightly tracked.
- All-caps labels need additional letter spacing.
- Chinese body and headings should usually use `letter-spacing: 0`.
- Avoid aggressive negative tracking on Chinese. Use at most `-0.01em` for very large short headings.
- Use positive tracking only for short Latin labels or all-caps English fragments, not normal Chinese labels.

## Chinese Punctuation, Numbers, And Units

- Use Chinese punctuation for Chinese prose and UI labels.
- Keep ASCII punctuation inside code, URLs, SQL, query IDs, filenames, and data attributes.
- Keep Arabic numerals for metrics, dates, money, percentages, and counts.
- Use natural Chinese units where appropriate: `万元`, `亿元`, `人`, `次`, `小时`, `近 7 天`, `2026 年 Q1`.
- Keep technical identifiers stable: `warehouse.orders`, `data-query-id`, `weekly_active_accounts`.

## Color System

A useful color system includes:

- Canvas.
- Surface.
- Text primary.
- Text secondary.
- Text muted.
- Border.
- Primary action.
- Link/accent.
- Semantic colors.
- Optional decorative accents.

Do not use decorative accent colors for body copy.

## Accent Discipline

Use accents by purpose:

- Primary action: one consistent color.
- Links: one consistent color.
- Badges/categories: limited secondary palette.
- Decoration: gradients or washes that sit behind content.
- Semantic state: never confused with brand decoration.

## Contrast

Minimum expectations:

- Body text must be clearly readable.
- Buttons must have strong text/background contrast.
- Muted text should still be legible.
- Focus states must be visible.
- Dark themes need more care: avoid low-contrast gray-on-black.

## Gradients

Use gradients when they support atmosphere:

- Hero background.
- Decorative aura.
- Product visualization.
- Feature accent.

Avoid gradients on every button or card. Avoid gradients that reduce text contrast.
