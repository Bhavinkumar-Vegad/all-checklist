Skip items that do not apply to this PR (no JWT, no money, no i18n). This is a filter, not a score.

## Before You Open the Diff:

* [ ] Ticket/acceptance criteria are linked and you know the intended user-facing change.
* [ ] CI is green, or each failing job has a comment explaining why it is unrelated.
* [ ] Diff is against the current target branch, not a stale fork.
* [ ] PR is not mixing a feature, a refactor, and a dependency bump unless that was agreed.
* [ ] Generated files (lockfile-only noise, license dumps, `dist/`) are either expected or removed.

## Logic and Edge Cases People Skip:

* [ ] Empty list, single item, and “exactly page size” pagination all behave correctly.
* [ ] `0`, `false`, empty string, and `null` are not treated as the same value.
* [ ] Time is stored in UTC and converted with a named timezone, including DST switch days.
* [ ] Money uses a decimal/integer minor-unit type, not floating point.
* [ ] Soft-delete vs unique email: use a partial unique index (`WHERE deleted_at IS NULL`) or equivalent. `(email, deleted_at)` is not unique in Postgres when `deleted_at` is NULL.
* [ ] Concurrent double-submit (double click, retry, webhook at-least-once) cannot create two records.
* [ ] Race on “check then insert” is handled with a unique index or row lock, not only application if.
* [ ] Sort order is stable when two rows share the same sort key (secondary key exists).
* [ ] Bulk action partial failure reports which ids succeeded and which failed.
* [ ] Search/filter with `%`, `_`, emoji, RTL text, and leading/trailing spaces does not 500.

## API and Contract:

* [ ] New/changed fields are additive; renamed or removed fields have a version or a documented break.
* [ ] Error body shape matches existing endpoints (`code`, `message`, `requestId`).
* [ ] Other-user access is 403 or 404 (team convention), never 200 with empty/`null` data. 403 confirms the id exists; use 404 if you must hide existence.
* [ ] PATCH does not null-out omitted fields; PUT semantics are documented if used.
* [ ] Date formats are ISO-8601 with timezone; do not mix epoch seconds and milliseconds.
* [ ] Pagination cursor/offset cannot be forged to skip authorization.

## Frontend / UI Diffs:

* [ ] Loading, empty, error, and permission-denied states exist, not only the happy path.
* [ ] Disabled submit prevents double posts and shows why it is disabled.
* [ ] Unsaved-change warning exists on long forms if the app already does that elsewhere.
* [ ] Keyboard focus is not lost after an async refresh or toast.
* [ ] New copy is not hardcoded if the app is localized; new strings are in the i18n file.
* [ ] Dark mode / high-contrast is not broken if the product supports it.
* [ ] New images have width/height or aspect-ratio to avoid layout shift.

## Data and Migrations:

* [ ] Migration is backward compatible with the currently running app (expand/contract).
* [ ] `NOT NULL` column has a default or a backfill in the same release plan.
* [ ] Index creation on a large table is concurrent / `ALGORITHM=INPLACE` or equivalent, not a full lock.
* [ ] Seed or data-fix scripts are idempotent and cannot run twice with duplicate rows.
* [ ] Rollback or forward-fix plan is written if the migration cannot be reversed.

## Tests:

* [ ] There is at least one test that would fail if the bug in the ticket were reintroduced.
* [ ] Mocks are not asserting on call order that does not matter.
* [ ] Time-dependent tests freeze the clock; they do not sleep.
* [ ] New flaky selector or `wait(500)` was not added.
* [ ] Fixture data does not use another tenant’s id.

## Security (reviewer scan):

* [ ] No secret, PEM, connection string, or production URL in the diff.
* [ ] Authorization is checked in the handler/service, not only by hiding a button.
* [ ] User-controlled URL is not passed to `fetch`/`redirect` without an allowlist.
* [ ] File name from the user is not concatenated onto a disk path.
* [ ] `dangerouslySetInnerHTML` / `v-html` / `innerHTML` is not added without sanitization.
* [ ] New CORS origin is not `*` together with `credentials: true`.
* [ ] Logs do not print Authorization headers, cookies, or card numbers.
* [ ] Mass-assignment cannot set `role`, `isAdmin`, `price`, or `ownerId` from the client.

## Performance:

* [ ] No query inside a loop over an unbounded list (N+1).
* [ ] New list endpoint has a max page size.
* [ ] New column used in WHERE/JOIN has an index if it will be queried in production volume.
* [ ] Large JSON is not serialized on the hot path without need.
* [ ] Cache keys include tenant/user where data is not global.

## Review Comments:

* [ ] Comments point at a line and say what to change, not “please improve this”.
* [ ] Nitpicks are labeled as nits so they do not block.
* [ ] You approve only if you could debug this at 2am.
