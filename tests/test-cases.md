# Test Plan — Home Credit LAP Voice Agent

## How to use this plan

Run each scenario through the configured voice agent. Speak naturally; do not only read one-word answers. Review both the recording and transcript. Mark a scenario **PASS** only when the observed behavior matches the expected behavior. Record defects and rerun after prompt changes.

## Core scenarios

### TC-01 — Fully eligible customer
**Customer inputs:** Verified identity; residential property; sole owner; original documents available; requests ₹50 lakh; salaried; income received in bank; estimated market value ₹1 crore; tenure 10 years; no existing property loan or EMI-transfer intent.

**Expected:** Agent captures all seven checklist items, does not repeat answered questions, confirms preliminary qualification, says a senior loan expert will contact the customer to discuss next steps and exact interest rate, and ends politely.

### TC-02 — Agricultural property
**Customer input:** “It's agricultural land.”

**Expected:** Agent politely states that the customer does not meet the criteria for this specific offer and ends immediately without asking remaining eligibility questions.

### TC-03 — Cash income
**Customer input:** “I run my own business, and I receive the income in cash.”

**Expected:** Self-employed status is accepted, but cash income triggers immediate disqualification and call termination.

### TC-04 — Original documents unavailable
**Customer input:** “I only have photocopies. The original documents are not available.”

**Expected:** Agent disqualifies politely and ends without continuing the checklist.

### TC-05 — Tenure below minimum
**Customer input:** “I want to repay it in two years.”

**Expected:** Agent recognizes tenure below three years, explains that the tenure does not meet this offer's criteria, and ends.

### TC-06 — Tenure above maximum
**Customer input:** “I need twenty years to repay.”

**Expected:** Agent recognizes tenure above fifteen years, explains that the tenure does not meet this offer's criteria, and ends.

### TC-07 — Requested amount above limit; customer accepts alternative
**Customer input:** “I need ₹90 lakh.”

**Expected:** Agent explains the maximum is ₹75 lakh and asks if the customer wants to proceed with ₹75 lakh. If customer agrees, the stored requested amount becomes ₹75 lakh and the flow continues.

### TC-08 — Requested amount above limit; customer declines alternative
**Customer input:** “No, I need the full ₹90 lakh.”

**Expected:** Agent politely ends because the customer does not want to proceed with the offered maximum. It must not continue asking the remaining checklist questions.

### TC-09 — Joint ownership
**Customer input:** “The property is jointly owned by me and my brother.”

**Expected:** Agent records joint ownership as accepted and continues with the earliest unanswered checklist item.

### TC-10 — Existing property loan
**Customer input:** “I already have a loan against this property.”

**Expected:** Agent explains that a loan-transfer specialist will contact the customer and ends the call. It must not continue the fresh-loan checklist.

### TC-11 — EMI reduction request
**Customer input:** “I want to reduce my current EMI.”

**Expected:** Agent uses the loan-transfer specialist route and ends the call.

### TC-12 — Busy customer
**Customer input:** “I'm in a meeting right now.”

**Expected:** Agent acknowledges the situation, asks for a convenient callback time, captures the preference, and ends. It must not continue pitching or asking eligibility questions. A scheduled callback may be claimed only if the platform confirms it.

## State, language, and conversation robustness

### TC-13 — Out-of-order information
**Customer input:** “It's a residential house, jointly owned with my wife, and worth about ₹1.2 crore.”

**Expected:** Agent stores property type, ownership, and market value, then asks only the earliest unanswered checklist item.

### TC-14 — Multiple answers in one turn
**Customer input:** “It's my own residential house, the original papers are available, I need ₹40 lakh, and I'd prefer ten years.”

**Expected:** Agent captures property type, sole ownership, document availability, loan amount, and tenure. It must not ask those questions again.

### TC-15 — Ambiguous document answer
**Customer input:** “I think the papers are somewhere at home.”

**Expected:** Agent asks whether the original property documents are available for verification; it must not assume availability.

### TC-16 — Customer corrects an answer
**Customer input:** “It's a residential property—sorry, I meant agricultural land.”

**Expected:** If the correction is clear, the latest answer is used and the customer is immediately disqualified for this offer.

### TC-17 — Interest-rate question
**Customer input:** “What exact interest rate will I get?”

**Expected:** Agent does not invent a rate. It explains that a senior loan expert will provide the exact rate after preliminary qualification, then resumes at the earliest missing item.

### TC-18 — Wrong person
**Customer input:** “You have the wrong number. I'm not that person.”

**Expected:** Agent apologizes, reveals no further loan details, and ends.

### TC-19 — Customer declines
**Customer input:** “I'm not interested. Please don't continue.”

**Expected:** Agent acknowledges the decision and ends promptly.

### TC-20 — Unrelated question unsupported by context
**Customer input:** “Where is your nearest branch?” when no branch information exists in the supplied product context.

**Expected:** Agent does not invent an address. It briefly explains that it does not have that information and returns to the next missing question if the customer is still willing to continue.

### TC-21 — Bank income and self-employed
**Customer input:** “I'm self-employed, and all my business income is deposited into my bank account.”

**Expected:** Agent records self-employed and bank income as accepted, then continues.

### TC-22 — Missing checklist item at handoff
**Test setup:** Provide six checklist items that all pass, but never provide market value (or another single required item).

**Expected:** Agent asks for the missing item and does not perform final handoff until it is answered.

### TC-23 — Call interruption / adversarial rapid-fire question test
**Customer input:** Interruption while offer is read (*"wait wait wait wait what is the call about and why do you need this information"*), followed by repeated demands (*"explain again explain again..."*), and finally polite decline (*"okay but i'm not interested in this offer sorry"*).

**Expected:** Agent cleanly stops speech mid-turn, clarifies purpose without panic or hallucination, patiently answers inquiries, and ends politely when customer declines.

## Suggested adversarial follow-ups

- Interrupt the agent while it is asking a question and ask what the call is about.
- Give two or more eligibility facts in a single answer.
- Provide an answer, then clearly correct it.
- Ask for unsupported fees, interest rates, or a minimum property value.
- Give an unclear answer and check that the agent clarifies instead of guessing.
- Try to make the agent skip a question and go straight to the handoff.

## Evaluation rubric for each test

Score each dimension as Pass/Fail and add a transcript timestamp or short note:

1. Business-rule accuracy
2. Correct state capture
3. No unnecessary repeated questions
4. Correct next question
5. Correct terminal routing
6. Natural, concise speech
7. No fabricated product claims
8. Accurate representation of callback/handoff capabilities
