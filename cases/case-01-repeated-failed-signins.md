# Case 01 — Repeated Failed Sign-ins

## Scenario

A fictional Microsoft 365 user account generated **15 failed sign-in attempts within 10 minutes**. The attempts originated from an unfamiliar external IP address. No successful sign-in from that IP address was recorded. The user had not yet been contacted.

## Initial Interpretation

The pattern warrants investigation because repeated authentication failures from an unfamiliar external source can be consistent with password guessing or use of incorrect/stolen credentials. The available facts do **not** establish account compromise because no successful sign-in from the source was reported.

## Evidence to Review

- Microsoft 365 / Entra sign-in history around the alert window
- Exact timestamps and frequency of the failures
- Source IP and available location/network context
- Authentication failure reason
- Device/client/application information
- Any successful sign-ins before or after the failures
- MFA activity or prompts
- Risk detections associated with the account
- User's normal sign-in pattern
- User confirmation regarding travel, VPN use, password problems, or unfamiliar prompts

## Possible Legitimate Explanations

- User repeatedly entered an incorrect password
- An application or device retained stale credentials
- A VPN or network service caused the source to appear unfamiliar
- A legitimate automated process attempted authentication with outdated credentials

These explanations require validation; they should not be assumed.

## Possible Malicious Explanations

- Password guessing
- Credential stuffing
- Attempted use of previously exposed credentials
- An attacker testing whether credentials are valid

## Proposed Severity

**Medium (provisional).**

Reasoning: the repeated failures and unfamiliar external source are security-relevant, but the scenario states that no successful authentication from that IP occurred. Severity should be reassessed if additional evidence shows successful access, MFA abuse, privileged-account targeting, or suspicious post-authentication activity.

## Additional Information Required

The most important missing context is the user's confirmation and surrounding authentication history. The analyst should determine whether the source/activity is recognized and whether any successful or risky authentication occurred near the same time.

## Recommended Actions

1. Review the account's authentication activity around the detection window.
2. Check for successful sign-ins associated with the same source or unusual locations/devices.
3. Review MFA and identity-risk information where available.
4. Contact the user through an approved channel to validate the activity.
5. Preserve/document relevant evidence and timestamps.
6. Follow the organization's identity-response process if compromise indicators are discovered.

## Escalation Decision

**Escalate for additional identity investigation / validation.**

The combination of repeated failures and an unfamiliar external source justifies additional review. Escalation here does not mean the account is confirmed compromised; it means the available evidence is insufficient to safely dismiss the activity.

## Analyst Conclusion

**Disposition:** Requires additional context / security-relevant authentication activity  
**Confidence:** Medium

No successful sign-in from the unfamiliar IP is reported, which reduces evidence of compromise. However, the source is unfamiliar, the attempt volume is notable, and the user has not yet validated the activity. Additional identity evidence is required before closure.
