# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

jadinee

**Plan comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/64#issuecomment-7141617643

I plan to update the sample text in `test_query_with_partial_overlap` so it matches three of the four query words. Right now it matches all four and gets a score of 1.0. I’ll rerun the same test from my reproduction and expect it to pass with a score of 0.75. Once it passes, I’ll remove the expected-failure marker and verify that it passes normally.

---

## Your branch

**Branch**

fix/64-partial-overlap

**Evidence**

I ran this command before and after the fix:

```bash
.venv/bin/python -m pytest -q --runxfail tests/unit/test_relevance_scorer.py::TestRelevanceScorer::test_query_with_partial_overlap
```

Before the fix, my Unit 2 output included:

```text
E       assert 1.0 < 0.9
tests/unit/test_relevance_scorer.py:58: AssertionError
1 failed in 0.10s
```

After the fix:

```text
.                                                                        [100%]
1 passed in 0.04s
```

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

I ran the full eval once.

```text
agreement: 19/20 scored items  (bar: 18/20: PASS)
```

**Package analysis**

For `pkg-20`, my rubric said `accept`, and the expected result was `reject`. The comment followed the direction in the issue thread, which may explain why it passed my check. The repo says “All AI usage in any form must be disclosed,” and the comment left out that disclosure.

**Check rationale**

```text
| Plan comment | Candidate plan comment, Thread highlights, and Repo facts | The comment follows any relevant requests in the issue thread and any contribution rules that apply to the proposed work. | required |
```

I added this check before the eval because even a clear plan can miss something the maintainer asks for. I made it required because those requests can affect whether the comment is ready to post.

**Trade-offs**

I kept the Plan comment check broad so it could apply to different repos. The trade-off is that it can miss a specific requirement, like the AI disclosure in `pkg-20`.

---

Related paths: `plan.md` and `eval-run.txt` in this directory, and the skill files in `tools/plan-check/`.