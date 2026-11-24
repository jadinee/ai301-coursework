# Rubric: is this reproduction package ready to post?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Repeatable steps | Commands and inputs in the same repro report | Someone using the stated environment can run the same test with the same inputs without guessing a missing step. | required |
| Environment | Setup details in the reproduction report and any versions named in the issue | The report identifies the code version tested and the software versions needed to repeat the test. If the setup differs from the one in the issue, the report says how. | required |
| Behavior shown | Test output, log or screenshot compared with the issue description | The evidence shows what happened when the reported behavior was tested, whether the problem appeared or the test passed. | required |
| Honesty | The report's conclusion and test output | The report says whether the problem happened and points to the test output that supports that conclusion. | required |
| GitHub comments | Claim comment, reproduction comment, and the repo's contribution instructions | The claim names the issue and says what the contributor will check next. Each comment follows any template or AI disclosure rule the repo requires for that comment. | required |

## Verdict rule

Accept if every required check that applies passes. Reject if any of those checks fails or is unclear. For a claim only draft, check only the claim comment and the repo rules that apply to it.