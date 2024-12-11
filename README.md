# Prompting-Handbook
Choosing the Right Prompt for Testing Agents is a very important step while testing an AI agent’s response. This document shares a list of prompts that can be used to validate a genai agent reponse in telcom cx setup

# Below are few common prompting methods that are generally followed:

1.    Zero/Few-ShotPrompting: Use when testing basic behavior without a need for multipleinputs. 

2.    Instruction-BasedPrompting: Use to directly validate whether the agent can handle clear,single-step requests. 

3.    Chain-of-ThoughtPrompting: Use to ensure the agent performs multi-step tasks with clear,logical reasoning. 

4.    ContextualPrompting: Essential for conversational agents to test if the agent retainsand uses prior information from the conversation.  

5.    Role-BasedPrompting: Use to validate how well the agent adapts its tone or languagebased on the user’s role (e.g., casual user vs. business client).

By combining these prompting types, we can test a wide range of use cases andscenarios, ensuring that the agent behaves appropriately and can handledifferent complexities effectively.

Here are three sample prompts for each type of prompting type, tailored specifically for a telcom based  GenAI agent handling custom queries:

# 1. Zero-Shot Prompting:
Prompt 1: “What’s the status of my claim for mybroken phone?”·

Prompt 2: “Can I add my tablet to my protectionplan?”·

Prompt 3: “How do I file a claim for a lostdevice?”

Expected Behavior: The agent should respond with answers without needing prior examples, likeproviding claim status or steps to file a claim.

# 2. One-Shot Prompting:·     
Prompt 1: “Last time I asked about my claim, youprovided an update. Now, give me an update for claim #12345.”·  

Prompt 2: “You helped me add my phone before.Can you add my laptop to the protection plan as well?”·  

Prompt 3: “You helped me remove a device before.Now, I need to remove my old tablet from the protection plan.”

Expected Behavior: The agent should understand the context from the previous examples and generalizeto the new task.3. 

# 3.Few-Shot (K-Shot) Prompting:
Prompt 1:·      

“Claim: ‘I dropped my phone, and the screen iscracked.’   

Outcome: ‘The claim was approved.’”·      

“Claim: ‘My tablet stopped charging, and I needa replacement.’ 

Outcome: ‘The claim is pending.’”·   

“Now, update me on the status of my claim for abroken laptop.”

Prompt 2:·     

“Device: ‘iPhone 12’ was added to the protectionplan.”·      

“Device: ‘Samsung Galaxy S21’ was added to theprotection plan.”·       

“Now, can you add my Apple Watch to theprotection plan?”

Prompt 3:·      

“Policy: ‘The protection plan covers accidentaldamage.’”·      

“Policy: ‘The protection plan covers lost orstolen devices.’”·      

“Does my protection plan cover water damage?”

Expected Behavior: Theagent will use the provided examples to infer responses to the new prompts.

# 4. Instruction-Based Prompting

Prompt 1: “File a claim for my damaged phone.”·

Prompt 2: “Remove my old laptop from theprotection plan.”·

Prompt 3: “Add my new iPad to the insurance.”Expected Behavior: Theagent should follow the explicit instruction and perform the necessary action.

# 5. Chain-of-Thought Prompting·

Prompt 1: “My phone is damaged. First, check ifit’s covered by my protection plan, then guide me through filing a claim.”·

Prompt 2: “I lost my tablet. First, confirm thatmy device is registered under the protection plan, then tell me if I can file aclaim.”·

Prompt 3: “I want to add a device to myprotection plan. First, tell me how many devices are currently covered, thenlet me add a new device.”

Expected Behavior: Theagent will break down its response step by step, logically walking through theproblem.

# 6. Role-Based Prompting·

Prompt 1: “As an expert in device protection,can you explain the steps to file a claim?”·

Prompt 2: “As a claims specialist, can youprovide me with an overview of the protection coverage I have?”·

Prompt 3: “Act as a customer support agent andhelp me remove a device from my insurance policy.”

Expected Behavior: Theagent will take on the specific role and respond in a tone suitable for thatrole, e.g., expert, support agent, etc.

# 7. Contextual Prompting·

Prompt 1: “Last time, you helped me file a claimfor my phone. Now I want to check its status.”·

Prompt 2: “Earlier, we talked about adding adevice to my protection plan. Can you help me finalize that?”·

Prompt 3: “I spoke with you earlier aboutcanceling my protection plan. Can you confirm if it’s been canceled?”

