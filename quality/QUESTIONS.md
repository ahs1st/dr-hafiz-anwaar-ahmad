# Open Questions / Needs owner input

Protocol P5/P10: facts and legal text are not invented; ambiguity is logged, not guessed.

1. **[OWNER INPUT REQUIRED] Legal regions & consent (D4).** Which privacy/cookie law applies (e.g. GDPR/UK, or none for a Pakistan clinic)? The site embeds Google Maps and loads Google Fonts ({3p}), which can set cookies. PRV-02/03 need a privacy-policy link in the footer and, where required, consent before these load. Provide the policy text or approve removing the third-party embed.
2. **[OWNER INPUT REQUIRED] Privacy & Terms pages.** No privacy or terms page exists. Supply text (do not copy another clinic's).
3. **[OWNER INPUT REQUIRED] Canonical host + hosting platform (D8).** Assumed `https://www.dranwaarsangra.com/`. Confirm apex vs www and which host (Netlify / Cloudflare Pages / other) so `_headers` and `404.html` are honoured — other hosts need the same headers set in their own config.
4. **[OWNER INPUT REQUIRED] security.txt contact (SCR-15, optional).** Provide a security contact email + expiry date to add `/.well-known/security.txt`.
5. **[OWNER INPUT REQUIRED] Search Console / Bing (SEO-17).** Owner to verify the property and submit `sitemap.xml`.
6. **Verify structured data.** Confirm the JSON-LD `aggregateRating` (5.0 / 25 reviews) in the Google Rich Results Test; review-snippet support for a physician/local business is not guaranteed. Keeping or removing it is an owner decision.
7. **Confirm facts are current:** fees (PKR 1,000–1,500), phone numbers, address, OPD timings, and the "11+ years" / "5.0, 25 reviews" claims — all were taken from `DR_HAFIZ_ANWAAR_AHMAD_SANGRA_DATA.md` unchanged.
8. **Image note:** the gallery images were downscaled to web sizes (~900 px). If print/zoom quality matters for the services banner, keep the originals from `quality/baseline/images/`.
