# Fix: Remove stat badges from homepage case study cards

**Problem:** Each of the 4 case study cards on the homepage had an absolutely-positioned `.case-badge` element overlaying the card image with stat text (800%+ ROAS, 312 LEADS, Under $30 CPL, 2,147 LEADS). These were visually noisy and inconsistent with the clean card design.

**Changes made to `index.html`:**
- Removed `<div class="case-badge">800%+ ROAS<span>Google Ads return</span></div>` from BB Garage card
- Removed `<div class="case-badge">312 LEADS<span>In 90 days</span></div>` from Accelerate Automotive card
- Removed `<div class="case-badge">Under $30 CPL<span>Cost per lead</span></div>` from Busselton Automotive card
- Removed `<div class="case-badge">2,147 LEADS<span>In 12 months</span></div>` from Core Diesel card

**Changes made to `css/components.css`:**
- Removed `.case-badge` and `.case-badge span` CSS rules (now unused on homepage)

Note: `case-studies/*.html` pages were not touched.
