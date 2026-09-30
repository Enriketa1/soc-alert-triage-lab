# Case 01 - Repeated Failed Sign-ins

## Scenario

A fictional Microsoft 365 user had 15 failed sign-in attempts in about 10 minutes. The attempts came from an external IP that was not recognized in the scenario. There was no successful sign-in from that IP, and the user had not been contacted yet.

## My first thought

I would not call this an account compromise based only on the failed attempts. However, 15 failures in a short period from an unfamiliar IP are enough for me to look into it further.

## What I would check

- Sign-in activity around the same time
- Exact timestamps of the failed attempts
- Source IP and location information
- Reason the authentication failed
- Device or application used
- Successful logins before or after the alert
- MFA activity
- Whether the user recognizes the activity
- Whether the user was traveling or using a VPN

## What could explain it?

A normal explanation could be the user entering an old password, a device or application still using saved credentials, or a VPN making the connection appear to come from a different location.

On the other hand, it could also be password guessing, credential stuffing, or someone testing credentials from outside the organization.

At this point I would keep both possibilities open because I do not have enough evidence to confirm either one.

## Severity

**Medium**

I chose Medium because the attempts are repeated and come from an unfamiliar source, but there is no successful login from that IP in the scenario. I would raise the severity if I later found a successful login, suspicious MFA activity, or other activity on the account.

## What I still need

The biggest missing piece is the user's confirmation. I would also want to see the sign-in activity before and after the failed attempts to make sure there was not a successful login from another suspicious source.

## Next steps

1. Review the account's sign-in history.
2. Check for successful logins around the same time.
3. Review MFA activity if available.
4. Contact the user through an approved method and ask whether they recognize the activity.
5. Escalate further if I find evidence of successful access or other suspicious activity.

## Decision

**Disposition:** Needs more context  
**Escalation:** Yes, for additional identity review  
**Confidence:** Medium

My reason for escalating is not that I think the account is definitely compromised. I would escalate because the source is unfamiliar, there are repeated attempts, and I still need more information before I would be comfortable closing the alert.
