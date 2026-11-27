I opened a fix for a misleading green checkmark in NomNom, the tool Worldcon members use to submit Hugo Award nominations. I tested the form with a required field blank, then filled it in and saved again.

A green checkmark can make you think your nomination was saved. With my change, the checkmark only appears after a successful save. All 59 nomination form tests passed on my computer, and my pull request is open for review.

https://github.com/WorldconVotingSystems/nomnom/pull/537