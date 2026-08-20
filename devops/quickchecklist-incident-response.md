## Detect:

* [ ] Confirm the alert, ticket, or user report is still happening.
* [ ] Note start time, environment, and customer impact.
* [ ] Check status pages for cloud, DNS, and payment providers.

## Triage:

* [ ] Assign an incident commander if more than one person is involved.
* [ ] Decide severity based on users affected and money or safety impact.
* [ ] Start a dedicated channel or call and keep a timeline.
* [ ] Page the right on-call, not everyone.

## Mitigate:

* [ ] Prefer restore service (rollback, failover, feature flag) over a perfect root cause.
* [ ] Communicate to users or stakeholders with facts and next update time.
* [ ] Avoid deploying unrelated changes during the incident.
* [ ] Preserve logs and metrics before they rotate.

## Recover:

* [ ] Confirm the user-facing symptom is gone, not only the graph.
* [ ] Watch for a second wave after traffic returns.
* [ ] Declare resolved only when monitoring and a smoke test agree.

## Learn:

* [ ] Write a short incident review: what happened, impact, timeline, actions.
* [ ] File follow-up work with owners and dates.
* [ ] Update the runbook while the memory is fresh.
