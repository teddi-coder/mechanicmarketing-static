# Brief: About Page Alignment and Image Fix

**File:** `about.html`, `css/components.css`
**Applied:** 2026-05-01

## Changes made

### Rogue image removal
- No `bb-garage`, `bb_garage`, `bbgarage`, `BB Garage`, or `workshop` `<img>` tags were found on `about.html` — no removal needed.

### css/components.css — `.page-hero`
- Added `text-align: center` to the `.page-hero` rule, centring the hero heading ("BUILT FOR THE TRADE"), eyebrow, and intro paragraph.

### css/components.css — `.cta-strip` (new rule)
- Added `.cta-strip` CSS block with `text-align: center`, `background: var(--mm-orange)`, and `padding: var(--sp-xxl) 54px`
- Added `.cta-strip h2` to colour heading `var(--mm-dark)` with bottom margin
- The "WANT TO WORK WITH US?" CTA section on about.html uses class `cta-strip` — this ensures centred alignment

### Notes
- No "Meet the team" heading/subhead, testimonial quote, or "Ready to grow?" heading were found in about.html at time of application — those elements are placeholders or not yet built. Brief items 3, 4, and the "Ready to grow?" label were interpreted as the existing "WANT TO WORK WITH US?" CTA strip.
- Josh and Teddi team cards were not present in the file and were not touched.
- No replacement images were added.
