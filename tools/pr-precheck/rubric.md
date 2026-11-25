# Rubric

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Plan alignment | Issue scope, plan and Deviations, committed diff | The diff addresses the planned fix. Material changes to the approach or omissions are explained in Deviations and disclosed in the PR. | required |
| Focus | Issue scope and all changed files and hunks | Every substantive edit belongs to the issue. The diff has no unrelated cleanup, debug leftovers, or abandoned code. | required |
| Test evidence | Plan’s test plan, reproduction steps, command output, and repo-required checks | The evidence shows the original failure and an observable after result tied to the fix, or equivalent verification appropriate to the change. Applicable repo checks have concrete results. An expected no-tests result or an honestly reported check failure with a reason can count as evidence. A result that contradicts the claimed fix fails. | required |
| Reviewability | PR title and body, issue, diff, and test evidence | A reviewer can tell what changed, why, and how it was verified. The description matches the diff and the claims and checkmarks match the evidence. Include a demo when it materially helps review. | required |
| Repo and thread requirements | PR template, contributor guide, issue thread, or bundled repo facts, plus draft and diff | The draft follows the applicable explicit requirements, including issue linkage, required template sections, and AI disclosure where required. Seeded-issue markers and matching suppressions are removed where applicable. Pending CI is reported accurately on a pre-open draft. | required |

## Verdict rule

Accept when every required check passes. Reject when any required check fails or is unclear. Preferred checks do not affect the verdict. Use fail for an observable violation or a required omission. Use unclear when the evidence is ambiguous or inaccessible and prevents a decision.
