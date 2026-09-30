# Case 02 - Suspicious Email

## Scenario

A fictional employee received an email asking them to verify their Microsoft 365 password using an external link. The display name looked similar to a known vendor, but the actual sending domain was different. The message was urgent and said the employee's account would be disabled. The employee did not click the link.

## What stood out to me

The biggest red flags were:

- The email asked for password verification through an external link.
- The display name looked familiar, but the domain did not match the vendor.
- The message tried to create urgency.
- It threatened that the account would be disabled.

This looks like a credential-phishing attempt, but I would still check the message details before making the final determination.

## What I would check

- Full email headers
- Sender address and domain
- Reply-To address
- SPF, DKIM, and DMARC results
- Where the message came from and how it was routed
- The link/domain without clicking the link
- Whether other employees received the same message
- Any email-security verdict or alert
- Confirmation that the employee did not interact with the message

## Could it be legitimate?

It is possible that a vendor changed domains or used another email service. I would verify that separately using contact information we already trust. I would not use the link or contact details inside the suspicious email to verify it.

## Severity

**Medium**

I chose Medium because the email is asking for credentials and has several phishing indicators. The employee did not click the link, so there is no indication in the scenario that credentials were entered or the account was compromised.

If the employee had clicked the link, entered credentials, or if the same email had reached many users, I would treat the situation as more urgent.

## Next steps

1. Save the email and headers for review.
2. Do not click the link.
3. Verify the sender/domain through a trusted source.
4. Check whether the same message was delivered to other users.
5. Report or contain the email through the normal security process if it is confirmed malicious.
6. Escalate immediately if I find that the employee entered credentials or interacted with malicious content.

## Decision

**Disposition:** Likely phishing  
**Escalation:** Yes, through the phishing review process  
**Confidence:** Medium-High

The mismatched domain, credential request, and urgency are enough for me to treat the email as suspicious. Since the employee did not click the link, I would focus first on confirming the sender and checking whether anyone else received or interacted with the message.
