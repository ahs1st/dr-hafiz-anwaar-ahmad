# Changelog

One line per fix: what, why, item ID, evidence. UTC 2026-10-17.

1. Head title shortened to 59 chars, topic-first, brand last. SEO-02. Evidence: index.html head.
2. Meta description rewritten to ~155 chars. SEO-02.
3. Removed obsolete `meta keywords` (ignored by search engines; keyword-stuffing risk). SEO-18.
4. Added `meta robots index,follow,max-image-preview:large`. SEO-04.
5. Open Graph completed: site_name, locale (+ur alternate), absolute `og:image` + width/height/alt, `og:url`. SEO-11.
6. Added Twitter card tags (card, title, description, image, image:alt). SEO-11.
7. Favicons: added real `favicon.ico` (32x32 PNG-in-ICO), `images/favicon.svg`, `images/apple-touch-icon.png` (180). HTM-10.
8. Added `rel=preload` for the hero image. PRF-01/03.
9. Removed unused `Playfair Display` from the Google Fonts request. PRF-03.
10. Added `decoding="async"` to all images; declared width/height on gallery images. HTM-06/PRF-02.
11. Resized/compressed oversized images (WebP): banner 3104²/1.8MB→900²/76KB, entrance 2084×4624/1.7MB→800×1775/100KB, desk 1200×1599/178KB→900×1199/47KB. Total 3.78MB→331KB. PRF-02/PRF-08 budget. Baseline kept in quality/baseline/images.
12. Added `robots.txt` (allow all, sitemap ref). SEO-04.
13. Added `sitemap.xml` (single canonical URL). SEO-05.
14. Added `_headers` with strict CSP, HSTS, nosniff, Referrer-Policy, Permissions-Policy, COOP/CORP/XFO + cache policy. SCR-02, PRF-07.
15. Added `404.html` (real 404, way back, no internal details, noindex). HTM-10, SEO-06.
16. CSS: added `--gold-text` token; eyebrow + light-background stars now ≥4.5:1; footer copy lightened for contrast. A11-03.
17. CSS: added `:focus-visible` outline (teal on light, gold on dark surfaces). A11-02.
18. Added `aria-label` to footer nav; `type="button"` on the menu button; `data-en/data-ur` on top-bar hours. HTM-02/AGT-02/FND-04.
19. `script.js` loaded with `defer`. PRF-05.
20. HTML validity: non-breaking hyphen/space in `tel:` link text → html-validate 0 errors. HTM-05.
21. `styles.css` converted desktop-first → **mobile-first**: base rules now target phones (single-column hero/about/creds/services/clinics/gallery/reviews/CTA, 2-col trust, stacked burger menu, 300px map, hidden header CTAs + brand tagline + top-bar hours), with progressive `@media (min-width:480px|768px|1024px)` enhancements. Removed all `max-width` breakpoints; RTL nav direction now set per-breakpoint. Braces balanced (227/227); html-validate exit 0. A11-06/HTM-06.
22. Fixed horizontal scrolling & full mobile-first UX: added `overflow-x: clip; overflow-x: hidden;` to both `html` and `body`; replaced `left: -999px` skip link; contained pulse animation; converted hero stats to balanced 3-col grid; added sticky mobile bottom action bar (`.mobile-bar`) with 1-tap Call/WhatsApp/Book; mobile header quick-call button; full-width touch buttons on clinic cards; clean time formatting without awkward wrapping. Tested 0px overflow across 320px–1920px. A11-06/FND-03.

