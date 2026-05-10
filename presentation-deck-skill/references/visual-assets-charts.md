# Visual Assets & Charts

Read this to handle data, charts, diagrams, screenshots, and imagery in a web-native presentation.

## Charts and Data Visualization

Default to native HTML/CSS/SVG for simple charts. If the user requests a framework or the host app already provides a charting library, adapt to that environment instead of forcing a single-file artifact.

Never fabricate, smooth, or "conceptualize" real metrics. Simplify chart presentation for slide readability, but preserve the underlying values, labels, comparisons, and time windows. If exact data is unavailable, label the chart as illustrative.

### 1. Evidence-Backed Metric Slide
- Use for traction, revenue, growth, retention, usage, or ROI claims.
- Show the headline metric large, then place the source and time window nearby in small but readable text.
- If the metric is calculated, include the formula or denominator where trust depends on it.

### 2. Bar / Column Chart
- Use for category comparison, growth over a small number of periods, or before/after.
- Keep the values accurate. Heights should match the values proportionally.
- Label the start, end, and decisive inflection point. Keep extra grid lines only if they improve interpretation.

### 3. Line / Trend Chart
- Use for time series where slope and inflection matter.
- Prefer SVG paths for precise lines and annotations.
- Annotate the event, cohort, or operational change that explains a visible shift.

### 4. Progress Ring / Donut
- Use only for part-to-whole percentages where the denominator is clear.
- Put the percentage in the center and the denominator/source below it.
- Avoid donut charts for multiple similar categories; use bars instead.

### 5. Comparison Table / Feature Matrix
- Use a clean CSS Grid.
- Competitor or baseline columns can be visually muted, but do not hide caveats.
- Highlight the important difference, not every cell.

## Source and Evidence Labels

Every chart or important number should carry a compact evidence label when source trust matters:
- `Source: warehouse.orders, Jan-Mar 2026`
- `Query: weekly_active_accounts, filtered to paid teams`
- `Input: user_research.csv, n=38`
- `Assumption: projected from current pilot conversion`

## Imagery Strategy

- **Product Screenshots:** Prefer real product screenshots when the slide claims product capability. Crop and annotate the part that supports the claim.
- **Abstract CSS Visuals:** Use abstract CSS visuals only when they clarify mood or section rhythm. Do not let decoration compete with evidence.
- **SVG Primitives:** For icons, use simple, inline SVG paths. Do not assume FontAwesome or Lucide are loaded.
- **Product Placeholders:** If a screenshot is needed but unavailable, build a "Wireframe Window".
  - Use a `div` with `border-radius`, a subtle `box-shadow`, and a top bar with three colored dots (macOS style window controls) to imply a software interface.

## Visual Coherence (The Token System)

Define a small set of color tokens in the `:root` and use them consistently:
1. `--bg`: The slide background (e.g., `#0f172a` for dark mode).
2. `--text-main`: High contrast text (e.g., `#f8fafc`).
3. `--text-muted`: For secondary labels (e.g., `#94a3b8`).
4. `--accent`: The single punchy color for key metrics, active states, and charts (e.g., `#3b82f6` or a vibrant neon).
5. `--warning` or `--risk`: Optional color for caveats, negative deltas, or confidence warnings.
