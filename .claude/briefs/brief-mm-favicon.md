# Brief: MM Favicon
Date: 2026-05-01

## What was done

### Step 1 — SVG icon copied
Copied `/Users/teddir/Downloads/files (3) 3/mm-icon.svg` to `/Volumes/KINGSTON/mechanicmarketing-static/assets/mm-icon.svg`.

### Step 2 — PNG favicon downloaded
Downloaded from `https://staging.mechanicmarketing.co/wp-content/uploads/2024/10/favicon.png`.
Result: SUCCESS — 6KB PNG, 200x200px RGBA, valid image file saved to `/Volumes/KINGSTON/mechanicmarketing-static/assets/favicon.png`.

### Step 3 — Favicon link tags added
Added to all 23 HTML files (excluding `._` macOS resource fork files and node_modules):

```html
<link rel="icon" type="image/svg+xml" href="/assets/mm-icon.svg">
<link rel="icon" type="image/png" sizes="200x200" href="/assets/favicon.png">
<link rel="apple-touch-icon" href="/assets/favicon.png">
```

Tags inserted just before `</head>` in:
- index.html, about.html, contact.html, pricing.html
- services/consultant.html, google-ads.html, seo.html, lead-generation.html
- industries/index.html, 4x4.html, american-trucks.html, auto-ac.html, diesel.html, european.html, heavy-vehicle.html, mobile-mechanic.html
- case-studies/index.html, bb-garage.html, accelerate-automotive.html, busselton-automotive.html, core-diesel.html
- blog/index.html
- admin/index.html

Absolute `/assets/...` paths used — works correctly on Cloudflare Pages for all subdirectory pages.
