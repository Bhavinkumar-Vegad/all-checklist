## Search Intent:

* [ ] Query is mapped to intent (informational / commercial / transactional / local); the page type matches (guide vs category vs PDP).
* [ ] You are not targeting a head term on a 300-word blog that cannot win.
* [ ] Title in SERP: ~50–60 chars, primary phrase near the front, no ALL CAPS, no duplicate titles in the site export.
* [ ] Meta description: ~140–160 chars, unique, has a reason to click; it is not the same sentence as the H1.
* [ ] H1 is the page topic (usually one primary H1), not “Welcome to Company”.
* [ ] URL: lowercase, hyphens, no session ids, no two URLs for one page (`/a` vs `/a/`).

## On-Page Content:

* [ ] First 100 words answer the query; keyword stuffing and hidden text are absent.
* [ ] H2/H3 match real subquestions (People Also Ask) you intend to rank for.
* [ ] Internal links: 2–10 relevant, descriptive anchors, not “click here”; orphan page has inbound links from a hub.
* [ ] Outbound links to sources where you cite stats; `rel` sponsored/ugc if paid.
* [ ] Thin sections (“lorem”, 50-word location pages cloned 200 times) are noindexed or rewritten.
* [ ] E-E-A-T: author, date, sources, about/contact — especially YMYL.
* [ ] Images: descriptive filename, alt that is not keyword spam, width/height, compressed; LCP image is prioritized.
* [ ] Video: transcript or captions if it holds the unique content.

## Canonical / Indexation:

* [ ] Canonical is self or the one true URL (https, host, trailing slash policy matches).
* [ ] `noindex` is not left on from staging.
* [ ] `hreflang` reciprocal if you have locales; x-default is set if you use it.
* [ ] Pagination: crawlable next links or a view-all URL Google can fetch. Do not rely on `rel=next/prev` — Google dropped that as a ranking signal.
* [ ] Faceted nav: parameter handling agreed (noindex or canonical to clean URL) so you do not index 10k sort variants.
* [ ] robots.txt does not block CSS/JS you need for rendering or the page itself.
* [ ] XML sitemap: only 200, canonical, indexable URLs; lastmod is honest.
* [ ] Soft 404 (200 with “not found” content) is a real 404/410.

## Technical That Affects Rank:

* [ ] Core Web Vitals field data (CrUX) for this URL group, not only Lighthouse on desktop.
* [ ] Main content is in the HTML; not only client-rendered empty shell if you have no SSR/prerender.
* [ ] Duplicate title/description cluster in Search Console is cleaned.
* [ ] Structured data: type matches page; rich result test valid; no fake review stars.
* [ ] Open Graph/Twitter tags match what you want shared; they do not contradict the title.

## After Publish:

* [ ] URL Inspection (GSC) for the live URL; request indexing if new.
* [ ] Internal search / nav can reach it within 3 clicks from home if it is important.
* [ ] Canonical vs redirected chains: max 1 hop when you control it.
* [ ] Tracking: landing page view + conversion event fire once (not double with GTM + in-code).
