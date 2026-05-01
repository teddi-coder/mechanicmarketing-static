# Brief: Fix Case Study Page Layout

## Fix 3a — Hero Stat Display
Replaced `.cs-big-stat` (orange pill/button) with `.cs-hero-stat` two-part structure on all 4 pages.

Old: `<div class="cs-big-stat">800%+ ROAS</div>`
New:
```html
<div class="cs-hero-stat">
  <span class="cs-hero-stat-number">800%+</span>
  <span class="cs-hero-stat-label">ROAS</span>
</div>
```

Replaced `.cs-big-stat` CSS in `components.css` with `.cs-hero-stat`, `.cs-hero-stat-number`, `.cs-hero-stat-label` rules.

Stat values per page:
- bb-garage.html: 800%+ / ROAS
- accelerate-automotive.html: 312 / LEADS IN 90 DAYS
- busselton-automotive.html: Under $30 / COST PER LEAD
- core-diesel.html: 2,147+ / LEADS IN 12 MONTHS

## Fix 3b — Right Column Proof Cards
Replaced 3× `.cs-sidebar-stat` divs (unstyled text) with structured `.cs-proof-cards` wrapper containing `.cs-proof-card` items on all 4 pages.

Replaced `.cs-sidebar-stat` CSS in `components.css` with `.cs-proof-cards`, `.cs-proof-card`, `.cs-proof-value`, `.cs-proof-descriptor` rules.

Card values per page:
- bb-garage.html: 800%+ / Best month / 100%
- accelerate-automotive.html: 312 / $29 / 100%
- busselton-automotive.html: Under $30 / #1 / 100%
- core-diesel.html: 2,147+ / $38 / 100%

## Files Changed
- `case-studies/bb-garage.html`
- `case-studies/accelerate-automotive.html`
- `case-studies/busselton-automotive.html`
- `case-studies/core-diesel.html`
- `css/components.css`
