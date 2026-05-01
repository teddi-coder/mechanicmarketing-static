# Fix: Pricing card layout

**Problem:** Pricing cards were left-aligned and too narrow due to the `.pricing-grid` using `repeat(3, 1fr)` for only 2 cards, and no `max-width` constraint was centring them.

**Changes made to `css/components.css`:**
- `.pricing-grid` `grid-template-columns` changed from `repeat(3, 1fr)` to `1fr 1fr`
- `.pricing-grid` `gap` changed from `var(--sp-md)` to `28px`
- `.pricing-grid` `max-width: 860px` and `margin: 0 auto` added for centring
- `.pricing-card` `width: 100%` added
- Mobile breakpoint: `max-width: 100%` added alongside existing `grid-template-columns: 1fr`

**Changes made to `css/global.css`:**
- Added `.comparison-table-wrapper` rule: `max-width: 860px`, `margin: 48px auto 0`, `overflow-x: auto`
- Added full `.comparison-table` base rule: `width: 100%`, `border-collapse: collapse`
- Added `th, td` padding, font-size, and border-bottom rules
- Added `th` font-family/weight/letter-spacing rules
- Added `th:first-child, td:first-child` muted colour rule

**Changes made to `pricing.html`:**
- Replaced `<div style="overflow-x: auto; margin-top: var(--sp-xl);">` wrapping the comparison table with `<div class="comparison-table-wrapper">`
