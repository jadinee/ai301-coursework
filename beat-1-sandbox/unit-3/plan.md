# Plan for issue #64

## Diagnosis

The partial-overlap test uses a sample that contains all four query words: Python, Django, web, and framework. The scorer returns `1.0` because all four words match. The test expects a score below `0.9` and fails with `assert 1.0 < 0.9`.

## Scope and approach

In `tests/unit/test_relevance_scorer.py`, update the sample text in `test_query_with_partial_overlap` so it matches three of the four query words. Keep the query, score assertions, and scorer code as they are. Remove the expected-failure marker once the corrected test passes.

## Test plan

From the root of my PathReview fork, rerun the Unit 2 test:

```bash
.venv/bin/python -m pytest -q --runxfail tests/unit/test_relevance_scorer.py::TestRelevanceScorer::test_query_with_partial_overlap
```

Before the fix, it failed with `assert 1.0 < 0.9`. After the fix, I expect `1 passed` because three of the four query words match, giving a score of `0.75`.

## Risks and unknowns

The `--runxfail` flag ignores the expected-failure marker. After removing the marker, I’ll also run the test without that flag to confirm it passes normally.

## Deviations

I followed the plan. I replaced “framework” with “toolkit” in the sample text, removed the expected-failure marker, and confirmed the test passed normally.
