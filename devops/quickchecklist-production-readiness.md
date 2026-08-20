## App:

* [ ] Production config has debug disabled and stack traces hidden from users.
* [ ] Health, readiness, and liveness endpoints exist if the platform needs them.
* [ ] Migrations have been run on a production-like copy first.
* [ ] Backups restore successfully in a drill, not only in theory.

## Security:

* [ ] TLS is valid and HTTP redirects to HTTPS.
* [ ] Secrets are rotated and not shared in chat.
* [ ] Admin surfaces are not public without auth.
* [ ] Dependency and container images are patched or accepted as risk.

## Reliability:

* [ ] Resource limits and autoscaling rules are set.
* [ ] Error tracking and logs are connected to this environment.
* [ ] Alerts fire on high error rate, saturation, and certificate expiry.
* [ ] On-call knows how to roll back and where the runbook lives.

## Data and Compliance:

* [ ] Retention and deletion processes match the privacy policy.
* [ ] Access to production data is limited and audited.
* [ ] Third-party processors are listed if you handle personal data.

## Sign-Off:

* [ ] Smoke tests passed on production after the first deploy.
* [ ] Owners for app, infra, and data are named.
* [ ] Known issues are written down before you call it live.
