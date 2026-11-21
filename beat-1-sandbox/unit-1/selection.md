# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/64

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

All three issues pass every required check, so all three are accepted. Ranked for your fit profile:

1. **#68: Keyword search raises `ZeroDivisionError` on an empty index.** This is the best fit. The issue names both files to touch (`rag/retriever/keyword_search.py` and `tests/unit/test_keyword_search.py`) and estimates 2–4 hours. The fix is a small empty-input guard in real code, plus removing the `xfail` marker on the test that checks it. That covers all three things you want to practice: reading code, making a specific change, and testing it.
2. **#64: Relevance scorer "partial overlap" test fixture.** This is the smallest and safest of the three: you change one test fixture and run one `pytest` command. It ranks second because you only edit test data, so you get less practice reading application code.
3. **#54: Resume section detection fails on leading whitespace.** It's still a good issue, with a repro snippet and three named failing tests. It ranks last because the fix means editing regex patterns, and several classmates found that a second function (`_strip_markdown()`) has the same problem. That's more to work through than the other two.

None of the three was rejected. The repo-level checks were the same for all of them: the repo isn't archived and its last commit was 2026-09-16, 66 days ago. That also passes Maintainer response under `scope.md`'s exception. `docs/CONTRIBUTING.md` says nothing about AI tooling.

**Things to know before you pick:**
- **These issues are crowded.** I read every open PR from a classmate as a classmate's claim, so it didn't block anything. `scope.md` only mentions claim comments, though, so if you meant open PRs to count against an issue, the rubric should say so. The PR counts:
  - #68: about 18 open PRs and over 20 people claiming it.
  - #54: 7 open PRs.
  - #64: 4 open PRs.

  Your PR still earns credit, but don't expect to be the first to solve any of them.
- **#68 has one closed PR (#194).** I didn't check whether it was merged. Even if it wasn't, your rubric only fails Small scope at 2 or more closed-unmerged PRs, so it doesn't change the result.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
    "checks": [
      {"name": "Clear problem", "grade": "pass", "evidence": "Body: `index([])` raises ZeroDivisionError inside BM25Okapi; 'index() shouldn't raise on an empty corpus either'; remove the xfail marker on the covering test."},
      {"name": "Small scope", "grade": "pass", "evidence": "Two named files, 'Estimated effort: 2–4 hours'; fewer than 2 closed linked PRs (only #194); nothing TBD."},
      {"name": "Available work", "grade": "pass", "evidence": "No assignees; ~18 open PRs and many claim comments are all from classmates, which scope.md's Path Review house rule says do not block."},
      {"name": "Maintainer response", "grade": "pass", "evidence": "scope.md Path Review exception: passes because Repo activity passes."},
      {"name": "Repo activity", "grade": "pass", "evidence": "archived=false; latest default-branch commit 2026-09-16 by Aburke225, 66 days before 2026-11-21."},
      {"name": "Contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md (linked from README) is silent on AI tooling; no AI_POLICY.md or AGENTS.md present."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/64",
    "checks": [
      {"name": "Clear problem", "grade": "pass", "evidence": "Body: fixture shares all four query terms so scorer correctly returns 1.0; 'Fix the fixture so the overlap is genuinely partial'; repro `pytest tests/unit/test_relevance_scorer.py -q` -> `assert 1.0 < 0.9` fails."},
      {"name": "Small scope", "grade": "pass", "evidence": "Single test-fixture change in tests/unit/test_relevance_scorer.py; no closed-unmerged linked PRs; nothing TBD."},
      {"name": "Available work", "grade": "pass", "evidence": "No assignees; open PRs #75, #87, #232, #279 and claim comments are all from classmates, which scope.md's Path Review house rule says do not block."},
      {"name": "Maintainer response", "grade": "pass", "evidence": "scope.md Path Review exception: passes because Repo activity passes."},
      {"name": "Repo activity", "grade": "pass", "evidence": "archived=false; latest default-branch commit 2026-09-16 by Aburke225, 66 days before 2026-11-21."},
      {"name": "Contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md (linked from README) is silent on AI tooling; no AI_POLICY.md or AGENTS.md present."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/54",
    "checks": [
      {"name": "Clear problem", "grade": "pass", "evidence": "Body gives a repro snippet with 'observed: [] (expected: Education, Skills)' and names three failing tests in tests/unit/test_resume_parser.py."},
      {"name": "Small scope", "grade": "pass", "evidence": "Bounded regex fix in _detect_sections() in ingestion/parsers/resume_parser.py (plans note _strip_markdown() too); no closed linked PRs; nothing TBD."},
      {"name": "Available work", "grade": "pass", "evidence": "No assignees; open PRs #76, #103, #126, #170, #204, #205, #226 and claim comments are all from classmates, which scope.md's Path Review house rule says do not block."},
      {"name": "Maintainer response", "grade": "pass", "evidence": "scope.md Path Review exception: passes because Repo activity passes."},
      {"name": "Repo activity", "grade": "pass", "evidence": "archived=false; latest default-branch commit 2026-09-16 by Aburke225, 66 days before 2026-11-21."},
      {"name": "Contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md (linked from README) is silent on AI tooling; no AI_POLICY.md or AGENTS.md present."}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

agreement: 20/20 scored items  (bar: 18/20: PASS)

**Issue analysis**

For issue-01, my rubric returned 'accept' and the expected result was also 'accept'. The issue gives a clear goal "add a stable docs location for the GA workflow and update the existing pages that currently mention older or temporary guidance." Even though it touches several files, the report names the pages and explains what to change on each one, so the work has a clear scope.

**Check rationale**

```
| Clear problem | Issue body and comment thread | The issue describes the current problem and the desired result in enough detail that a newcomer can tell what "done" looks like. For bug reports, provide either reproduction steps OR a clear statement of observed vs. expected behavior that a developer could act on. A maintainer-filed issue that enumerates specific missing items or lists acceptance criteria satisfies this check. | required |
```

I wrote this check so that I can tell when my fix actually works. As a newcomer, I need to know what "done" looks like before I start, or I could change code and still not know whether I fixed anything. For a bug report, either of two things gives me that. Reproduction steps let me run the problem myself, watch it fail, and run the same steps after my change to see that it no longer fails. A clear observed vs. expected statement tells me the wrong result I see now and the right result I should see after the fix, so I can compare the two directly. I accept either one, rather than requiring both, because each gives me a concrete before-and-after test. Requiring both would reject issues that are clear enough to work on.

**Trade-offs**

My check asks for “either reproduction steps OR a clear statement of observed vs. expected behavior that a developer could act on.” This can rule out a small bug if the report has no reproduction steps and also leaves out what should happen. I’m okay with that because knowing the expected behavior gives me a clear way to test the fix.

---

## Selection rationale

**Selection rationale**

I picked #64 because I want more practice with Python tests, and it's a small change I can finish in the time I have left. The verdict got it right that the issue explains what the tests would check, and I also considered how easy it would be to run the test locally. I think claiming it will be pretty straightforward because I can explain what's wrong with the test and what I'll check first.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
