# mechanicmarketing-static

Static HTML rebuild of [mechanicmarketing.co](https://mechanicmarketing.co) — plain HTML, CSS, and vanilla JS. No framework, no build step. Deployed via Cloudways Git Deployment.

---

## Deployment

**Host:** Cloudways Git Deployment — MM Server
**Trigger:** Push to `main` → Cloudways auto-pulls → live within ~30 seconds
**Manual deploy:** Cloudways dashboard → Application → Git Deployment → Pull
**Domain:** mechanicmarketing.co

### Update workflow

```bash
git add <files>
git commit -m "describe change"
git push
```

---

## Repo structure

```
public/          ← web root (all site files served from here)
  index.html
  about.html
  contact.html
  pricing.html
  blog/
  case-studies/
  industries/
  services/
  css/
  js/
  images/
  assets/
  robots.txt
  sitemap.xml
functions/       ← Cloudflare Pages Functions (contact form handler)
audit/           ← site audit reports
```

**Cloudways document root must be set to `public_html/public/`** — `index.html` is in the `public/` subfolder, not the repo root.

---

## Local preview

Open any `.html` file directly in a browser, or use any static server:

```bash
cd public && python3 -m http.server 8080
```
