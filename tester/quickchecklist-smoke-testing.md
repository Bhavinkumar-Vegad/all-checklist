## Build and Access:

* [ ] Confirm you have the correct build, URL, or app package.
* [ ] Confirm test users can log in on this environment.
* [ ] Confirm third-party test keys (payments, SMS, email) are pointed at sandbox.

## Critical Path:

* [ ] App or site loads without a blank screen or uncaught error.
* [ ] Sign up or login works for a standard user.
* [ ] The main landing screen after login is usable.
* [ ] A core create/read/update action saves and displays again after refresh.
* [ ] Logout works and the next user cannot see the previous session.

## Obvious Breakage:

* [ ] Primary navigation links open the right pages.
* [ ] Forms show validation instead of a silent failure.
* [ ] Images, fonts, and API calls are not all failing in the network tab.
* [ ] Mobile viewport is not completely unusable if the product is responsive.

## Decision:

* [ ] If smoke fails, stop deeper testing and report the build as blocked.
* [ ] If smoke passes, proceed to regression or exploratory testing.
* [ ] Note environment issues separately from product defects.
