# MM Static Site — Homepage Addendum Brief

**Date:** 2026-05-01
**Status:** Implemented

---

## Objective

Replace the scaffolded `index.html` with a full implementation derived from the approved mockup `mm-homepage-v3-with-motifs.html`, update the font setup across the whole site, and commit + push.

---

## Font Specification

### Font Family
**TT Commons Pro** — replaces Barlow/Barlow Condensed from the mockup.

### @font-face Declarations (top of global.css, before :root)

```css
@font-face {
  font-family: 'TT Commons Pro';
  src: url('/assets/fonts/TT_Commons_Pro_Regular.woff2') format('woff2'),
       url('/assets/fonts/TT_Commons_Pro_Regular.woff') format('woff');
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}
@font-face {
  font-family: 'TT Commons Pro';
  src: url('/assets/fonts/TT_Commons_Pro_Bold.woff2') format('woff2'),
       url('/assets/fonts/TT_Commons_Pro_Bold.woff') format('woff');
  font-weight: 700;
  font-style: normal;
  font-display: swap;
}
@font-face {
  font-family: 'TT Commons Pro';
  src: url('/assets/fonts/TT_Commons_Pro_ExtraBlack.woff2') format('woff2'),
       url('/assets/fonts/TT_Commons_Pro_ExtraBlack.woff') format('woff');
  font-weight: 900;
  font-style: normal;
  font-display: swap;
}
```

### CSS Variables

```css
--font-display: 'TT Commons Pro', 'Helvetica Neue', Arial, sans-serif;
--font-body:    'TT Commons Pro', 'Helvetica Neue', Arial, sans-serif;
```

### Weight Mapping (mockup → site)

| Mockup token | CSS output |
|---|---|
| `font-family: var(--fd); font-weight: 900` | `font-family: var(--font-display); font-weight: 900` |
| `font-family: var(--fd); font-weight: 700` | `font-family: var(--font-display); font-weight: 700` |
| `font-family: var(--fb); font-weight: 500` | `font-family: var(--font-body); font-weight: 400` |

### Letter-spacing

- Hero H1, section headings at 54px+: `letter-spacing: -0.03em`
- Buttons, nav, section labels: `letter-spacing: -0.01em`

---

## Brand Tokens

| Token | Value |
|---|---|
| `--mm-orange` | `#FF3D02` |
| `--mm-warm-white` | `#F0F0EC` |
| `--mm-dark` | `#1c1c1a` (replaces `#000000` from mockup) |
| `--mm-golden` | `#F0AA00` |
| `--mm-orange-t1` | `#FF6746` |
| `--mm-orange-t2` | `#FF8A6F` |
| `--mm-orange-t3` | `#FFAC98` |
| `--mm-orange-t4` | `#FFD1C6` |

**Rule:** All `#000000` and `var(--b)` from the mockup → replaced with `#1c1c1a` (`var(--mm-dark)`).

---

## Adaptations from Mockup to Multi-Page Site

### CSS/JS extraction
- All `<style>` content → merged into `/css/global.css` and `/css/components.css`
- All `<script>` content → `/js/main.js`

### Removed
- Google Fonts `@import url('https://fonts.googleapis.com/...')` — replaced by @font-face block above
- Inline `var(--b)`, `var(--fd)`, `var(--fb)`, `var(--o)`, `var(--w)` shorthand tokens — replaced with full `var(--mm-*)` token names

### Nav links (anchor → page paths)
| Label | Mockup href | Site href |
|---|---|---|
| Services | `#services` | `/services/google-ads.html` |
| Case Studies | `#cases` | `/case-studies/` |
| Pricing | `#pricing` | `/pricing.html` |
| Blog | `/blog/` | `/blog/` |
| About | (new) | `/about.html` |
| Get in Touch | `#contact` | `/contact.html` |

### Case study card links
| Workshop | href |
|---|---|
| BB Garage | `/case-studies/bb-garage.html` |
| Accelerate Automotive | `/case-studies/accelerate-automotive.html` |
| Busselton Automotive | `/case-studies/busselton-automotive.html` |
| Core Diesel | `/case-studies/core-diesel.html` |

### Contact form endpoint
Literal placeholder `__CONTACT_FORM_ENDPOINT__` — do NOT replace with a real URL.

---

## Sections in index.html (in order)

1. Tyre bar (orange strip, base64 SVG tyre tread motif, opacity 0.2)
2. Nav (dark bg, MM logo ExtraBlack orange, "MECHANIC MARKETING" small-caps bold, links Regular 16px, orange "GET IN TOUCH" CTA)
3. Hero (2-col grid, left: eyebrow + H1 `GET MORE CARS IN BAYS` with `IN BAYS` in orange + subhead + 2 CTAs + hero-stats row with animated counters; right: workshop photo with heroZoom animation + orange left border + tyre motif overlay)
4. Ticker bar (dark bg, 4 stats: 2,147+ leads / $38 CPL / 850% ROAS / 100% transparent, JS counter animation)
5. Client logos (grayscale 30% opacity, full colour on hover)
6. Services (dark bg, 6 cards with inline SVG icons)
7. Motif divider 1 (tyre tread SVG, ~35% opacity, dark bg)
8. How It Works (cream bg, 4-step grid, ghost step numbers 01–04)
9. Case Studies (orange bg, 2×2 grid, REAL stats: BB Garage 850% ROAS, Accelerate 312 LEADS, Busselton $29 CPL, Core Diesel 2,147 LEADS)
10. Testimonial (dark bg, Bodie Geck quote)
11. Motif divider 2 (identical to divider 1)
12. Pricing (cream bg, Ignite $1,500/m and Accelerate $2,500/m)
13. FAQ (accordion, JS toggle, first item open by default)
14. Final CTA (orange bg, "QUIET BAYS?" headline, tyre motif overlay at 12% opacity)
15. Footer (dark bg, 4-col grid, social icons, © 2026)

---

## JavaScript Behaviours

- **Animated counters:** scroll-triggered, cubic ease-out, 2000ms duration, targets `.counter` and `[data-target]`
- **Scroll reveal:** `.reveal` class, 60px threshold from bottom of viewport, adds `.visible`
- **FAQ accordion:** click on `.faq-q` toggles `.open` on parent `.faq-i`
- **@keyframes heroZoom:** `scale(1.08) translateY(-1%)` → `scale(1.12) translateY(1%)`, 12s infinite alternate
- **@keyframes slideUp:** opacity 0 + translateY(24px) → opacity 1 + translateY(0)

---

## Validation Rules

- No `#000000` anywhere in `/css/`
- No `Barlow` anywhere in `/css/`
- No `Google Fonts` anywhere in the site
