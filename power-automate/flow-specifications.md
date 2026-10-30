# Power Automate flow specifications

These are implementation-ready flow designs, not deployed flows. Build them in a solution with connection references and environment variables.

## PF-01 — Start onboarding
- Trigger: Dataverse row added to Lifecycle Case where Case Type = Onboarding.
- Validate: employee, start date, manager, owner team are present.
- Actions: create standard task rows; notify HR, IT and manager in Teams/email; write Activity row.
- Guardrails: idempotency key = CaseId + template version; handle duplicate trigger; log failures.

## PF-02 — Approval gate
- Trigger: task requires approval or case reaches approval stage.
- Actions: create approval; Start and wait for an approval; on approve update status and activity; on reject record comments and notify owner.
- Escalation: reminder after configured business-day interval; route unresolved approval to HR lead.
- Guardrails: approval decision and approver identity must be persisted.

## PF-03 — Due-date reminders
- Trigger: recurrence each business day.
- Actions: query open tasks due soon or overdue; group by owner; send digest; update reminder timestamp.
- Guardrails: avoid duplicate reminders; respect time zone and leave calendars; allow configurable cadence.

## PF-04 — Start offboarding
- Trigger: Dataverse row added with Case Type = Offboarding.
- Actions: create handover, equipment recovery, exit interview and access-revocation tasks; notify HR/IT/manager.
- Critical control: access revocation must be approved and scheduled against authoritative HR termination date. Never disable accounts solely from an unverified form submission.

## PF-05 — Close lifecycle case
- Trigger: all required tasks complete.
- Actions: verify mandatory approvals/evidence; set case Complete; notify case owner; append activity.
- Error path: if required tasks remain, do not close; alert owner.

## Shared implementation conventions
Use scopes named Try, Catch and Finally; configure retry policies for transient errors; send failures to a monitored queue; use service principals/managed identities where supported; keep secrets in approved secure stores; apply DLP policies; document data retention. Test with synthetic identities in a non-production environment.
