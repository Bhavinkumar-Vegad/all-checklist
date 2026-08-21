## Image:

* [ ] Base image digest pinned; weekly rebuild for patches, not `FROM node:latest`.
* [ ] Non-root `USER`; filesystem read-only where the app allows.
* [ ] No secrets in `ENV` or `docker history` (use runtime inject).
* [ ] Multi-stage build: compiler/toolchain not in the final image.
* [ ] `.dockerignore` excludes `.git`, tests, `.env`, `node_modules` from the wrong stage.
* [ ] Healthcheck: CMD that fails when the app is not ready (not `exit 0`).
* [ ] Signal: Node/Python receives SIGTERM (dumb-init/tini if PID 1 is a shell).

## Local Compose:

* [ ] `compose up` from a clean clone works with documented `.env.example`.
* [ ] Ports do not clash; published ports are not `5432:5432` on a laptop that already runs Postgres unless documented.
* [ ] Named volumes for DB data; you know how to `down -v` without destroying someone’s work by accident.
* [ ] Depends_on + healthcheck so the API does not start before Postgres is accepting connections.
* [ ] Bind mounts: file permissions on Linux vs Mac (UID) are documented.

## Registries and Tags:

* [ ] Prod tag is the Git SHA, not `latest`.
* [ ] `latest` if used is only for dev.
* [ ] Image scan (Trivy/Grype) in CI; criticals have a waiver or a fix.
* [ ] Registry auth is not a robot password in a screenshot in Confluence.

## Orchestration:

* [ ] Resource requests/limits set; without limits a memory leak eats the node.
* [ ] PDB / maxUnavailable so you do not take all replicas down on a deploy.
* [ ] PreStop sleep if you need to leave the LB before SIGTERM.
* [ ] ConfigMaps vs Secrets: do not put TLS keys in ConfigMaps.
* [ ] ImagePullPolicy and pull secrets for private registries.

## Runtime Data:

* [ ] Migrations: init container or Job, not every replica racing `migrate`.
* [ ] Persistent volume: storage class, backup, and what happens if the node dies.
* [ ] Log driver: not unbounded json-file filling the disk.

## Networking:

* [ ] App talks to DB via internal DNS, not a hardcoded laptop IP.
* [ ] Ingress TLS and timeouts (WebSockets, long uploads).
* [ ] NetworkPolicy if you claim zero-trust; default-deny tested.

## Verify:

* [ ] Kill the container: orchestrator restarts it; in-flight request behavior is known.
* [ ] Rollback by SHA on staging.
* [ ] Time inside container is NTP-synced; cert verify works.
