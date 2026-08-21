## List and Legal:

* [ ] Segment: last engagement, country, language, customer vs lead; you are not mailing the whole database “to be safe”.
* [ ] Suppression: unsubscribes, bounces (hard), complaints, legal holds, competitors, employees if policy says so.
* [ ] Law that actually applies to this list: DPDP (India), GDPR, CAN-SPAM, CASL — physical address / unsubscribe / consent as required. Do not copy a US-only footer onto an India-only list.
* [ ] Preference center link works; unsubscribe is processed before the next send (not “in 10 days”).
* [ ] From name + address are the ones they reply to; reply-to is monitored.

## Render:

* [ ] Subject ≤ ~40–60 chars; no spam-trigger ALL CAPS + “!!!” + fake Re:/Fwd:.
* [ ] Preheader is not the same as the subject and not “Having trouble viewing”.
* [ ] Dark mode: logos not black-on-black; buttons still contrast.
* [ ] Images off: alt text + the email still makes sense.
* [ ] Plain-text MIME part exists and has the same links.
* [ ] Footer: address, unsubscribe, why they received this.

## Personalization Landmines:

* [ ] Merge tags: fallbacks (`*|FNAME|*` → “there”) so you never send “Hi ,”.
* [ ] Dynamic content: empty blocks do not leave giant white gaps.
* [ ] Time/date in body uses the recipient timezone if you claim that.
* [ ] Currency and tax in the email match the linked checkout.

## Links and Tracking:

* [ ] All tracked links resolve (no 404, no staging).
* [ ] UTM consistent; you do not wrap already-wrapped tracking URLs twice.
* [ ] “View in browser” version matches.
* [ ] Deep links / app links fallback to web.
* [ ] Unsubscribe and preference URLs are not rewritten to a broken tracker.

## Deliverability QA:

* [ ] Seed list: Gmail (Primary vs Promotions), Outlook 365, Apple Mail, a corporate filter if you sell B2B.
* [ ] Authentication: SPF, DKIM, DMARC pass on this sending domain/subdomain.
* [ ] Link domain / click tracking domain is warmed if new.
* [ ] Spam test is a hint, not a pass; you still read the email as a human.
* [ ] List-Unsubscribe header (one-click) if the ESP supports it.

## Send:

* [ ] Audience count in ESP matches the expected segment size (±1% — investigate huge gaps).
* [ ] Throttle if you have a new domain or a huge blast.
* [ ] Send time: recipient TZ or evidence-based slot, not “when we finished the HTML”.
* [ ] Holding page / product is live 15 minutes before send.

## After:

* [ ] Hard bounce < ~2%; complaint spike → pause.
* [ ] Click map vs heat: dead CTA vs dead audience.
* [ ] CRM: campaign member / last emailed updated; sales is not calling people who unsubscribed today.
