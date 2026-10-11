# Test Results — Home Credit LAP Voice Agent

## Test run details
- Platform: Retell AI
- Agent: Home Credit LAP Preliminary Qualification
- Prompt version/date: Final prompt version used for the calls shared in the development conversation; exact version identifier not provided
- Test date: 11 October 2026 (document updated; individual call dates were not provided)
- Tested by: Project owner
- Published version: Exact published version identifier not provided

## Summary
- Tests with transcript evidence reviewed here: 5 observed call scenarios
- Pass: 3 observed scenarios matched the main expected business outcome
- Partial / needs review: 2 observed scenarios had unresolved conversation-quality or amount-confirmation concerns
- Fail: Not established from the available transcripts
- Not run / not evidenced: The remaining rows in the results log below

**Important evidence note:** This document is updated on 11 October 2026 using only the call transcripts described during development. I cannot truthfully mark every test as run because transcripts or call IDs were not supplied for every scenario. “Not run / not evidenced” means no supporting transcript was available in the material reviewed here; it does not necessarily mean the agent would fail that test. Add each Retell call ID and recording link when available.

## Results log

| Test ID | Expected outcome | Actual outcome / evidence | Status | Call ID / recording |
|---|---|---|---|---|
| TC-01 | All seven items pass; appropriate handoff; no approval guarantee | A shared successful-path transcript included commercial property, sole ownership, originals available, an amount within the cap, self-employed/bank income, an estimated market value, and 3-year tenure. The agent offered the senior-expert next step and stated final approval was subject to review. The transcript appears to cover the seven required items. | Pass for observed behavior | Not provided |
| TC-04 | Agricultural property causes immediate disqualification | No supporting transcript for agricultural property was available in the reviewed conversation. | Not run / not evidenced | Not provided |
| TC-05 | Missing originals cause immediate disqualification | No supporting transcript for unavailable original documents was available in the reviewed conversation. | Not run / not evidenced | Not provided |
| TC-06 | Cash income causes immediate disqualification; no remaining questions | In a shared transcript, after the customer answered “In cash,” the agent thanked them, said the offer could not proceed under the criteria, and ended. It did not ask the remaining eligibility questions. | Pass for observed behavior | Not provided |
| TC-07 | 2-year tenure causes immediate disqualification | A shared transcript with 1-year tenure was rejected because the allowed tenure is 3–15 years. This supports the below-minimum rule, but it was not specifically a 2-year test. | Partial — 1-year boundary observed; TC-07 exact input not tested | Not provided |
| TC-09 | 15-year tenure accepted | A shared successful-path transcript used 3-year tenure, not 15 years. No transcript for exactly 15 years was available. | Not run / not evidenced | Not provided |
| TC-11 | ₹90 lakh request + acceptance: record ₹75 lakh and continue | In one transcript, the customer requested ₹90 lakh and the agent explained the ₹75 lakh cap. The customer accepted, but then disclosed cash income and the agent correctly disqualified. This did not demonstrate a successful completion of the remaining checks after cap acceptance. | Partial — cap acceptance observed; full eligible path not verified | Not provided |
| TC-12 | ₹90 lakh request + rejection: end fresh-loan flow | No supporting transcript for rejection of the ₹75 lakh alternative was available. | Not run / not evidenced | Not provided |
| TC-14 | Ambiguous amount is clarified rather than guessed | In a shared transcript, the loan amount was initially unclear and later clarified as ₹30 lakh. In another, an amount was initially interpreted as ₹2 lakh without an explicit confirmation, so the behavior was not consistently verified. | Partial — clarification observed, but confirmation needs more testing | Not provided |
| TC-16 | Out-of-order answers are remembered | The shared transcripts generally followed the question sequence. No clear test transcript demonstrated multiple eligibility answers being given out of order and then remembered without repetition. | Not run / not evidenced | Not provided |
| TC-19 | Unclear ownership is clarified | In a shared transcript, the customer's ownership answer was unclear (“Phone by me”), and the agent asked whether the property was solely or jointly owned. The customer clarified that it was already owned by them; the agent continued. | Pass for observed clarification behavior | Not provided |
| TC-25 | Busy customer is asked for callback time and qualification ends | No supporting transcript for a busy customer requesting a callback was available. | Not run / not evidenced | Not provided |
| TC-27 | Existing loan/EMI request is routed away from fresh-loan flow | No supporting transcript for an existing property loan, EMI reduction, or loan transfer was available. | Not run / not evidenced | Not provided |
| TC-30 | Handoff only after all seven items pass | A shared successful-path transcript completed the seven checks and offered a senior-expert next step. Other transcripts also showed immediate stopping after cash income. The available evidence supports these observed examples, but it does not prove every possible branch. | Pass for observed examples; broader coverage still needed | Not provided |
| TC-31 | Missing required item blocks handoff | No supporting transcript showed the agent attempting handoff while a required item was missing. | Not run / not evidenced | Not provided |

## Additional observed conversation-quality notes

1. In multiple calls, the greeting or some questions were split into short fragments. Review Retell turn-taking, interruption handling, speech recognition, and voice settings as well as the prompt.
2. The agent successfully clarified the customer's name in a shared test.
3. The agent handled a customer requesting ₹90 lakh by stating the ₹75 lakh cap and asking whether the customer would proceed at the cap.
4. A shared call demonstrated immediate termination after cash income was disclosed.
5. An unclear loan amount was not always explicitly confirmed before interpretation. Continue testing financial amounts and ambiguous acceptance responses such as “okay.”
6. A 1-year tenure was rejected. The exact 2-year and 16-year test cases, plus the 3-year and 15-year inclusive boundaries, still need individual evidence.

## Risks to verify
- Greeting and questions may sound fragmented; check turn-taking, interruption detection, speech recognition, and TTS in addition to prompt wording.
- Verify an accepted ₹75 lakh amount in a successful end-to-end call where all remaining criteria pass.
- Verify the customer-declines-the-cap branch.
- Verify each hard disqualifier separately.
- Verify existing-loan routing and callback handling.
- Verify that missing or unclear required information blocks handoff.
- Add actual Retell call IDs and recording links; they were not available in the transcript excerpts used for this update.
- Ensure recording links do not expose private customer data.

## Release checklist
- [ ] Remaining test scenarios run and documented.
- [ ] Failures and partial results documented honestly.
- [ ] High-risk regression tests rerun after final prompt changes.
- [ ] Agent published with final prompt; exact version noted.
- [ ] Demo link tested from a logged-out/incognito session.
- [ ] Recording links open without access requests.
- [ ] Customer details anonymized.
- [ ] No API keys or secrets included.
