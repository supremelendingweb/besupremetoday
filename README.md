# besupremetoday.com

Static recruiting site for Supreme Lending. Plain HTML, CSS, and a small JavaScript file. No build step.

## Structure

```
/                    Home
/why-supreme/        Why top producers choose Supreme, leadership, testimonials
/onboarding/         Onboarding and the first 30 days
/products/           Product lineup
/marketing/          Marketing support and tech stack
/training/           Training and monthly calls
/events/             Events and awards
/contact/            Contact recruiting
/404.html            Not found page (served automatically by Cloudflare Pages)
/assets/css/styles.css
/assets/js/main.js   Mobile menu
/assets/img/         Images, favicon, social share image
_headers             Security and cache headers for Cloudflare Pages
sitemap.xml, robots.txt
```

Each page lives in its own folder as `index.html`, so URLs are clean (`/products/`).
Links and assets use root paths (`/assets/...`), so preview with a local server,
not by double-clicking a file:

```
cd besupremetoday-site
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy (GitHub + Cloudflare Pages)

1. Push this folder's contents to the root of a GitHub repository.
2. Cloudflare dashboard > Workers & Pages > Create > Pages > Connect to Git, and pick the repo.
3. Build settings: Framework preset **None**, build command **empty**, build output directory **/**.
4. Deploy, then add `besupremetoday.com` (and `www`) under the project's Custom domains.
5. Every push to the production branch redeploys automatically.

## Editing

- Shared header, footer, and disclosures appear on every page. When you change them, change them in all 9 HTML files (search and replace works well).
- Brand colors and fonts are set once at the top of `assets/css/styles.css` (`.bst { --navy ... }`).
- Before launch, replace `assets/img/bst-logo-lockup-white.png` with the official logo file (same name).
