# Copilot Studio — HR lifecycle helper

## Purpose
Answer approved, general questions about onboarding/offboarding processes and guide users to the correct HR channel. It is not an HR decision-maker and must not disclose employee-specific records.

## Topics
- **Onboarding overview** — utterances: “How do I prepare for a new starter?”, “What happens before day one?”
- **IT setup** — utterances: “What equipment is needed?”, “How do I request access?”
- **Offboarding checklist** — utterances: “What happens when someone leaves?”, “How is equipment returned?”
- **Contact HR** — utterances: “I need help with a sensitive case”, “Who can approve an exception?”

## Knowledge sources
Connect only HR-approved policy documents in a governed SharePoint location. Set content owners and review dates. Exclude personal employee folders, payroll, medical information and unrestricted document libraries.

## Example response
“Typical onboarding work includes confirming the employee record, preparing approved access and equipment, and scheduling orientation. Your HR team’s current policy and checklist are authoritative.”

## Escalation and safety
- Escalate case-specific, legal, payroll, accommodation, disciplinary or sensitive questions to HR.
- Do not infer policy where a cited source is unavailable.
- Do not reveal employee data or perform access changes.
- Include source citations in answers where available.
- Add feedback and unresolved-question reporting.

## Configuration checklist
Create agent in the target environment; add approved knowledge; define topics and fallback; configure authentication; test permissions and data boundaries; publish to a restricted channel; monitor unanswered topics; review knowledge on a defined cadence.
