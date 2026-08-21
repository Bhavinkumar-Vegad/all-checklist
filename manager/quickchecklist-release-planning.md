## Freeze:

* [ ] Change list is a ticket dump with owners, not a slide that says “improvements”.
* [ ] Explicitly not shipping: listed so sales/CS do not promise them on the webinar.
* [ ] Version: semver/build/store version codes for iOS/Android/web all recorded (they often diverge).
* [ ] Flag matrix: what is on in prod at T+0 vs T+24h ramp.
* [ ] Migration + search reindex + cache flush + cron: ordered, with who runs them.

## Quality Bar:

* [ ] Exit criteria from the test plan are copied here; “QA is done” is not a criterion.
* [ ] Sev-1 = no release; Sev-2 = named accepter and user workaround.
* [ ] Perf budget: p95 of the hot path vs last release, not “felt fine on office wifi”.
* [ ] Accessibility/security tickets that were “next sprint” for three sprints are either in or accepted in writing.
* [ ] Staging data volume is closer to prod for the one query you know is slow.

## Comms:

* [ ] Internal notes: what support should say, including “this button moved”.
* [ ] Customer notes: user-visible behavior only; no git jargon.
* [ ] Status page: pre-approved maintenance text if you expect blips.
* [ ] Marketing/sales enablement date is not the same hour as an untested migrate.
* [ ] Who tweets / emails customers if you rollback.

## Window:

* [ ] Not Friday 16:00 unless you have weekend on-call that agreed.
* [ ] Not during the customer’s peak (timezone, month-end, campaign).
* [ ] Vendor change freezes (cloud, payment, Apple) checked.
* [ ] Dual control: one deploys, another watches metrics; same person is documented if unavoidable.

## Rollback Is a Plan, Not a Hope:

* [ ] Previous artifact id is known and a dry-run happened on staging.
* [ ] DB rollback vs roll-forward: if you cannot reverse, the forward fix script is reviewed.
* [ ] Feature flag off is the first lever for UI/API that supports it; you tested the off path this week.
* [ ] CDN/asset rollback if HTML caches old JS.

## T+0 to T+24h:

* [ ] Smoke on prod with a canary user / region.
* [ ] Watch: 5xx, p95, queue lag, error tracker, payment success rate, sign-up rate — pick the ones this release can break.
* [ ] CS queue: spike in “can’t log in” in the first hour is an incident, not a ticket pile.
* [ ] Close the release only after the watch window, not after the pipeline is green.
