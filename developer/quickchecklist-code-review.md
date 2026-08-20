## Before You Start:

* [ ] Confirm the pull request description explains why the change exists, not only what changed.
* [ ] Check that related tickets, designs, or requirements are linked.
* [ ] Confirm CI is green or understand why it is not.
* [ ] Pull the latest target branch and scan the full diff, not only the files you expected.

## Correctness:

* [ ] Verify the change solves the stated problem and nothing extra slipped in.
* [ ] Check edge cases: empty states, null values, permission errors, and retries.
* [ ] Confirm error handling returns a useful message and does not hide the real failure.
* [ ] Check that business rules match the requirements or ticket acceptance criteria.
* [ ] Verify feature flags, environment variables, and config defaults are documented.

## Code Quality:

* [ ] Check naming is clear and consistent with the rest of the codebase.
* [ ] Look for duplicated logic that should be reused or extracted.
* [ ] Confirm functions and components stay small enough to understand.
* [ ] Check that comments explain why, not what the code already shows.
* [ ] Remove leftover debug logs, commented-out code, and unused imports.

## Tests:

* [ ] Confirm new behavior is covered by unit, integration, or end-to-end tests.
* [ ] Check that failing tests would actually catch a regression in this change.
* [ ] Verify fixtures and mocks are realistic and not over-specified.
* [ ] Confirm flaky tests are not being ignored or skipped without a reason.

## Security and Data:

* [ ] Check user input is validated and sanitized before use.
* [ ] Confirm secrets, tokens, and credentials are not committed.
* [ ] Verify authorization checks exist on every sensitive action, not only in the UI.
* [ ] Check logs do not print passwords, tokens, personal data, or full payment details.
* [ ] Confirm file uploads, redirects, and query parameters cannot be abused.

## Performance and Reliability:

* [ ] Look for N+1 queries, unbounded lists, and missing pagination.
* [ ] Check expensive work is not done on the main request path when it can be async.
* [ ] Confirm indexes, caching, and timeouts are considered for new data access.
* [ ] Verify the change will not break existing API consumers or mobile clients.

## Review Outcome:

* [ ] Leave specific, actionable comments instead of vague requests.
* [ ] Approve only when you would be comfortable supporting this in production.
* [ ] Request changes when correctness, security, or missing tests are blockers.
* [ ] Thank the author for good work when the change is clean and well explained.
