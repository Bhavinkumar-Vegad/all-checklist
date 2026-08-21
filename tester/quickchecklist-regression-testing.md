## Entry Criteria (do not start a full regression if these fail):

* [ ] Build number / Git SHA / package version is recorded in the report.
* [ ] Environment URL matches the one in the release ticket (no testing last week’s staging by mistake).
* [ ] Migrations have run; feature flags for this release are in the intended state.
* [ ] Test users exist for every role in scope; passwords are not expired mid-run.
* [ ] Payment/SMS/email sandboxes are the test ones; you are not charging a real card.
* [ ] Known blockers from smoke are fixed or explicitly waived.

## Select What to Run (risk, not “all tests”):

* [ ] Map each change in the release notes to a module: auth, billing, search, notifications, admin, imports.
* [ ] Include modules that share code/tables with the change (tax calc when you touched rounding).
* [ ] Include last 2–3 production incidents’ paths even if they were “unrelated”.
* [ ] Include integrations: webhooks in/out, SSO, file storage, search index rebuild.
* [ ] Exclude frozen modules only if they have no shared library bump in this build.

## Data Setup People Forget:

* [ ] User with empty optional profile fields, and user with max-length unicode name.
* [ ] Tenant on a trial, past-due, and enterprise plan if billing exists.
* [ ] Record in a terminal state (cancelled, void, paid) plus one in draft.
* [ ] Clock-sensitive data: expired token, subscription ending today, DST if you have timezones.
* [ ] Dirty data: duplicate emails if the DB still allows them, orphaned FK if staging is messy — document if you skip.

## Must-Repeat Suites:

* [ ] Login, logout, session timeout, SSO if used.
* [ ] Create → edit → list → filter → export of the primary entity.
* [ ] Permissions: each role hits one allowed and one denied action (UI and direct URL/API).
* [ ] Notifications: in-app + email/SMS for the event you shipped.
* [ ] File upload/download if the change touched storage or MIME handling.
* [ ] Search/index: new record appears; deleted/hidden does not.
* [ ] Mobile or responsive if CSS/layout libraries changed.

## Cross-Cut:

* [ ] Browser matrix: at least one Chromium, one Safari/WebKit if you have iOS users, one Firefox if you claim it.
* [ ] Feature flag off: old path still works; flag on: new path; mid-session toggle does not 500.
* [ ] Localization: a long German/Finnish string does not break the header on the changed screens.
* [ ] Observability: a failed action still produces a user-visible error, not a spinner forever.

## Defects During Regression:

* [ ] Build SHA is on every bug; “works on my env” is not possible without it.
* [ ] New fail vs old fail: search the ticket system before opening a duplicate.
* [ ] Do not abort the whole suite for a low-severity visual unless it is a go/no-go item.

## Exit:

* [ ] Pass/fail/blocked counts; remaining Sev-1/2 listed by name.
* [ ] Explicit residual risk: “import of 10k rows not retested”.
* [ ] Go / no-go sentence, not only a spreadsheet dump.
