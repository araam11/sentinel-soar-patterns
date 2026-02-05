\# Pattern: Device Tagging for Triage



\## Objective

Apply non-enforcing tags to devices associated with a Sentinel incident

to support \*\*triage, investigation, and prioritization\*\*.



This pattern enables visibility \*\*without changing device behavior\*\*.



---



\## When to use

\- New Sentinel incidents under investigation

\- Devices requiring analyst attention

\- Early-stage triage workflows

\- Cross-team visibility requirements



---



\## What this pattern does

\- Triggers on Sentinel incident creation

\- Identifies affected devices

\- Applies descriptive tags such as:

&nbsp; - `UnderInvestigation`

&nbsp; - `SOC-Review`

&nbsp; - `PotentialCompromise`

\- Tags are applied \*\*only\*\* in Defender for Endpoint



---



\## Guardrails

\- ❌ No enforcement actions

\- ❌ No isolation

\- ❌ No user impact

\- ❌ No Conditional Access triggers tied directly to tags



Tags must remain \*\*informational\*\*, not punitive.



---



\## Failure handling

\- If tagging fails:

&nbsp; - Log the failure

&nbsp; - Do not retry indefinitely

&nbsp; - Do not block other automation



Tagging should never become a point of failure.



---



\## Audit and lifecycle

\- Tags should:

&nbsp; - Be removed once investigation is complete

&nbsp; - Not persist indefinitely

\- Tag lifecycle should align with incident lifecycle



---



\## Notes

This pattern is often paired with:

\- Incident notification

\- Analyst approval workflows

\- Manual containment decisions



Tagging provides \*\*context\*\*, not conclusions.



