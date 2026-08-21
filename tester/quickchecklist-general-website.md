## Content and Trust:

* [ ] Phone, email, address, GST/VAT, and hours match Google Business / letterhead — not an old landing page.
* [ ] Duplicate H1s, lorem, “Coming soon”, and unpublished team bios are gone.
* [ ] Legal names of products/partners are spelled as in the contract.
* [ ] Blog/news dates are real; future-dated posts are intentional.
* [ ] 404 and 500 pages are branded and include a path home / contact — not the hosting default.

## Links and Assets:

* [ ] Crawl or a link checker: no 404, 403, or redirect chains > 1 on primary nav + footer.
* [ ] `mailto:` and `tel:` work on mobile; tel uses country code.
* [ ] PDFs/docs open; they are not a 50MB uncompressed scan.
* [ ] Social icons go to the live profiles, not the agency’s placeholder.
* [ ] Logo click → home; favicon present (and not the framework default).

## Forms (contact, quote, newsletter, careers):

* [ ] JS off: either HTML5 validation + server, or a clear “enable JS” — not a dead button.
* [ ] Autocomplete attributes on name/email/address.
* [ ] File upload on careers: size/type; thank-you does not expose the file URL as public listing.
* [ ] Spam: honeypot/rate limit/captcha — you can still submit as a human.
* [ ] Confirmation email (if promised) arrives; it is not in spam only because SPF is missing.
* [ ] Success URL is unique if ads need a conversion page.

## Nav and IA:

* [ ] Current page is indicated; deep pages have breadcrumbs or a way up.
* [ ] Mobile menu: open, close, lock scroll, no off-screen focus trap after close.
* [ ] Search: 0 results, typo, special characters; results are relevant not a 500.
* [ ] Language switcher keeps you on the equivalent page, not always home.

## SEO technical (launch-day):

* [ ] Unique title/description; no “Home | Home | Home”.
* [ ] One H1; heading order is not used as a font-size hack only.
* [ ] Canonical + https + host (www vs apex) match; no mixed sitemap hosts.
* [ ] robots.txt does not Disallow `/` on production; staging is noindex.
* [ ] XML sitemap submitted; it does not list noindex or 404 URLs.
* [ ] OG tags: debugger preview is not a relative URL or localhost.

## Visual:

* [ ] Overlap at 320px: cookie banner vs CTA vs chat widget — you can still click “Buy”.
* [ ] Images: no stretched logos, no watermark stock, width/height to avoid CLS.
* [ ] Hover/focus on buttons; visited links if that is in the design system.
* [ ] Horizontal scroll is not caused by a 1400px hero on mobile.

## Performance:

* [ ] LCP image is compressed and not a 4000px PNG.
* [ ] Fonts: `font-display` so text is not invisible for seconds.
* [ ] Third-party scripts (chat, pixel, A/B) do not block first paint without a reason.

## Security / hygiene:

* [ ] Valid cert; HSTS only if you mean it.
* [ ] Admin `/wp-admin` or `/admin` is not trivially brute-forceable (rate limit / MFA).
* [ ] Directory listing off; `.git` / `.env` not public.
* [ ] Cookie banner: non-essential pixels wait for consent if you claim GDPR.

## Analytics:

* [ ] Pageview on SPA route change if it is an SPA.
* [ ] Thank-you conversion fires once.
* [ ] Cross-domain / referral exclusion so payment gateways do not steal sessions.

## Accessibility:

* [ ] Keyboard through header, menu, form, footer.
* [ ] Alt on content images; empty alt on decorative.
* [ ] Contrast on overlay text on photos.
