# SOC Alert Triage Lab

A hands-on Security Operations Center (SOC) portfolio project demonstrating a structured approach to reviewing, classifying, documenting, and escalating security alerts.

## Project Objective

This lab demonstrates foundational SOC alert-triage skills using **fictional security scenarios**. The focus is not simply deciding whether activity is malicious, but documenting the evidence available, identifying missing context, considering legitimate explanations, assessing potential impact, and making an evidence-based escalation recommendation.

> **Portfolio safety:** All scenarios in this repository are simulated. No real employer users, accounts, devices, IP addresses, credentials, emails, or production-system data are included.

## Skills Demonstrated

- Security event, alert, and incident classification
- True-positive and false-positive analysis
- Severity vs. priority assessment
- Evidence-driven alert triage
- Authentication alert analysis
- Phishing indicator analysis
- Escalation decision-making
- SOC case documentation
- Identification of missing evidence and assumptions

## Triage Workflow

1. Identify the alert and detection source.
2. Record the detection time and affected identity/device.
3. Understand what behavior triggered the alert.
4. Review the evidence available.
5. Identify the potential security impact.
6. Consider legitimate explanations.
7. Consider malicious explanations.
8. Identify missing information.
9. Assign a proposed severity based on available evidence.
10. Recommend immediate next steps.
11. Decide whether escalation is appropriate.
12. Document the reasoning and assumptions.

## Core SOC Concepts

| Concept | Working Definition |
|---|---|
| **Security Event** | An observable action or occurrence in a system, application, account, or network. An event is not automatically malicious. |
| **Security Alert** | A notification generated when activity matches a detection condition or behavior requiring analyst review. |
| **Security Incident** | A security event or collection of events determined to have affected, or credibly threatened, confidentiality, integrity, or availability. |
| **True Positive** | An alert that correctly identifies security-relevant activity. |
| **False Positive** | An alert that fires even though the underlying activity is legitimate or does not represent the suspected threat. |
| **Severity** | The potential technical/security impact associated with the detected activity. |
| **Priority** | How urgently the alert should be handled, considering severity, context, affected assets, and business impact. |
| **Escalation** | Transferring or raising a case for additional investigation, authority, expertise, or response when the available evidence or potential impact warrants it. |

## Common Alert Categories

| Alert Category | Why It May Matter | Evidence to Review | Possible Legitimate Context | Escalation Indicators |
|---|---|---|---|---|
| Repeated failed sign-ins | May indicate password guessing or unauthorized access attempts | Sign-in logs, source IP, timestamps, location, device, successful logins, MFA activity | Mistyped password, stale credentials, old device/application | Successful access, repeated attacks, unusual geography, MFA abuse, privileged account |
| Unusual-location sign-in | May indicate compromised credentials | Sign-in history, IP/geolocation, device, user travel, VPN use, MFA | Travel, corporate VPN, mobile carrier routing | Impossible travel, unknown device, risky follow-on activity |
| Suspicious email/phishing | May attempt credential theft or malware delivery | Headers, sender/domain, authentication results, URLs, attachments, recipient activity | Vendor domain change or legitimate external service | Link clicked, credentials entered, malicious attachment, multiple recipients |
| Malware detection | May indicate execution of malicious software | EDR alert, process tree, file hash/path, parent process, network activity | Approved security/testing software or false detection | Execution confirmed, persistence, credential access, lateral movement |
| Administrative-role change | Could provide unauthorized privileged access | Audit logs, actor, target, approval/change record, sign-in context | Approved administrator provisioning | Unapproved change, compromised actor, privileged account abuse |
| Mailbox-forwarding rule | Can be used for persistence or data collection | Mailbox audit logs, rule destination, creator, sign-ins, user confirmation | User-created workflow or approved forwarding | External forwarding, unknown creator, suspicious sign-in, sensitive mailbox |

## Investigation Cases

### Case 01 — Repeated Failed Sign-ins

A fictional Microsoft 365 account generated **15 failed sign-in attempts within 10 minutes** from an unfamiliar external IP address. No successful sign-in from that IP was recorded and the user had not yet been contacted.

**Focus:** authentication evidence, credential-attack possibilities, missing user context, severity, and escalation.

➡️ See: [Case 01 — Repeated Failed Sign-ins](cases/case-01-repeated-failed-signins.md)

### Case 02 — Suspicious Email

A fictional employee received an email requesting Microsoft 365 password verification through an external link. The display name resembled a known vendor, but the sending domain differed. The message used urgency and threatened account disablement. The employee had not clicked the link.

**Focus:** phishing indicators, sender validation, header review, user impact, containment recommendations, and escalation.

➡️ See: [Case 02 — Suspicious Email](cases/case-02-suspicious-email.md)

## Reusable Analyst Template

A reusable triage checklist is included here:

➡️ [SOC Alert Triage Checklist](templates/alert-triage-checklist.md)

## Key Lessons

- An alert is the beginning of an investigation, not proof of compromise.
- Severity and priority should be based on context and potential impact rather than alert wording alone.
- Legitimate explanations should be considered before reaching a conclusion.
- Missing evidence should be documented explicitly instead of replaced with assumptions.
- Escalation is appropriate when risk, uncertainty, required authority, or potential impact exceeds the analyst's available evidence or scope.
- Clear case notes make investigations easier to review, hand off, and continue.

## Portfolio Roadmap

This repository begins with foundational alert triage. Later portfolio projects expand the same methodology into Microsoft security investigations, Defender XDR threat hunting, Wazuh/Sysmon monitoring, detection engineering, and endpoint/network correlation.

---

**Author:** Enriketa Hoxha  
**Focus:** SOC Analysis • Threat Detection • Incident Response • Security Monitoring