Expected Behavior: Theagent will use the conversation history or previous context to answer thecurrent question.

# 8. Self-Correction Prompting·

Prompt 1: “You mentioned my claim was approved,but I haven’t received confirmation. Can you double-check that for me?”·

Prompt 2: “You said I can file a claim for waterdamage, but I thought my plan doesn’t cover that. Please verify.”·

Prompt 3: “You said my phone is protected, butit’s not showing in my account. Can you correct that?”

Expected Behavior: Theagent will evaluate its previous response, correct any errors, and give anupdated answer.

# 9. Multi-Task Prompting·

Prompt 1: “Can you check the status of my claimand also tell me how to file a new one for my tablet?”·

Prompt 2: “Can you add my laptop to theprotection plan and also remove my old phone from the insurance?”·

Prompt 3: “Tell me my claim status and thenprovide the details of my current protection coverage.

”Expected Behavior: The agent will perform multiple tasks within the same prompt.

# 10. Comparative Prompting·

Prompt 1: “Compare the coverage of my currentdevice protection plan with the premium plan.”·

Prompt 2: “What’s the difference between filinga claim for accidental damage versus lost or stolen devices?”·

Prompt 3: “How does my device protection for myphone compare to the coverage for my tablet?”

Expected Behavior: The agent will provide a comparison between two items, outlining key differences and similarities.

These examples provide a range ofprompt types for us to test the robustness and accuracy of the claims anddevice protection agent. Each prompt type encourages different behaviors fromthe agent, helping validate its performance in various scenarios.

# Prompts for Telcom-CX project specific scenarios
Below are some Project specificscenarios related prompts for testing the agent:

# 1. Fallback Scenario: Incomplete User Input:·

“Checkclaim status” (without providing a claim number)·

“What’sthe status of my last claim?” (vague query)·

“Find my claim” (without any context)·

“Show myclaim status from last month” (missing specific details)·

“Claim status”(just the term without additional info)

# 2. API Call Issue Scenario: API Timeout or Error:·

“Checkthe status of my claim” (force an API timeout to simulate failure)·

“What isthe protection plan for my device?” (trigger a scenario where the API fails)·

“File a claim” (simulate an API failuremid-action)·

“Removedevice protection” (test how the agent responds to API error)·

“Check myinsurance coverage” (simulate API downtime)

# 3. Scenario: Unavailable Insurance Plan:·

“Add protection for my smartwatch” (unsupporteddevice)·

“Can Iadd protection for my old phone?” (unsupported due to age)·

“I want to insure my non-standard device”(unsupported product category)·

“Why can’t I insure this tablet?” (unsupportedmodel)·

“Showinsurance options for this out-of-warranty phone” (unsupported warranty status)
  
# 4.Unrecognized User Intent:·

“Terminatemy protection plan” (use incorrect terminology)·      

“Getrid of my insurance” (vague, incorrect phrasing)·      

“Iwant to cancel coverage” (not the standard term)·      

“Deletedevice insurance” (wrong action term)·      

“Stopmy insurance” (non-standard phrasing)

# 5.User Requests Action Without Authorization:·      

“Removeprotection for this device” (simulate unauthorized removal)·      

“Cancelthis protection plan” (action not allowed by user role)·      

“Deleteinsurance without approval” (unauthorized action)·      

“Canyou end this coverage without permission?” (test agent’s restriction handling)·      

“Iwant to remove this plan” (no authority to execute)

# 6.Partial Data Provided for Claim Creation:·      

“Filea claim for my phone” (without providing required device details)·      

“Iwant to file a claim” (without device or incident info)·      

“Submita claim” (missing device identification)·      

“Filea claim, but I’m not sure what’s required” (lacking information)·      

“Startthe claim process” (vague, with missing key details) 

# 7.Conflicting Actions:·      

“Removemy old device and add a new one at the same time” (conflicting request)·      

“Adda phone and remove protection for my tablet” (simultaneous conflicting actions)·      

“Cancelthis device and replace it with another” (simultaneous removal and addition)·      

“Switchprotection from my phone to my tablet” (conflicting swap request)·      

“Removeand add protection for different devices” (dual, opposing actions)

# 8.User Confusion: Wrong Terminology:·      

“Terminatethe protection plan” (incorrect term for “remove”)·      

“Cancelmy device insurance” (confusing term for “remove protection”)·      

“Endmy protection” (ambiguous phrasing)·      

“Closethis insurance plan” (wrong term)·      

