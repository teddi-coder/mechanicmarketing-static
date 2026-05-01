# Brief: Fix Blog — Real Posts, Post Pages, Blog CSS

## Date
2026-05-01

## Summary
Four-part blog fix:

1. **Blog index real cards** — Replaced 6 placeholder cards (with `[DATE]` tokens and black placeholder image boxes) with real post data. Each card is wrapped in `<a href="/blog/{slug}.html" class="blog-card">` so the entire card is clickable. Featured post hero text colour fixed from white-on-cream to `var(--b)`.

2. **Featured post hero fix** — Added `.blog-featured` class to the featured post wrapper. Title now uses `color: var(--b)`. Background is `var(--w)`. CSS rules added: `.blog-featured`, `.blog-featured h2, .blog-featured-title`, `.blog-featured p, .blog-featured-excerpt`.

3. **6 individual blog post HTML files** — Created at `blog/{slug}.html`:
   - `facebook-ads-for-a-mechanic-workshop.html`
   - `market-dyno-tuning.html`
   - `market-european-car-mechanic.html`
   - `tactics-for-growing-auto-repair-chains.html`
   - `auto-repair-shops-waste-marketing.html`
   - `google-ads-landing-page-for-mechanics.html`

   Each uses: dark hero with white title, pullout image with negative margin, 2-col body (content + sticky sidebar CTA), standard site header/footer.

4. **Blog post CSS** — Appended to `css/global.css`: `.blog-post-hero`, `.blog-post-title`, `.blog-post-meta`, `.blog-post-image`, `.blog-post-body`, `.blog-post-content p`, `.blog-cta-box`, `a.blog-card` (hover lift), `.blog-featured` visibility fix. Responsive breakpoint at 768px collapses sidebar.

## Files changed
- `blog/index.html`
- `css/global.css`
- `blog/facebook-ads-for-a-mechanic-workshop.html` (new)
- `blog/market-dyno-tuning.html` (new)
- `blog/market-european-car-mechanic.html` (new)
- `blog/tactics-for-growing-auto-repair-chains.html` (new)
- `blog/auto-repair-shops-waste-marketing.html` (new)
- `blog/google-ads-landing-page-for-mechanics.html` (new)
