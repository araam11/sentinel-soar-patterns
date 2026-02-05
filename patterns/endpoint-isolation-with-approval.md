\# Pattern: Endpoint Isolation with Approval



\## Objective

Isolate an endpoint \*\*only after explicit analyst approval\*\*

when a Microsoft Sentinel incident meets predefined risk criteria.



This pattern exists to prevent \*\*automation-induced outages\*\*

and \*\*false-positive containment\*\*.



---



\## Why this pattern is necessary



Endpoint isolation:

\- Immediately disrupts user productivity

\- Can interrupt mission-critical services

\- Is difficult to roll back automatically



Blind isolation based on incident creation alone

creates \*\*more risk than it removes\*\*.



---



\## When isolation may be considered

Isolation may be proposed when \*\*all\*\* of the following are true:



\- Incident severity is \*\*High or Critical\*\*

\- Alert source is \*\*high-confidence\*\* (Defender XDR, identity protection, etc.)

\- Affected device is \*\*not\*\* a critical infrastructure system

\- The incident is \*\*not\*\* a known false-positive pattern



Meeting these conditions \*\*does not automatically isolate the device\*\*.



---



\## What this pattern does



1\. Trigger on Sentinel incident creation

2\. Evaluate isolation eligibility:

&nbsp;  - Severity

&nbsp;  - Alert provider

&nbsp;  - Device classification

3\. If eligible:

&nbsp;  - Send approval request to:

&nbsp;    - SOC analyst

&nbsp;    - On-call security engineer

4\. Await explicit approval

5\. Only after approval:

&nbsp;  - Isolate device in Defender for Endpoint

&nbsp;  - Record action in Sentinel incident comments



---



\## Guardrails



\- ❌ No automatic isolation without approval

\- ❌ No isolation of:

&nbsp; - Domain controllers

&nbsp; - Jump hosts

&nbsp; - Identity infrastructure

\- ❌ No retry loops on failed isolation



Isolation is a \*\*deliberate action\*\*, not a reflex.



---



\## Failure handling



\- If approval is denied:

&nbsp; - Log decision

&nbsp; - Take no action

\- If isolation fails:

&nbsp; - Log failure

&nbsp; - Escalate to human response

\- If approval times out:

&nbsp; - Do not auto-isolate



---



\## Audit and visibility



This pattern must:

\- Add a comment to the Sentinel incident

\- Record:

&nbsp; - Who approved

&nbsp; - When isolation occurred

&nbsp; - Which device was affected



Automation without auditability is operationally unsafe.



---



\## Notes



This pattern is often paired with:

\- Device tagging for triage

\- Post-isolation notification

\- Manual release workflows



Isolation should always be \*\*reversible\*\*, \*\*traceable\*\*, and \*\*intentional\*\*.



