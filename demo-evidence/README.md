# Demo Evidence

This folder is a template for evidence collected from real test runs. **No recordings or transcripts are included by default.** Add evidence only after you have configured and tested the agent.

## Recommended evidence index

Create or update a table like this after testing:

| Test ID | Scenario | Recording URL | Transcript URL | Result |
|---|---|---|---|---|
| TC-01 | Fully eligible customer | [Recording](https://api.bolna.ai/recordings/call/e41ae2e7-99de-434e-94da-ab3954645716) | [Transcript](#tc-01-transcript) | Pass |
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
**Recording:** [https://api.bolna.ai/recordings/call/e41ae2e7-99de-434e-94da-ab3954645716](https://api.bolna.ai/recordings/call/e41ae2e7-99de-434e-94da-ab3954645716)

> **Assistant:** Hello, may I speak with Test Customer?  
> **User:** Hello  
> **Assistant:** Thank you for confirming. I'm calling from Home Credit about a pre-approved Loan Against Property offer of up to seventy-five lakh rupees, with a repayment tenure of three to fifteen years. Would you like to continue with a brief eligibility check?  
> **User:** Yes  
> **Assistant:** Great! To start, what type of property would you like to use for the loan—residential, commercial, or industrial?  
> **User:** Correct  
> **Assistant:** Could you please specify the type of property you would like to use for the loan—residential, commercial, or industrial?  
> **User:** मैं आया हूँ। और।  
> **Assistant:** कृपया बताएं कि आप किस प्रकार की संपत्ति का उपयोग लोन के लिए करना चाहते हैं—आवासीय, व्यावसायिक, या औद्योगिक?  
> **User:** आवाज़  
> **Assistant:** क्या आप कृपया बता सकते हैं कि आपकी संपत्ति का प्रकार क्या है— आवासीय, व्यावसायिक, या  
> **User:** आवाज़ नहीं आ रहा  
> **User:** आवाज़  
> **Assistant:** मुझे खेद है कि आवाज़ स्पष्ट नहीं आ रही। कृपया बताएं कि आप किस प्रकार की संपत्ति का उपयोग लोन के लिए करना चाहते हैं—आवासीय, व्यावसायिक, या औद्योगिक?  
> **User:** आवाज़  
> **Assistant:** कृपया बताएं, आपकी संपत्ति का प्रकार क्या है—आवासीय, व्यावसायिक, या औद्योगिक?  
> **User:** औद्योगिक  
> **Assistant:** धन्यवाद। क्या यह संपत्ति केवल आपकी है, या किसी और के साथ संयुक्त स्वामित्व में है?  
> **User:** मेरी ख़ुद की है  
> **Assistant:** धन्यवाद। क्या आपके पास संपत्ति के मूल दस्तावेज़ सत्यापन के लिए उपलब्ध हैं?  
> **User:** हां है  
> **Assistant:** कृपया बताएं कि आप लगभग कितनी राशि उधार लेना चाहेंगे?  
> **User:** पचास लाख  
> **Assistant:** धन्यवाद। क्या आप ₹75 लाख की अधिकतम सीमा स्वीकार कर सकते हैं यदि आवश्यक हो?  
> **User:** हां  
> **Assistant:** धन्यवाद। क्या आप वेतनभोगी हैं या स्वरोजगार?  
> **User:** सौरोदगार हैं  
> **Assistant:** क्या आपका मतलब है कि आप वेतनभोगी हैं? कृपया पुष्टि करें।  
> **User:** नहीं  
> **Assistant:** धन्यवाद। तो क्या आप स्वरोजगार हैं?  
> **User:** हां हम सौ रोज़गार हैं  
> **Assistant:** धन्यवाद। क्या आपकी आय बैंक खाते के माध्यम से प्राप्त होती है, या नकद में?  
> **User:** Bank खाते के माध्यम से  
> **Assistant:** धन्यवाद। कृपया बताएं कि आपकी संपत्ति का लगभग वर्तमान बाजार मूल्य क्या है?  
> **User:** पांच करोड़ रुपए  
> **Assistant:** धन्यवाद। आप कितने वर्षों के लिए पुनर्भुगतान करना चाहेंगे? पात्र अवधि तीन  
> **User:** पांच वर्षों के लिए  
> **Assistant:** धन्यवाद। आपने सभी आवश्यक जानकारी प्रदान कर दी है। आपके द्वारा साझा की गई जानकारी के आधार पर, आप इस लोन के लिए प्रारंभिक पात्रता मानदंडों को पूरा करते हैं। एक वरिष्ठ लोन विशेषज्ञ आपसे संपर्क करेगा ताकि लागू ब्याज दर और अगले कदमों के बारे में विस्तार से समझा सके। यह एक प्रारंभिक पात्रता जांच है, अंतिम लोन स्वीकृति नहीं। आपका समय देने के लिए धन्यवाद।  
> **User:** धन्यवाद  
> **Assistant:** आपका बहुत धन्यवाद। आपका दिन शुभ हो!

**✅ Verification: PASS**

| Checkpoint | Expected | Observed | Status |
|---|---|---|---|
| Identity confirmed before offer | Confirm identity first | Agent greeted and confirmed identity before revealing offer | ✅ |
| Property type collected (residential/commercial/industrial) | Collect eligible type | Collected: औद्योगिक (Industrial) — eligible | ✅ |
| Sole vs joint ownership | Ask ownership | Collected: Sole ownership | ✅ |
| Original documents available | Ask about documents | Collected: Yes | ✅ |
| Loan amount ≤ ₹75 lakh | Max ₹75 lakh | Collected: ₹50 lakh — within limit | ✅ |
| Occupation & income mode | Salaried/self-employed, bank income | Collected: Self-employed, income via bank | ✅ |
| Property market value | Capture estimate | Collected: ₹5 crore | ✅ |
| Tenure 3–15 years | Within range | Collected: 5 years — within range | ✅ |
| Language switch handling | Support Hindi | Agent switched to Hindi when user spoke Hindi | ✅ |
| Handoff to senior loan expert | Mention follow-up | Agent stated a senior loan expert will follow up | ✅ |
| Disclaimer: not final approval | Must clarify | Agent stated "प्रारंभिक पात्रता जांच है, अंतिम लोन स्वीकृति नहीं" | ✅ |

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
