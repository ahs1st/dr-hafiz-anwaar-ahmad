# Quality Report

Site: Dr. Hafiz Anwaar Ahmad Sangra — Consultant Cardiologist, Faisalabad
Profile: LITE (brochure / single-page static site; no accounts, no forms, no backend)
Baseline: `quality/baseline/images/` (originals)  ·  Date (UTC): 2026-10-17 03:03Z
Environment: no Chrome / Lighthouse / axe available in this environment — browser-based scores are NOT_TESTED.

## Scorecard (home template; mobile / desktop)
| Template | Perf | A11y | BP | SEO | Agentic pass ratio | Evidence path |
|---|---|---|---|---|---|---|
| index.html (home) | NOT_TESTED | NOT_TESTED | NOT_TESTED | NOT_TESTED | NOT_TESTED | static checks below |
| 404.html | NOT_TESTED | NOT_TESTED | NOT_TESTED | n/a (noindex) | NOT_TESTED | static checks below |

## Gates run
| Gate | Command | Exit | Evidence |
|---|---|---|---|
| HTML validity (home) | `npx html-validate@9 index.html` | 0 | 0 errors |
| HTML validity (404) | `npx html-validate@9 404.html` | 0 | 0 errors |
| JSON-LD parses | node JSON.parse of the ld+json block | 0 | valid JSON |
| Duplicate IDs | scripted scan | 0 | 13 IDs, 0 duplicates |
| One H1 / alt / dimensions / rel=noopener | scripted scan | 0 | 1 h1; 7/7 imgs alt; 7/7 width+height; 0 target=_blank missing noopener |
| Asset weight audit | WIC size/measure | - | page images 3.78 MB → 331 KB (see CHANGELOG) |
| Lint / types / unit / build | none present (vanilla HTML/CSS/JS) | n/a | - |
| Lighthouse, axe, links, headers, raw-vs-rendered, manual keyboard/SR | not runnable here | - | NOT_TESTED |

## Fixes applied (summary)
SEO-02 (title/description length), SEO-11 (OG/Twitter + absolute image), HTM-10 (favicon.ico + SVG + apple-touch-icon + real 404), SCR-02 (security headers), SCR-12/HTM-09 (valid HTML), PRF-01/02 (LCP preload + decoding + dimensions), PRF-03/06 (dropped unused Playfair Display), PRF-07 (cache headers), SEO-04/05 (robots.txt + sitemap.xml), A11-02 (focus-visible), A11-03 (gold-on-white contrast), footer nav label, i18n for top-bar hours, `defer`, `type="button"`, A11-06/HTM-06 (mobile-first responsive rewrite).

## Not met or NOT_TESTED
- Lighthouse Perf/A11y/BP/SEO/Agentic, axe-core: NOT_TESTED — no browser in this environment. Run on the production build before claiming a score.
- Raw vs rendered parity, Link checker on served site, Header scan, Mixed content: NOT_TESTED — need the deployed host.
- Manual keyboard run + screen-reader pass (`quality/a11y-manual.md`): NOT_TESTED — needs a human.
- PRV-02/03 (privacy policy link + consent before Google Maps/Fonts): NOT met — legal text is owner input (see QUESTIONS).
- Field data (CrUX / Search Console): N/A until the site has traffic.

## Exceptions
- JSON-LD `aggregateRating` (5.0, 25 reviews) kept from owner data. Review-snippet support for `Physician`/LocalBusiness is not guaranteed — verify in the Google Rich Results Test. Owner decision; not removed because the reviews are real (P4/P5).
- Google Fonts + Google Maps embed are third-party ({3p}) and currently load without a consent gate. Proportionate for LITE, but a legal/consent decision is required (D4).

## Conditions false (NA)
`{forms}`, `{auth}`, `{data}`, `{store}`, `{upload}`, `{actions}`, `{email}`, `{pwa}`, `{pdf}`, `{drag}` are all false → their conditional items are NA.
Conditions true: `{public}`, `{local}`, `{i18n}` (EN/UR), `{rtl}` (Urdu), `{3p}` (Google Fonts, Google Maps, WhatsApp).

## Owner inputs still needed ([OWNER INPUT REQUIRED])
See `quality/QUESTIONS.md`: legal regions/consent (D4), canonical host + hosting platform (D8), privacy/terms text, security.txt contact, Search Console/Bing verification.
