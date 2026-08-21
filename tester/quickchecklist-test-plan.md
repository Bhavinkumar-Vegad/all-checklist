## Scope Lock:

* [ ] In-scope stories/tickets listed by ID; out-of-scope is written (not “we’ll see”).
* [ ] Environments: which one is test-of-record; which is only for debugging.
* [ ] Browser/device/OS matrix with owners; “all browsers” is replaced with a finite list.
* [ ] Roles in scope (guest, user, manager, admin, API client).
* [ ] Data classification: can testers use production copies? If yes, who approved?

## Risks That Change the Plan:

* [ ] New auth, payments, migrations, or file parsing → extra security/perf cases.
* [ ] Third parties (Stripe, Firebase, SSO) → sandbox limits and who owns vendor access.
* [ ] Tight deadline → which cases are must vs skip, signed by PM.

## Coverage Design:

* [ ] Each in-scope requirement/AC maps to at least one case ID (traceability column).
* [ ] Negative cases: validation, authz deny, duplicate submit, stale tab.
* [ ] State cases: empty, 1, many, max, expired, cancelled.
* [ ] Accessibility: at least keyboard + one AT pass on the new UI, not a separate “maybe later”.
* [ ] API: contract cases if UI is not the only client.
* [ ] Non-functional: what you will measure (p95, error rate) and what you will not (full soak) this cycle.

## Data and Environments:

* [ ] Named accounts per role; 2FA/reset path documented so testers are not locked out.
* [ ] Refresh policy: who resets staging and when; testers warned before wipe.
* [ ] Feature flags: matrix of on/off if both must work.
* [ ] Time travel: how to test expiry without waiting 30 days (fixture, admin tool).
* [ ] Observability access: testers can see logs/Sentry for the test env.

## Execution Rules:

* [ ] Severity/priority definitions (user cannot proceed vs cosmetic).
* [ ] Bug template: SHA, env, user, steps, expected, actual, logs.
* [ ] Daily standup artifact: executed, passed, failed, blocked, not-run.
* [ ] Entry: smoke green. Exit: no open Sev-1, Sev-2 waived in writing, coverage % or “all must-run IDs done”.

## UAT Handoff:

* [ ] UAT script is not a dump of 400 QA cases; it is the business scenarios.
* [ ] Known defects UAT will hit are listed so they do not file duplicates.
