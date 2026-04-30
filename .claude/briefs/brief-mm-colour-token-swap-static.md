# MM Static Site — Colour Token Swap Brief

**Date applied:** 2026-05-01  
**Branch:** main  
**Files changed:** css/global.css, css/components.css, index.html

---

## What was done

### Step 1 — Shorthand tokens added to `:root` in `css/global.css`
The `:root` block was extended to include the shorthand token aliases alongside the existing `--mm-*` names:
- `--o: #FF3D02` (orange)
- `--w: #F0F0EC` (warm white / cream)
- `--b: #1c1c1a` (warm charcoal — NOT pure black)
- `--g: #F0AA00` (golden)
- `--t1: #FF6746` (orange tint 1)

### Step 2 — Hardcoded black values replaced
No hardcoded black values (`#000000`, `#000`, `#0a0a0a`, `#111111`) were found in `css/global.css` or `index.html`.

One instance of `#111` was found and replaced in `css/components.css` (`.hero-img` background panel — used as a placeholder colour behind the hero photo). Replaced with `#1c1c1a`.

`rgba(0,0,0,X)` overlay/shadow/scrim values were intentionally left unchanged throughout.

SVG `fill="black"` attributes inside the inline tyre motif SVGs (base64-encoded) were not touched — intentional per brief.

### Step 3 — Testimonial section moved to cream background
In `css/components.css`, the `.test` section background was changed from `var(--mm-dark)` to `var(--mm-warm-white)`.

A `.testimonial-card` rule was added to `css/components.css`:
- `background: var(--b)` (warm charcoal dark card)
- `color: #fff`
- `border-radius: 12px`
- `padding: var(--sp-xl) var(--sp-xxl)`
- `max-width: 760px; margin: 0 auto; text-align: center`

In `index.html`, the blockquote and cite elements inside `<section class="test reveal">` were wrapped in `<div class="testimonial-card">`, keeping the quote readable on the cream section background.

### Verification
```
grep -in '#000000\|: #000[^0-9a-f]' css/global.css index.html
```
Result: 0 matches.

---

## Intentionally unchanged
- `rgba(0,0,0,X)` values — overlays, shadows, scrims
- SVG `fill="black"` in base64-encoded tyre motif images
