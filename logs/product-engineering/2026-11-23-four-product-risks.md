# Product Engineering: Four product risks + CSV-export exercise
- **Date:** 2026-11-23 (planned slot, ledger W01-Mon)
- **Actual minutes:** not reported (he studied in pieces, not continuously, and chose not to log minutes)
- **Roadmap:** PE Week 1/24
- **Status:** done (explain-back passed, artifact written and reviewed)

## Covered
- The four risks: value, usability, feasibility, viability. What each one is, its usual owner (PM / designer / engineering / PM + stakeholders), and how each one fails.
- Engineers over-focus on feasibility, but value risk kills most features. Test the riskiest assumption (most uncertain × most damaging) with the cheapest real evidence before building. Use past behaviour, not opinions.
- Non-code tests: existing data, "walk me through last time" interviews, concierge/manual version, fake door, mockup.

## Explain-back (summary)
- Value: nobody uses it. Usability: nobody can work out how to use it. Feasibility: partway through the build you find you lack the data or resources. Viability: it breaks legal or business policy.
- Devs over-focus on feasibility; value is what kills features ("No value, no positive impact on the business").
- Bloopo: the assumption is that buyers who see the chat icon will message, and that this leads to a reservation or closed deal. Risk = value. Proposed test: A/B test measuring tap → reservation. (This closes Nov 21's open feedback: he chose the deeper outcome metric.)

## CSV exercise (his answers)
- First pass: understand the ask. What does "slow" mean, what counts as fast, does the data have value more often than monthly. Biggest risk named as viability (uncontrolled export costs). He didn't know which tests to run.
- Revised (as a Slack reply to a PM): before working on it, clarify what "slow" and "fast enough" mean, what data they export, who uses it and what they're trying to accomplish. Ask for a call or screen share where they walk through it.

## Feedback given
- An A/B test measures the outcome after you build. It isn't the cheapest pre-build test. Before building: existing contact/reservation data plus 5 "walk me through your last purchase" buyer conversations. Split the assumption into (a) contact friction is what blocks reservations (value) and (b) a chat icon removes that friction (closer to usability).
- CSV: the customer brought a solution; find the job (who reads the report, what decision it feeds). The biggest risk is value: CSV may not fix what's actually slow if the time goes into cleanup after the export. Viability (cost) is real but usually cheap to control with rate limits.
- Tests toolkit: watch them do last month's report (time each step), concierge (hand-run a query, email the CSV, ask what it saved), check whether other customers have the same need, then build the smallest version.
- Revised reply was strong on the job and on evidence from past behaviour. Gap: it didn't name the biggest risk or the step after the call. Model lines were given. Next time, write those lines unprompted.

## Next
W01-Tue (Tue 2026-11-24): evidence-based skills baseline across the 6 roadmap capabilities. Habit to carry: always name the riskiest assumption plus the cheapest test in any feature reply.
