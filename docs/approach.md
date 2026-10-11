# Approach and Design Notes

## 1. Problem framing

The agent conducts a preliminary Loan Against Property qualification conversation. It is not the final underwriter and must not guarantee approval or provide an invented interest rate.

## 2. State-first conversation design

For every customer turn, the intended control sequence is:

1. Extract all clear facts from the utterance.
2. Update the qualification state, including out-of-order facts and clear corrections.
3. Check loan-transfer intent.
4. Check mandatory disqualifying criteria.
5. Answer supported diversions briefly.
6. Ask the earliest unanswered checklist item.
7. Handoff only when all seven items are answered and every applicable criterion passes.

## 3. Why state tracking matters

A rigid question-by-question script can repeat questions when the customer volunteers multiple facts. Tracking each required field allows the agent to retain known facts and continue with the first missing item.

## 4. Known decision branches

- Wrong person → apologize without revealing offer details → end.
- Busy customer → ask preferred callback time → capture preference → end.
- Existing property loan or EMI-reduction request → loan-transfer specialist message → end.
- Agricultural property, unavailable original documents, cash income, or invalid tenure → polite disqualification → end.
- Requested amount above ₹75 lakh → offer the ₹75 lakh maximum; continue only if customer accepts.
- All seven items complete and criteria pass → preliminary qualification message and senior expert callback expectation.

## 5. Assumptions and limits

- No minimum market-value threshold is specified in the assignment.
- Exact interest rates are to be provided by the senior loan expert.
- Automatic callback scheduling and live human transfer are platform capabilities, not guaranteed by prompt text alone.
- The agent should only claim an action occurred if the platform confirms it.
- The configured voice platform may use a different variable interpolation syntax; verify before running tests.

## 6. Iteration process

Run the test plan, inspect recordings and transcripts, log failures in the CSV, update the prompt, and rerun the failed scenario plus relevant regression tests. Never label a scenario as passed without observed evidence.
