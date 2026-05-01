# Fix: Nav links invisible on cream background

**Problem:** After nav background changed from dark to cream, link text colour stayed white/light — invisible against the cream background.

**Changes made to `css/global.css`:**
- Announce bar `height` changed from `32px` to `24px`
- `body { padding-top }` changed from `96px` to `88px` (24px announce bar + 64px nav)
- Consolidated `.site-header, .site-nav` into a single rule with: `background: var(--w)`, `border-bottom: 1px solid rgba(28,28,26,0.08)`, `position: fixed`, `top: 24px`, `height: 64px`
- Added explicit `.nav-links, .site-nav ul, .site-nav nav ul` flex row layout rules
- Added `.nav-links li, .site-nav ul li { display: list-item }`
- `.nav-links a, .site-nav ul a, .site-nav nav a` colour set to `rgba(28,28,26,0.65)` with `white-space: nowrap`
- `.nav-links a:hover, .site-nav ul a:hover` colour set to `var(--b)`
- `.nav-logo, .logo, .logo-text` colour confirmed as `var(--b)`
