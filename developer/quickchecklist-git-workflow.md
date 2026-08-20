## Daily Hygiene:

* [ ] Pull or fetch the latest changes before starting work.
* [ ] Create a branch with a clear name, such as `feature/login-otp` or `fix/cart-total`.
* [ ] Make small, focused commits with messages that explain why.
* [ ] Do not commit generated files, secrets, or personal IDE config.
* [ ] Run tests locally before you push.

## Branching:

* [ ] Use the agreed model (trunk-based, GitHub Flow, or Git Flow).
* [ ] Keep feature branches short-lived.
* [ ] Protect main and require reviews on that branch.
* [ ] Never force-push shared branches unless the team explicitly agrees.
* [ ] Delete merged branches to keep the remote clean.

## Collaboration:

* [ ] Open a pull request early if you need design feedback.
* [ ] Rebase or merge main often so conflicts stay small.
* [ ] Resolve conflicts carefully and re-run tests after resolving them.
* [ ] Do not rewrite history on a branch that others are using.

## Releases and Hotfixes:

* [ ] Tag releases with a version the team can identify in logs and stores.
* [ ] Cherry-pick hotfixes only when a full merge is too risky.
* [ ] Record the production commit hash in the release notes.
* [ ] Confirm CI runs on release tags and hotfix branches.

## Recovery:

* [ ] Know how to undo a local unpushed commit without losing work.
* [ ] Know who can revert a bad merge on main.
* [ ] Keep backups or mirrors if the repo is business-critical.
* [ ] Document the branching rules in the project README.
