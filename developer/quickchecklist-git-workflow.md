## Daily:

* [ ] `git fetch --prune` before you branch so you do not build on a deleted remote.
* [ ] Do not commit `node_modules`, `vendor`, `.next`, `build`, `coverage`, or `*.log`.
* [ ] Commit message subject ≤ 72 chars, body explains why if the diff is not obvious.
* [ ] Do not commit `git update-index --assume-unchanged` hacks for local config; use `.env.local`.
* [ ] If you changed line endings, do not convert the whole repo; check `.gitattributes`.

## Branching:

* [ ] `main` is protected: no direct push, required reviews, required status checks.
* [ ] Long-lived `develop` vs trunk-based: you are not mixing both without a written rule.
* [ ] Hotfix branches are cut from the production tag, not from an unreleased `main` if prod is behind.
* [ ] You never `--force` to `main` or `release/*`.
* [ ] `--force-with-lease` only on your personal branch, after checking nobody else pushed.
* [ ] Submodules: pointer commit is updated intentionally; you did not leave a detached dirty submodule.

## History and Secrets:

* [ ] If a secret was committed, rotate it; removing it in a later commit is not enough.
* [ ] Do not `git rebase` a branch that is the base of someone else’s open PR without coordinating.
* [ ] `git revert` for shared history; `reset --hard` only for unpushed local commits.
* [ ] Large file: Git LFS or artifact storage; do not push a 200MB video to git.

## Merging:

* [ ] Merge strategy is consistent (squash vs merge commits vs rebase) so `git bisect` still works.
* [ ] “Update branch” on GitHub does not sneak in unrelated main commits you have not tested.
* [ ] After resolving conflicts, re-run tests; do not assume both sides of a conflict were kept correctly (especially lockfiles and migrations).
* [ ] Migration files: never rewrite a migration that already ran in staging/prod; add a new one.

## Tags and Releases:

* [ ] Tags are annotated (`v1.4.2`) and match the changelog.
* [ ] Do not move a published tag; cut `v1.4.2-hotfix.1`.
* [ ] Release branch includes only cherry-picks that have a ticket.

## Recover:

* [ ] You know `reflog` for a commit you thought you lost locally.
* [ ] Orphaned feature flags/branches older than N days are deleted on a schedule.
* [ ] CODEOWNERS and branch protection were not bypassed with an admin merge unless incident-documented.
