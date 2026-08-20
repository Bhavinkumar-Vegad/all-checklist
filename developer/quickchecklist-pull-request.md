## Prepare the Branch:

* [ ] Create the branch from the latest main or agreed base branch.
* [ ] Keep the branch focused on one feature, bug, or chore.
* [ ] Rebase or merge the base branch so the pull request is not far behind.
* [ ] Remove local-only files, IDE settings, and generated artifacts from the commit.

## Write a Clear Pull Request:

* [ ] Use a title that states the outcome, for example "Fix checkout tax rounding".
* [ ] Describe the problem, the solution, and any trade-offs in the description.
* [ ] Link the ticket, design, or related pull requests.
* [ ] List test steps a reviewer can follow locally or on a preview URL.
* [ ] Call out breaking changes, migrations, and required environment variables.

## Self Review:

* [ ] Read your own diff before requesting review.
* [ ] Confirm you did not commit `.env` files, API keys, or customer data.
* [ ] Check screenshots or recordings are included for UI changes.
* [ ] Verify new or changed APIs are documented.
* [ ] Confirm database migrations are backward compatible or have a rollback plan.

## Checks and Reviewers:

* [ ] Wait for lint, unit tests, and build checks to pass.
* [ ] Add the right reviewers and any required code owners.
* [ ] Keep the pull request small enough to review in one sitting when possible.
* [ ] Reply to review comments with what you changed or why you did not.

## Merge and Follow-Up:

* [ ] Squash or merge using the team convention.
* [ ] Delete the remote branch after merge if that is the team rule.
* [ ] Confirm staging or production deploy notes are added when needed.
* [ ] Update the ticket status and notify QA or the product owner.
* [ ] Watch logs and error tracking for a short time after deploy.
