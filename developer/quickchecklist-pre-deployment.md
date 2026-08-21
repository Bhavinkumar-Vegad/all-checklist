## Config and Flags:

* [ ] Production env vars are present in the secret store for this SHA, including new ones from the PR list.
* [ ] Missing env var fails boot (or a health check), not a latent 500 on first request.
* [ ] Feature flags default to the safe state; the enable ticket is separate from deploy.
* [ ] Debug/profiler/toolbar (`DJANGO_DEBUG`, `APP_DEBUG`, Rails `consider_all_requests_local`) is false.
* [ ] Test payment keys, Slack incoming-webhook to #dev, and seed admin `admin@example.com` / `Password1` are gone.
* [ ] CORS allowlist is production hosts only, not `localhost:3000`.
* [ ] Cookie domain/secure/SameSite match the real site (www vs apex, HTTPS).

## Migrations (the usual outage causes):

* [ ] Backup completed and a restore was tested recently, not only “backups are enabled”.
* [ ] Expand/contract: old app servers can still run against the new schema during rolling deploy.
* [ ] Adding `NOT NULL` without default on a hot table is not in this release.
* [ ] Index on a large table is created concurrently; estimate time on a prod-sized copy.
* [ ] Data backfill is batched; it will not lock users for 40 minutes.
* [ ] `LOCK TABLE` / changing enum in Postgres / dropping a column still read by old code is not in the same deploy as the code that needs it.
* [ ] Migration order matches deploy order (migrate then bounce vs bounce then migrate).

## Jobs, Cron, Queues:

* [ ] New workers are deployed before you enqueue a new job type.
* [ ] Cron is not duplicated (two schedulers firing the same invoice job).
* [ ] Job payload is backward compatible with in-flight messages from the previous version.
* [ ] Dead-letter / retry is watched; a poison message cannot block the queue.
* [ ] Timezone of cron is explicit (`UTC`); month-end and DST days are considered.

## Cache, CDN, Assets:

* [ ] Fingerprinted assets; HTML is not cached longer than the new JS/CSS.
* [ ] CDN purge or cache-bust query is planned for logo/legal PDF changes.
* [ ] Redis key prefix/version changed if the value shape changed (avoid deserializing old JSON into new structs).
* [ ] Session store is not wiped unless you intend to log everyone out.

## Traffic and Limits:

* [ ] Connection pool ≥ (app instances × threads/workers) with headroom for migrations.
* [ ] File/disk: log rotation, upload temp dir, and inode limits on the host/container.
* [ ] Rate limits / WAF / bot rules will not block the new URL pattern or webhook IP.
* [ ] File descriptor and ulimit are fine for the expected WebSocket/SSE count.

## DNS, TLS, Email:

* [ ] Certificate expires > 14 days; ACME renewal is known to work.
* [ ] Apex/www redirect does not loop; HSTS is not enabled on a host that still has HTTP-only subdomains you care about.
* [ ] Transactional email SPF/DKIM/DMARC still pass from this environment’s sending domain.
* [ ] Webhook endpoints on the public host are reachable from the vendor’s IPs.

## Go-live window:

* [ ] Owner for deploy, owner for rollback, owner for comms are three named people (or explicitly the same person).
* [ ] Rollback is “redeploy previous artifact”, not “we’ll git revert and wait for CI” unless that is tested.
* [ ] Support has the change list and known broken workarounds.
* [ ] Status page / Slack #incidents is ready if this is a peak-traffic deploy.

## After deploy (first hour):

* [ ] Hit login, the #1 revenue path, and the new feature with a real (or prod-like) account.
* [ ] Compare 5xx rate, p95 latency, queue lag, and DB CPU to the previous hour.
* [ ] Error tracker grouping is not exploding on a new `TypeError` in one region.
* [ ] Background job success rate did not drop.
* [ ] If you use canary: attach % is ramping; you have a metric that would stop the ramp.
