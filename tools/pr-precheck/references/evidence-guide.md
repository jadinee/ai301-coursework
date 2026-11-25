# Evidence guide: where evidence lives in a PR package

## Plan fidelity (harness category: silent-drift)

In eval, compare the scope, boundaries, and any deviations in Plan context with Issue and Candidate PR > Diff and Description. In live mode, compare the issue and `plan.md` (including Deviations) with `git diff main...HEAD` and `pr_draft.md`. The diff delivers what the plan promises, with any material departure explained in the plan and disclosed in the draft. The description accurately reflects the diff.

## Test evidence (harness category: not-tested)

In eval, compare Plan context's test plan and the reproduction with Candidate PR > Test evidence and any relevant Repo facts about required checks. In live mode, use `plan.md`, the issue's repro, and command output in `test_evidence.md`. Look for an observable failure and a result after the fix or equivalent verification relevant to the change. Required check outcomes are recorded and any claimed pass is supported.

## Diff quality (harness category: unreviewable)

In eval, read Candidate PR > Commits and Diff alongside Issue and Plan context. In live mode, read the branch commits and `git diff main...HEAD` alongside the issue and plan. The fix is easy to isolate, with no debug leftovers, commented-out code, or unrelated edits.

## Standards and comms (harness category: standards-wall)

In eval, compare Repo facts and Thread highlights with Candidate PR > Title and Description and any relevant part of the diff. In live mode, use the issue thread, the repo PR template, `docs/CONTRIBUTING.md`, and `pr_draft.md`. Required sections give concrete information, the PR links the issue, and applicable AI disclosure and maintainer requests are addressed.
