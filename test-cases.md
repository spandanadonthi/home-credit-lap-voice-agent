# Test Cases — Home Credit LAP Voice Agent

Run each case against the published agent using synthetic test data. Compare the transcript with expected behavior and record evidence in `test-results.md`. Mark Pass only when the transcript supports the expected result.

## Core eligibility

| ID | Scenario | Expected behavior |
|---|---|---|
| TC-01 | Residential; sole ownership; originals available; ₹65 lakh; salaried/bank; value ₹1 crore; tenure 10 years | Collect all seven items and offer senior-expert next step; no approval guarantee. |
| TC-02 | Commercial; joint ownership; originals available; ₹40 lakh; self-employed/bank; value ₹80 lakh; tenure 15 years | Joint ownership and self-employment are acceptable; 15 years is accepted. |
| TC-03 | Industrial; sole; originals available; ₹30 lakh; salaried/bank; value ₹1 crore; tenure 3 years | Industrial property and 3-year boundary are accepted. |
| TC-04 | Agricultural property | Disqualify immediately; do not ask remaining fresh-loan questions. |
| TC-05 | Original documents unavailable | Disqualify immediately. |
| TC-06 | Income received in cash | Disqualify immediately; do not continue with remaining questions. |
| TC-07 | Tenure 2 years | Disqualify immediately. |
| TC-08 | Tenure 16 years | Disqualify immediately. |
| TC-09 | Tenure exactly 15 years | Accept tenure if other items pass. |
| TC-10 | Low estimated market value, with no other disqualifier | Record the estimate; do not invent a minimum value. |

## Loan amount cap

| ID | Scenario | Expected behavior |
|---|---|---|
| TC-11 | Requests ₹90 lakh, clearly accepts ₹75 lakh | Record ₹75 lakh and continue; handoff only if all other items pass. |
| TC-12 | Requests ₹90 lakh, declines ₹75 lakh alternative | Explain that the offer cannot proceed at the requested amount and end. |
| TC-13 | Requests exactly ₹75 lakh | Treat as within the cap. |
| TC-14 | Amount could be misheard (e.g. ₹15 lakh vs ₹50 lakh) | Ask for confirmation; do not guess. |
| TC-15 | Says “okay” ambiguously after cap offer | Clarify acceptance if context does not make intent clear. |

## Memory and recovery

| ID | Scenario | Expected behavior |
|---|---|---|
| TC-16 | Gives answers out of order | Store clear answers and do not unnecessarily repeat questions. |
| TC-17 | Corrects sole ownership to joint ownership | Update the answer; joint ownership is acceptable. |
| TC-18 | Name is unclear | Ask briefly and use confirmed name. |
| TC-19 | Ownership answer is unclear | Clarify sole vs joint before proceeding. |
| TC-20 | Market value is unclear | Ask for a repeat/confirmation. |
| TC-21 | Says “sorry,” answers off-topic, or speech is unintelligible | Restate the current question simply; do not treat as yes. |
| TC-22 | Interrupts the agent | Address the relevant response and resume without losing state. |
| TC-23 | Contradictory answers | Ask which answer is correct; do not proceed until resolved. |
| TC-24 | Silence/no clear answer | Do not infer consent or a positive answer. |

## Routing and boundaries

| ID | Scenario | Expected behavior |
|---|---|---|
| TC-25 | Customer is busy | Ask for preferred callback time and end without eligibility questions. |
| TC-26 | Customer declines permission | End politely. |
| TC-27 | Wants EMI reduction on an existing property loan | Route to relevant specialist if supported; stop fresh-loan flow. |
| TC-28 | Wants to transfer an existing property loan | Route if supported; stop fresh-loan flow. |
| TC-29 | Asks for exact interest rate not in verified context | Do not invent rate; refer to senior expert for current details. |
| TC-30 | All seven items pass | Offer senior-expert next step; explain preliminary status. |
| TC-31 | One required item is missing | Do not hand off; ask for the missing item. |
| TC-32 | Asks “Am I approved?” | Clarify that this is preliminary qualification, not approval. |

## Regression suite
After changing the prompt/settings, rerun TC-01, TC-04, TC-06, TC-11, TC-12, TC-14, TC-16, TC-25, TC-27, TC-30, and TC-31.

## Evidence to capture
For every test, record the test ID, date, call ID, transcript/recording link, expected outcome, actual outcome, status (Pass/Fail/Partial), and notes. Use anonymized test calls only.
