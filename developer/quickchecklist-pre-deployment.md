## Code and Config:

* [ ] Confirm the release branch includes only intended changes.
* [ ] Verify environment variables are set for the target environment.
* [ ] Confirm secrets are loaded from a secret manager, not from the repo.
* [ ] Check feature flags for the release are in the correct state.
* [ ] Remove debug endpoints, test accounts, and seed data that must not go live.

## Database and Jobs:

* [ ] Review migrations and confirm they are backward compatible.
* [ ] Take a verified backup before applying production migrations.
* [ ] Confirm cron jobs, queues, and workers are ready for the new code.
* [ ] Check indexes and long-running migrations will not lock busy tables.

## Quality Gates:

* [ ] Confirm unit, integration, and smoke tests passed on this build.
* [ ] Run a production-like smoke test on staging with real-ish data.
* [ ] Check error tracking, logs, and APM are receiving events from staging.
* [ ] Verify the build artifact version matches the release notes.

## Infrastructure:

* [ ] Confirm SSL, domains, DNS, and redirects point to the right place.
* [ ] Check disk, memory, and connection limits can absorb the release.
* [ ] Confirm CDN, cache, and object storage configs match the new assets.
* [ ] Verify health checks and rollback or previous-version deploy still work.

## Go-Live:

* [ ] Agree a deploy window and a rollback owner.
* [ ] Notify support, QA, and stakeholders of the start and expected impact.
* [ ] Deploy, then hit the critical user paths immediately.
* [ ] Watch error rate, latency, and business metrics for the first 30 to 60 minutes.
* [ ] Write down what shipped, what broke, and follow-up tasks.
