## Runtime:

* [ ] `DEBUG`/`APP_ENV=production`; stack traces not returned to clients.
* [ ] Graceful shutdown: SIGTERM waits for in-flight requests (K8s `terminationGracePeriodSeconds` ≥ that).
* [ ] Readiness vs liveness: readiness fails when DB is down; liveness is not the same probe (avoid restart loops).
* [ ] Single-writer jobs (cron) have a lock; 3 replicas do not send 3 invoices.
* [ ] Timezone of the process is UTC; you do not depend on the host’s local TZ.

## Data:

* [ ] Backup: RPO/RTO written; last restore drill date is not “never”.
* [ ] Point-in-time recovery is on if the DB offers it and you need it.
* [ ] Migrations in this release were run on a prod-sized copy.
* [ ] Disk for WAL/binlogs will not fill in 24h at current write rate.
* [ ] Redis/Memcached is not the only copy of durable data.

## Secrets and Access:

* [ ] Secrets rotated from the last incident or employee exit.
* [ ] Prod IAM is not a shared “admin” AWS key in a 1Password vault named “old”.
* [ ] Break-glass user is tested and alerting fires when it is used.
* [ ] Public buckets/objects: list and GET are not open; screenshot of the policy.
* [ ] Admin UI is not on the internet without SSO + MFA + IP allow or similar.

## Network and TLS:

* [ ] Cert expiry monitor (not a calendar reminder in one person’s head).
* [ ] HTTP→HTTPS. HSTS `includeSubDomains` / `preload` only if every subdomain still in use is HTTPS.
* [ ] Security groups: 0.0.0.0/0 on DB/Redis/SSH is not left from debugging.
* [ ] Egress: app can still reach the payment/email APIs after a lock-down.

## Capacity:

* [ ] HPA/autoscaling metrics are the right ones (CPU vs queue depth vs RPS).
* [ ] Connection pools and DB `max_connections` math was done for max replicas.
* [ ] Rate limits / WAF in front of login and webhooks.
* [ ] Load test number you cite is from this architecture, not a blog.

## Observability:

* [ ] Logs: JSON, request id, no PII/secrets; retention matches policy.
* [ ] Metrics: RED (rate, errors, duration) per service.
* [ ] Traces on the payment/login path.
* [ ] Alerts: page a human for user-facing SLO burn; do not page on disk 70% at 3am unless it is a trend.
* [ ] Runbook link in the alert; on-call can follow it without the author.

## Compliance:

* [ ] Subprocessors list vs what is actually configured (analytics, error tracking, CRM).
* [ ] Data retention job exists if the privacy policy promises deletion.
* [ ] Audit logs for admin actions if you are in a regulated industry.

## Sign-off:

* [ ] Smoke on prod after first deploy of this stack.
* [ ] Named owners: app, platform, data, security.
* [ ] Known issues list is in the same place as the dashboard link.
