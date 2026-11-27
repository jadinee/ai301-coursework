# Contribution: NomNom #221 shows a green checkmark on an incomplete nomination

Path: `beat-2-contribution/contribution-story.md`

This file is Assignment 5, and it is graded at the path above; a copy kept anywhere else in
the repository is not read. **Keep every section header below under its exact name** — the
format criteria grade exactly that. Your course repo link is the whole submission: no tool
files and no evidence uploads are part of Assignment 5.

**Contribution Number:** [1]
**Student:** Jadine Delfin-Watanabe
**GitHub Username:** jadinee
**Issue:** [NomNom issue #221](https://github.com/WorldconVotingSystems/nomnom/issues/221)
**Pull Request:** [NomNom PR #537](https://github.com/WorldconVotingSystems/nomnom/pull/537)

One repository, built across units 5 to 8, telling the whole story of your real
contribution. Fill it as you work, not at the end — the sections below ask for evidence that
is far easier to write down as it happens than to reconstruct in the last weekend.

Contribution Number stays `[1]` unless you make more than one contribution this term; it
just numbers them.

---

## Toolkit

Every story section below, from Why I Chose This Issue through Pull
Request, ends with a Toolkit block: which tool did that phase's work
and how you used it, what it produced, what difficulties or
shortcomings it presented, and what you changed or would change
because of them. Together the blocks are the thread the rubric's
Toolkit points read, and they are the raw material for your unit-9
portfolio, so keep them current as you work rather than
reconstructing them later.

A Toolkit block looks like this (copy it into each story section and
fill it there):

```text
**Toolkit**

- Tool: [which tool did this phase's work, and how you used it]
- What it produced: [described in a sentence or a short excerpt]
- Difficulties: [what fought you or fell short, or "none met"]
- What changed: [the patch, revision, or workaround, what you would
  update, or "nothing"]
```

This section also keeps one short dated entry per week of tool work,
starting below: what you built or changed that week, what broke, and
what you changed because of it. The blocks tell the story where it
happened; these entries are the toolkit's own timeline.

All four entries are graded. Keep every heading below, and fill each
one in the week it belongs to.

**Unit 5: I changed how my scout picks issues to review**

November 25, 2026. I set up issue-scout to search GitHub and sort issues by fewest comments. Most results had zero comments, and four of the five issues it graded came from the same repo. I added a rule to grade at most one issue per repo so I could see a wider mix of projects.

**Unit 6: I tested the voice guard and saved my NomNom notes**

November 26, 2026. The voice guard blocked my test command because there was no comment text to check. I saved the claim draft in a file and reviewed it locally. I also made a local notes file with the NomNom files I worked in and the commands I used to run the site and tests.

**Unit 7: Ship-gate caught a formatting issue**

November 26, 2026. I set up the ship-gate manifest to run NomNom’s lint and full test suite. The first run flagged formatting in `renderers.py`, so I formatted the file with Ruff and committed the change. The second run passed both checks and accepted my PR draft. I then pushed the formatting fix and updated the description on PR #537.

**Unit 8: I checked my PR and decided to wait**

November 27, 2026. The PR monitor checked PR #537 and found no reviews or comments. My playbook says to wait seven quiet days before following up. The monitor drafted a note to wait, so I kept it local and left my PR open for review.

---

## Why I Chose This Issue

I found NomNom #221 on the CodePath Issue Selection site while looking for a Python project with a clear bug I could test. I also looked at GRASS #1522, but my scout rejected it because it tracks multiple fixes. The scout accepted NomNom #221 and rated it ambitious because the fix may involve both Django form validation and how the page shows the checkmark. I chose it because the report gives a clear way to reproduce the problem, and I want to learn how a form shows whether a save actually worked.

In my first scan, four of the five issues came from the same repo, so I changed the search to grade at most one issue per repo. I also changed the scope check to ask whether there’s one clear task to start. The difficulty note helped me see that NomNom is one task, but the fix may still take some digging.

Claim comment: I drafted a claim for NomNom #221 and kept it local.

**Toolkit**

- Tool: I used issue-scout to search GitHub and grade two issues I found on the CodePath tracker.
- What it produced: It accepted NomNom #221 as ambitious and rejected GRASS #1522 because it tracks multiple fixes.
- Difficulties: Four of the five issues in my first scan came from the same repo. My original scope check also made it hard to tell the difference between one difficult task and an issue that tracks several tasks.
- What changed: I limited the scan to one issue per repo and replaced Small scope with scope-feasible. I added a difficulty note so I can see how hard an accepted issue might be.

---

## Understanding the Issue

**Problem Description**

The issue reports that the nomination form can show a green checkmark for a field even when a required field is missing and the nomination wasn’t saved.

**Expected Behavior**

The form should show a green checkmark only for information that was actually saved.

**Current Behavior**

The reporter filled in Developer, left the required Title field blank, and clicked “Save as you go.” The form showed a green checkmark next to Developer, but the emailed ballot did not include that nomination.

**Affected Components**

In `nominate/views/nominate.py`, the view returns the invalid ballot before saving it. In `nominate/renderers.py`, the renderer still gives Developer a green checkmark because the field has a value and no error of its own.

**Toolkit**

- Tool: I read GitHub issue #221 and traced the save behavior in VS Code.
- What it produced: I found that the view rejected the whole ballot, but the renderer still showed a green checkmark for Developer.
- Difficulties: The checkmark looked like confirmation that the field saved, even though it only reflected validation for that field.
- What changed: I focused the fix on when the form shows checkmarks and kept the existing validation rules.

---

## Reproduction Process

**Environment Setup**

I reproduced NomNom #221 locally on macOS at commit `22d531f04da7748ac0daee7f5d7d8e59981d1f77` using Python 3.13.5, Django 6.0.8, and Docker Desktop. The `just dev-env` command in the docs wasn’t available in this checkout, so I ran `just bootstrap` to load the test data and `just serve` to start the app at `http://localhost:8000/`.

**Steps to Reproduce**

1. In the local admin page, set The Yugo Awards to Nominating and give `member0001` the Can nominate in WSFS elections permission.
2. Sign in as `member0001`, open the nomination form, and find Best Game or Interactive Work.
3. Clear the first Title field, leave Developer set to Heisenberg Studios, and click Save as you go.
4. The Title field shows “This field is required,” but Heisenberg Studios still shows a green checkmark in the same row.

**Reproduction Evidence**

- **Commit tested during reproduction:** [`22d531f`](https://github.com/jadinee/nomnom/commit/22d531f04da7748ac0daee7f5d7d8e59981d1f77)

- **Screenshots/logs:** The [before-fix screenshot](nomnom-221-before.png) shows the required Title error and the green checkmark beside Heisenberg Studios in the same row.

- **My findings:** After I cleared the first Title and clicked Save as you go, the form showed “This field is required” next to Title and a green checkmark beside Developer. After I refreshed the page, the original title, The Quantum Paradox, reappeared. The title change didn’t persist even though the row showed a green checkmark.

**Toolkit**

- Tool: I used Docker Desktop and my browser to run NomNom locally and reproduce the bug.
- What it produced: I captured the red Title error and the green Developer checkmark in the same row. Refreshing brought back the original title.
- Difficulties: `just dev-env` wasn’t available in my local copy.
- What changed: I ran `just bootstrap` to load the test data and `just serve` to start the site.

---

## Solution Approach

**Analysis**

The nomination view checks whether the whole ballot is valid before saving it. The renderer in `nominate/renderers.py` checks each field on its own. It gives Developer a green checkmark when the field has a value and no error, even when the missing Title prevents the ballot from saving.

**Proposed Solution**

I plan to hide green checkmarks when the nomination ballot fails validation. The form will still show which fields need attention, and a successful save will still show the usual checkmarks. The change only affects what the form displays after a save attempt.

**Implementation Plan**

1. Pass the save result from the nomination view to the form renderer.
2. Show green checkmarks only after a successful save. Keep the existing field errors visible when validation fails.
3. Test both cases locally: save with Title blank, then fill in Title and save again.

Ship-gate flagged a formatting issue in renderers.py. I ran Ruff to format the file, then reran ship-gate. The lint and test checks both passed.

**Toolkit**

- Tool: plan-check
- What it produced: It reviewed my local plan and draft comment but didn’t give a verdict.
- Difficulties: It looked for a claim and reproduction comment on issue #221. My reproduction was in my local write-up.
- What changed: I kept the reproduction steps and test results in my contribution story.

---

## Testing Strategy

- Before the fix saving with Title blank showed a red required-field error and a green checkmark beside Heisenberg Studios.
- After the fix I repeated the same steps. The red error still appeared, and the green checkmark was gone. [Failed save](nomnom-221-invalid-save.png)
- I entered The Quantum Paradox and saved again. Both the title and developer fields showed green checkmarks. [Successful save](nomnom-221-valid-save.png)
- I ran NomNom’s nomination view tests locally. All 59 passed in 2.89 seconds.

**Toolkit**

- Tool: Browser and pytest.
- What it produced: I verified both save cases in the browser, and all 59 nomination view tests passed.
- Difficulties: Pytest stopped on the first run because the database settings were missing.
- What changed: I reran pytest with `--env-file .env` to load the local settings.

---

## Implementation Notes

**2026-11-26**

I passed the save result from the nomination view to the template. When a save fails, the form uses a renderer that keeps the red field errors visible. After a successful save, the form uses its original checkmark styling. I registered the new renderer in both the local settings and the convention settings template. I tested both save cases and committed the fix as `209b55c`.

**Toolkit**

- Tool: I used VS Code to make the fix and Git to commit it.
- What it produced: The form uses the save result to decide when to show green checkmarks. I recorded the fix in commit `209b55c`.
- Difficulties: The new renderer needed to be registered in both the local settings and the convention settings template.
- What changed: I added it to both settings files so the nomination form could use it.

---

## Pull Request

**PR Link:** [NomNom PR #537](https://github.com/WorldconVotingSystems/nomnom/pull/537)

**PR Description:** Keep required-field errors visible when a save fails, and show green checkmarks only after a successful save. I tested both cases in the browser, and all 59 nomination view tests passed.

**Maintainer Feedback:** None yet as of November 27, 2026 check.

**Status:** Opened, awaiting review.

**Toolkit**

- Tool: I used ship-gate to check my branch and PR draft after I opened PR #537.
- What it produced: The second run passed lint and the full test suite. The draft passed all required checks.
- Difficulties: The first run stopped because Ruff wanted to reformat `renderers.py`.
- What changed: I formatted the file, pushed commit `79f10b3`, and updated the PR description with my test results and AI disclosure.

---

## Learnings and Reflections

**Technical Skills Gained**

I learned how to pass a save result from a Django view to a template and use it to control which validation styles appear.

**Challenges Overcome**

Pytest stopped before running because it hadn’t loaded the local database settings. I reran it with `--env-file .env`, and all 59 tests passed.

**What I'd Do Differently Next Time**

I’d check the repo’s setup and test commands first. I’d also record the before and after browser results as I go.

---

## Resources Used

- [NomNom issue #221](https://github.com/WorldconVotingSystems/nomnom/issues/221) gave me the steps to reproduce the misleading checkmark.
- NomNom’s `justfile` gave me the commands to set up the local site and run the project checks.
