## Design:

* [ ] Define the resource, action, and who is allowed to call it.
* [ ] Choose a consistent URL, method, and status-code pattern with the rest of the API.
* [ ] Document request and response payloads, including optional fields.
* [ ] Agree on pagination, filtering, and sorting before implementation.
* [ ] Decide versioning strategy if this is a breaking change.

## Implementation:

* [ ] Validate all incoming fields and reject unknown or malformed input.
* [ ] Return consistent error bodies with a code, message, and request id.
* [ ] Keep business logic out of the HTTP layer when the project already has a service layer.
* [ ] Use transactions where multiple writes must succeed or fail together.
* [ ] Avoid leaking stack traces or internal table names in responses.

## Security:

* [ ] Require authentication on every private endpoint.
* [ ] Check authorization against the target resource, not only "user is logged in".
* [ ] Rate-limit public and login-related endpoints.
* [ ] Sanitize output and use parameterized queries.
* [ ] Do not log tokens, passwords, or full personal records.

## Compatibility:

* [ ] Confirm existing clients still work if you changed a field.
* [ ] Add, do not remove, fields unless you are shipping a new version.
* [ ] Document deprecated fields and a removal date.
* [ ] Keep date, money, and id formats consistent with other endpoints.

## Testing:

* [ ] Write happy-path tests for the documented contract.
* [ ] Write tests for 400, 401, 403, 404, and 409 cases that apply.
* [ ] Test concurrent updates if two users can change the same record.
* [ ] Verify idempotency for retries on POST/PUT/PATCH where required.

## Release:

* [ ] Update OpenAPI, Postman, or internal API docs.
* [ ] Add monitoring for error rate, latency, and saturation.
* [ ] Provide a sample request for QA and frontend developers.
* [ ] Plan a rollback if the endpoint is already used in production.
