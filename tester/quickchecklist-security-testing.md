## Scope:

* [ ] Identify the features, APIs, and user roles in scope for this security test.
* [ ] Confirm you have written permission to test the environment.
* [ ] Use a dedicated test account, never a real customer account.
* [ ] Note which data is synthetic and which must not be exported.

## Authentication and Session:

* [ ] Test login with valid, invalid, locked, and expired credentials.
* [ ] Confirm password reset does not reveal whether an email exists, unless that is intended.
* [ ] Verify sessions expire after logout and after inactivity.
* [ ] Check that tokens cannot be reused after logout when that is required.
* [ ] Try accessing a privileged page while logged in as a lower-privilege user.

## Input and Injection:

* [ ] Submit XSS payloads in text fields, search, and URL parameters.
* [ ] Submit SQL or NoSQL injection attempts on filters and login forms.
* [ ] Test file upload with disallowed types, oversized files, and double extensions.
* [ ] Check open redirects on `returnUrl` or similar parameters.
* [ ] Verify the app rejects unexpected HTTP methods on sensitive endpoints.

## Access Control:

* [ ] Call APIs that belong to another user and confirm 403 or 404.
* [ ] Tamper with IDs in URLs and request bodies (IDOR).
* [ ] Confirm admin actions are impossible from a normal user token.
* [ ] Check that hidden UI is not the only protection for restricted features.

## Data Protection:

* [ ] Confirm HTTPS is enforced and mixed content is not loaded.
* [ ] Check cookies use Secure, HttpOnly, and an appropriate SameSite value.
* [ ] Verify sensitive fields are masked in the UI and in logs.
* [ ] Confirm backups, exports, and error pages do not leak stack traces or secrets.

## Reporting:

* [ ] Record steps to reproduce, impact, and a suggested severity.
* [ ] Do not share raw exploits outside the agreed security channel.
* [ ] Retest after the fix and update the original finding.
