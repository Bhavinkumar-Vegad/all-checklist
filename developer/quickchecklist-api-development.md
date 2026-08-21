Skip items that do not apply (no webhooks, no multi-tenant, no file upload).

## Contract Before Code:

* [ ] Resource name is a noun; action is the HTTP method, not `/getUser` + POST.
* [ ] Authn vs authz is explicit: which roles, which relationship (`owner`, `org-admin`, `support-read`).
* [ ] Idempotency: if the call can charge money or create a record twice on retry, require an idempotency key (or a unique business key) and replay the first response.
* [ ] Pagination: default and max page size are documented; total count is omitted if it is expensive.
* [ ] Filter/sort allowlist is documented; clients cannot sort by arbitrary SQL columns.
* [ ] Error model: stable `code` (string/enum), human `message`, `requestId`, optional `fields[]`.
* [ ] Breaking vs additive: removing a field, changing type, or making optional → required needs a new version or flag.
* [ ] Webhook payload, retry policy (e.g. 1m/5m/30m), and signature header are documented if you emit events.

## Request Validation:

* [ ] Unknown JSON properties: reject (`additionalProperties: false`) or ignore — pick one and stay consistent.
* [ ] String max length is enforced (name 200, comment 5k, not unbounded TEXT from the client).
* [ ] Integers: min/max; IDs are strings if they can exceed JS `Number.MAX_SAFE_INTEGER`.
* [ ] Enums: unknown value returns 400 with the allowed set, not 500.
* [ ] Dates: reject `31-02-2026` and timezone-less local datetimes if you expect instants.
* [ ] Nested arrays have a max length (do not accept 100k line items in one call).
* [ ] Content-Type must be `application/json` (or documented multipart); `text/plain` JSON is rejected.
* [ ] Charset is UTF-8; invalid UTF-8 is 400, not a truncated row.

## Authorization and Tenancy:

* [ ] Every query is scoped by tenant/org from the token, not from a client-supplied `orgId` unless it is verified.
* [ ] Object-level check: user A cannot GET/PATCH/DELETE `/resources/{id}` of user B by guessing UUID/int.
* [ ] Collection endpoints cannot leak other tenants by omitting the tenant filter on a JOIN.
* [ ] Support/admin impersonation is audited and time-boxed if it exists.
* [ ] Field-level: user cannot set `discountPercent`, `role`, `verifiedAt` unless allowed.

## Responses:

* [ ] 201 + `Location` on create if you already do that elsewhere; do not mix 200 and 201 randomly.
* [ ] 204 has an empty body; clients that parse JSON on 204 will break if you send `null`.
* [ ] 409 on unique conflict includes which field collided when it is safe to say.
* [ ] 429 includes `Retry-After`.
* [ ] List response does not include deleted rows unless `includeDeleted=true` and the caller may see them.
* [ ] Null vs omitted: pick a rule for optional fields and stick to it in OpenAPI.

## Persistence:

* [ ] Multi-row writes use a transaction; webhook side effects are outbox/queue, not in the request transaction if they can fail independently.
* [ ] Optimistic concurrency: `version` / `updatedAt` / `If-Match` if two clients can edit.
* [ ] Unique indexes exist for business keys you treat as unique in code.
* [ ] Soft-deleted unique keys: partial unique index on live rows (`WHERE deleted_at IS NULL`). Do not rely on `(email, deleted_at)` — SQL NULLs do not make that unique.
* [ ] Migrations: nullable first, backfill, then constrain — not `NOT NULL` on a live table with rows.

## Security:

* [ ] Parameterized queries / ORM bind params; no string-built SQL with user input.
* [ ] Rate limit login, password reset, OTP, and expensive search separately from CRUD.
* [ ] Export/download endpoints are authz-checked and not guessable (`/exports/1.csv`).
* [ ] Signed URLs expire; content-disposition is `attachment` for untrusted files.
* [ ] Redirect `returnTo` is allowlisted to your hosts.
* [ ] CORS: explicit origins; no `*` with cookies.
* [ ] Do not log bodies of `/login`, `/tokens`, `/cards`.
* [ ] File upload: MIME sniffed from content, extension allowlist, virus scan if you store executable-looking types.

## Compatibility and Clients:

* [ ] Mobile app on last two store versions still parses the JSON (unknown fields ignored).
* [ ] You did not change a field from string to number without a version.
* [ ] Money is integer minor units or a decimal string — never a JSON number float. Document which, and keep it the same as existing endpoints.
* [ ] Deprecated field remains for one release with a header or doc note.

## Tests You Should Have:

* [ ] Happy path + 400 validation + 401 missing token + 403 other user’s id + 404 unknown id.
* [ ] Duplicate create with same idempotency key returns the original resource, not 500.
* [ ] Two parallel PATCHes: one 200, one 409/412, no silent overwrite unless last-write-wins is specified.
* [ ] Pagination: page 2 of 2, empty page past the end, invalid cursor 400.
* [ ] Contract test or OpenAPI snapshot fails if you rename a field.

## Observability:

* [ ] `requestId` is in logs and the response header.
* [ ] Metrics: count, latency histogram, 4xx/5xx by route template not by raw URL.
* [ ] Slow query / N+1 logging is on in staging for this endpoint.
* [ ] Alert exists if error rate on this route exceeds the service SLO.
