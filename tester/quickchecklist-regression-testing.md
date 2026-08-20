## Prepare:

* [ ] Identify the build, environment, and ticket or release under test.
* [ ] Collect the list of changes since the last stable version.
* [ ] Select regression cases for areas that often break: auth, payments, search, and permissions.
* [ ] Confirm test data, accounts, and third-party sandboxes are available.

## Smoke First:

* [ ] Run a short smoke pass to confirm the build is installable and the app starts.
* [ ] Stop and report if login, home, or a critical create/save path is down.

## Core Regression:

* [ ] Re-run high-value happy paths for unchanged features.
* [ ] Re-run the last round of defect fixes to confirm they still hold.
* [ ] Test integrations that sit next to the changed code.
* [ ] Repeat key flows on the primary browser or device matrix.

## Risk-Based Areas:

* [ ] Payments, subscriptions, and tax calculations if they exist.
* [ ] File upload, email, and notification side effects.
* [ ] Role-based access for admin vs normal user.
* [ ] Data migration or settings that persist between versions.

## Report:

* [ ] Mark each case as pass, fail, or blocked with evidence.
* [ ] File defects with build number, environment, and steps.
* [ ] Call out residual risk if some cases were skipped.
* [ ] Give a clear go / no-go recommendation for the release.
