## Install and First Launch:

* [ ] Fresh install vs update from previous store version (data migration, not a wipe unless you intend it).
* [ ] First-run: permission prompts happen at the moment of need, not a wall of five dialogs.
* [ ] Kill from recents and reopen: you land where the spec says (cold start vs restore).
* [ ] Tablet / foldable / split-screen if you claim support; iPad does not look like a stretched iPhone unless that is the spec.
* [ ] RTL and large Dynamic Type / Android font scale 1.3+: primary CTA still tappable.

## Permissions (deny is more important than allow):

* [ ] Camera/mic/location/photos/notifications: Allow, Don’t allow, and “Don’t ask again”.
* [ ] After deny, the feature shows how to open Settings, not a crash.
* [ ] iOS Photo Library Limited Access vs Full; Android photo picker vs legacy storage.
* [ ] Location: while using vs always vs precise vs approximate (iOS 14+ / Android 12+).
* [ ] Bluetooth/Nearby if you use it: the extra Android 12 permission.

## Interruptions:

* [ ] Phone call, alarm, and Control Center overlay during payment / recording / navigation.
* [ ] Rotation lock on/off; orientation change mid-form does not wipe input.
* [ ] App switcher snapshot: no OTP, card number, or medical data in the preview (iOS snapshot privacy).
* [ ] Background → foreground after 5 minutes: token refresh, not a stuck spinner.
* [ ] Airplane mode, then restore: queued actions either send or explain.

## Offline and Sync:

* [ ] Airplane: which screens work; writes queue or fail clearly.
* [ ] Conflict: two devices edit the same record offline.
* [ ] Clock skew: device date set 2 days ahead (cert / token failures).
* [ ] Large file upload: background, lock screen, and failure retry (not silent drop).

## Push and Deep Links:

* [ ] Cold start from a push vs already running: correct thread/screen, not just home.
* [ ] Tapping an expired notification.
* [ ] Universal Links / App Links: https URL opens the app when installed, web when not; `applinks:` associated domains are live.
* [ ] Custom scheme: `myapp://` is not hijacked by another app if you still use it.
* [ ] Email magic link / OTP autofill (iOS keyboard, Android SMS retriever).

## Device Features:

* [ ] Camera: front/back, missing camera tablet, simulator vs device.
* [ ] GPS: indoor, mocked location (Android), permission revoked mid-session.
* [ ] Biometrics: Face ID fail → passcode; no biometrics enrolled; backgrounded during prompt.
* [ ] Share sheet / files / in-app browser: back returns to the app with state.

## Store and OS Matrix (pick real devices, not only the newest flagship):

* [ ] Oldest OS you support (API / iOS version in the store listing).
* [ ] Notch, punch-hole, gesture nav vs 3-button, Samsung One UI vs Pixel.
* [ ] Low storage: install and cache behavior.
* [ ] Battery saver / Low Power Mode: timers, location, background fetch.

## Performance and Heat:

* [ ] Cold start to first interactive < the number you put in the PRD (measure, don’t guess).
* [ ] Scroll 60fps on a mid-range Android, not only on your iPhone.
* [ ] Memory warning: list screens after 20 minutes of use.
* [ ] Wake locks / background location: battery drain over 30 minutes vs a competitor baseline if that is a claim.

## Security:

* [ ] Traffic is HTTPS; you tried a proxy (user installed CA) if you claim pinning — pinning fails gracefully on cert rotate.
* [ ] Tokens not in logs; screenshots of SharedPreferences/Keychain dumps are not plaintext passwords.
* [ ] Jailbreak/root detection only if product requires it; false positives on stock Samsung.
* [ ] Clipboard: OTP is not left forever if you copy it.

## i18n:

* [ ] Pseudo-localization: truncation on tab bar labels (4–5 items).
* [ ] Region: India 12-hour vs 24-hour; Saudi week start; currency symbol position.

## Store Build:

* [ ] Release vs debug: logging, inspector, staging API URL cannot ship.
* [ ] Version code / CFBundleVersion incremented; you cannot upload a lower code.
