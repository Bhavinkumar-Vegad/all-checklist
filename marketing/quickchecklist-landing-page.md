## Above the Fold:

* [ ] Headline is specific (“Payroll in 12 minutes for teams under 50”) not “Welcome to the future”.
* [ ] Subhead names who it is for and the constraint (time, industry, role).
* [ ] Primary CTA is one verb + noun; secondary is visually weaker (text link), not two equal buttons.
* [ ] Hero image/video does not delay LCP past ~2.5s on mobile 4G; poster frame if video.
* [ ] Trust: logos, count, or quoted result near the CTA; fake “As seen in” is not used.

## Offer Integrity:

* [ ] Price, trial length, “no credit card”, and what happens at day 15 match billing and legal.
* [ ] Coupon in the URL still works; expired promo is not the H1.
* [ ] Geographic restrictions (cannot sell in X) are stated before the form.

## Form:

* [ ] Fields are the minimum; each extra field needs a reason (sales asked vs actually used).
* [ ] Work email vs personal: validation matches GTM/CRM routing.
* [ ] Phone: country code; do not strip leading zeros if you store as string.
* [ ] Error on submit is inline; 500 from HubSpot/Marketo is not a blank button.
* [ ] Double-submit is blocked; success is a thank-you URL (for ads conversion) not only a JS toast.
* [ ] Hidden fields: UTM, gclid, referrer persist through the thank-you page into CRM.
* [ ] GDPR/consent checkbox is unchecked by default if required; copy names what they get.

## Message Match (ads → page):

* [ ] Keyword/ad headline and page H1 share the same phrase.
* [ ] Promo code in the ad is visible on the page.
* [ ] Audience (e.g. “for dentists”) is not sent to a generic homepage.

## Proof and FAQ:

* [ ] Testimonials have name, role, company; you have permission.
* [ ] Case study numbers are the approved ones (finance/legal).
* [ ] FAQ answers objections from sales call notes, not filler.

## Tracking:

* [ ] Thank-you page is excluded from the ad “view” conversion or you use a distinct event.
* [ ] Pixel fires once; GTM preview on a cold session.
* [ ] Form abandon vs submit events are named so ops can debug.
* [ ] Call tracking numbers if you use them do not break SEO duplicate if this URL is indexed — decide index/noindex.

## QA:

* [ ] Mobile: CTA not covered by chat widget / cookie banner.
* [ ] Cookie banner: CTA still clickable; consent mode if you claim ads measurement.
* [ ] 404s on nav; logo goes to the right home for this campaign microsite.
* [ ] Spellcheck product names; trademark symbols if brand requires.
* [ ] Social card (Slack/iMessage/LinkedIn debugger) matches the campaign.
