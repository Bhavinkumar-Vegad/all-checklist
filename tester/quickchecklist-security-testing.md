Skip JWT / OAuth items if the app uses opaque server sessions. Skip upload items if there is no upload.

## Rules of Engagement:

* [ ] Written permission names the environment, date window, and forbidden tests (no DoS on prod unless agreed).
* [ ] You are on a staging/test tenant; production PII is not downloaded to your laptop.
* [ ] Intercepting proxy (Burp/ZAP/mitmproxy) is trusted only on the test device/profile.
* [ ] Rate-limit / WAF may block you; have an allowlist or a lower rps, do not “try harder” with a flood.

## Session and Auth:

* [ ] Logout invalidates server-side session or token denylist; old `Authorization` header fails.
* [ ] Refresh token rotation: reuse of an old refresh token is rejected (theft detection).
* [ ] If you use JWTs: `alg` is not `none`; you cannot swap RS256 → HS256 with the public key as the HMAC secret. Skip this if sessions are server-side cookies.
* [ ] `exp` / `nbf` enforced; tokens with future `iat` far ahead are rejected if that is your policy.
* [ ] Cookie: `Secure`, `HttpOnly` for session, `SameSite=Lax` or `Strict`; `None` only if you need cross-site and HTTPS.
* [ ] Session fixation: new session id after login.
* [ ] Remember-me / “stay logged in” has an absolute max age, not forever.
* [ ] Password reset token is single-use, time-limited, and not in referrer logs (POST the token, not GET if you can).
* [ ] Reset does not reveal whether the email exists unless product requires it; if it does, that is documented.
* [ ] MFA bypass: API still requires the second factor; recovery codes are one-time.
* [ ] After N failures: lockout or backoff; lockout is not a user-enumeration oracle if you can avoid it.
* [ ] Change-password and change-email require re-auth.

## Access Control (IDOR / BOLA):
* [ ] Swap resource id (UUID and sequential int) in GET/PUT/DELETE while logged in as another user.
* [ ] Horizontal: same role, other user’s invoice/file/message.
* [ ] Vertical: user token on `/admin/*` and admin-only GraphQL fields.
* [ ] Create-as: POST body `userId`/`orgId` of someone else is ignored or 403.
* [ ] Batch endpoints (`ids[]=`) cannot include another tenant’s ids mixed with yours.
* [ ] WebSocket/SSE subscribe topic is authorized, not only the HTTP handshake.
* [ ] Export/report jobs cannot be downloaded by guessing `/jobs/{id}/file`.
* [ ] Hidden parameter `role=admin` / `is_staff=true` is ignored.

## Injection and XSS:

* [ ] Reflected XSS in query, hash, and JSON error messages rendered into HTML.
* [ ] Stored XSS in profile name, comments, markdown, and file names shown in UI.
* [ ] DOM XSS: `innerHTML`, `document.write`, `eval`, `postMessage` without origin check.
* [ ] SQL/NoSQL: quotes, `$gt`, `$where`, comment `--` in search and sort params.
* [ ] Command injection on export/filename/imagemagick paths.
* [ ] SSTI: `{{7*7}}`, `${7*7}` in fields that end up in templates.
* [ ] LDAP/XML/XPath if those backends exist.
* [ ] CSV/formula injection on export (`=CMD`, `@SUM`) — cells prefixed or quoted.

## Uploads and Files:

* [ ] Double extension `invoice.pdf.exe`, `file.jpg.php`, null byte `file.php%00.jpg`.
* [ ] Content-Type is not trusted; magic bytes checked.
* [ ] SVG/HTML upload is not served as `text/html` from your domain (XSS).
* [ ] Path traversal in filename `../../etc/passwd`.
* [ ] Zip bomb / zip-slip if you extract archives.
* [ ] Image resize pipeline (ImageMagick/Ghostscript) is patched; polyglot files tested.

## CSRF, CORS, Clickjacking:

* [ ] State-changing cookie-auth requests need CSRF token or SameSite that actually applies.
* [ ] CORS: `Access-Control-Allow-Origin` is not reflected arbitrary origin with credentials.
* [ ] `X-Frame-Options` / CSP `frame-ancestors` on login and payment pages.
* [ ] JSON endpoints used from a browser form POST are not CSRF-able if they mutate.

## Redirects and SSRF:

* [ ] `redirect=`, `next=`, `returnUrl=` only allow relative paths or an allowlist of hosts.
* [ ] Server-side fetch of user URL (webhooks, preview, importers) cannot hit `169.254.169.254`, `localhost`, or internal CIDR.
* [ ] Redirect follows are limited; protocol `file://` / `gopher://` blocked.

## Crypto and Data:

* [ ] Passwords hashed with a modern KDF (Argon2/bcrypt/scrypt), not MD5/SHA1.
* [ ] Tokens are high entropy; not `md5(email+timestamp)`.
* [ ] PII in URLs is avoided (email in query string lands in logs and Referer).
* [ ] Backup/export files are not world-readable on the bucket.
* [ ] Verbose 500s are off in the test of record (staging should match prod error shape).

## Headers:

* [ ] HTTPS redirect. Do not set HSTS `includeSubDomains` or `preload` unless every subdomain you still use is HTTPS.
* [ ] CSP is present on HTML; `unsafe-inline` is called out if you still need it.
* [ ] `Cache-Control: no-store` on authenticated HTML and API that returns PII.

## Report:

* [ ] Finding includes request/response (redacted), impact, and likely CWE.
* [ ] You retest on the fix commit, not “dev said it’s fixed”.
