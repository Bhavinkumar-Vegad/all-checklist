## Branch Hygiene:

* [ ] Branch was cut from the latest `main`/`develop` today, not from a week-old local copy.
* [ ] Branch name matches team pattern (`fix/INV-1842-tax-rounding`, not `final-final-2`).
* [ ] One concern per PR; extract drive-by refactors into a follow-up.
* [ ] `git status` is clean: no `.DS_Store`, `Thumbs.db`, `.idea/`, `*.iml`, or local `.env`.
* [ ] `package-lock.json` / `yarn.lock` / `pnpm-lock.yaml` is committed if you changed dependencies, and only that lockfile.
* [ ] You did not `git add .` after running a formatter on the whole repo unless that was the task.

## Description That Saves Review Time:

* [ ] Title is imperative and specific: “Prevent duplicate invoice on payment webhook retry”.
* [ ] First paragraph is the user/business problem, then the approach.
* [ ] Screenshots: before/after for UI; include mobile width if the change is responsive.
* [ ] Test plan lists exact URLs, users/roles, and the one edge case you worry about.
* [ ] Feature flag name and default (`off` in production until enablement) are written.
* [ ] New env vars: name, example value, which environments need them, what happens if missing.
* [ ] DB migration file names are listed and whether they lock tables.
* [ ] If this is user-visible, the description says what QA should retest and what support should expect (moved button, new error, flag default).

## Secrets and Accidental Commits:

* [ ] Search the diff for `AKIA`, `ghp_`, `sk_live`, `BEGIN PRIVATE`, `password=`, `api_key`.
* [ ] No production dump, customer CSV, or HAR file with cookies.
* [ ] No `console.log` of the whole response object on an auth endpoint.
* [ ] `.env.example` was updated instead of committing `.env`.

## Self-Review of the Diff:

* [ ] You opened the Files tab and scrolled every file, including YAML and SQL.
* [ ] Left-over `TODO`, `FIXME`, `debugger`, `fdescribe`, `xit` are gone or ticketed.
* [ ] You did not change formatting in files you did not mean to touch (noisy diff).
* [ ] Binary assets are reasonably sized; no 8MB PNG when a 40KB WebP would do.
* [ ] `package.json` version bump matches the release process if you ship libraries.

## Checks Before Requesting Review:

* [ ] Lint, unit, and build jobs are green on this commit SHA.
* [ ] You ran the new path locally with the same feature flags as staging.
* [ ] Code owners / required reviewers are requested; optional reviewers are not blocking.
* [ ] PR is not 80 files unless it is a generated/lockstep change you explain.
* [ ] Conflicts with `main` are resolved; “merge commit” vs rebase matches team rule.

## During Review:

* [ ] Each comment is resolved with a reply: code change, or why you will not change it.
* [ ] You do not force-push after someone started reviewing unless the team uses stacked PRs and you warn them.
* [ ] Force-push, if allowed, uses `--force-with-lease`.
* [ ] You do not resolve a comment without addressing it.

## Merge:

* [ ] Required approvals and status checks are actually green, not skipped.
* [ ] Squash message still makes sense (not “fix comments” as the only commit).
* [ ] You are not merging with `WIP`, `DO NOT MERGE`, or a failing migration on staging.
* [ ] Linked ticket moves to the next column; QA has the preview URL or build number.
* [ ] After merge, you confirm the deploy pipeline picked this SHA, then watch error tracker for 15 minutes.
* [ ] Delete the remote branch if that is the repo setting.
