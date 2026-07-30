# Cares360.org — SEO Optimization To-Dos

Source: Search Console 12-month export (Jul 2025–Jul 2026). Copy each item below into Basecamp as a to-do. Task **name** is the to-do title; **Notes** goes in the to-do description. Do these top-to-bottom — #1 (DEV) unblocks the rest.

---

## To-Do List: DEVELOPER

### 1. Consolidate www vs. non-www (fix homepage canonicalization) — HIGH
**Notes:** Google indexes the homepage as two competing URLs: `cares360.org/` (1,217 clicks, 40,968 impressions, avg position 10.76 — page 2) and `www.cares360.org/` (393 clicks, position 6.56). Same page, split authority, primary version ranks worse.
- Pick one canonical host (recommend non-www: `https://cares360.org`).
- 301 redirect the other host → canonical, site-wide.
- Add self-referencing `rel=canonical` tags.
- Set the preferred domain / confirm both properties in Search Console.
**Done when:** one host resolves, the other 301s, canonical tags present, verified with a crawl.

### 2. Finish index hygiene — remove duplicate & junk URLs — HIGH
**Notes:** Beyond the staging (noindex) and `-m` (301) fixes already made, Search Console still shows duplicate/junk URLs competing for the same content:
- Joomla duplicates: `/index.php/about`, `/index.php/services`, `/index.php/insurance`
- Leftover temp path: `/~lvzwzycm/...`
- System URLs: `/component/content/...`, `/?view=category&id=2`
Actions: 301 or canonical each to its clean URL; block the rest in `robots.txt`; regenerate and resubmit `sitemap.xml` (clean URLs only).
**Done when:** junk URLs return 301/canonical or are disallowed; clean sitemap resubmitted.

### 3. Validate the staging + `-m` fixes in Search Console — MEDIUM
**Notes:** The staging noindex and `-m` → non-`-m` 301s are done, but those URLs still appear in reports because Google hasn't recrawled. Don't assume they're clear.
- In Search Console, use "Validate Fix" on the affected URLs and request re-indexing of the canonical pages.
- Confirm `staging.cares360.org` is noindex AND ideally password/IP-protected so it stops getting crawled.
**Done when:** validation passing; staging + `-m` impressions trending to zero.

### 4. Scaffold indexable landing pages for services — MEDIUM
**Notes:** Content team needs real, crawlable URLs for the new service/location pages (see Content #1). Build the page templates and clean URL structure (e.g. `/std-testing`, `/std-testing-memphis`, `/free-confidential-testing`, `/hiv-testing`, `/hep-c-testing`). Ensure each is in the sitemap, has editable title/meta fields, and isn't blocked.
**Done when:** URLs live, indexable, and ready for content.

### 5. Mobile Core Web Vitals + desktop ranking investigation — MEDIUM
**Notes:** Mobile ranks position 6.99 / 4.46% CTR and drives ~70% of clicks; desktop lags at position 14.02 / 1.98% CTR. Prioritize mobile page experience (Core Web Vitals — LCP, CLS, INP). Separately, investigate the desktop position gap — often a symptom of the duplicate-host issue in #1, so re-check after that ships.
**Done when:** mobile CWV in "good" range; desktop position gap explained/addressed.

---

## To-Do List: CONTENT

### 1. Build dedicated service & location landing pages for testing demand — HIGH
**Notes:** This is the biggest growth lever. Non-brand testing queries pull 17,791 impressions but only 256 clicks because one homepage tries to rank for everything and lands on pages 3–4. Write standalone pages targeting:
- "STD testing Nashville" (1,185 impr, currently pos 24.7)
- "Free STD testing Nashville" (1,115 impr, pos 21.6)
- "STD testing near me" (761 impr, pos 8.25)
- "STI testing Nashville / near me"
- Memphis equivalents ("STD testing Memphis," etc.)
- HIV testing, Hep C testing
Each page: clear H1, location + "free/confidential/same-day" language, services offered, hours/locations, and a booking CTA. Coordinate URLs with Developer #4.
**Done when:** pages published on the scaffolded URLs and submitted for indexing.

### 2. Rewrite title tags & meta descriptions to lift CTR — HIGH
**Notes:** Several pages already rank but barely get clicked — a title/meta problem, not a ranking one. Rewrite with location + benefit hooks ("free," "confidential," "same-day"):
- "free hep c testing near me" — position 1.2, 743 impressions, **0% CTR** (fix first)
- "std testing" — pos 4.9, 0.47% CTR
- "nashville care" — pos 3.5, 0.27% CTR
- Homepage on "nashville cares" — 4,499 impressions, only 1.42% CTR
Keep titles ~55–60 chars, metas ~150 chars, one clear value prop + CTA each.
**Done when:** new titles/metas written and handed to Developer for implementation.

### 3. Add supporting on-page content for brand + "my house" terms — LOW
**Notes:** Terms like "my house clinic," "nashville cares my house," "the corner memphis," and "nashville cares metroplex" get impressions — make sure each location/program has a clearly named, indexable page with its own copy so Google can match intent precisely.
**Done when:** each named program/location has a dedicated, optimized page.

---

**Suggested sequence:** DEV #1 → DEV #2 → DEV #4 + CONTENT #1 (parallel) → CONTENT #2 + DEV (implement) → DEV #3, #5, CONTENT #3. #1 amplifies everything else, so ship it first.
