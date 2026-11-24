# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

Compare the cause in Candidate plan with what happened in Repro evidence. In calib-01, the push succeeds, but the color updates only after reopening the view. That supports the plan’s explanation that the view needs to refresh after a push.

## Scope

Look at the Change, In, and Out lines under Candidate plan. In calib-01, the plan refreshes the commits view after a successful push and leaves push-status calculations and other views alone. A good scope makes those boundaries clear.

## Executability

<!-- Where the plan says what will actually be done: files or areas,
approach, order of work. What it means for a stranger to be able to
start executing without asking the author anything. -->

## Test plan

Compare the Test line under Candidate plan with the steps in Repro evidence. In calib-01, step 3 says the commit keeps its old color after a push. The plan gives a clear passing result: the color updates while the view is still open.

## Honesty

<!-- Where claims meet uncertainty: risks, unknowns, and deviations.
How to tell stated unknowns from false confidence, and where an
honest mid-build deviation gets recorded. -->

## Comms

Compare Candidate plan comment with Thread highlights and the contribution policy in Repo facts. In calib-01, there are no thread requests, and the comment explains that the fix will stay small because the maintainer has limited time to review PRs.