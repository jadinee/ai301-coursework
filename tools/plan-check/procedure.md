# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

1. Read the issue description and reproduction evidence first.
2. Read the proposed fix and test plan with that evidence in mind.
3. Read the draft comment alongside the issue thread and any repo rules provided.

## Evidence gathering

1. Find the plan’s explanation of the cause and the reproduction output that supports it.
2. Find the proposed changes and compare them with what the issue asks for.
3. Find the test command or steps and the expected result. Compare them with the original reproduction steps.

## Check execution

1. For each rubric check, read the evidence listed in that row.
2. Mark the check as pass if the evidence meets the pass condition, fail if it falls short, or unclear if there isn’t enough information to decide.
3. Give a short reason that points to the evidence you used or says what’s missing.

## Verdict assembly

1. Review the result of each required check.
2. Return `accept` if every required check passes. Return `reject` if any required check fails or is unclear.
