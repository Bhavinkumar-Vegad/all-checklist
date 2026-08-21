## 0–5 Minutes:

* [ ] Symptom in one sentence: “EU checkout 5xx since 14:12 UTC”, not “site is slow”.
* [ ] Scope: one region, one SKU, one IdP, or global.
* [ ] Still happening: refresh dashboards; it is not a single tweet.
* [ ] Status of cloud, DNS, CDN, identity, payments — official pages + your synthetic checks.
* [ ] Severity: SEV1 (money/login down for many) vs SEV3 (one tenant). Write it down so paging matches.

## Command:

* [ ] Incident commander (IC) is named; they do not also deep-dive the DB.
* [ ] Scribe keeps a timeline (UTC).
* [ ] Channel: `#inc-YYYYMMDD-shortname`; off-topic goes elsewhere.
* [ ] Page only the rotations you need; do not @channel the company.

## Mitigate First:

* [ ] Rollback / flag off / failover / disable the bad cron — pick the fastest safe lever.
* [ ] Do not “quickly deploy a fix” as the first action unless rollback is impossible.
* [ ] Scale-out is not a fix for a crashing tight loop (it multiplies cost and crash rate).
* [ ] Feature that is on fire: turn it off even if marketing wanted it today.

## Comms:

* [ ] Internal: every 15–30 min even if “no change”.
* [ ] External: honest, no speculation (“we’re investigating login failures”), next update time.
* [ ] Legal/PR involved if data may have leaked — before tweets.
* [ ] Do not paste customer PII or tokens in Slack.

## Evidence:

* [ ] Snapshot graphs; increase log retention if the default is 3 days.
* [ ] Do not restart pods “to see” before you capture heap/thread dumps if that is the only evidence.
* [ ] Change list: deploys, flags, DNS, certs, vendor in the last 24h.

## Recover:

* [ ] User path works from outside the office network.
* [ ] Backfill: failed jobs replayed once, with idempotency (no double charges).
* [ ] Error budget / SLO: declare resolved when symptom is gone, not when you have a root-cause essay.

## After:

* [ ] Blameless review within a few days: contributing factors, not a person.
* [ ] Action items have owners and dates; “be more careful” is not an action.
* [ ] Runbook updated with the actual commands that worked.
* [ ] Customer credits / regulatory notification if that is in policy.
