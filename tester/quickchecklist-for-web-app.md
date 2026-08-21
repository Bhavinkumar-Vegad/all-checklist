## Auth and Session (where most “it works on my machine” bugs hide):

* [ ] Login, logout, refresh, and “open in a second tab” keep a single coherent session (or you document that two tabs are unsupported).
* [ ] Expired session: user sees a login, not a JSON dump or infinite spinner; deep link is restored after login if the product claims that.
* [ ] Password reset: token expires, cannot be reused, does not leak whether the email exists unless product requires it.
* [ ] Role A cannot open role B’s URL by pasting it; API is 403 or 404, not 200 with an empty body that looks like “no data”.
* [ ] Impersonation / “view as user” (if any) is banner-visible and audited.

## Forms and Data:

* [ ] Required fields, min/max, regex, and server-side reject of what the UI allows (disable JS and submit).
* [ ] Duplicate submit (double click, Enter twice) does not create two orders/tickets.
* [ ] Unsaved changes: navigate away warning on long forms if other screens have it.
* [ ] File upload: type, size, virus-ish payload, filename with emoji/spaces; download the same file.
* [ ] Date pickers: timezone of user vs server; “today” around midnight UTC.
* [ ] Money: 0.10 + 0.20, rounding, thousand separators, trailing zeros.
* [ ] Empty, 1 row, page-size rows, and last page of pagination (including “page 99” of 2).
* [ ] Filters + sort + search together; “clear filters” actually clears query params.
* [ ] CSV/Excel export opens and matches the grid (formulas escaped).

## UI States:

* [ ] Loading, empty, error, forbidden, not found — each has copy and a next action.
* [ ] Toasts do not cover the primary button on mobile; they can be dismissed.
* [ ] Modals: scroll lock, close on Escape, focus return, background not clickable if that is the spec.
* [ ] Sticky header does not hide focused inputs or in-page anchors.
* [ ] Dark mode / high contrast if shipped: charts and borders still visible.

## Responsive and Browsers:

* [ ] 320, 375, 768, 1024, 1440 widths; 200% zoom.
* [ ] Safari (iOS) vs Chrome: `100vh`, date inputs, position sticky, autofill yellow.
* [ ] Back/forward cache: after Back, form is not silently stale vs a paid order.
* [ ] Print stylesheet if users print invoices/reports.

## Realtime / Async:

* [ ] Websocket/SSE reconnect after laptop sleep.
* [ ] Two users edit the same record: last-write, lock, or conflict message — match the spec.
* [ ] Notifications: badge count vs list; mark-read does not mark the wrong tenant.

## Performance (practical, not “make it fast”):

* [ ] Slow 3G: primary path usable; you see which call blocks TTI.
* [ ] Large list: virtualization or pagination; 1k rows does not freeze the tab.
* [ ] Memory: 15 minutes of SPA navigation without leaking (heap snapshot if it feels sticky).
* [ ] Cached HTML + new JS after deploy: users are not stuck on a white screen (chunk 404).

## Security smoke (QA-level, not a pentest):

* [ ] HTTPS, no mixed content on the logged-in shell.
* [ ] XSS: `<script>alert(1)</script>` in a comment/name field is stored as text.
* [ ] Cookie flags on session cookie (Secure, HttpOnly) in DevTools.
* [ ] Direct object id in URL swapped to another user’s.

## i18n:

* [ ] Pseudo-locale or German long strings: buttons do not overflow.
* [ ] RTL if you ship Arabic/Hebrew: alignment and chevrons.
* [ ] `1.234,56` vs `1,234.56`; Monday-first vs Sunday-first calendars.

## Accessibility (minimum on every story):

* [ ] Keyboard through the new flow; visible focus.
* [ ] Name, role, value on custom widgets (dropdown not a non-focusable div).
* [ ] Form errors announced and tied to fields.

## Reporting:

* [ ] Bugs include URL, role, SHA/build, request id from network tab, and whether JS was disabled for validation tests.
