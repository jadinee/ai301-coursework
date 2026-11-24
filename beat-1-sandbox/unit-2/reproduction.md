# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

---

## Your identity upstream

**GitHub username**

jadinee

---

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/64#issuecomment-7139042325

I’d like to work on #64. I’ll run the partial-overlap test and check which words the sample texts share. I’ll follow up here with the result.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/64#issuecomment-7139472974

I reproduced #64 on my fork at commit `2f4e82f` on `main`. I used macOS 27.3 (arm64), Python 3.13.5, pytest 9.2.0, and structlog 26.1.0.

From the root of the clone, I set up a virtual environment and ran just the partial-overlap test. I used `--runxfail` to see the assertion failure for the test marked as an expected failure.

```bash
python3 -m venv .venv
.venv/bin/python -m pip install "pytest==9.2.0" "structlog==26.1.0"
.venv/bin/python -m pytest -q --runxfail tests/unit/test_relevance_scorer.py::TestRelevanceScorer::test_query_with_partial_overlap
```

The test expected a score above 0.3 and below 0.9. The scorer returned 1.0. My output included:

```text
E       assert 1.0 < 0.9
tests/unit/test_relevance_scorer.py:58: AssertionError
1 failed in 0.10s
```

I checked the sample text, and it contains all four query words: Python, Django, web, and framework. That explains why this example gets a full match even though the test expects a partial match.

## Eval iterations

**Run history**

I did one full run. My rubric matched the expected result on 18 of the 20 packages and passed the minimum for every category.

```text
agreement: 18/20 scored items  (bar: 18/20: PASS)
```

**Package analysis**

For `pkg-05`, my rubric returned `reject` and the expected result was `accept`. The run says “failed: Repeatable steps.” The report gives the command and shows the error. It also describes the input file as containing “a valid `dependencies:` list plus a `category:` section,” but it leaves out which dependencies were in the file. My check asks whether someone can use the same inputs without guessing. That missing detail helps explain why my rubric rejected the package.

**Check rationale**

```text
| Repeatable steps | Commands and inputs in the same repro report | Someone using the stated environment can run the same test with the same inputs without guessing a missing step. | required |
```

I chose “without guessing a missing step” because it gives me a specific way to decide whether I could repeat the test. I considered whether seeing the command would be enough. In `pkg-05`, I could copy the command, but I’d still have to decide what to put in `env.yml` before I could run it.

**Trade-offs**

Asking for “the same inputs” can be too strict. In `pkg-05`, the output points to `category` as the section that caused the warning. Someone familiar with conda could use a different dependency list and still see that warning. My check helps someone like me follow the steps, but it can also reject a useful report when the missing detail wouldn’t change the result.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
