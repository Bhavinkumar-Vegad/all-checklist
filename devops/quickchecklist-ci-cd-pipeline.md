## Pipeline Design:

* [ ] Source is built on every push or pull request to protected branches.
* [ ] Stages are clear: lint, test, build, scan, deploy.
* [ ] Failed stages stop the pipeline unless skipped with a documented reason.
* [ ] Secrets are stored in the CI secret store, not in YAML.

## Quality Gates:

* [ ] Unit tests run on every change.
* [ ] A build artifact is produced once and reused for later stages.
* [ ] Dependency or image scanning runs on a schedule and on main.
* [ ] Preview or staging deploy is available for UI review when needed.

## Deploy:

* [ ] Production deploy is manual approval or a protected environment.
* [ ] Deploy is idempotent and tagged with a git SHA.
* [ ] Health check runs after deploy and fails the job if the app is down.
* [ ] Rollback to the previous artifact is documented and tested.

## Operations:

* [ ] Logs for pipeline runs are retained long enough to debug.
* [ ] Notifications go to the right channel on failure.
* [ ] Only required people can change production workflow files.
* [ ] Document how to replay a job and how to skip a flaky test the right way.
