# 🛡️ Elevate Labs - Cyber Security Internship Report

**🧑‍💻 Analyst:** DIGVIJAY NETKE  
**📅 Date:** October 22, 2025

---

## 📝 Task 2: Analyze a Phishing Email Sample

### 🎯 Objective
[cite_start]The primary objective of this task is to dissect a suspicious email sample to identify and document its phishing characteristics. [cite: 4]

### 🛠️ Tools & Deliverables
* [cite_start]**Tools Used:** Email Client, Online Header Analyzer. [cite: 5]
* [cite_start]**Deliverable:** A comprehensive report detailing all identified phishing indicators. [cite: 5]

---

## 🎣 Phishing Email Analysis: "PayPal Customer Scam"

[cite_start]An email impersonating PayPal was identified as the phishing sample for this analysis. [cite: 7] The following sections break down the investigation step-by-step.

> #### 🖼️ Visual Evidence
> **

### 1️⃣ Step 1: Examine Sender's Email Address

The sender's address was immediately flagged as suspicious.

* [cite_start]**Displayed Sender:** `Team Support services@paypal-accounts.com` [cite: 10]

> [cite_start]🚨 **Major Red Flag:** The domain `paypal-accounts.com` is a classic example of a **look-alike domain**. [cite: 13] It is crafted to appear legitimate but is not the official `paypal.com` domain. [cite_start]This is a strong initial indicator of a spoofing attempt. [cite: 14]

### 2️⃣ Step 2: Check Email Headers for Discrepancies

A deeper analysis of the email's (hypothetical) headers reveals multiple discrepancies that would be expected in a phishing attack.

| Header Field | Expected in a Legitimate Email | Finding in Phishing Email | Analysis |
| :--- | :--- | :--- | :--- |
| **`From:`** | An address ending in `@paypal.com`. | [cite_start]`services@paypal-accounts.com` [cite: 13] | [cite_start]The domain is not official, confirming impersonation. [cite: 13] |
| **`Return-Path:`** | [cite_start]Should match the official domain (e.g., `bounce@e.paypal.com`). [cite: 15] | [cite_start]Likely shows a completely different, non-PayPal domain. [cite: 15] | [cite_start]This mismatch confirms the email was not sent from PayPal's servers. [cite: 15] |
| **`Received-SPF:`**| [cite_start]Should show a `Pass` result for the `paypal.com` domain. [cite: 16] | [cite_start]Expected to be `Fail` or `Softfail`. [cite: 16] | [cite_start]This indicates the sending server is not authorized by PayPal to send emails on its behalf. [cite: 16] |
| **`Received:`** | [cite_start]The origin IP should belong to PayPal or its authorized email provider. [cite: 17] | [cite_start]The origin IP would likely trace back to a generic web host or an unrelated server. [cite: 17] | [cite_start]This reveals the true, unauthorized origin of the email. [cite: 17] |

### 3️⃣ Step 3: Identify Suspicious Links & Attachments

The email's payload is delivered through a malicious hyperlink disguised as a button.

> ####  malicious Call-to-Action (CTA) Button
> **

* [cite_start]**Analysis:** The email contains a large, blue **"Confirm Your Information"** button. [cite: 20] This is the central focus of the attack, designed to be the single action the user takes. [cite_start]The text leverages the urgent narrative of the email to seem like a necessary step. [cite: 21]

### 4️⃣ Step 4: Note Mismatched URLs

Hovering over the CTA button without clicking would reveal its true, malicious destination.

* [cite_start]**Crucial Red Flag:** The link's destination URL would **not** be `https://www.paypal.com/`. [cite: 22]

* **Examples of Deceptive URLs:**
    * [cite_start]**Typosquatted Domain:** `http://www.paypa1.com` (using a `1` instead of an `l`). [cite: 36]
    * [cite_start]**Deceptive Subdomain:** `http://paypal.security-update-center.com` (the real domain is `security-update-center.com`). [cite: 37]
    * [cite_start]**Raw IP Address:** `http://192.168.x.x/paypal`. [cite: 38]
    * [cite_start]**Unrelated Domain:** `http://www.secure-login-portal.net/Oauth/`. [cite: 39]

### 5️⃣ Step 5: Look for Urgent or Threatening Language

The email's body is crafted to manipulate the user through social engineering tactics.

* [cite_start]**Artificial Deadline:** The phrase **"You have 24 hours to solve the problem or your account will be permanetly disabled"** creates a false sense of urgency to provoke a panicked reaction. [cite: 26, 28] [cite_start]Legitimate companies do not use such aggressive deadlines. [cite: 27]
* [cite_start]**Immediate Consequence:** The statement **"you no longer have access to PayPal's advantages"** makes the threat feel current and real, increasing anxiety. [cite: 29, 30]
* [cite_start]**Security Threat:** By claiming the **"account is in danger from unauthorized users,"** the attacker uses fear to position their malicious link as the only solution. [cite: 31, 32]

### 6️⃣ Step 6: Verify Presence of Spelling or Grammar Errors

The email contains basic errors that are uncharacteristic of a professional organization.

* [cite_start]**❌ Incorrect:** `...permanetly disabled.` [cite: 42]
* [cite_start]**✔️ Correct:** `...permanently disabled.` [cite: 43]
* [cite_start]**❌ Incorrect:** `...is limited, You have 24 hours...` [cite: 44]
* [cite_start]**✔️ Correct:** `...is limited, you have 24 hours...` (lowercase "you" after a comma). [cite: 45, 46]

