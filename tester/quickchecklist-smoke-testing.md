## Identify the Build:

* [ ] You are on the URL/artifact named in the deploy message, not a bookmarked staging.
* [ ] SHA or version is visible (footer, `/health`, about screen) and matches CI.
* [ ] Feature flags for the smoke scope are on; unrelated experiments are noted.

## Blockers (stop the release if any fail):

* [ ] TLS certificate is valid; mixed-content is not breaking login.
* [ ] Home/landing loads; no white screen, no continuous 5xx in network tab.
* [ ] Login works for a standard user; error on bad password is sane (no 500, no stack trace).
* [ ] Session cookie is set; refresh keeps you logged in if that is the product behavior.
* [ ] The #1 money or mission path completes once (checkout, create project, send message — whatever you sell).
* [ ] Logout (or token expiry) prevents using the back button to see PII if that is required.

## App Shell:

* [ ] Primary nav links return 200, not 404 on renamed routes this release.
* [ ] API host is the right environment (no accidental prod API from staging UI or the reverse).
* [ ] Static assets (JS/CSS) are not 404 after a CDN/cache deploy.
* [ ] Time/clock: page does not show 1970 or “Invalid Date” in header widgets.

## Data and Jobs:

* [ ] A write persists after hard refresh (not only in memory).
* [ ] If you have a queue: one worker is alive (dummy job or admin “queue depth”).
* [ ] Email/SMS sandbox: one notification is received or visibly queued, if the release touches that.

## Integrations:

* [ ] Webhook URL health or “test connection” for the one integration in this release.
* [ ] OAuth callback does not fail with `redirect_uri_mismatch` after an env change.

## Decision:

* [ ] Record pass/fail with timestamp and tester name.
* [ ] Fail = blocked: do not start full regression; ping deploy owner with SHA and screenshot of the 5xx/white screen.
* [ ] Pass: hand off to regression/UAT with the same SHA.
