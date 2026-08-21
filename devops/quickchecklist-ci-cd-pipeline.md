## Triggers:

* [ ] Every PR to protected branches; tags; and a nightly if you have flaky-slow suites you still need.
* [ ] Fork PRs from outside cannot access production secrets (no `pull_request_target` with secrets unless you know the exploit).
* [ ] `repository_dispatch` / `workflow_dispatch` that deploy production are not callable with a widely shared token.

## Pipeline Shape:

* [ ] Lint → unit → build → SCA/SAST → (optional e2e) → publish artifact → deploy.
* [ ] Fail-fast on lint/unit; e2e is not the first gate for a typo.
* [ ] Same artifact is promoted; you do not `npm run build` again on the prod runner with different env.
* [ ] Matrix OS/Node only where it matters; you are not paying for 12 redundant jobs.

## Supply Chain:

* [ ] Dependencies pinned or lockfile committed; `npm ci` / `pip install -r` equivalent, not “latest”.
* [ ] Actions/orbs pinned to SHA, not `@v4` floating, for deploy jobs.
* [ ] OIDC to cloud (no long-lived AWS keys in GitHub secrets) if you can.
* [ ] SBOM or `npm audit` / `osv-scanner` on main; license allowlist if legal requires it.
* [ ] Secrets scanning (gitleaks) on PRs.

## Tests in CI:

* [ ] Unit tests do not need the real VPN; they use fixtures.
* [ ] Integration tests use ephemeral DB/container; they do not share a staging schema with humans.
* [ ] Flakes: quarantine with a ticket, not `retry: 5` forever.
* [ ] Coverage gate only if you maintain it; a lying 90% on untested files is worse than none.

## Deploy Jobs:

* [ ] Environment protection: required reviewers on `production`.
* [ ] Concurrency: one prod deploy at a time; cancelled in-progress is understood.
* [ ] Migrations job is explicit and ordered vs app rollout.
* [ ] After deploy, readiness is actually ready (health/ready 200, or your agreed ready status). Do not treat a cached public `/` as proof.
* [ ] Notifications: fail to Slack/Teams with SHA, actor, and link; success is quieter.

## What Not to Do:

* [ ] `continue-on-error: true` on tests.
* [ ] Echoing secrets (`set -x` with `curl -H "Authorization: $TOKEN"`).
* [ ] Deploying from a contributor’s branch without review.
* [ ] Using `latest` tag as the only prod pin.

## Operability:

* [ ] Logs retained ≥ 30 days for prod deploys.
* [ ] You can re-run a failed job on the same SHA.
* [ ] README: how to skip a job the right way (empty commit vs `ci skip` policy).
* [ ] Self-hosted runners: labels, who patches the box, and they are not world-writable.