### 7️⃣ Step 7: Final Summary of Phishing Traits

[cite_start]This email is a textbook phishing scam that exhibits multiple classic indicators. [cite: 49]

* [cite_start]**Fake Urgency:** It pressures the user with a 24-hour deadline and a threat to disable the account. [cite: 50]
* [cite_start]**Sender Spoofing:** The sender's domain (`paypal-accounts.com`) is not official. [cite: 51]
* [cite_start]**Lack of Personalization:** It uses a generic "Dear PayPal customer" greeting. [cite: 51]
* [cite_start]**Poor Quality:** The email contains a clear spelling error ("permanetly"). [cite: 52]
* [cite_start]**Malicious Intent:** All tactics are designed to rush the user into clicking a link that leads to a fraudulent site to steal their login credentials. [cite: 53]

---

## 🎙️ Interview Questions & Answers

### ### What is phishing?
[cite_start]Phishing is a cyberattack where an attacker impersonates a trusted entity, like a bank or a known company, through deceptive communications like emails or websites. [cite: 55, 56] [cite_start]The primary goal is to use social engineering to trick victims into revealing sensitive information, such as login credentials or credit card numbers. [cite: 57] [cite_start]It’s essentially a digital con that preys on human trust. [cite: 58]

### ### How do you identify a phishing email?
[cite_start]You can identify a phishing email by looking for several key red flags: [cite: 59]
* [cite_start]**Mismatched Sender Address:** The domain name in the "From" address doesn't match the legitimate company's domain. [cite: 60]
* [cite_start]**Generic Greetings:** It uses vague greetings like "Dear Valued Customer" instead of your actual name. [cite: 61]
* [cite_start]**Urgent or Threatening Language:** It creates a sense of panic to rush you into action. [cite: 62]
* [cite_start]**Suspicious Links/Attachments:** Hovering over a link reveals a URL that is different from the legitimate site. [cite: 63, 64] [cite_start]Unexpected attachments are also a major warning. [cite: 65]
* [cite_start]**Spelling and Grammar Errors:** Obvious mistakes are a strong sign that the email is fraudulent. [cite: 66, 67]

### ### What is email spoofing?
[cite_start]Email spoofing is a technique where an attacker forges the sender's address in an email header to make the message appear as if it came from a legitimate or trusted source. [cite: 68, 69] [cite_start]It's a critical component of phishing because a convincing "From" address makes the entire scam much more believable. [cite: 70, 71]

### ### Why are phishing emails so dangerous?
[cite_start]Phishing emails are dangerous because they are a primary entry point for a wide range of cyberattacks, effectively bypassing technical security by targeting people. [cite: 72, 73]
* [cite_start]**For an individual**, this can lead to identity theft and direct financial loss. [cite: 74]
* [cite_start]**For a company**, one employee falling for a phish can lead to a full-scale data breach, ransomware infection, or massive financial fraud. [cite: 75] [cite_start]It's often the initial foothold attackers use to compromise an entire network. [cite: 76]

### ### How can you verify a sender’s authenticity?
[cite_start]The safest way is to use an "out-of-band" method. [cite: 78] [cite_start]Never use the contact info provided in the suspicious email. [cite: 77] [cite_start]Instead, go directly to the company's official website by typing the address yourself or call a phone number you know to be legitimate, like the one on the back of your bank card. [cite: 79, 80] [cite_start]Technically, you can also analyze the email headers and check the SPF and DKIM authentication results; a "fail" status is a clear sign of spoofing. [cite: 81, 82]

### ### What tools can analyze email headers?
[cite_start]There are several great online tools that parse raw email headers into a readable format. [cite: 83] Some of the most common are:
* [cite_start]MxToolbox Email Header Analyzer [cite: 85]
* [cite_start]Google Admin Toolbox Messageheader [cite: 86]
* [cite_start]Microsoft's Message Header Analyzer [cite: 87]

[cite_start]These tools trace the email's path and clearly show the results of security checks like SPF, DKIM, and DMARC. [cite: 88]

### ### What actions should be taken on suspected phishing emails?
[cite_start]First, do not interact with it—don't click links, download attachments, or reply. [cite: 89, 90] Then:
1.  [cite_start]**Report it** using the "Report Phishing" feature in your email client. [cite: 92] [cite_start]This helps improve spam filters. [cite: 93]
2.  [cite_start]In a corporate setting, **forward it to the IT/cybersecurity department** immediately. [cite: 94]
3.  [cite_start]**Delete the email** permanently after reporting it. [cite: 96]

[cite_start]If you accidentally clicked a link or entered credentials, you must change your password on that site and any other accounts using the same password immediately and report the incident. [cite: 97]

### ### How do attackers use social engineering in phishing?
[cite_start]Social engineering is the core of phishing; it's the art of manipulating people. [cite: 98] [cite_start]Attackers use several psychological triggers: [cite: 99]
* [cite_start]**Urgency and Fear:** They create a false emergency to cause panic and rush you into a mistake. [cite: 100]
* [cite_start]**Authority:** They impersonate a person of power, like a CEO, to make their request seem non-negotiable. [cite: 101]
* [cite_start]**Trust:** They impersonate brands or colleagues you already trust. [cite: 102]
* [cite_start]**Greed and Curiosity:** They lure you with promises of prizes or intriguing stories to tempt you into clicking. [cite: 103]
