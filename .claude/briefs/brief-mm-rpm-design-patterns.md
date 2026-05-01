# Brief: RPM-Inspired Design Patterns
Date: 2026-05-01

## Scope
Applied to `index.html`, `css/global.css`, and all 4 case study pages.

---

## Change 1 — Announcement bar
- Added `<div class="announce-bar">` as first element inside `<body>` on every HTML page
- Text: "No lock-in contracts. Month-to-month. Cancel any time."
- CSS added to `global.css`: fixed orange bar, 32px height, uppercase, z-index 101
- Nav updated to `top: 32px` to sit below the bar
- `body { padding-top: 88px }` updated to account for both bar and nav

**Status:** Applied (was already present from prior session).

---

## Change 2 — Nav: cream background
- `.site-header`, `.site-nav` switched from `var(--b)` to `var(--w)` with subtle bottom border
- Nav link colour changed to `rgba(28,28,26,0.65)` with dark hover
- `.logo-text`, `.nav-logo` set to `color: var(--b)`

**Status:** Applied (was already present from prior session).

---

## Change 3 — Section label pills
- `.section-label` replaced from plain text to pill style
- Orange background, white text, 20px border-radius, 10px font
- No HTML changes — existing `<span class="section-label">` picks up new styling

**Status:** Applied (was already present from prior session).

---

## Change 4 — Hero: cream background
- `.hero { background: var(--w) }` in `global.css`
- Hero H1, subhead, and outline CTA button colours updated for dark-on-cream
- Hero image right column (photo, tyre overlay, orange border, stat badge) unchanged

**Status:** Applied (was already present from prior session).

---

## Change 5 — Pain point cards section (NEW)
- Inserted new `<section class="pain-section">` into `index.html`
- **Position:** Between How It Works section and Case Studies section
- Three cards: "You're paying for clicks, not customers." / "They don't know what a DPF is." / "Quiet Tuesdays. Empty bays."
- CSS added to `global.css`: cream background, 3-column grid, orange top border on cards

**Status:** Applied this session — section inserted at line ~179 of `index.html`.

---

## Change 6 — Guarantees section (NEW)
- Inserted new `<section class="guarantees-section">` into `index.html`
- **Position:** Between Testimonial section and Pricing section (before Motif Divider 2)
- Three guarantee cards with SVG icons: "3× ROAS or we work for free." / "No lock-in. Ever." / "You own everything we build."
- CSS added to `global.css`: dark background (`var(--b)`), 3-column grid, subtle card borders

**Status:** Applied this session — section inserted at line ~233 of updated `index.html`.

---

## Change 7 — Case study hero: result-led headlines + meta pills
All 4 case study pages updated. Old `<h1>` (all-caps client name) replaced with result-led `<h1 class="cs-hero-h1">`. Meta pills `<div class="cs-meta">` added after eyebrow, before stat block.

| Page | New H1 | Pills |
|------|--------|-------|
| bb-garage.html | 800%+ ROAS. / Best month, every month. | BB Garage / Google Ads / Queensland / Ongoing |
| accelerate-automotive.html | 312 Leads. / 90 Days Of Consistent Growth. | Accelerate Automotive / Google Ads + SEO / NSW / Ongoing |
| busselton-automotive.html | Under $30 CPL. / Dominating Local Search. | Busselton Automotive / Google Ads / WA / Ongoing |
| core-diesel.html | 2,147 Leads. / 12 Months Of Compounding Volume. | Core Diesel / Google Ads + Landing Pages / QLD / 12 months |

CSS added to `global.css`: `.cs-hero-h1` (large, cream, tight tracking) and `.cs-meta-pill` (frosted glass style on dark hero bg).

**Status:** Applied this session.

---

## Final homepage section order (verified)

1. Announce bar
2. Nav/header
3. Hero (cream)
4. Ticker bar (dark)
5. Client logos (cream)
6. Services (dark)
7. Pain point cards (cream) — NEW
8. How It Works (cream)
9. Case Studies (orange)
10. Testimonial (cream)
11. Guarantees (dark) — NEW
12. Pricing (cream)
13. FAQ (cream)
14. Final CTA (orange)
15. Footer (dark)
