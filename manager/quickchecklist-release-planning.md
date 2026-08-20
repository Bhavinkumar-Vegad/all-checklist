## Release Scope:

* [ ] Freeze the list of features, fixes, and known exclusions.
* [ ] Confirm version number, release name, and target environments.
* [ ] List migrations, config changes, and feature flags that must ship together.
* [ ] Identify rollback or feature-toggle off as a real option.

## Quality:

* [ ] Confirm QA sign-off or a written list of remaining risks.
* [ ] Confirm critical defects are fixed or explicitly accepted.
* [ ] Confirm staging matches production closely enough for the smoke pass.
* [ ] Confirm support has a short list of expected user-facing changes.

## Communication:

* [ ] Draft release notes for internal and, if needed, customer audiences.
* [ ] Notify customer success, marketing, and on-call before the window.
* [ ] Agree who announces go-live and who handles "is it down?" questions.
* [ ] Schedule a war-room or chat channel for the deploy window.

## Go-Live:

* [ ] Confirm deploy owner, verifier, and rollback owner.
* [ ] Run production smoke tests immediately after deploy.
* [ ] Watch errors, latency, and a business KPI for an agreed period.
* [ ] Mark the release done only after smoke and monitoring look healthy.

## After:

* [ ] File follow-up tickets for leftover issues.
* [ ] Hold a short review if anything unexpected happened.
* [ ] Update runbooks with what you learned.
