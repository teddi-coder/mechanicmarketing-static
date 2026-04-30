# Brief: How It Works Section Expansion

**Files:** `index.html`, `css/global.css`, `js/main.js`
**Applied:** 2026-05-01

## Changes made

### index.html
- Added `step-card` class to all four `.step` elements (alongside existing `reveal` classes)
- Replaced one-line descriptions with expanded copy for all four steps
- Added inline SVG icons (32x32, stroke, currentColor) to each step:
  - Step 01: magnifying glass over document
  - Step 02: wrench and screwdriver crossed
  - Step 03: rocket
  - Step 04: upward trending chart
- Ghost numbers (01-04) and headings preserved exactly

### css/global.css
- Added `.step-card` staggered entrance animation block before the Animations section
- Uses `opacity` + `translateY` transitions with `is-visible` trigger class
- Transition delays: 0s, 0.12s, 0.24s, 0.36s for children 1-4

### js/main.js
- Added IntersectionObserver for `.step-card` elements
- Fires at 15% threshold, adds `is-visible` class, then unobserves
- Implemented as separate observer (existing `.reveal` uses scroll listener, not IntersectionObserver)
