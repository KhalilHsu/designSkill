# Web-Native Implementation Patterns

Read this to generate the actual web deck code. The default output is a self-contained HTML document with inline CSS and JS, unless the user asks for React components, an existing app integration, or a specific framework.

## The Web-Native Slide Architecture

Do not use React, Vue, Marp, or Reveal.js by default. If the user is building inside an existing web app, follow that app's stack and component conventions while preserving the deck behavior.

### 1. HTML Skeleton
The document should be a container of `<section>` elements.
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Presentation</title>
  <style>
    /* CSS goes here */
  </style>
</head>
<body>
  <main id="deck">
    <section class="slide current">...</section>
    <section class="slide">...</section>
  </main>
  <script>
    /* JS goes here */
  </script>
</body>
</html>
```

### 2. Core CSS Mechanics

**Viewport & Aspect Ratio Locking:**
Ensure slides always look like slides, regardless of browser shape.
```css
:root {
  --aspect-ratio: 16 / 9;
}
body { margin: 0; background: #000; overflow: hidden; display: flex; align-items: center; justify-content: center; height: 100vh; }
#deck {
  width: 100vw;
  height: 100vh;
  /* Lock to 16:9 like a real slide surface */
  max-width: calc(100vh * (16 / 9));
  max-height: calc(100vw * (9 / 16));
  position: relative;
  overflow: hidden;
  background: var(--bg);
}
```

**Slide Positioning (Absolute Stacking):**
Instead of scrolling, stack slides and cross-fade them for a professional feel.
```css
.slide {
  position: absolute;
  top: 0; left: 0; width: 100%; height: 100%;
  padding: 4vw 6vw; /* Viewport based padding */
  box-sizing: border-box;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.4s ease-in-out;
  display: flex; /* Setup for flex/grid layouts inside */
  flex-direction: column;
}
.slide.current {
  opacity: 1;
  pointer-events: auto;
}
```

### 3. Minimal Vanilla JS Navigation

Implement basic keyboard (Arrows, Space) and click navigation.
```javascript
const slides = document.querySelectorAll('.slide');
let currentIndex = 0;

function goToSlide(index) {
  slides[currentIndex].classList.remove('current');
  currentIndex = Math.max(0, Math.min(index, slides.length - 1));
  slides[currentIndex].classList.add('current');
}

document.addEventListener('keydown', (e) => {
  if (e.key === 'ArrowRight' || e.key === 'Space' || e.key === 'Enter') goToSlide(currentIndex + 1);
  if (e.key === 'ArrowLeft') goToSlide(currentIndex - 1);
});

// Optional: Click right side of screen to advance
document.addEventListener('click', (e) => {
  if (e.clientX > window.innerWidth / 2) goToSlide(currentIndex + 1);
  else goToSlide(currentIndex - 1);
});
```

### 4. Styling the Content

Use modern CSS primitives (Grid/Flex) and Viewport units (`vw`/`vh`) inside the slide.
- Avoid fixed `px` heights.
- Use CSS Variables heavily to maintain the "Vibe".
- Include a subtle progress indicator (e.g., a tiny bottom bar that scales its `width` based on `(currentIndex / total) * 100%`).

### 5. Evidence Metadata

For decks based on data, include unobtrusive evidence metadata in the DOM so the rendered slide can stay clean while the source remains inspectable.
```html
<section class="slide current" data-source="warehouse.orders" data-query="weekly_revenue_paid_accounts">
  <p class="eyebrow">Q3 revenue</p>
  <h1>Enterprise revenue doubled year over year</h1>
  <p class="source-note">Source: warehouse.orders, paid enterprise accounts, Q3 2025 vs Q3 2026</p>
</section>
```

Use visible source notes for investor, board, research, and customer-facing data claims. Hide or minimize them only when the user explicitly wants a stage-presentation mode.
