# Brief: Case Studies Section Layout Fix

**Files:** `index.html`, `css/components.css`
**Applied:** 2026-05-01

## Changes made

### css/components.css — `.cases-hdr`
- Added `text-align: center` (previously had no text-align)

### css/components.css — `.cases-grid`
- Changed `grid-template-columns` from `repeat(2, 1fr)` to `1fr 1fr` (equivalent, explicit)
- Changed `gap` from `24px` to `36px`
- Added `margin: 0 auto`
- `max-width: 1100px` was already present — retained

### Mobile breakpoint
- `.cases-grid { grid-template-columns: 1fr; }` at `@media (max-width: 768px)` was already present in components.css — no change needed

Card content, stats, client names, links, and the orange section background were not changed.
