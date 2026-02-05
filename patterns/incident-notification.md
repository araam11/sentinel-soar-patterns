\# Pattern: Incident Notification



\## Objective

Notify relevant teams when a Microsoft Sentinel incident is created

\*\*without altering system state\*\*.



This is the \*\*lowest-risk, highest-value\*\* SOAR pattern and should exist

in every SOC, regardless of maturity.



---



\## When to use

\- New Sentinel incidents

\- Governance and compliance visibility

\- SOC awareness and triage

\- Tier-1 analyst workflows



---



\## What this pattern does

\- Triggers on incident creation

\- Extracts key metadata:

&nbsp; - Incident title

&nbsp; - Severity

&nbsp; - Incident number

&nbsp; - Affected entities

\- Sends notifications to:

&nbsp; - Microsoft Teams

&nbsp; - Email distribution lists

&nbsp; - Ticketing systems (optional)



---



\## Guardrails

\- ❌ No remediation

\- ❌ No isolation

\- ❌ No device changes

\- ❌ No user impact



This pattern is \*\*informational only\*\*.



---



\## Failure handling

\- Notification failure must:

&nbsp; - Be logged

&nbsp; - Not block other playbooks

&nbsp; - Not retry indefinitely



---



\## Notes

This pattern is commonly paired with:

\- Device tagging for triage

\- Analyst approval workflows

\- Manual investigation steps



