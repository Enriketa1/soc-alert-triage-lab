# SOC Alert Triage Lab

This is one of my first SOC practice projects. I used two fictional alerts to practice how I would review an alert, figure out what information is missing, decide on a severity, and document whether I would escalate it.

The scenarios are simulated and do not contain any company or production data.

## What I practiced

- Difference between an event, alert, and incident
- True positives and false positives
- Severity vs. priority
- Reviewing authentication and phishing alerts
- Looking for missing context before making a decision
- Writing analyst notes and escalation recommendations

## My basic triage process

When reviewing an alert, I try to answer a few questions first:

1. What triggered the alert?
2. Which user, account, or device is involved?
3. What evidence do I have?
4. Is there a normal explanation for the activity?
5. What information am I still missing?
6. What could the impact be if the activity is malicious?
7. Does it need to be escalated?

I also try not to treat an alert as proof that something malicious happened. The alert tells me what needs to be investigated.

## SOC terms I used in this lab

| Term | How I understand it |
|---|---|
| **Event** | Something that happened on a system, account, application, or network. Most events are not incidents. |
| **Alert** | A notification that some activity matched a detection or needs review. |
| **Incident** | A security issue where the available evidence shows, or strongly suggests, an actual impact or threat that needs response. |
| **True positive** | The alert correctly detected security-relevant activity. |
| **False positive** | The alert fired, but the activity was legitimate or did not represent the suspected threat. |
| **Severity** | How serious the potential security impact is. |
| **Priority** | How quickly the alert should be handled based on the situation and business context. |
| **Escalation** | Passing the case for additional investigation or action when more review, authority, or expertise is needed. |

## Common alerts I reviewed

Some common alerts I would expect to see in a SOC include failed sign-ins, unusual sign-ins, phishing emails, malware detections, unexpected administrator-role changes, and mailbox-forwarding rules.

The evidence needed is different for each alert. For example, with a failed sign-in alert I would look at the source IP, timestamps, successful logins, MFA activity, device information, and the user's normal activity. For a phishing alert I would focus more on the sender, domain, headers, authentication results, links, attachments, and whether the user interacted with the message.

## Cases

### [Case 01 - Repeated Failed Sign-ins](cases/case-01-repeated-failed-signins.md)

A Microsoft 365 account received 15 failed sign-in attempts in 10 minutes from an unfamiliar external IP. There was no successful login from that IP.

### [Case 02 - Suspicious Email](cases/case-02-suspicious-email.md)

An employee received an email that looked like it came from a known vendor and asked the employee to verify a Microsoft 365 password through an external link. The sending domain did not match the vendor and the employee did not click the link.

## Triage template

I created a simple checklist that I can reuse when documenting future alerts:

[Alert Triage Checklist](templates/alert-triage-checklist.md)

## What I learned

The main thing I took from this exercise is that I should not make a decision from the alert title alone. I need to check the surrounding activity and be clear about what I know versus what I am assuming.

I also learned that escalation does not automatically mean an incident is confirmed. Sometimes escalation is needed because important context is missing and another analyst or team needs to continue the investigation.

---

**Enriketa Hoxha**  
Cybersecurity | SOC & Incident Response
