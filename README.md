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

| Test ID | Scenario | Recording | Transcript / Review | Result |
|---|---|---|---|---|
| TC-01 | Fully eligible customer | [Recording](https://api.bolna.ai/recordings/call/c507da24-4fc2-4e88-aff3-2d5846c4e5ee) | [Transcript](docs/test-evidence.md#tc-01-transcript) | **PASS** |
| TC-02 | Agricultural property | [Recording](https://api.bolna.ai/recordings/call/2af6811d-778d-46e5-9a19-6bbafb4d9db1) | [Transcript](docs/test-evidence.md#tc-02-transcript) | **PASS** |
| TC-03 | Cash income | [Recording](https://api.bolna.ai/recordings/call/42166302-55da-4de1-9f11-65c2b8bf02d9) | [Transcript](docs/test-evidence.md#tc-03-transcript) | **PASS** |
| TC-04 | Original documents unavailable | [Recording](https://api.bolna.ai/recordings/call/d3d96933-c500-4919-8fe7-94cf3afaf274) | [Transcript](docs/test-evidence.md#tc-04-transcript) | **PASS** |
| TC-05 | Tenure below 3 years | [Recording](https://api.bolna.ai/recordings/call/ab049189-e53e-427d-b3ad-8646a08200e0) | [Transcript](docs/test-evidence.md#tc-05-transcript) | **PASS** |
| TC-06 | Tenure above 15 years | [Recording](https://api.bolna.ai/recordings/call/76beb574-1d2b-4448-9694-261cb90f852b) | [Transcript](docs/test-evidence.md#tc-06-transcript) | **PASS** |
| TC-07 | Amount above ₹75 lakh | [Recording](https://api.bolna.ai/recordings/call/3342066e-f151-4f01-b897-38fe3cc48592) | [Transcript](docs/test-evidence.md#tc-07-transcript) | **PASS** |
| TC-08 | Amount above limit & customer declines | [Recording](https://api.bolna.ai/recordings/call/97fd70e0-ceb4-48c9-9253-243f68ad15bf) | [Transcript](docs/test-evidence.md#tc-08-transcript) | **PASS** |
| TC-09 | Joint ownership | [Same recording as TC-01](https://api.bolna.ai/recordings/call/c507da24-4fc2-4e88-aff3-2d5846c4e5ee) | [Transcript](docs/test-evidence.md#tc-01-transcript) | **PASS** |
| TC-10 | Existing property loan | [Recording](https://api.bolna.ai/recordings/call/10350bed-c5fc-4005-bd4a-eeeef7fcde00) | [Transcript](docs/test-evidence.md#tc-10-transcript) | **PASS** |
| TC-11 | EMI reduction request | [Recording](https://api.bolna.ai/recordings/call/10350bed-c5fc-4005-bd4a-eeeef7fcde00) | [Transcript](docs/test-evidence.md#tc-10-transcript) | **PASS** |
| TC-12 | Busy customer | [Recording](https://api.bolna.ai/recordings/call/7c6699ff-e467-44fa-a2aa-fff2cb0b7196) | [Transcript](docs/test-evidence.md#tc-12-transcript) | **PASS** |
| TC-13 | Out-of-order information | [Recording](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript](docs/test-evidence.md#tc-13-transcript) | **PASS** |
| TC-14 | Multiple answers in one turn | [Same recording as TC-13](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript](docs/test-evidence.md#tc-13-transcript) | **PASS** |
| TC-15 | Ambiguous document answer | [Recording](https://api.bolna.ai/recordings/call/1465aec0-6c98-4801-a57a-d73ad6b74280) | [Transcript](docs/test-evidence.md#tc-15-transcript) | **PASS** |
| TC-16 | Customer correction | [Recording](https://api.bolna.ai/recordings/call/247e8788-dc01-403c-8410-69bf80a48400) | [Transcript](docs/test-evidence.md#tc-16-transcript) | **PASS** |
| TC-17 | Interest-rate inquiry | [Recording](https://api.bolna.ai/recordings/call/a1aa28fb-2d30-4b80-aed3-d37581e537d2) | [Transcript](docs/test-evidence.md#tc-17-transcript) | **PASS** |
| TC-18 | Wrong person reached | [Recording](https://api.bolna.ai/recordings/call/6db43621-d4af-4eaa-9b6d-808b1823ec41) | [Transcript](docs/test-evidence.md#tc-18-transcript) | **PASS** |
| TC-19 | Customer declines offer | [Recording](https://api.bolna.ai/recordings/call/28209702-17da-41e0-9f0b-75e56c0ffc85) | [Transcript](docs/test-evidence.md#tc-19-transcript) | **PASS** |
| TC-20 | Unrelated question unsupported | [Recording](https://api.bolna.ai/recordings/call/25127b12-f2a3-4452-af53-d82c22aa753f) | [Transcript](docs/test-evidence.md#tc-20-transcript) | **PASS** |
| TC-21 | Self-employed with bank income | [Same recording as TC-13](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript](docs/test-evidence.md#tc-13-transcript) | **PASS** |
| TC-22 | Missing item before handoff | [Same recording as TC-13](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript](docs/test-evidence.md#tc-13-transcript) | **PASS** |
| TC-23 | Call interrupt / adversarial test | — | — | **NOT TESTED** |

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
