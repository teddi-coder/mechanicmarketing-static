# Brief: Fix Broken Navigation

## Problem
Nav rendering as vertical unstyled list on case study and sub-pages. Affects all pages using `.site-header` / `.site-nav` markup.

## Root Cause
`global.css` had CSS rules for the homepage nav (`.nav`, `.nav-logo`, `.nav-links`) but zero rules for the `.site-header` / `.site-nav` structure used on case study pages and sub-pages.

## Fix Applied
Added to `css/global.css`:
- `.site-header` — fixed position, full width, 64px height, dark background, z-index 100
- `.site-header .container` — flex row, space-between, max-width 1200px, padding 0 40px
- `.site-header + *` — padding-top: 64px to push content below fixed header
- `.logo`, `.logo-text` — TT Commons Pro ExtraBlack 22px, warm white
- `.site-nav ul` — `display: flex; flex-direction: row; gap: 32px` (THE critical fix)
- `.site-nav ul a` — 14px body font, rgba(240,240,236,0.75), hover to --w
- `.nav-toggle` — hidden on desktop, block on mobile
- Mobile media query — `.site-nav ul` becomes column dropdown with `.is-open` toggle

## Files Changed
- `css/global.css`
