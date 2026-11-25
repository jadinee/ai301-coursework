---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

## The question

Decide whether one PR package is ready to submit. Grade its title, description, commits, diff, and test evidence against the plan and issue it implements.

## Inputs and modes

In live mode, read the named plan, including Deviations, the draft PR title and description, and the captured test evidence. From the fork, read the committed diff with `git diff main...HEAD` and the branch commits. Read the issue and its thread, the repo PR template, and `docs/CONTRIBUTING.md`. For a house-chain submission, use the assigned house plan and repro pack. Keep the review read-only.

In eval mode, grade one supplied bundle. Use the bundle text as the sole source of facts. Apply every check and the full verdict rule.

## The scope seam (live mode only)

In live mode, read `scope.md` before anything else. Apply its house rules and refuse packages outside the scoped repository. If `Repo:` still has a placeholder, stop and tell the student to fill it with their section's Path Review repo. Ignore `scope.md` entirely in eval mode.

## The voice seam (live mode only)

In live mode, compare the title and description with `voice-guide.md` and quote any broken rule in the summary. Voice feedback affects the verdict only if a rubric check uses it. Ignore the guide in eval mode.

## Component reads

Read `rubric.md` for the checks and verdict rule and `references/evidence-guide.md` for evidence locations. Execute `procedure.md` as written and report any gaps in the procedure. If the rubric or procedure has no substantive content, stop and explain what needs filling in.

## Verdict and output

Return `accept` when the rubric says ready to submit or `reject` when it says hold. Give a short per-check summary, then finish with one valid fenced JSON block in exactly the format below. Use the bundle ID in eval mode and the PR URL or issue URL for a live draft. Put nothing after the JSON.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

Name the fact or quote that decides each check. Judge the substance against the plan, issue, and stated standards. Apply the rubric and procedure as written. If the verdict rule is silent about an unclear grade, treat it as a fail.
