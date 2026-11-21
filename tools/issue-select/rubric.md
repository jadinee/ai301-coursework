# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Clear problem | Issue body and comment thread | The issue describes the current problem and the desired result in enough detail that a newcomer can tell what "done" looks like. For bug reports, provide either reproduction steps OR a clear statement of observed vs. expected behavior that a developer could act on. A maintainer-filed issue that enumerates specific missing items or lists acceptance criteria satisfies this check. | required |
| Small scope | Issue body, comment thread, and repo-facts linked-PRs line | The work is a bounded set of changes a newcomer could enumerate upfront. A single bug fix with multiple internal fixes or named root causes counts as bounded; so does a documentation change across several files, or a small feature with concrete acceptance criteria. Fail if any of these apply: (a) the issue is a tracking/umbrella task, requires a broad rewrite or major redesign, or describes open-ended work whose scope cannot be fixed upfront (e.g., "improve typing across the codebase"); (b) the issue has 2 or more linked PRs that were opened and later closed without merging, signaling multiple attempts have failed because the spec is unsettled; (c) a key deliverable is explicitly marked TBD, undecided, or awaiting a product decision, and no maintainer has confirmed the direction in comments. | required |
| Available work | Repo-facts assignees and linked PRs, issue comment thread | No assignee, open PR addressing the same work, or a comment saying someone is still working on it. In live Path Review mode, follow scope.md's exception for classmates' claims. | required |
| Maintainer response | Repo-facts maintainer first-response sample and last-5 default-branch commits | Pass if the repo shows at least one of: (a) a sampled issue opened by a non-maintainer received a maintainer response within 45 days, or (b) the last 5 default-branch commits include a merge or commit by a maintainer within the past 30 days (use the snapshot date in eval mode, today in live mode). Issues opened by maintainers are excluded from the sample numerator and denominator. Mark unclear only when neither signal can be evaluated — i.e., the sample contains no non-maintainer issues AND the commit list is empty. In live Path Review mode, follow scope.md's Maintainer response exception. | required |
| Repo activity | Repo-facts archived status and last 5 default branch commits | The repo is not archived and at least one listed commit by a person is within the past 90 days. Use the snapshot date in eval mode and today's date in live mode. | required |
| Contribution policy | Repo-facts "contribution policy" line | Pass if the policy is silent on AI tooling, or permits AI contributions (with or without a human-review requirement). Fail if the policy explicitly prohibits AI-generated code or documentation. Mark unclear only if no "contribution policy" line is present in repo-facts at all. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

Accept only if every required check passed. Reject if any required check fails or is unclear. Preferred checks only rank accepted issues. 