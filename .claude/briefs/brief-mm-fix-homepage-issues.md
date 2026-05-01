# Brief: Fix Homepage Rendering Issues

## Fix 2a — ROAS Ticker Suffix
The ROAS ticker stat on the homepage already had `&times;` as the `.tick-suf` suffix when this brief was applied. No change required — the file was already correct.

## Fix 2b — Remove Inline Hero Stats Row
Removed the `.hero-stats` block from `index.html` (3 counters: 5,000+ Leads, 12+ Workshops, 4.2× ROI).

Also cleaned up from `css/components.css`:
- `.hero-stats` rule (flex, gap, border-top, animation)
- `.hero-stat-num` rule
- `.hero-stat-lbl` rule
- `.hero-stats` from mobile responsive block

The CTA buttons (`.hero-actions`) above were untouched.

## Fix 2c — Logo Marquee Opacity
Changed `.logos-row img { opacity: 0.3 }` to `opacity: 0.6` in `css/components.css`.
`filter: grayscale(100%)` and hover state left unchanged.

## Files Changed
- `index.html`
- `css/components.css`
