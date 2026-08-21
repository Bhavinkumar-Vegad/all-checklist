Use this for Scrum planning. If the team is Kanban, use the same items for the weekly commit, ignore “sprint goal” wording.

## Inputs You Need Before the Meeting:

* [ ] Previous sprint: committed vs done vs carry-over with the actual reason (blocked, underestimated, production fire), not “we were busy”.
* [ ] Velocity: last 3 sprints of *done* points/items, not the inflated commitment.
* [ ] Calendar: public holidays, company all-hands, on-call rotation, two people on the same PTO week.
* [ ] Production: open Sev-1/2, debt you already promised, compliance date that is not on the board.
* [ ] Refinement: stories without AC, designs, or an env dependency are not in the candidate list (or they are spikes with a time box).

## Goal:

* [ ] Sprint goal is one outcome (“First-time payer can complete checkout without support”) not a list of 14 tickets.
* [ ] Goal is testable at review (demo script exists or can be written today).
* [ ] If leadership wants two goals, name a primary and a stretch. Do not put both on the stakeholder slide as committed.

## Story Readiness (INVEST in practice):

* [ ] AC are examples: given/when/then or bullets that QA can fail a build on.
* [ ] Analytics/event names are in the story if “we’ll add tracking later” is not acceptable.
* [ ] Feature flag, migration, and rollback are mentioned if the story can brick prod.
* [ ] Copy/legal/design owners named when the story is blocked on them; otherwise it is not committed.
* [ ] Split: “front-end + API + migration + backfill” is more than one sprint item unless the team is tiny.

## Capacity Math:

* [ ] Meetings: planning, review, retro, refinement, 1:1s — hours removed from the week.
* [ ] Support/on-call and **QA** time are in the capacity math. “We’ll test after code freeze” is not a plan unless QA said so.
* [ ] New joiner / interviewer load is not counted as full maker time.
* [ ] You do not “stretch” to match a date that was set before capacity was calculated.

## Dependencies:

* [ ] Vendor SLA, another team’s API, App Store review, customer UAT slot — dated, with a named owner outside the team if needed.
* [ ] Stories that must ship in order are sequenced; the second story is not committed as if it were independent.
* [ ] Shared staging: who else is deploying this sprint so you do not wipe UAT.

## Commitment:

* [ ] Team says the word commit (or “forecast” if you use that language) after capacity, not before.
* [ ] Stretch items are labeled stretch and are not in the stakeholder slide as promised.
* [ ] First-day WIP: who starts what tomorrow morning so Monday is not “we’ll pick something”.
* [ ] Risks: top 3 with trigger (“if SSO vendor is late by Wednesday, drop story X”).

## Output:

* [ ] Board: sprint field, rank order, owners (even if swarming, an initial owner).
* [ ] Slack/email to stakeholders: goal, not-in-sprint, review date, link to board.
* [ ] Review calendar invite has the demo environment and test users, not “TBD”.
