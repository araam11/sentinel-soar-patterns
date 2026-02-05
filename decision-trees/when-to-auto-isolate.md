\# Decision Tree: When to Automatically Isolate an Endpoint



This decision tree defines \*\*when endpoint isolation may be automated\*\*

and when it must remain a \*\*human decision\*\*.



The goal is to \*\*minimize attacker dwell time without introducing

automation-driven outages or false containment\*\*.



---



\## Step 1: Incident Severity



\*\*Is the Sentinel incident severity High or Critical?\*\*



\- ❌ No → Do NOT auto-isolate

\- ✅ Yes → Proceed to Step 2



Low and Medium severity incidents \*\*do not justify automatic isolation\*\*.



---



\## Step 2: Alert Confidence



\*\*Is the alert source high-confidence?\*\*



Examples of high-confidence sources:

\- Microsoft Defender XDR

\- Identity protection with confirmed compromise

\- Correlated multi-signal detections



\- ❌ No → Require analyst review

\- ✅ Yes → Proceed to Step 3



Severity alone is insufficient without confidence.



---



\## Step 3: Asset Criticality



\*\*Is the affected device business-critical?\*\*



Examples of critical assets:

\- Domain controllers

\- Identity infrastructure

\- Jump hosts

\- Production servers



\- ❌ Yes → Require approval

\- ✅ No → Proceed to Step 4



Critical assets demand human oversight.



---



\## Step 4: Context Awareness



\*\*Is this a known false-positive or noisy pattern?\*\*



\- ❌ Yes → Do NOT isolate

\- ✅ No → Proceed to Step 5



Automation must respect historical context.



---



\## Step 5: Approval Requirement



Even when all conditions are met:



\- Automatic isolation should be \*\*proposed\*\*, not executed

\- Explicit analyst approval is required

\- Isolation actions must be logged and auditable



---



\## Summary



Automatic isolation is \*\*rare by design\*\*.



In most cases, the correct flow is:

> Detect → Propose → Approve → Contain



Automation accelerates response —  

it should \*\*never replace judgment\*\*.



