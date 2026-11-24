# Evidence guide: where proof lives in a reproduction package

## Environment

**Where to look:** In an eval package, compare the setup in the reproduction report with the setup described in the issue. In live mode, compare your draft report with the GitHub issue.

**What to check:** The report names the code version tested and the software versions needed to repeat the test. If the setup differs from what the issue describes, the report explains how.

## Steps

**Where to look:** Read the steps in the sample report or live draft. Compare them with the action that triggered the problem in the issue.

**What to check:** Someone can tell where to start, what to run or click, and which inputs to use. They can repeat the test without guessing a missing step.

## Behavior shown

**Where to look:** Compare the test output, log, or screenshot in the sample report or live draft with the behavior described in the issue.

**What to check:** The evidence shows what happened when the reported action was tried. For example, if the issue is about a score, look for the score the test expected and the score it actually returned.

## Honesty

**Where to look:** Read the conclusion in the sample report or live draft alongside the output from that run.

**What to check:** Check that the report's conclusion matches the test output. If the test couldn't run, check that the report explains what stopped it.

## Comms

**Where to look:** In an eval package, compare the comments with the issue and the contribution rules in the repo facts. In live mode, compare the draft comments with the GitHub issue and the repo's contribution instructions.

**What to check:** The claim names the specific problem and says what the contributor will check next. Each comment follows any template or AI disclosure rule the repo requires for that comment.