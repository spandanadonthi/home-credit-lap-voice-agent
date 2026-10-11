# Home Credit LAP AI Voice Agent

## Overview
A Retell AI voice agent for preliminary qualification of existing Home Credit customers interested in a Loan Against Property (LAP). It gathers eligibility information, applies assignment-defined rules, and refers qualifying customers to a senior expert. It does not approve or sanction loans.

## Eligibility rules
| Item | Rule |
|---|---|
| Property type | Residential, commercial, or industrial: continue. Agricultural: disqualify immediately. |
| Ownership | Sole or joint ownership are both acceptable. |
| Original property documents | Must be available; otherwise disqualify immediately. |
| Loan amount | Maximum ₹75 lakh. If the requested amount is higher, ask whether the customer accepts ₹75 lakh. Continue only after clear acceptance. |
| Occupation and income mode | Salaried or self-employed are acceptable. Bank-received income is acceptable; cash income disqualifies immediately. |
| Estimated market value | Record the customer's estimate. The assignment specifies no minimum value; do not invent one. |
| Tenure | 3–15 years inclusive. Outside this range: disqualify immediately. |

Existing property-loan, EMI-reduction, or transfer enquiries should be routed to the appropriate specialist instead of continuing the fresh-loan flow.

## Conversation flow
1. Greet the customer, verify who is speaking, and ask whether it is a convenient time.
2. If busy, ask for a preferred callback time and end politely.
3. Explain the potential offer of up to ₹75 lakh and ask permission to continue.
4. Gather all seven eligibility items, in any order.
5. Clarify ambiguous amounts or answers; remember clear answers and avoid unnecessary repetition.
6. Stop the fresh-loan flow immediately when a hard disqualifier is established.
7. Offer a senior-expert next step only when all seven items are complete and pass.
8. State that this is preliminary qualification, not guaranteed approval.

## Files
- `system-prompt.md`: prompt for the Retell agent.
- `test-cases.md`: scenarios and expected behavior.
- `test-results.md`: test log and observed development notes.

## Demo links
- Retell demo: [Add shareable published demo link]
- Screen recording: [Add shareable recording link]

## Limitations
The assignment does not specify minimum property value, interest rates, fees, or detailed underwriting rules. Do not invent these. Final eligibility and approval remain subject to lender review and verification. Test results should be supported by transcripts or recordings. Do not publish secrets or real customer personal data.

## Author
[Your Name]
