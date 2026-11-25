# Voice guide: how I talk upstream


## Who I am in threads

I’m a student getting more practice with Python tests and learning how to contribute to an open source project. When I pick up an issue, I’ll explain what I plan to check and follow up with what I find.

## Rules I write by

### Rule: Say what I’ll check first

When I claim an issue, I’ll name the part I’m looking at and give one specific next step.

- Wrong: “I’d like to work on this. I’ll look into it.”
- Right: “I’d like to work on #64. I’ll run the partial-overlap test and check which words the two inputs share.”

### Rule: Show what I saw

When I report a result, I’ll include the part of the output that led me to that conclusion.

- Wrong: “I ran the test and got the same problem.”
- Right: “The partial-overlap test expected a score below 0.9, but it got 1.0.”

### Rule: Say when I’m still figuring something out

If something stops me from running the test, I’ll explain where I got stuck. I can follow up once I know more.

- Wrong: “The test failed on my Mac too.”
- Right: “I got an import error before the test ran, so I can’t tell yet what score the test would return.”

## Things I never post

- A promise to fix the issue or finish by a certain date.
- “Same here” based only on someone else’s result.
- A guess about what caused the problem written as if I’ve confirmed it.
## Pull requests

- Use a short title that names the actual change.
- Explain why the change was needed and quote the test output that supports it.
- Say how AI helped, in your own words. Describe any unfinished verification plainly.
