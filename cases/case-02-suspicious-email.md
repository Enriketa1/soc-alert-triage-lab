# Case 02 — Suspicious Email

## Scenario

A fictional employee received an email asking them to verify their Microsoft 365 password through an external link. The sender's display name resembled a known vendor, but the sending domain was different. The email used urgent language and warned that the employee's account would be disabled. The employee had **not clicked the link**.

## Suspicious Indicators

- Request to verify Microsoft 365 credentials through an external link
- Display-name resemblance to a trusted vendor
- Sending domain different from the expected vendor domain
- Urgent language designed to pressure the recipient
- Threat that the employee's account would be disabled

Together, these characteristics are consistent with common credential-phishing techniques, although sender and message evidence should still be validated.

## Evidence to Review

- Full message headers
- Sender address and sending domain
- Reply-To address
- SPF, DKIM, and DMARC results where available
- Message routing information
- URL destination/domain without directly visiting the suspicious link
- Whether similar messages reached other recipients
- Email-security detections/verdicts
- User confirmation that the link was not clicked
- Any related sign-in activity if exposure is suspected

## Possible Legitimate Explanation

A legitimate vendor could theoretically use a changed domain or third-party email service. However, a legitimate explanation would need to be verified through trusted contact information or established organizational procedures—not through the link or contact details in the suspicious message.

## Proposed Severity

**Medium (provisional).**

The message contains multiple phishing indicators and requests credentials, creating meaningful potential impact. The reported lack of user interaction lowers the immediate impact compared with a case involving clicked links or submitted credentials.

## Recommended Actions

1. Preserve the message and relevant headers for analysis.
2. Do not click or test the suspicious link.
3. Validate the sender/domain using trusted information.
4. Check whether the same or similar message reached additional recipients.
5. Use the organization's email-security/reporting process to contain the message if confirmed malicious.
6. Continue to verify that the recipient did not interact with the link.
7. Escalate immediately if evidence shows credential submission, malicious attachment execution, or broader targeting.

## Escalation Decision

**Escalate/report through the phishing investigation process.**

The credential request, mismatched domain, vendor impersonation pattern, and urgency provide sufficient indicators for security review. Because the employee reportedly did not click the link, there is no stated evidence of account compromise in the scenario.

## Analyst Conclusion

**Disposition:** Likely phishing attempt requiring security review  
**Confidence:** Medium-High based on the scenario indicators

The message contains several independent phishing indicators. The absence of user interaction reduces immediate exposure, but sender/header analysis and organization-wide message search would be appropriate before final closure.
