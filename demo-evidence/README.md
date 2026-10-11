# Demo Evidence

This folder is a template for evidence collected from real test runs. **No recordings or transcripts are included by default.** Add evidence only after you have configured and tested the agent.

## Recommended evidence index

Create or update a table like this after testing:

| Test ID | Scenario | Recording URL | Transcript URL | Result |
|---|---|---|---|---|
| TC-01 | Fully eligible customer | [Recording](https://api.bolna.ai/recordings/call/c507da24-4fc2-4e88-aff3-2d5846c4e5ee) | [Transcript](#tc-01-transcript) | Pass |
| TC-02 | Agricultural property | [Recording](https://api.bolna.ai/recordings/call/2af6811d-778d-46e5-9a19-6bbafb4d9db1) | [Transcript](#tc-02-transcript) | Pass |
| TC-03 | Cash income | [Recording](https://api.bolna.ai/recordings/call/42166302-55da-4de1-9f11-65c2b8bf02d9) | [Transcript](#tc-03-transcript) | Pass |
| TC-04 | Amount above ₹75 lakh | [Recording](https://api.bolna.ai/recordings/call/3342066e-f151-4f01-b897-38fe3cc48592) | [Transcript](#tc-04-transcript) | Pass |
| TC-05 | Existing property loan | Add actual share link | Add actual share link | Pass/Fail |
| TC-06 | Busy customer | [Recording](https://api.bolna.ai/recordings/call/7c6699ff-e467-44fa-a2aa-fff2cb0b7196) | [Transcript](#tc-06-transcript) | Pass |
| TC-07 | Out-of-order information | [Recording](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c) | [Transcript](#tc-07-transcript) | Pass |
| TC-08 | Missing item before handoff | Add actual share link | Add actual share link | Pass/Fail |

---

### TC-01 Transcript

**Scenario:** Fully eligible customer  
**Recording:** [https://api.bolna.ai/recordings/call/c507da24-4fc2-4e88-aff3-2d5846c4e5ee](https://api.bolna.ai/recordings/call/c507da24-4fc2-4e88-aff3-2d5846c4e5ee)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** yeah this is the customer  
> **Assistant:** Thank you for confirming. I’m calling from Home Credit about a pre-approved Loan Against Property offer of up to seventy-five lakh rupees, with a repayment tenure of three to fifteen years. Would you like to continue with a brief eligibility check?  
> **User:** yes i would like to continue with eligibility check  
> **Assistant:** Great! To start, what type of property would you like to use for the loan—residential, commercial, or industrial?  
> **User:** it's residential property  
> **Assistant:** Thank you. Is the property solely owned by you, or jointly owned with someone else?  
> **User:** it's jointly owned by my wife  
> **Assistant:** Are the original property ownership documents available for verification?  
> **User:** s the original documents are available  
> **Assistant:** Approximately how much would you like to borrow?  
> **User:** i need rupee like rupees  
> **Assistant:** Sorry, I didn’t catch that. Could you please tell me approximately how much you would like to borrow?  
> **User:** i need a fifty lakh rupees  
> **Assistant:** Thank you. Are you salaried or self-employed?  
> **User:** i'm saladed  
> **Assistant:** Sorry, I didn’t catch that. Are you salaried, or do you run your own business?  
> **User:** i'm celery  
> **Assistant:** Thank you for clarifying. Is your income received through a bank account, or is it paid in cash?  
> **User:** my salary is deposited into my bank account  
> **Assistant:** What is the approximate current market value of the property?  
> **User:** it's worth around eighty lakh rupees  
> **Assistant:** How many years would you prefer for repayment? The eligible range is three to fifteen years.  
> **User:** ten yes  
> **Assistant:** Based on the information you shared, you meet the initial criteria for this Loan Against Property offer. A senior loan expert will follow up to explain the applicable interest rate and next steps. This is an initial eligibility check, not final loan approval. Thank you for your time. Have a great day!

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Identity confirmed before offer | Confirm identity first | User explicitly confirmed "yeah this is the customer" before offer details | ✅ |
| Offer introduction & consent | Introduce LAP offer & ask consent | Stated up to ₹75L offer, 3-15 years tenure, customer consented to proceed | ✅ |
| Property type collected (residential/commercial/industrial) | Collect eligible type | Collected: residential — eligible | ✅ |
| Sole vs joint ownership | Ask ownership | Collected: jointly owned with wife — eligible | ✅ |
| Original documents available | Ask about documents | Collected: original documents available — eligible | ✅ |
| Loan amount ≤ ₹75 lakh | Capture requested loan amount | Clarified and collected: ₹50 lakh (within limit) | ✅ |
| Occupation & income mode | Salaried/self-employed, bank income | Clarified speech noise ("saladed", "celery" -> salaried), confirmed salary deposited into bank account | ✅ |
| Property market value | Capture estimate | Collected: ₹80 lakh | ✅ |
| Tenure 3–15 years | Within range | Collected: 10 years ("ten yes") — within range | ✅ |
| Handoff to senior loan expert | Mention follow-up | Agent stated a senior loan expert will follow up | ✅ |
| Disclaimer: not final approval | Must clarify | Agent stated "This is an initial eligibility check, not final loan approval." | ✅ |

---

### TC-02 Transcript

**Scenario:** Agricultural property  
**Recording:** [https://api.bolna.ai/recordings/call/2af6811d-778d-46e5-9a19-6bbafb4d9db1](https://api.bolna.ai/recordings/call/2af6811d-778d-46e5-9a19-6bbafb4d9db1)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** Yes  
> **User:** This is the test customer  
> **Assistant:** Thank you for confirming. I'm calling from Home Credit about a pre-approved Loan Against Property offer of up to seventy-five lakh rupees, with a repayment tenure of three to fifteen years. Would you like to continue with a brief eligibility check?  
> **User:** Yes I would like to continue  
> **Assistant:** Great! To start, what type of property would you like to use for the loan—residential, commercial, or industrial?  
> **User:** It is agricultural land  
> **Assistant:** Thank you for sharing that. Based on this detail, you do not meet the criteria for this specific offer at this time. Thank you for your time.

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Identity confirmed before offer | Confirm identity first | User confirmed identity before offer was revealed | ✅ |
| Property type collected | Ask property type | Agent asked for property type | ✅ |
| Agricultural land rejected | Agricultural = ineligible | User said "agricultural land", agent correctly rejected | ✅ |
| Polite rejection | End call gracefully | Agent thanked and ended politely | ✅ |
| No further questions after rejection | Stop collecting info | Agent did not ask further eligibility questions | ✅ |

---

### TC-03 Transcript

**Scenario:** Cash income  
**Recording:** [https://api.bolna.ai/recordings/call/42166302-55da-4de1-9f11-65c2b8bf02d9](https://api.bolna.ai/recordings/call/42166302-55da-4de1-9f11-65c2b8bf02d9)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** Hello  
> **Assistant:** Sorry, I just need to confirm—am I speaking with Test Customer?  
> **User:** Yes  
> **User:** I'm just customer  
> **Assistant:** Thank you for confirming. I'm calling from Home Credit about a pre-approved Loan Against Property offer of up to seventy-five lakh rupees, with a repayment tenure of three to fifteen years. Would you like to continue with a brief eligibility check?  
> **User:** Yes I would like to continue  
> **Assistant:** Great! To start, what type of property would you like to use for the loan—residential, commercial, or industrial?  
> **User:** Residential  
> **Assistant:** Thank you. Is the property solely owned by you, or jointly owned with someone else?  
> **User:** It's only one by me  
> **Assistant:** Are the original property ownership documents available for verification?  
> **User:** Yes the original documents are available  
> **Assistant:** Approximately how much would you like to borrow?  
> **User:** I need forty lakh rupees  
> **Assistant:** Thank you. Are you salaried or self-employed?  
> **User:** I'm self reliant I'm ratio all my incoming cash  
> **Assistant:** Sorry, I didn't catch that clearly. Are you salaried, or do you run your own business?  
> **User:** I'm self employed  
> **Assistant:** Is your income received through a bank account, or is it paid in cash?  
> **User:** I receive all my income in cash  
> **Assistant:** Thank you for sharing that. Based on this detail, you do not meet the criteria for this specific offer at this time. Thank you for your time.

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Identity confirmed before offer | Confirm identity first | Agent re-confirmed identity before proceeding | ✅ |
| Property type collected | Eligible type | Collected: Residential — eligible | ✅ |
| Sole vs joint ownership | Ask ownership | Collected: Sole ownership | ✅ |
| Original documents available | Ask about documents | Collected: Yes | ✅ |
| Loan amount ≤ ₹75 lakh | Max ₹75 lakh | Collected: ₹40 lakh — within limit | ✅ |
| Occupation collected | Salaried/self-employed | Collected: Self-employed | ✅ |
| Cash income rejected | Cash-only = ineligible | User said "all my income in cash", agent correctly rejected | ✅ |
| Polite rejection | End call gracefully | Agent thanked and ended politely | ✅ |
| No further questions after rejection | Stop collecting info | Agent did not ask further eligibility questions | ✅ |

---

### TC-04 Transcript

**Scenario:** Amount above ₹75 lakh  
**Recording:** [https://api.bolna.ai/recordings/call/3342066e-f151-4f01-b897-38fe3cc48592](https://api.bolna.ai/recordings/call/3342066e-f151-4f01-b897-38fe3cc48592)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** Yes I'm test customer  
> **Assistant:** Thank you for confirming. I'm calling from Home Credit about a pre-approved Loan Against Property offer of up to seventy-five lakh rupees, with a repayment tenure of three to fifteen years. Would you like to continue with a brief eligibility check?  
> **User:** Yes I would like to continue  
> **Assistant:** Great! To start, what type of property would you like to use for the loan—residential, commercial, or industrial?  
> **User:** An accident  
> **Assistant:** Sorry, I didn't catch that. What type of property would you like to use for the loan—residential, commercial, or industrial?  
> **User:** It's residential  
> **Assistant:** Thank you. Is the property solely owned by you, or jointly owned with someone else?  
> **User:** Yes it's only on my meat  
> **Assistant:** Just to clarify, is the property solely owned by you, or is it jointly owned with someone else?  
> **User:** Yes it's totally owned by me  
> **Assistant:** Thank you. Are the original property ownership documents available for verification?  
> **User:** Yes the original documents are available  
> **Assistant:** Approximately how much would you like to borrow?  
> **User:** I need ninety lakh rupees  
> **Assistant:** The offer is limited to seventy-five lakh rupees. Would you like to proceed with the loan amount of seventy-five lakh rupees?  
> **User:** Yes I can proceed with seventy five rupees  
> **Assistant:** Thank you. Are you salaried or self-employed?  
> **User:** I'm calorator  
> **Assistant:** Sorry, I didn't catch that. Are you salaried, or do you run your own business?  
> **User:** I'm salaried  
> **Assistant:** Is your income received through a bank account, or is it paid in cash?  
> **User:** Yes my salary is deposited into my bank account  
> **Assistant:** What is the approximate current market value of the property?  
> **User:** It's around one crore rupee  
> **Assistant:** How many years would you prefer for repayment? The eligible range is three to fifteen years.  
> **User:** It's  
> **Assistant:** Sorry, I didn't catch that. How many years would you prefer for repayment? The eligible range is three to fifteen years.  
> **User:** Ten yes  
> **Assistant:** Based on the information you shared, you meet the initial criteria for this Loan Against Property offer. A senior loan expert will follow up to explain the applicable interest rate and next steps. This is an initial eligibility check, not final loan approval. Thank you for your time. Have a good day!

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Identity confirmed before offer | Confirm identity first | User confirmed identity before offer was revealed | ✅ |
| Property type collected | Eligible type | Collected: Residential — eligible | ✅ |
| Sole vs joint ownership | Ask ownership | Collected: Sole ownership (agent re-clarified unclear response) | ✅ |
| Original documents available | Ask about documents | Collected: Yes | ✅ |
| Amount above ₹75 lakh handled | Explain cap, ask to proceed at ₹75L | User requested ₹90L, agent explained cap of ₹75L and asked if user wants to proceed | ✅ |
| Occupation & income mode | Salaried/self-employed, bank income | Collected: Salaried, salary via bank account | ✅ |
| Property market value | Capture estimate | Collected: ₹1 crore | ✅ |
| Tenure 3–15 years | Within range | Collected: 10 years — within range | ✅ |
| Unclear speech handling | Re-ask politely | Agent re-asked when input was unclear ("an accident", "calorator") | ✅ |
| Handoff to senior loan expert | Mention follow-up | Agent stated a senior loan expert will follow up | ✅ |
| Disclaimer: not final approval | Must clarify | Agent stated "This is an initial eligibility check, not final loan approval" | ✅ |

---

### TC-06 Transcript

**Scenario:** Busy customer  
**Recording:** [https://api.bolna.ai/recordings/call/7c6699ff-e467-44fa-a2aa-fff2cb0b7196](https://api.bolna.ai/recordings/call/7c6699ff-e467-44fa-a2aa-fff2cb0b7196)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** I'm test customer but I am busy right now please call me tomorrow at eleven in the morning  
> **Assistant:** I understand you're busy right now. Just to confirm, would you like me to call you tomorrow at 11 AM?  
> **User:** Yes  
> **Assistant:** Thank you for sharing your preferred callback time. I will note that you would like to be called tomorrow at 11 AM. Thank you for your time. Have a good day.

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Customer says busy | Acknowledge and ask for callback time | Agent acknowledged customer is busy | ✅ |
| Callback date and time captured | Ask for preferred callback date/time | Captured: Tomorrow at 11 AM | ✅ |
| Confirmed callback time | Confirm back to customer | Agent confirmed "tomorrow at 11 AM" | ✅ |
| No false claim of scheduling | Do not claim callback is scheduled unless workflow confirms | Agent said "I will note that" — did not claim callback was scheduled | ✅ |
| Offer not revealed | Do not proceed with eligibility | Agent did not reveal offer details or start eligibility check | ✅ |
| Polite closure | End call gracefully | Agent thanked and wished a good day | ✅ |

---

### TC-07 Transcript

**Scenario:** Out-of-order information  
**Recording:** [https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c](https://api.bolna.ai/recordings/call/cefb8b92-6772-4d72-b5d3-7d28664dfa5c)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** Yeah this is it test customer  
> **Assistant:** Thank you for confirming. I'm calling from Home Credit about a pre-approved Loan Against Property offer of up to seventy-five lakh rupees, with a repayment tenure of three to fifteen years. Would you like to continue with a brief eligibility check?  
> **User:** Yes my property is I'm self employed my income goes into my bank account the original documents are available I want to forty lakh rupees and I will prefer a ten year dollar the property is only owned  
> **Assistant:** Thank you for sharing that information. To make sure I have everything correctly, co  
> **User:** I just said  
> **Assistant:** Thank you for sharing those detail  
> **User:** It's it's it's it's it's it's  
> **Assistant:** To proceed, could you please confirm the type of property you would like to use for the loan—residential, commercial, or industrial?  
> **User:** It's residential and I am self employed my income goes my bank account the order and documents are available I want forty lakh rupees nine will prefer ten year tenure the property is only owned  
> **Assistant:** Thank you for confirming those details. To summarize: your property is residential, solely owned by you, original documents are available, you want to borrow forty lakh rupees, you are self-employed with income received through your bank account, and you prefer a ten-year repayment tenure. Also, may I ask what is the approximate current market value of the property?  
> **User:** I don't know the approximate approximate market value  
> **Assistant:** I understand. Could you please provide a rough estimate or a range for the current market  
> **User:** I still can't provide  
> **Assistant:** I understand. I'm unable to complete the preliminary eligibility check without that detail. Thank you for your time.

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Identity confirmed before offer | Confirm identity first | User confirmed identity before offer was revealed | ✅ |
| Out-of-order info handled | Accept and organize jumbled info | Agent accepted bulk info and summarized it back correctly | ✅ |
| Missing field identified | Identify any missing required fields | Agent identified missing property market value | ✅ |
| Summary provided | Confirm all captured details | Agent summarized: residential, sole ownership, docs available, ₹40L, self-employed, bank income, 10-year tenure | ✅ |
| Property type confirmed | Ask to confirm type | Agent specifically asked to confirm property type (residential/commercial/industrial) | ✅ |
| Graceful handling of unclear input | Re-ask or clarify | Agent handled repeated/unclear user input patiently | ✅ |
| Unable to proceed without required info | End if mandatory field missing | Agent ended call when property market value could not be provided | ✅ |
| Polite closure | End call gracefully | Agent thanked for their time | ✅ |

## Evidence rules

- Use links generated by the voice platform or a permitted storage service; do not invent URLs.
- Verify that the reviewer can open each link without requesting access.
- Use synthetic/test customer details wherever possible.
- Remove or redact phone numbers, real customer names, account details, and other personal or financial information before making evidence public.
- Do not commit API keys, access tokens, provider credentials, or raw environment files.
- If recordings cannot be shared publicly, follow the recruiter's approved alternative.
- Keep the exact system prompt version used for each test run.
