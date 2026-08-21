## Problem:

* [ ] Job-to-be-done is restated; if the screen is pretty but the job is “export CSV”, the export is not buried.
* [ ] Success metric for this flow is known (completion, time, error rate).
* [ ] You are not reviewing a flow that legal/compliance has not seen if it collects health/finance data.

## Information Architecture:

* [ ] Primary action is the most prominent; secondary is not competing (ghost vs filled).
* [ ] Back/cancel/close do not lose data without warning on long forms.
* [ ] Nav label matches the page title.
* [ ] Search vs filter vs sort: users can recover from zero results.

## Consistency:

* [ ] Spacing/type/color from the system; new one-off components have a reason.
* [ ] Same verb for the same action across screens (Start vs Begin vs Launch).
* [ ] Destructive vs primary color is not swapped vs the rest of the product.
* [ ] Platform: iOS vs Android vs web patterns are not mixed on one OS.

## Completeness:

* [ ] Validation messages are written, not “show error”.
* [ ] Permissions, billing gates, and feature flags have UI, not a blank gap.
* [ ] Admin vs member: you reviewed both, not only admin.
* [ ] Print / PDF / email template if that is part of the journey.

## Cognitive Load:

* [ ] Defaults are safe; pre-checked marketing consent is flagged.
* [ ] Progressive disclosure vs 20 fields at once.
* [ ] Confirmations quote the thing you will delete (“Delete invoice INV-2044”).

## Visual QA:

* [ ] Alignment, 4/8 grid, accidental 1px shadows.
* [ ] Contrast on the actual background images, not on a white artboard.
* [ ] Motion is short and interruptible.

## Feedback Hygiene:

* [ ] Comment format: screen / component / severity (blocker vs nit) / suggested fix.
* [ ] You do not redesign the information architecture in a visual QA session unless that is the agenda.
* [ ] Decisions (we will not do X) are written so they do not reopen next week.