“Stopcoverage for this device” (vague or non-standard wording)

# 9.Repeated Attempts with the Same Error:·      

“Whycan’t I submit this claim?” (after multiple failed attempts)·      

“Filemy claim” (repeated submission with missing document)·      

“Whydo I keep getting an error on claim submission?” (after repeated failure)·      

“Tryfiling my claim again” (after multiple attempts with same error)·      

“Submitthe claim, even if it’s incomplete” (attempting to bypass error)

# 10.Multiple Choices: Selecting a Specific Action:·      

“Managemy account” (test agent’s ability to provide multiple options)·      

“Helpme with my insurance” (broad request to trigger a choice of actions)·      

“Whatare my account management options?” (prompt agent to offer choices)·      

“Showme what I can do with my protection plan” (general query with multiple paths)·      

“Helpme update my device insurance or check my claims” (test ability to handlemultiple options)

# 11.User Attempts to Perform Unauthorized Actions:·      

“Deletemy protection plan now” (without authorization)·      

“Removethis device from insurance without approval” (unauthorized attempt)·      

“Cancelinsurance without permission” (force unauthorized action)·      

“Endmy plan without logging in” (attempt to bypass authentication)·      

“Removethe device without an account” (simulate unauthorized action)

# 12.Outdated Device Information:·      

“Filea claim for my old phone” (outdated device not in system)·      

“Whycan’t I file a claim for my old device?” (test outdated data handling)·      

“Submita claim for this device that’s not listed” (missing device in system)·      

“Filea claim for a device I no longer use” (outdated info)·      

“Whyis my device not showing for the claim?” (missing device scenario)

# 13.User Requests Service for Unsupported Device:·      

“Addprotection for this unsupported phone” (unsupported device test)·      

“Whycan’t I insure my smartwatch?” (trigger unsupported product category)·      

“Protectthis old phone” (unsupported device model)·      

“Addinsurance for my non-standard device” (unsupported scenario)·      

“Whyisn’t this device eligible for protection?” (unsupported eligibility)

# 14.Multiple Devices in Account Confusion:·      

“Filea claim” (without specifying the device in a multi-device account)·      

“Checkmy device insurance” (without identifying the specific device)·      

“Submita claim for one of my devices” (ambiguous prompt)·      

“Whichdevice is insured? File a claim on it.” (vague request)·      

“Filea claim but I don’t know which device to choose” (confused user prompt)

# 15.Claim Filed on an Incorrect Device:·      

“Ifiled a claim for the wrong device” (after filing incorrectly)·      

“Canyou change the device for my claim?” (incorrect device selection)·      

“Imade a mistake; the wrong device was selected” (post-claim mistake)·      

“Filemy claim on this device, not the one I chose” (switching devices post-filing)·      

“Helpme change the device for my claim” (error correction)

# 16.Repeated Cancellations by User:·      

“Cancelthe claim process” (repeated cancellations)·      

“Stopthe submission, I’m unsure” (cancel mid-action)·      

“Nevermind, I don’t want to file the claim now” (cancel after starting)·      

“Forgetit, I’ll file the claim later” (cancel before completion)·      

“Cancelagain, I’m not ready” (repeated cancellations)

# 17.User Asks for Unsupported Features:·      

“Generatea claim summary from 5 years ago” (unsupported range)·      

“Showclaim history for 10 years” (unsupported request)·      

“CanI get a report on all my claims ever?” (unsupported time range)·      

“Whycan’t I see claims older than two years?” (unsupported request)·      

“Providea full claim history summary” (unsupported feature)

# 18.Expired Insurance Coverage:·      

“Filea claim even though my insurance expired” (test agent handling expired policy)·      

“Submita claim for this expired plan” (post-expiry request)·      

“Whycan’t I file a claim on expired coverage?” (expired policy test)·      

“Helpme file a claim after my plan expired” (expired coverage test)

# 19.Escalating Complex Actions to a Human Agent:·      

“Disputethis claim” (trigger escalation to human agent)·      

“Iwant to appeal the claim decision” (complex request requiring humanintervention)·      

“Canyou help me with a claim dispute?” (test escalation logic)·      

“Ineed to escalate my claim issue” (force human agent escalation)·      

“Howdo I dispute this claim outcome?” (test escalation)

# 20.Outdated Information During Execution:·      

“Usemy outdated information to file the claim” (attempt to bypass updating info)·      

“Filethe claim without updating my device info” (outdated data usage test)
