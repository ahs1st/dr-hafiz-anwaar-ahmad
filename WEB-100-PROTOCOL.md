# WEB-100 PROTOCOL: Perfect-Score Website Checklist for AI Agents

**Version:** 1.1 | **Date:** 17 October 2026 | **Audience:** AI coding agent (primary), site owner (secondary)
**Purpose:** Make a NEW or EXISTING website score 100/100 in every measurable category and stay secure, accessible, discoverable and agent-ready, **without adding weight the project does not need.**
**v1.1 changes:** project-size profiles (LITE/STANDARD/FULL); condition tags so irrelevant items are skipped; "read only what you need" map; proportionality and precedence rules; fewer mandatory items; lighter report. Method inherited from the Master Spec Architect Protocol (decide, don't delegate; no claim without run output; stop on ambiguity; honest uncertainty).

---

## 0. HOW TO USE THIS FILE

1. **Placement.** Save as `docs/WEB-100-PROTOCOL.md`. Some IDEs limit rule-file size (reports for Google Antigravity mention about 12,000 characters; verify in your version), so do not paste this file into a rules file. Put this pointer in `AGENTS.md`:
   ```
   For any web page work (new build, change, audit), use docs/WEB-100-PROTOCOL.md: pick the profile, read only the sections your task needs (Section 0.5), run the gates for that profile, and record results in quality/REPORT.md.
   Never claim a score or PASS without a recorded run. Do the least that meets each item. Ambiguity: log it in quality/QUESTIONS.md and continue unaffected work.
   ```
2. **Profile.** In step 1 of any task, choose one profile from the brief and state it in one line (owner may override). If unsure, use STANDARD.

| Profile | Typical project | Apply | Gates (Section 17) |
|---|---|---|---|
| **LITE** | Brochure, portfolio, landing page, small blog; static or near-static; no accounts; at most one simple form | all **[M]** whose condition holds | LITE column |
| **STANDARD** (default) | Business site with CMS/forms/backend, analytics, small store, growing blog | **[M]** + **[S]** whose condition holds | STANDARD column |
| **FULL** | App with login, payments, multi-language, regulated or sensitive data, high traffic | **[M]** + **[S]** + **[C]** the owner wants | FULL column |

3. **Item format:** `ID [tag]{condition} rule`.
   - **[M]** core: always required when the condition holds (these are what Lighthouse, axe and basic security demand).
   - **[S]** standard: required in STANDARD and FULL; in LITE only if free.
   - **[C]** optional: only if the owner asks or FULL with budget. Never build a feature just to satisfy a [C].
4. **Conditions** (no condition = always applies). If a condition is false, the item is NA automatically; record one line per false condition in the report, not one line per item.
   `{forms}` has user-submitted forms | `{auth}` has login/accounts | `{data}` has own server, database or API | `{i18n}` more than one language | `{rtl}` right-to-left script (Urdu, Arabic, Persian, Hebrew) | `{3p}` third-party scripts/embeds/analytics | `{store}` payments or orders | `{upload}` file uploads | `{actions}` meaningful user actions an agent could perform | `{email}` domain sends email | `{local}` physical location or service area | `{public}` pages meant to be found in search | `{pwa}` installable/offline app.
5. **Read only what you need.**

| Task | Read |
|---|---|
| New page or component | 6, 8, PRF-01/02/10/11 (7), SEO-01..03 (11), AGT-02..04 (13) |
| Styling or design change | 5 (FND-03, 05), 7, 8, 14 |
| Forms, login, API work | 8 (A11-05), 9, 10, 13 |
| Content or SEO edit | 11, 12, HTM-03/06 (6) |
| Speed complaint | 7, 16 |
| Launch or deployment | 15, 9, 11, 17 |
| Full audit or fix of a whole site | everything, via Section 3.2 |

6. **Precedence.** If the project has its own spec, it wins on product and business decisions. This file wins only on the measurable minimums in Section 2 and on security basics. On conflict: do not edit the spec; log the conflict in `quality/QUESTIONS.md`; continue unaffected work.
7. **Volatile facts** (versions, vendor crawler names, standards status, prices, policies): verify against the official page at build time and record source and date. Never rely on memory.

---

## 1. PRIME RULES

- **P1 Proportionality.** Do the least that meets the item. No extra pages, features, dependencies, config options or files "just in case". Every added script or package must earn its place with a measured benefit. Simple beats clever.
- **P2 Evidence over claims.** "Done", "100/100", "PASS" require a recorded command, UTC time, exit code and report path. Otherwise write `NOT_TESTED`.
- **P3 Measure the production build** (minified, compressed, with real cache headers), never the dev server.
- **P4 No cheating.** Never detect Lighthouse or bots to serve a different page; never hide text for SEO; never stuff keywords; never fake reviews, ratings or schema; never add text aimed at AI systems; never delete a real feature to raise a score.
- **P5 Never invent facts.** Business name, address, phone, prices, legal text, testimonials, statistics, certifications stay `[OWNER INPUT REQUIRED]` until supplied. No lorem ipsum or fake data in production.
- **P6 Changeable values are not hardcoded** (URLs, keys, copy, contact data, SEO text, colors outside tokens). Proportionate means: a small content/config file is enough for LITE; no CMS needed.
- **P7 Server is the authority** for prices, permissions, totals and eligibility. All client input is untrusted, including input arriving from AI agents.
- **P8 Fix root causes.** Never disable lint, tests, type checks, CSP or audits to get green. Never silence console errors; remove their cause.
- **P9 Small safe steps.** One category per change set, commit after each, re-run the affected gates. If a fix breaks another gate, revert and rethink.
- **P10 Stop on ambiguity.** Log the question; continue only unaffected work.

---

## 2. TARGET SCORECARD (production build; mobile and desktop)

Measure **per page template** (home, content page, listing, form page, etc.), not every URL. LITE: home + one content page + any form page.

| Area | Target | Measured by |
|---|---|---|
| Lighthouse Performance | 100 (median of 5 runs) | Lighthouse CLI |
| Lighthouse Accessibility / Best Practices / SEO | 100 each | Lighthouse (+ axe for accessibility) |
| Lighthouse Agentic Browsing | all applicable audits pass; **no 0-100 score** (fractional pass ratio, experimental, needs a recent Lighthouse and Chrome; WebMCP audits are informational and need the origin trial/flag) | Lighthouse 13.3+ |
| Core Web Vitals, field p75 | LCP <= 2.5 s, INP <= 200 ms, CLS <= 0.1 (official; unchanged in Aug 2026 sources). Internal stricter budget: LCP <= 2.0 s, INP <= 150 ms, CLS <= 0.05 | RUM, CrUX, Search Console (needs real traffic) |
| Lab engineering targets for a stable 100 | FCP <= 1.0 s, LCP <= 1.5 s, TBT <= 100 ms, CLS ~ 0 (our targets, not official) | Lighthouse |
| Accessibility | WCAG 2.2 AA, 0 axe violations, manual keyboard pass | axe, manual |
| Security | 0 high/critical dependency vulns, 0 leaked secrets, headers per Section 9, no mixed content | audit tools |
| Quality | 0 console errors/warnings, 0 broken internal links, 0 HTML validation errors, no horizontal scroll or overlap at 320/375/768/1024/1440 px | browser run, checkers |

**Honesty clause.** A lab 100 is a snapshot. If a legally required widget or platform limit blocks 100 somewhere, record audit ID, measured value, cause, what was tried, owner decision. Never hide it.

---

## 3. WORKFLOW

### 3.1 New site
1. **Discover:** read the brief; choose profile; list page templates, flows, languages, integrations. Ask at most 7 questions in one batch; otherwise take the default from Section 4 and mark `[DEFAULTED]`.
2. **Decide:** complete Section 4 (only unresolved rows).
3. **Foundation:** scaffold, tokens, env handling, lint/test, and the gates for the profile before feature work.
4. **Build template by template:** semantic HTML first, then CSS, then behavior. Apply only the sections the task needs (0.5). Run per-page gates after each template.
5. **Verify and report:** run the profile's gates on the production build; fix loop; write `quality/REPORT.md`.

### 3.2 Existing site (fix mode)
1. Branch. Save a baseline to `quality/baseline/`: Lighthouse (all categories, 3-5 runs), axe, header scan, dependency audit, link check, screenshots at 375/768/1440.
2. Triage: P0 security or broken function; P1 accessibility blockers, console errors, indexing blockers; P2 score gaps; P3 polish.
3. Fix order: **security, correctness/best practices, accessibility, SEO, performance, agentic readiness** (performance work is the riskiest, so do it on a correct base).
4. After each category: re-run gates and compare screenshots with baseline. Unintended change = revert.
5. No rewrites without owner approval. Log each fix in `quality/CHANGELOG.md` (what, why, item ID, evidence).

### 3.3 Small change (one page, component or text)
Read only the sections from 0.5. Run the per-page gates (Lighthouse on that page, axe, console clean, links). Run the full set only if you touched shared code: layout, tokens, config, dependencies, headers, build setup.

---

## 4. DECISION SHEET (decide only what is unresolved; default applies if the owner is silent)

| ID | Decision | Default if owner is silent |
|---|---|---|
| D1 | Profile (LITE/STANDARD/FULL) | STANDARD |
| D2 | Rendering for public pages | Static or server-rendered HTML; public content present in the first HTML response |
| D3 | Languages; RTL needed? | One language from the brief; `{rtl}` true if the content language is RTL |
| D4 | Legal regions (privacy, consent, accessibility law) | `[OWNER INPUT REQUIRED]`; assume consent is needed before non-essential trackers |
| D5 | Third parties allowed | None until a need is stated; each needs reason, cost and consent rule |
| D6 | Crawler policy: search engines / AI training / AI search / user-triggered AI agents | Allow search engines; no special rules for the AI classes until the owner decides |
| D7 | Agent actions exposed (WebMCP) | None |
| D8 | Canonical host (www or apex) and domain | `[OWNER INPUT REQUIRED]` |

---

## 5. FOUNDATIONS (FND)

- FND-01 [M] One source of truth for repeated facts (site name, contacts, nav, socials, SEO defaults); reuse in footer, schema and contact page.
- FND-02 [M]{data} Env variables validated at startup/build; only listed variables reach the browser; no secrets in client bundles or the repo.
- FND-03 [M] Colors, spacing, type scale, radii, motion and breakpoints come from one token layer (CSS custom properties are enough). Lint for raw literals is [S].
- FND-04 [M]{i18n} All user-visible strings in an i18n catalog. Single-language sites: strings in content files, not scattered in components [S].
- FND-05 [S] Logical CSS properties (`margin-inline-start`, `padding-inline`, `inset-inline`, `text-align: start`) instead of left/right; **[M]** when `{rtl}`.
- FND-06 [M]{rtl} `<html lang dir="rtl">`, `lang`/`dir` on mixed-language fragments, mirrored direction-implying icons, locale-aware numbers/dates (`Intl`), every page tested in RTL.
- FND-07 [S]{rtl} Urdu/Arabic-script typography: font with full coverage (Nastaliq face if that style is wanted), self-hosted and subset, `font-display: swap`, line-height about 1.9-2.2 for Nastaliq, no letter-spacing on Arabic-script text, check descender clipping in buttons and headings.
- FND-08 [M] No mock or placeholder data in production; fixtures live only in `fixtures/` or dev seeds. Every data region has a defined empty state.
- FND-09 [S]{data} Redirects, menus and SEO defaults are data (config or CMS), not code constants.
- FND-10 [M] `.gitignore` covers env files, build output and report outputs; `.env.example` lists names only. Conventional commits and protected main are [S].
- FND-11 [S]{data} One typed API client or wrapper module for all data calls.
- FND-12 [S] README: run, build, test, deploy, edit content, rotate secrets.

---

## 6. HTML AND CODE QUALITY (HTM)

- HTM-01 [M] `<!doctype html>`, `<meta charset="utf-8">` early, correct `<html lang>`, `<meta name="viewport" content="width=device-width, initial-scale=1">`. Never disable zoom (`user-scalable=no`, `maximum-scale=1`).
- HTM-02 [M] Landmarks: `<header>`, `<nav>` (labelled if several), one `<main>`, `<footer>`.
- HTM-03 [M] Exactly one `<h1>`; headings in order without skipping; headings describe content, not styling.
- HTM-04 [M] Native elements first: `<a href>` navigates, `<button>` acts, `<label for>` with `<input>`, `<select>`, `<dialog>`, `<details>`. No `<div onclick>`.
- HTM-05 [M] Valid HTML (0 errors), no duplicate IDs, no inline event-handler attributes (they block a strict CSP).
- HTM-06 [M] Every `<img>` has `width`/`height` (or CSS `aspect-ratio`), meaningful `alt` (`alt=""` if decorative), `srcset`/`sizes` where sizes vary.
- HTM-07 [M] Descriptive link text (never "click here"); `rel="noopener"` on `target="_blank"` links.
- HTM-08 [M] Tables only for data, with `<th scope>`; never for layout.
- HTM-09 [M] Zero console errors/warnings, no failed requests, no 404 assets, no mixed content, no deprecated APIs on any page or flow.
- HTM-10 [M] Real HTTP 404 and 500 pages with a way back and no internal details; `/favicon.ico` exists (a missing one logs a console error), plus an SVG or PNG icon and a 180px touch icon.
- HTM-11 [S] Progressive enhancement: content, navigation and forms work without JS where the stack allows.
- HTM-12 [S] Code quality: strict types (if TypeScript), linter and formatter, no swallowed exceptions, no dead code.
- HTM-13 [C]{pwa} Web manifest, offline page, service worker with a tested update flow.

---

## 7. PERFORMANCE (PRF)

Default budgets (change only with a written reason): JS <= 100 KB gz on content pages (<= 170 KB gz on app pages); above-the-fold images <= 150 KB total; first-load page weight <= 500 KB on content pages; DOM < 800 nodes (never > 1,500).

- PRF-01 [M] **LCP element** known per template: in the initial HTML, `fetchpriority="high"`, never `loading="lazy"`, never rendered by JS, right size and format.
- PRF-02 [M] Images: AVIF or WebP (with fallback if needed), responsive `srcset`, no upscaling, lazy-load below the fold, `decoding="async"`, dimensions declared.
- PRF-03 [M] Fonts: self-host WOFF2, subset, at most 2 families, `font-display`, preload only the one or two critical files (with `crossorigin`), fallback metrics adjusted to avoid shift.
- PRF-04 [M] CSS: critical CSS inline or a small stylesheet, no `@import` chains, remove unused CSS, animate only `transform` and `opacity`.
- PRF-05 [M] JS: split per route, tree-shake, `defer` or `type=module`, no tasks over 50 ms, no heavy libraries for small jobs (no whole lodash/moment), no unneeded polyfills.
- PRF-06 [M]{3p} Each third-party script justified, loaded on interaction/idle or via a facade (video, chat, maps), measured, consent-gated where required.
- PRF-07 [M] Caching: hashed assets `Cache-Control: public, max-age=31536000, immutable`; HTML revalidated (`no-cache` or short s-maxage with revalidation).
- PRF-08 [M] Brotli (gzip fallback), HTTP/2 or HTTP/3, TLS 1.3 where available, CDN edge caching for public pages, TTFB <= 200 ms for cached pages.
- PRF-09 [M] **INP:** handlers under 50 ms, no heavy work on input, debounce, avoid forced reflow, virtualize long lists, `content-visibility: auto` on long off-screen sections.
- PRF-10 [M] **CLS:** reserve space for images, embeds, banners and late fonts; never insert content above existing content after load; skeletons match final size; cookie banner overlays, never pushes.
- PRF-11 [M]{data} Read endpoints p95 <= 300 ms; indexes for known queries; no N+1; pagination on every list.
- PRF-12 [S] Back/forward cache eligible: no `unload` handlers, no `no-store` on HTML unless required.
- PRF-13 [S] Field measurement (RUM with `web-vitals`, CrUX, Search Console) as well as lab; budget gate in CI where CI exists.
- PRF-14 [S] Video: no autoplay with sound, poster image, `preload="none"` or metadata, captions.
- PRF-15 [C] Speculation Rules (prefetch/prerender) for likely next pages, only if safe; resource hints sparingly (at most 2 `preconnect`).

---

## 8. ACCESSIBILITY (A11): WCAG 2.2 AA

Lighthouse covers only an automated subset; the manual checks matter.

- A11-01 [M] Keyboard: everything operable with Tab, Shift+Tab, Enter, Space, arrows, Esc; order matches visual order; no traps; skip link to `#main` as the first focusable element.
- A11-02 [M] Visible focus ring on every focusable element (>= 3:1); never removed without replacement; focused element never hidden behind sticky headers or banners.
- A11-03 [M] Contrast: text >= 4.5:1 (large text >= 3:1); UI components and focus rings >= 3:1; in light, dark, hover and disabled states. Record pairs in tokens.
- A11-04 [M] Every control has an accessible name that contains its visible label text; valid ARIA only; no ARIA where a native element works; no `aria-hidden` on focusable content.
- A11-05 [M]{forms} Persistent visible labels (not placeholder-only); correct `type` and `autocomplete`; required state in text and programmatically; errors in text, linked with `aria-describedby`, announced; error summary on submit; entered data kept.
- A11-06 [M] Targets >= 24x24 CSS px (WCAG 2.2 minimum); aim for 44x44 px for primary touch targets.
- A11-07 [M] Usable at 200% text size and 400% zoom (320 CSS px) without loss or horizontal scroll; relative units; no fixed-height text boxes.
- A11-08 [M] No information by color alone; meaningful icons have text alternatives.
- A11-09 [M] Media: captions for video, transcript for audio, no autoplay audio, pause control for motion over 5 s, no flashing over 3 times per second.
- A11-10 [M] Dialogs, menus, tabs, accordions follow WAI-ARIA Authoring Practices or use native `<dialog>`/`<details>`: focus moves in, is trapped appropriately, returns on close, Esc closes.
- A11-11 [M] Dynamic updates (toasts, cart count, results count, loading) announced through polite live regions; loading states have text.
- A11-12 [M] Unique descriptive page `<title>`; on client-side route changes move focus and announce the new page; language of page and parts declared.
- A11-13 [M] `prefers-reduced-motion` respected; `forced-colors` does not break the UI. `prefers-color-scheme` and `prefers-contrast` are [S].
- A11-14 [M]{auth} Authentication allows paste and password managers (no cognitive test). [M]{drag} Drag interactions have a single-pointer alternative. [S] Do not ask for data already given in the same flow; keep help links in a consistent place.
- A11-15 [M] Manual log (`quality/a11y-manual.md`): keyboard-only run of every key flow. Screen-reader pass (NVDA or VoiceOver) on home, one content page and one form: [S] in LITE and STANDARD, [M] in FULL.
- A11-16 [M]{pdf} PDFs are tagged (title, language, reading order) or an accessible HTML alternative exists.
- A11-17 [C] Accessibility statement page (only true statements; legal wording is owner input). Check whether local law applies and record the decision.

---

## 9. SECURITY (SCR)

Apply by condition. A static site with no forms or backend needs only SCR-01, 02, 11, 12 and 15.

- SCR-01 [M] HTTPS everywhere; HTTP 301-redirects to the canonical HTTPS host; no mixed content; TLS 1.2+ (prefer 1.3); automatic certificate renewal.
- SCR-02 [M] Security headers on all responses (test in report-only where possible, then enforce):
  - `Content-Security-Policy`: strict, nonce- or hash-based; no `unsafe-inline`/`unsafe-eval` for scripts; `object-src 'none'`; `base-uri 'none'`; `frame-ancestors 'none'` (or an explicit list); `form-action 'self'`.
  - `Strict-Transport-Security: max-age=63072000` (add `includeSubDomains` only if every subdomain serves HTTPS; add `preload` only with owner approval, it is hard to undo).
  - `X-Content-Type-Options: nosniff`; `Referrer-Policy: strict-origin-when-cross-origin`.
  - `Permissions-Policy` disabling unused features (camera, microphone, geolocation, payment, usb); do not block what the site uses.
  - `Cross-Origin-Opener-Policy: same-origin` (use `same-origin-allow-popups` if OAuth or payment popups need it); `Cross-Origin-Resource-Policy` per asset intent.
  - Hide server and framework version headers.
- SCR-03 [M]{auth} Session cookies `Secure; HttpOnly; SameSite=Lax` (or `Strict`), short lifetime, rotated on login, invalidated on logout and password change.
- SCR-04 [M]{auth} Passwords hashed with Argon2id (or bcrypt/scrypt, strong parameters); login throttled; generic error messages; single-use short-lived reset tokens with no account enumeration. MFA or passkeys for privileged roles [S].
- SCR-05 [M]{auth} Authorization enforced **on the server for every request**: role x action matrix, object-level checks (no IDOR), deny by default, tests per role.
- SCR-06 [M]{data}{forms} Validate all input server-side (type, length, range, allowlist); parameterized queries only; encode output by context; no `innerHTML` with untrusted data; sanitize rich text with a vetted library.
- SCR-07 [M]{auth}{forms} CSRF protection on state-changing requests (SameSite plus token or origin check); CORS allowlist, never `*` with credentials.
- SCR-08 [M]{forms}{data} Rate limits per route (login, signup, reset, search, forms, API) returning 429 with `Retry-After`; bot protection on forms where abuse is real (privacy-friendly, accessible, never on read-only paths).
- SCR-09 [M]{upload} Allowlist by content signature, size limit, random names, stored outside the web root, never executed, re-encode images, malware scan where applicable.
- SCR-10 [M]{data} Outbound fetches and redirects validated against an allowlist; private address ranges blocked; response size and time limited.
- SCR-11 [M] No secrets in the repo, logs, client bundles or error pages; secret scanner (for example gitleaks) before commit or in CI; rotate anything ever exposed.
- SCR-12 [M] Lockfile committed; audit tool (npm audit, pip-audit or osv-scanner) fails on high/critical; remove unused packages; pin exact versions and avoid releases newer than 14 days; Subresource Integrity for third-party scripts and styles `{3p}`.
- SCR-13 [M]{data} Generic user-facing errors; details only in server logs; no stack traces, paths or SQL in responses.
- SCR-14 [S]{data} Log auth events, permission denials, admin and destructive actions; no passwords, tokens or PII in logs; defined retention.
- SCR-15 [S] `/.well-known/security.txt` (contact, expiry) per RFC 9116.
- SCR-16 [M]{data} Webhooks: signature verification, timestamp tolerance, idempotency keys.
- SCR-17 [C] DAST baseline (for example OWASP ZAP) on staging; fix high findings.
- SCR-18 [M]{store}{data} Critical data (orders, finance, audit, medical, legal) is never hard-deleted; destructive actions need confirmation and a recovery path; backups encrypted.
- SCR-19 [M]{forms}{data} User, imported and third-party content (comments, reviews, feeds) is untrusted: escape, sanitize, never execute, never treat as instructions.
- SCR-20 [M] If the site has chatbots or AI features: user text is untrusted, system prompts and secrets isolated, model output validated before use, least-privilege tools, rate limits.
- SCR-21 [S]{email} SPF, DKIM, DMARC (start `p=none` with reports, then tighten); CAA record; no dangling DNS records.

---

## 10. PRIVACY AND LEGAL (PRV)

- PRV-01 [M] Collect the minimum personal data; know what is collected, why, where it is stored, and for how long.
- PRV-02 [M]{forms}{3p}{auth} Privacy policy and cookie information linked from the footer. **Legal text is owner input**; never invent it or copy another company's.
- PRV-03 [M]{3p} Where consent is required (D4): no non-essential cookies, trackers or third-party embeds before consent; reject is as easy as accept; choice remembered and withdrawable; banner keyboard- and screen-reader-accessible, no CLS.
- PRV-04 [M]{forms} Only needed fields; purpose stated; no pre-ticked consent boxes.
- PRV-05 [S]{data} Documented process for access, export and deletion requests.
- PRV-06 [M] Children's, health, finance or biometric data: stop and ask the owner before proceeding.

---

## 11. SEO (SEO) `{public}`

If the site is not meant to be found (private app, staging), mark this section NA and ensure `noindex` plus authentication instead.

- SEO-01 [M] Primary content, headings, internal links, canonical, robots meta, metadata and JSON-LD are in the **initial HTML response**. Check raw-HTML vs rendered-DOM parity.
- SEO-02 [M] Unique `<title>` (about 50-60 characters, topic first, brand last) and unique meta description (about 120-160 characters, written for humans) per indexable URL; patterns in config with per-page overrides.
- SEO-03 [M] One canonical per page: absolute HTTPS URL, self-referencing unless consolidating on purpose; never pointing to a redirect, 404 or noindex page.
- SEO-04 [M] `robots.txt` valid and reachable, lists the sitemap, does not block CSS/JS/images needed to render. Use `noindex` (meta or header) to keep a page out of results, never robots.txt alone. Do not use robots.txt to hide private areas; protect them with authentication.
- SEO-05 [M] XML sitemap: only canonical, indexable 200 URLs; `lastmod` only when content truly changed; referenced in robots.txt; submitted to Search Console and Bing Webmaster Tools [S].
- SEO-06 [M] Status codes: 200, 301 for moves (no chains or loops), real 404 or 410 for missing pages (no soft-404 returning 200), 5xx only for real errors; redirect map for any migration.
- SEO-07 [M] One host form and one trailing-slash policy enforced by 301; short, lowercase, stable URLs; no session IDs; written rule for parameter and filter URLs (noindex or canonical).
- SEO-08 [M] Every page reachable within 3 clicks, no orphans, descriptive anchor text, visible breadcrumbs on deep pages; build fails on internal 404s.
- SEO-09 [M] Structured data, where present, is true, valid, generated from the same data as the UI. No fake ratings or reviews; FAQ markup only if the FAQ is visible.
- SEO-10 [S] Add `Organization` and `WebSite`, `BreadcrumbList` on deep pages, and type-specific markup (`Article`, `Product`/`Offer`, `Event`) where the content supports it. Rich results are never guaranteed. `LocalBusiness` only with a real location.
- SEO-11 [S] Open Graph and Twitter card tags (title, description, 1200x630 image with alt, `og:url`); image rule in config.
- SEO-12 [M]{i18n} `hreflang` with reciprocal links and `x-default`; one URL per language; localized metadata; language switcher uses real links.
- SEO-13 [M] Mobile and desktop serve the same content, metadata, structured data and links.
- SEO-14 [M] One primary search intent per page; no two pages for the same intent; no thin, duplicate or mass-generated filler; visible author and last-updated date on articles.
- SEO-15 [S] Trust pages: About, Contact (real data), Privacy, Terms; author pages for expert content; consistent business name, address and phone everywhere.
- SEO-16 [S] Pagination and "load more" have crawlable `<a href>` links behind them.
- SEO-17 [S] Search Console verified; indexing and Core Web Vitals reports reviewed after launch.
- SEO-18 [M] Never: hidden text, cloaking, doorway pages, keyword stuffing, link schemes, fake reviews, ranking guarantees.
- SEO-19 [S]{local} One business record feeds name, address, phone, hours everywhere; map listing consistent.
- SEO-20 [C] `content-plan.md`: intent groups, page-to-intent map, topic clusters, update cadence.

---

## 12. AI SEARCH VISIBILITY: AEO AND GEO (AIV) `{public}`

Nothing here guarantees citations. It makes correct content easy to find, quote and attribute.

- AIV-01 [S] Answer first: key pages state the direct answer or definition near the top, in a self-contained sentence that names the entity (not "it" or "they").
- AIV-02 [M] Facts identical across page text, JSON-LD and settings (name, description, contacts, prices only if real).
- AIV-03 [S] Visible author, publish and last-updated dates; sources cited for claims; stable canonical URLs for key facts.
- AIV-04 [S] Crawler policy per D6: classify crawlers as search engine, AI training, AI search, user-triggered AI agent; record the decision; write rules in `robots.txt`; verify each vendor's current user-agent names in its official documentation at build time (names change); do not use unverified names from memory.
- AIV-05 [M] Primary content readable without login, CAPTCHA or client-side-only rendering.
- AIV-06 [M] Never: hidden text for AI, prompt-injection text, mass-generated thin pages, fake expertise.
- AIV-07 [C] `llms.txt` at the root (short summary and links, Markdown). Benefit is not established; Lighthouse checks for it but its absence does not fail the audit; never a substitute for real content; no secrets, no instructions aimed at AI.
- AIV-08 [C] Comparison tables, glossaries and Markdown alternates of key pages if cheap on the platform.

---

## 13. AGENTIC BROWSING READINESS (AGT)

AI agents operate sites through the **accessibility tree**, the DOM and, increasingly, structured tools. A site that is good for assistive technology is mostly good for agents. Most of this section is already covered by Sections 6 and 8, so there is little extra work.

- AGT-01 [M] Sections 6 and 8 satisfied: names, roles, labels, valid tree, no content hidden from the tree while interactive.
- AGT-02 [M] Native controls (HTM-04); button text says the action ("Add to cart: Blue Mug", not "Click"); icon-only buttons have an accessible name.
- AGT-03 [M]{forms} Proper `<form>`, `<label>`, `name`, `type`, `autocomplete`, `required`, `min`/`max`/`pattern`; submit button inside the form; errors programmatically associated; success and failure shown as text.
- AGT-04 [M] Stable UI: CLS ~ 0; nothing moves between an agent seeing it and clicking it; no surprise overlays; cookie banner dismissible by keyboard.
- AGT-05 [M] State lives in real URLs (filters, sort, pagination, tabs, search); back button and deep links work; no navigation that exists only as a JS click handler.
- AGT-06 [M] No hover-only, gesture-only, timing-dependent or drag-only steps; no CAPTCHA on read-only paths.
- AGT-07 [M]{store} Clear summary and confirmation before irreversible actions (payment, delete, send); server validation and authorization stay the authority.
- AGT-08 [S] Agent-test run: complete each key flow with Playwright (or a browser agent) using only role/label locators (`getByRole`, `getByLabel`). If a flow needs brittle CSS selectors, fix the markup. `data-testid` is for tests only.
- AGT-09 [C]{actions} **WebMCP** (experimental and changing; verify the current spec and Chrome status first; Lighthouse's WebMCP audits are informational and weigh nothing). Only add it when the site has real actions and the owner wants it (D7); never in LITE.
  - Declarative: `toolname` and `tooldescription` on the `<form>` (both required); field types and constraints become the input schema, so keep them accurate; clear action names and descriptions.
  - Imperative: register tools in JavaScript with a precise schema; the API shape changed during the draft, so check current docs; register early and deterministically.
  - No auto-submit for payment, deletion or account changes; the human confirms.
  - Tool input is untrusted: validate, authorize and rate-limit on the server exactly like any user input.
  - Feature-detect; the page must work unchanged without it.
- AGT-10 [C] Public API docs (OpenAPI) if the product has an API. A conventional MCP server only if the owner wants one, after a separate security review.

---

## 14. BEST PRACTICES: UX, CONTENT, ANALYTICS (BPR)

- BPR-01 [M] Mobile-first responsive layouts using token breakpoints; test at 320, 375, 768, 1024, 1440; layouts are recomposed, not just scaled.
- BPR-02 [M] Every interactive element has default, hover, focus-visible, active, disabled and (where relevant) loading and error states; every data region has loading, empty and error states.
- BPR-03 [M] Body text >= 16 px, line length 45-75 characters, line-height 1.5-1.7 (Latin; see FND-07 for Nastaliq), clear hierarchy from the token scale.
- BPR-04 [M] Real copy only: no lorem ipsum, no placeholder images, spelling checked in each language.
- BPR-05 [M] No `document.write`, synchronous XHR, deprecated APIs, `alert()` for UX, or permission prompts on page load.
- BPR-06 [M]{forms} Minimal fields, inline validation after blur, clear success confirmation, double-submit protection.
- BPR-07 [S] Clear primary navigation (at most 7 items), current-page indicator, footer with legal and contact links, search when over about 30 pages.
- BPR-08 [S] Dark mode with tokens for both schemes, tested including images and logos.
- BPR-09 [S] Avoid generic-AI look unless the design concept chooses it: stock gradient hero with two identical buttons, uniform card grids everywhere, emoji as UI icons, decorative blobs, identical padding on every section, shadows on everything.
- BPR-10 [S]{3p} Analytics privacy-friendly or consent-gated; documented event list; no PII in events.
- BPR-11 [S]{data} Frontend and backend error monitoring with alerts; source maps uploaded privately.
- BPR-12 [S]{email} Emails accessible with a plain-text alternative; unsubscribe where required.
- BPR-13 [C] Print stylesheet, uptime checks on key flows, View Transitions only if they cost nothing in INP/CLS and respect reduced motion.

---

## 15. DEPLOYMENT AND OPERATIONS (OPS)

- OPS-01 [M] Gates for the profile run before every deploy (in CI if it exists, otherwise a manual script); deploys are repeatable and reversible.
- OPS-02 [M] Staging, if it exists, is never indexable (`X-Robots-Tag: noindex` plus password) and never shares production secrets or data.
- OPS-03 [M] Pre-launch: remove staging `noindex`; canonical host correct; robots.txt and sitemap live; old URLs redirected; consent works `{3p}`; forms reach real inboxes `{forms}`; 404 and 500 tested; favicons and social previews OK; legal pages supplied by the owner.
- OPS-04 [S]{data} Automated encrypted backups; restore test in FULL, with date.
- OPS-05 [S] Alerts for uptime, error rate, certificate and domain expiry.
- OPS-06 [S] Registrar lock, 2FA on all accounts, auto-renew, DNS records documented.
- OPS-07 [S] Upgrades of frameworks or major dependencies are separate tasks, never mixed into feature work.
- OPS-08 [S] After launch (30/60/90 days): Search Console and CWV field review, broken-link scan, dependency updates, header re-scan, accessibility re-test after releases.
- OPS-09 [C] Runbook: deploy, roll back, rotate secrets, restore backup, handle an incident.

---

## 16. SCORE-FIX PLAYBOOK (when an audit is below 100)

| Symptom | Likely causes | Correct fix | Wrong "fix" (never) |
|---|---|---|---|
| LCP high | Lazy or late hero image, big image, slow TTFB, render-blocking CSS/JS, JS-rendered hero | Hero `<img>` in HTML, `fetchpriority=high`, right size/format, cache/CDN, inline critical CSS, SSR/SSG | Lazy-loading the hero; hiding it until JS runs |
| TBT/INP high | Large bundles, long tasks, heavy third parties, whole-page hydration | Split code, defer or drop third parties, partial hydration, yield to main thread, simplify DOM | Silently removing features; delaying scripts past the audit window |
| CLS > 0 | Missing image/embed sizes, late fonts, injected banners | Declare dimensions/aspect-ratio, font fallback metrics, reserve space | Hiding content |
| Unused JS/CSS | Whole libraries, global styles | Tree-shake, route-split, replace libraries | Deleting code without tests |
| Image audits | Wrong size/format, no `srcset` | Responsive pipeline, AVIF/WebP, correct `sizes` | Quality so low it looks broken |
| Contrast, names, labels | Low-contrast tokens, icon buttons, placeholder-only labels | Fix tokens and markup; visible label plus accessible name | `aria-label` that differs from visible text; disabling axe rules |
| ARIA errors | ARIA on wrong roles, `aria-hidden` on focusable | Native elements, valid roles | Spraying ARIA to silence tools |
| Console errors | Missing assets, CSP violations, blocked scripts | Fix the cause (paths, nonces, error handling) | `console.error = () => {}`; removing the CSP |
| CSP/HSTS/COOP findings | Missing or weak headers | Strict CSP with nonce, HSTS, COOP | `unsafe-inline` to "make it work" |
| SEO: links or meta | JS-only links, missing title/description, wrong canonical | Real `<a href>`, unique metadata, correct canonical | Hidden SEO text; duplicated meta |
| SEO: robots/indexing | Blocked CSS/JS, leftover noindex, broken robots.txt | Fix rules; verify in final HTML and headers | Deleting robots.txt unreviewed |
| Tap targets, legible fonts | Tiny controls or text | Token sizes: text >= 16 px, targets >= 44 px | `zoom` hacks, `user-scalable=no` |
| Agentic: unlabeled controls | Same as accessibility | Same as accessibility | Junk `title` attributes |
| Agentic: WebMCP schema | Wrong field types, missing descriptions | Fix form constraints; check current spec | Registering do-nothing tools |
| Score flaky (+/- 3) | Single run, noisy machine, third parties | 5 runs, median, quiet machine, consistent throttling | Cherry-picking the best run |
| Dev and prod differ | Dev server unminified/uncached | Test the production build served like production | Reporting dev-server numbers |

---

## 17. VERIFICATION GATES

Record each in `quality/REPORT.md`: command, UTC time, exit code, evidence path. Commands are examples; check tool names and flags with `--help` and adapt to the stack. For LITE use one-off `npx` runs; do not add tooling the project will not keep.

| Gate | Example | Pass | LITE | STD | FULL |
|---|---|---|---|---|---|
| Build | `npm ci && npm run build` | exit 0, budgets respected | yes | yes | yes |
| Lint, types | `npm run lint && npm run typecheck` | 0 errors | if present | yes | yes |
| Unit/E2E | project test command; Playwright on key flows (mobile + desktop viewport) | all pass | - | key flows | all flows, 2 engines |
| HTML validity | html-validate or Nu Html Checker | 0 errors | yes | yes | yes |
| Lighthouse | `npx lighthouse@13 <url> --only-categories=performance,accessibility,best-practices,seo,agentic-browsing --output=json --output-path=quality/lh/<page>.json` (confirm `agentic-browsing` exists via `--help`; older versions silently ignore unknown categories) | four scored categories = 100; applicable agentic audits pass | 3 runs | 5 runs | 5 runs, CI |
| Lighthouse CI | `lhci autorun` (5 runs); assert accessibility, best-practices, seo `minScore: 1`; performance `minScore: 0.99` (lab noise); release report shows median 100 | exit 0 | - | optional | yes |
| Accessibility | axe-core via Playwright on each template and key states (menu open, dialog open, error) | 0 violations | yes | yes | yes |
| Manual a11y | keyboard run (all tiers); screen reader per A11-15 | log complete | keyboard | keyboard | keyboard + SR |
| Links | link checker on built site and sitemap | 0 broken, 0 chains | yes | yes | yes |
| SEO script | one H1, unique title/description, canonical consistent, sitemap URLs 200 and indexable, JSON-LD parses and matches visible text, hreflang reciprocal, images have alt | 0 findings | yes | yes | yes |
| Raw vs rendered parity | fetch HTML without JS; compare headings, links, content, JSON-LD with the rendered DOM | parity | - | yes | yes |
| Security headers | scanner or script against staging | Section 9 set present | yes | yes | yes |
| Dependencies and secrets | `npm audit --audit-level=high` or `osv-scanner`; `gitleaks detect` | 0 high/critical; 0 findings | yes | yes | yes |
| DAST | OWASP ZAP baseline on staging | 0 high | - | - | yes |
| No-hardcode scan | grep/lint for URLs, hex colors, `localhost`, key-like strings outside an allowlist (each entry justified) | 0 findings | quick grep | yes | yes |
| Visual | screenshots at 375/768/1440 (+ RTL if `{rtl}`) of each template and states | no overflow, no unexpected diffs | yes | yes | yes |
| Field data (after launch) | CrUX, Search Console, RUM | CWV pass at p75 | if traffic | yes | yes |

---

## 18. SELF-CORRECTION

1. **Read the failing audit's own explanation** and fix the stated cause; do not guess.
2. **Regression:** if a gate that passed now fails, revert or bisect the last change set; never stack fixes on a broken state.
3. **Green but wrong is a FAIL:** a passing audit with hidden content, an unusable focus ring or an empty page fails. Open it in a real browser and look.
4. **Typical mistakes to catch in your own output:** hardcoded strings, URLs or colors; leftover placeholder text; fake testimonials or statistics; unlabeled icon buttons; `div` buttons; missing `alt`; `loading="lazy"` on the hero; missing image dimensions; skipped heading levels; two H1s; JSON-LD not matching visible content; wrong canonical; staging `noindex` left on; robots.txt blocking everything; CSP with `unsafe-inline`; secrets in client code; ignored console errors; third-party scripts added "just in case"; auto-submitting WebMCP forms; skipped or deleted tests; reports claiming PASS without run output; extra features or dependencies nobody asked for (P1).
5. **Seemingly impossible check** (a required widget hurts performance): load it on interaction or consent, isolate it with reserved space, measure, and document the exception with evidence and owner decision.
6. **Bug outside the task:** log it in `quality/QUESTIONS.md` with file and reproduction; do not silently expand scope.
7. **Before finishing (adversarial review):** LITE: steps (a) to (c). STANDARD: (a) to (d). FULL: all.
   (a) Hostile user: bad input, empty data, slow network, JS off, keyboard only, 400% zoom, RTL, small phone.
   (b) Lazy agent: where could generic or fake content have slipped in?
   (c) Owner in six months: can content, SEO text and redirects change without code?
   (d) Attacker: IDOR, XSS payloads in every field, CSRF, rate-limit bypass, open redirect, upload abuse.
   (e) Pre-mortem: assume the site failed after launch; name the five likeliest causes (for example a new third-party script wrecking CWV, accidental noindex, expired certificate, leaked key, broken form) and the control that prevents each. No control means a gap.

---

## 19. REPORT TEMPLATE (`quality/REPORT.md`): keep it short

Do **not** write a row per checklist item. Report scores, failures, exceptions and unknowns only.

```
# Quality Report
Site: <name>  Profile: <LITE|STANDARD|FULL>  Commit: <hash>  Date (UTC): <date>
Environment: production build at <url>; Lighthouse <version>; Chrome <version>

## Scorecard (per template; mobile / desktop)
| Template | Perf | A11y | BP | SEO | Agentic pass ratio | Evidence path |

## Gates run
| Gate | Command | Exit | Evidence |

## Not met or NOT_TESTED (item ID, what, why, next action)
## Exceptions (audit ID, value, cause, tried, owner decision)
## Conditions that were false (one line each, e.g. "{auth} false: SCR-03..05 NA")
## Owner inputs still needed ([OWNER INPUT REQUIRED])
```

---

## 20. REFERENCE SNIPPETS (adapt, never copy blindly)

**20.1 Head template (values from config/i18n, not literals)**
```html
<!doctype html>
<html lang="{{lang}}" dir="{{dir}}">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>{{pageTitle}} | {{siteName}}</title>
  <meta name="description" content="{{pageDescription}}">
  <link rel="canonical" href="{{canonicalUrl}}">
  <link rel="icon" href="/favicon.ico" sizes="32x32">
  <link rel="icon" href="/icon.svg" type="image/svg+xml">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">
  <meta name="theme-color" content="{{themeColor}}">
  <meta property="og:title" content="{{pageTitle}}">
  <meta property="og:description" content="{{pageDescription}}">
  <meta property="og:url" content="{{canonicalUrl}}">
  <meta property="og:image" content="{{ogImageUrl}}">
  <meta name="twitter:card" content="summary_large_image">
  <!-- {i18n}: hreflang links. Preload only the single LCP resource. Critical CSS, then deferred scripts. -->
  <script type="application/ld+json">{{jsonLdFromSameDataAsUI}}</script>
</head>
```

**20.2 Strict CSP starting point** (nonce generated per response; test in report-only first; adjust for the framework)
```
Content-Security-Policy: default-src 'self'; script-src 'self' 'nonce-{RANDOM}' 'strict-dynamic'; style-src 'self'; img-src 'self' data:; font-src 'self'; connect-src 'self'; object-src 'none'; base-uri 'none'; frame-ancestors 'none'; form-action 'self'; upgrade-insecure-requests
```
If inline styles are unavoidable, use nonces or hashes for styles, not `unsafe-inline`.

**20.3 robots.txt skeleton** (AI crawler groups per D6 only after the owner decides; verify vendor names in official docs)
```
User-agent: *
Allow: /
# Add Disallow only for low-value crawl traps (for example internal search results).
# Protect private areas with authentication, not robots.txt.

Sitemap: https://example.com/sitemap.xml
```

**20.4 Declarative WebMCP form** (only for [C] AGT-09; experimental; confirm attribute names in current docs)
```html
<form toolname="search_products" tooldescription="Search the product catalog by keyword." action="/search" method="get">
  <label for="q">Search</label>
  <input id="q" name="q" type="search" required minlength="2" autocomplete="off">
  <button type="submit">Search products</button>
</form>
```

**20.5 `lighthouserc.json` skeleton** (STANDARD/FULL; serve the production build with compression and cache headers)
```json
{
  "ci": {
    "collect": { "url": ["http://localhost:4173/"], "numberOfRuns": 5 },
    "assert": {
      "assertions": {
        "categories:performance": ["error", { "minScore": 0.99 }],
        "categories:accessibility": ["error", { "minScore": 1 }],
        "categories:best-practices": ["error", { "minScore": 1 }],
        "categories:seo": ["error", { "minScore": 1 }]
      }
    }
  }
}
```

**20.6 Start prompt for the agent**
```
You are a production web engineer. Read docs/WEB-100-PROTOCOL.md Sections 0-3.
Mode: <NEW | FIX | SMALL CHANGE>. Brief: <paste>.
State the profile and which condition tags are true. Read only the sections your task needs.
Do the least that meets each applicable item. Do not invent business facts; mark owner inputs.
Run the gates for the profile on the production build, fix until the scorecard is met, and write quality/REPORT.md.
Stop and log questions in quality/QUESTIONS.md instead of guessing.
Report: built, commands run, results, deviations, open questions, next step.
```

---

## 21. DEFINITION OF DONE

- [ ] Section 2 scorecard met per template, or each exception documented and approved by the owner
- [ ] All applicable [M] items pass; for STANDARD/FULL all applicable [S] pass or are justified
- [ ] 0 console errors, 0 broken links, no placeholder or invented content
- [ ] Security headers, dependency audit and secret scan clean
- [ ] Keyboard pass logged (screen-reader pass per A11-15)
- [ ] Gates for the profile run on a clean checkout and production build, results in `quality/REPORT.md`
- [ ] FULL only: second-session or owner verification, restore test, monitoring live
- [ ] Owner inputs listed; legal text supplied by the owner
