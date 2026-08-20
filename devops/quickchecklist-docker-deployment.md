## Image:

* [ ] App has a Dockerfile that runs as a non-root user when possible.
* [ ] Image is built from a pinned base tag, not `latest` in production.
* [ ] Secrets are injected at runtime, not baked into layers.
* [ ] Health check is defined for the container.

## Compose or Orchestration:

* [ ] Local `docker compose` brings up app, database, and cache with one command.
* [ ] Volumes persist data you cannot afford to lose in the target environment.
* [ ] Networks isolate public traffic from internal services.
* [ ] Resource limits are set in staging and production.

## Deploy:

* [ ] Registry credentials are stored securely.
* [ ] Rolling or blue-green deploy is documented.
* [ ] Old images can be rolled back by tag.
* [ ] Logs are shipped off the container filesystem.

## Verify:

* [ ] Container restarts cleanly after a crash.
* [ ] Migrations run in a controlled job, not as a race on every replica.
* [ ] Timezone, locale, and file permissions match what the app expects.
