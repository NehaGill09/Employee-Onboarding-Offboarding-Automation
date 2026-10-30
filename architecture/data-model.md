# Logical data model

## Entities
- **Employee**: employee identifier, name, work email, department, manager, employment dates, lifecycle state.
- **LifecycleCase**: case identifier, employee lookup, type (Onboarding/Offboarding), event date, owner, status, notes, created/updated timestamps.
- **LifecycleTask**: task identifier, case lookup, title, assigned team/person, due date, status, completion timestamp, evidence link.
- **Approval**: approval identifier, case/task lookup, approver, decision, comments, decision timestamp.
- **Activity**: activity identifier, case lookup, actor, action, timestamp, detail.
- **FAQKnowledge**: approved question, answer, source, review date, owner.

## Relationships
Employee 1—many LifecycleCase; LifecycleCase 1—many LifecycleTask; LifecycleCase 1—many Approval and Activity. A case has one employee and one lifecycle type. A task can have zero or more approval records.

## Dataverse mapping
Use Employee, Lifecycle Case, Lifecycle Task, Approval and Activity as Dataverse tables. Use lookups for relationships, choice columns for type/status, owner/team columns for assignment, and auditing for sensitive updates. SharePoint Lists can be used for a lightweight pilot but should not duplicate authoritative employee records.

## Governance
Use synthetic data in demos. In production, classify HR data, restrict row/column access, define retention and deletion policies, audit access changes, and avoid storing passwords, authentication secrets, or unnecessary sensitive employee details.
