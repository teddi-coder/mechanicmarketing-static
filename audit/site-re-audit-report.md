# Mechanic Marketing — Site Re-Audit Report
**Date:** 2026-05-02
**Repo:** teddi-coder/mechanicmarketing-static
**Assets root:** public/
**Previous audit:** audit/site-audit-report.md

---

## Fix verification summary

| Fix | PR | Status | Notes |
|---|---|---|---|
| Staging image hotlinks | #8 | ✅ Pass | Zero `staging.mechanicmarketing.co` refs in `public/` |
| GA4/GTM | #9 | ✅ Pass | GTM-KVCKK93P present on all 45 pages (exactly 2 occurrences each); `form_submission` event confirmed in `public/contact.html:251` |
| Canonical tags | #10 | ✅ Pass | All 45 pages have exactly 1 canonical; all URLs well-formed (`https://mechanicmarketing.co/...`, no `.html`, no `www`) |
| OG + blog meta descriptions | #11 | ✅ Pass | All 45 pages have `og:title`; all 23 blog posts have meta descriptions; single consistent OG image URL |
| Header rebuild | #12 | ✅ Pass | `mm-header` on all 45 pages; no staging logo refs; no old `.site-header` |
| Logo marquee | #13 | ✅ Pass | 10 workshops in marquee, CSS `@keyframes mm-scroll` animation confirmed |

---

## New issues found

### Technical

**T1 — Favicon files missing at `public/` root** (P1)
`favicon.png`, `favicon.ico`, and `apple-touch-icon.png` do not exist at `public/`. The `<link rel="icon">` tags in every page point to `/assets/favicon.png` (which does exist at `public/assets/favicon.png`) — so the icon works via the explicit link tag, but browsers that probe `/favicon.ico` directly (and social crawlers expecting `/apple-touch-icon.png`) will get 404s.
- `public/assets/favicon.png` ✅ (exists, referenced correctly in `<head>`)
- `public/favicon.ico` ❌ (missing)
- `public/apple-touch-icon.png` ❌ (missing)

**T2 — robots.txt missing** (P1)
No `public/robots.txt`. Without it, all crawlers have unrestricted access. Needed to block `/admin/` from indexing and to reference the sitemap.

**T3 — sitemap.xml missing** (P1)
No `public/sitemap.xml`. Required for Google Search Console submission, especially important around the domain cutover.

**T4 — 188 macOS resource fork files (`._*`) in `public/`** (P2)
`find public/ -name '._*' | wc -l` returns 188. These are macOS metadata files that will be deployed as real assets by Wrangler, wasting bandwidth and potentially confusing crawlers. Should be deleted and added to `.gitignore`.

**T5 — WP production CDN links in `index.html`** (Known — logged separately)
2 case study card thumbnails on `index.html` still point to `mechanicmarketing.co/wp-content/...` (production WordPress CDN). Will break when WP is decommissioned. Not a regression from this sprint — flagged in PR #13 and logged for a separate brief.

### Analytics & tracking

None found beyond known items.

### Content & SEO

**S1 — 23 of 45 page titles exceed 60 characters** (P2)
All blog post titles and 2 industry page titles are over the recommended 60-char limit. Google will truncate them in SERPs. The worst offenders (all blog posts using full article title + " — Mechanic Marketing" suffix):
- `How to Turn Google Ads Landing Page Clicks...` — 98 chars
- `How Much Does It Cost to Open an Auto Repair Shop?...` — 91 chars
- `Why Most Auto Repair Shops Waste Marketing Spend...` — 91 chars
- `Dropped in Google Rankings?...` — 91 chars
Full list: all 23 blog post pages, plus `industries/american-trucks.html` (61) and `industries/european.html` (61).

**S2 — No `<script type="application/ld+json">` structured data** (P2)
No Organisation, LocalBusiness, or WebSite schema on any page. Missing from `public/index.html`. Important for rich results and Knowledge Panel at launch.

**S3 — `__BOOKING_URL__` placeholder still in `public/contact.html`** (P1)
Line 85: `<a href="__BOOKING_URL__" class="btn btn-secondary" ...>Book a call</a>` — the booking calendar URL was never substituted. Live users clicking "Book a call" will get a broken link.

---

## Known outstanding items (not regressions)
- WP production CDN links in case study thumbnails on `index.html` (T5 above — separate brief)
- Mailchannels DNS record (Cloudflare dashboard task — not a code issue)

---

## Prioritised fix list (new issues only)

| Priority | Issue | File(s) | Effort |
|---|---|---|---|
| P1 — High | S3: `__BOOKING_URL__` placeholder — broken CTA on contact page | `public/contact.html:85` | 5 min — just needs the real URL |
| P1 — High | T1: favicon.ico + apple-touch-icon.png missing at root | `public/` | Low — copy/convert from existing `public/assets/favicon.png` |
| P1 — High | T2: robots.txt missing | `public/robots.txt` | Low — create file, block `/admin/`, add sitemap ref |
| P1 — High | T3: sitemap.xml missing | `public/sitemap.xml` | Medium — generate from page inventory (45 pages) |
| P2 — Medium | T4: 188 macOS `._*` files in `public/` | `public/**` | Low — `find public/ -name '._*' -delete` + `.gitignore` entry |
| P2 — Medium | S1: 23 blog titles over 60 chars | `public/blog/*.html` | Medium — rewrite `<title>` tags (separate brief) |
| P2 — Medium | S2: No structured data / schema | `public/index.html` | Medium — add Organisation + WebSite JSON-LD |
