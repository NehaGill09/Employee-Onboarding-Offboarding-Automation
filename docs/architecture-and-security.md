# Architecture and security notes

## Target architecture
Power Apps canvas app → Dataverse (system of record) → Power Automate (orchestration) → Teams/email notifications. Copilot Studio answers approved HR process FAQs. Power BI reads governed, minimized lifecycle metrics from Dataverse.

## Suggested Power BI measures
- Active cases = count of cases where status is not Complete
- Onboarding cases / Offboarding cases = count by CaseType
- Task completion % = completed required tasks / total required tasks
- Overdue tasks = open tasks with due date before today
- Average time to complete = average completed timestamp minus created timestamp
- Approval turnaround = decision timestamp minus request timestamp

## Security
Use Entra ID authentication, least privilege, Dataverse security roles and team ownership. Restrict employee data to authorized HR roles; IT should see only the fields required for provisioning. Use audit logs for approvals and access lifecycle actions. Use synthetic demo data in development. Define retention, legal hold, deletion and incident response before production.

## AI governance
Ground answers in approved knowledge. Do not use an AI assistant to approve access, decide employment outcomes, or autonomously revoke access. Require human approval for consequential actions and keep a traceable audit trail.
