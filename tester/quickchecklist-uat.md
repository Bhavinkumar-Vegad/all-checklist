## Before You Invite the Business User:

* [ ] Environment is stable on a frozen SHA; you will not deploy mid-UAT without telling them.
* [ ] Their accounts match real roles (branch manager, not superadmin “to make it easy”).
* [ ] Data looks like theirs: real product names, their tax region, their timezone.
* [ ] Scripts are scenario-based (“month-end close”) not “click menu 3”.
* [ ] Known defects and workarounds are on a one-pager so UAT is not a bug-bash of old issues.

## Scenarios That Matter:

* [ ] Happy path they bill the company on.
* [ ] Their exception path (partial refund, split shipment, dual approval).
* [ ] Report/export they send to a regulator or finance — numbers match the UI.
* [ ] Permission: they cannot see another team’s records.
* [ ] Notification they rely on (email PDF, Slack) actually arrives.

## During the Session:

* [ ] You do not take the mouse unless they are blocked; note where they hesitate (UX debt).
* [ ] Capture exact records they used (invoice #) for later debugging.
* [ ] Timebox; park “would be nice” as tickets, not scope creep in UAT.

## Evidence:

* [ ] Pass/fail per scenario with tester/business name and date.
* [ ] Screenshots of reports they care about.
* [ ] Waivers: named person accepted a defect to ship.

## Sign-off:

* [ ] Written accept / accept-with-waivers / reject.
* [ ] If reject: the failing scenario IDs, not a vibe.
* [ ] Store the sign-off with the release, not only in chat.
