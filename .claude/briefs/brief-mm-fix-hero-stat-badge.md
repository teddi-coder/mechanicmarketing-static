# Fix: Hero stat badge overflow

**Problem:** `.hero-stat-badge` had `left: -20px` which pushed it outside its container, showing a white rectangle against the cream hero background.

**Changes made to `css/global.css`:**
- `.hero-stat-badge` `left` changed from `-20px` to `16px`
- Added `min-width: 140px` to `.hero-stat-badge`
- Added new rule: `.hero-img, .hero-image-wrapper { position: relative; overflow: hidden; height: 100%; }` to ensure the badge clips to the image container boundary
