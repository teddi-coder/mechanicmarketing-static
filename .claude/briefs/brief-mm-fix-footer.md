# Fix: Footer background and layout

**Problem:** Footer background was rendering as cream (should be dark), and columns were not displaying as a grid. Root cause: HTML uses `.site-footer` / `.footer-top` / `.footer-col` class names but no CSS existed for those selectors — only old `.footer` / `.ft-top` / `.ft-col` rules existed.

**Changes made to `css/global.css`:**
Added a new "Site Footer" section with rules for:
- `.site-footer` — `background: var(--b)`, `padding: 64px 0 40px`, `color: var(--w)`
- `.footer-top` — `max-width: 1200px`, `display: grid`, `grid-template-columns: 2fr 1fr 1fr 1fr`, `gap: 48px`
- `.footer-brand p` — `color: rgba(240,240,236,0.55)`, `font-size: 13px`
- `.footer-links { display: contents }` — allows child `.footer-col` divs to participate in the parent grid
- `.footer-col h4` — uppercase label style in `var(--w)`
- `.footer-col a` — `color: rgba(240,240,236,0.55)`, hover `var(--o)`
- `.footer-col ul` — reset list styles
- `.footer-bottom` — border-top, muted white text
- `.footer-brand .logo-text` — `color: var(--w)`
- Responsive: 2-col grid at 768px, 1-col at 480px
