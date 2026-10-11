# Home Credit LAP AI Voice Agent

A Bolna-based AI voice-agent prototype for the SalesAgents AI Intern — Prompt Engineer assessment. The agent conducts a preliminary eligibility conversation for Home Credit's pre-approved Loan Against Property (LAP) offer of up to **₹75,00,000 (₹75 lakh)**.

> **Scope:** This is a preliminary qualification assistant, not a loan-approval system. Final approval and exact loan terms remain with the lender or senior loan expert.

## Objectives

- Verify the customer's identity before revealing offer details.
- Explain the LAP offer and ask whether the customer wants to continue.
- Collect all seven required checklist items, including occupation and income mode.
- Remember information provided out of order and avoid unnecessary repeated questions.
- Apply disqualification rules only when an explicit stated criterion fails.
- Route property-loan transfer and EMI-reduction cases away from the fresh-loan flow.
- Avoid inventing interest rates, fees, minimum property values, or approval guarantees.
- Confirm initial eligibility only after all required fields are complete and the eligibility checks pass.

## Eligibility checklist

| # | Item | Rule |
|---|---|---|
| 1 | Property type | Residential, commercial, and industrial are eligible; agricultural property is not eligible. |
| 2 | Ownership | Sole and joint ownership are both eligible. |
| 3 | Original property documents | Original documents must be available for verification. |
| 4 | Desired loan amount | Maximum ₹75 lakh. If the customer requests more, explain the limit and ask whether they will proceed at ₹75 lakh. |
| 5 | Occupation and income mode | Salaried and self-employed applicants are eligible; income must be received through a bank. Cash-only income is ineligible. |
| 6 | Estimated market value | Capture the customer's estimate. The assignment does not specify a minimum valuation. |
| 7 | Tenure | Three to fifteen years inclusive. Tenures outside this range are ineligible. |

## Test evidence

Detailed transcripts and notes are in [`docs/test-evidence.md`](docs/test-evidence.md). The statuses below are based on the transcript evidence reviewed so far. A call finishing normally does not automatically mean the test passed.

| Assignment Test ID | Scenario | Recording | Transcript / review | Result |
|---|---|---|---|---|
| TC-01 | Fully eligible customer | [Recording](https://api.bolna.ai/recordings/call/e41ae2e7-99de-434e-94da-ab3954645716) | [Transcript and review](docs/test-evidence.md#tc-01-transcript) | **FAIL** — the agent treated “Hello” as identity confirmation and asked about accepting the ₹75 lakh cap after a ₹50 lakh request. |
| TC-02 | Agricultural property | [Recording](https://api.bolna.ai/recordings/call/2af6811d-778d-46e5-9a19-6bbafb4d9db1) | [Transcript and review](docs/test-evidence.md#tc-02-transcript) | **PASS** |
| TC-03 | Cash income | [Recording](https://api.bolna.ai/recordings/call/42166302-55da-4de1-9f11-65c2b8bf02d9) | [Transcript and review](docs/test-evidence.md#tc-03-transcript) | **PASS** |
| TC-07 | Amount above ₹75 lakh | [Recording](https://api.bolna.ai/recordings/call/3342066e-f151-4f01-b897-38fe3cc48592) | [Transcript and review](docs/test-evidence.md#tc-07-transcript) | **NEEDS REVIEW** — confirm the customer's acceptance from audio because the transcript says “seventy five rupees.” |
| TC-10 | Existing property loan | Not tested yet | Not tested yet | **NOT TESTED** |
| TC-12 | Busy customer | [Recording](https://api.bolna.ai/recordings/call/7c6699ff-e467-44fa-a2aa-fff2cb0b7196) | [Transcript and review](docs/test-evidence.md#tc-06-transcript) | **PASS** |
| TC-13 | Out-of-order information | [Recording](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript and review](docs/test-evidence.md#tc-07-transcript) | **PASS** |
| TC-22 | Missing item before handoff | [Same recording as TC-13](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript and review](docs/test-evidence.md#tc-07-transcript) | **PASS** — the agent did not confirm eligibility when property market value was missing. |

## Platform and configuration

- **Voice-agent platform:** Bolna.
- **Voice and transcription services:** ElevenLabs and Deepgram, as configured in Bolna.
- **Baseline test language:** English was configured for the initial test, but the agent switched to Hindi after the user spoke Hindi. Verify language-mode behavior before claiming strict English-only control.
- **External actions:** Callback scheduling, live transfer, CRM updates, and do-not-contact persistence must not be claimed as completed unless the configured workflow confirms them.

## Repository contents

- `prompts/system-prompt-v4.txt` — include the exact prompt version that was used for each linked call.
- `tests/essential-test-cases.md` — test scripts and expected behavior.
- `docs/test-evidence.md` — detailed transcripts and observed results.

## Privacy and evidence handling

- Use synthetic customer details for demos wherever possible.
- Redact personal phone numbers and sensitive financial information before making evidence public.
- Never commit API keys, access tokens, provider credentials, or private environment files.
- Verify each recording link is accessible to the reviewer, or follow the recruiter's approved alternative.
- Keep the exact system prompt version associated with each test run.

## Limitations

This prototype provides preliminary qualification only. It is not a production lending system and does not determine final approval. Any callback, transfer, opt-out, or CRM action depends on a verified integration.
