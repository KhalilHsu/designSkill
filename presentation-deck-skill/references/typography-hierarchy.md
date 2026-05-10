# Typography & Hierarchy for Presentations

Read this to choose fonts, sizes, and spacing. Presentation typography is about "glanceability" from a distance, not deep reading.

## The Scale (View-Port Based)

Never use fixed pixel (`px`) or `rem` sizes designed for documents. Use Viewport Height (`vh`) or Viewport Width (`vw`) combined with `clamp()` to ensure text scales perfectly regardless of window size or screen aspect ratio.

- **Mega Display (Hero):** `clamp(4rem, 8vw, 10rem)` - For the single most important number or 2-word phrase.
- **Slide Title:** `clamp(2.5rem, 5vw, 6rem)` - The conclusion statement at the top of the slide.
- **Section Headers (in Grids):** `clamp(1.5rem, 3vw, 3rem)` - Titles for features or metric labels.
- **Body Text (Keep to a minimum):** `clamp(1.2rem, 2vw, 2rem)` - The absolute minimum size. If you need it smaller, you have too much text.

## Font Selection

- **Rule 1:** Prefer system fonts or extremely robust Google Fonts to avoid Flash of Unstyled Text (FOUT).
- **Rule 2:** Contrast is king. Pair a heavy, distinctive display font with a clean, highly legible sans-serif.

### Aesthetic Pairs
1. **The Modern Tech (Default):** Inter / Roboto (Body) + SF Pro Display / Helvetica Neue (Bold, for headers).
2. **The "Editorial / Luxury" Pitch:** Playfair Display / Merriweather (Headers) + Lato / Source Sans Pro (Body).
3. **The "Neo-Brutalist / Startup":** Space Grotesk / Syne (Headers) + Inter (Body).

## Formatting Rules

- **Line Height (Leading):** Tighter than web documents. Use `1.1` to `1.2` for massive titles. Use `1.4` for short body text.
- **Tracking (Letter Spacing):** Tighten up huge text (`-0.02em` or `-0.04em`). Slightly loosen all-caps labels (`0.05em`).
- **Contrast:** Ensure WCAG AAA contrast. If using a dark mode deck (highly recommended for tech/AI pitches), use off-white (e.g., `#f3f4f6`) for text, not pure `#ffffff`, to reduce blooming.

## The "Squint Test"
If you step back 10 feet from the monitor and squint, the one thing the audience needs to know on the slide should be the *only* thing clearly readable.
