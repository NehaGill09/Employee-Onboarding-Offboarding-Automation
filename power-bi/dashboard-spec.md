# Power BI dashboard specification

## Report pages
1. **Executive overview** — active cases, onboarding/offboarding split, overdue tasks, task completion rate.
2. **Onboarding operations** — cases by department, readiness by start date, outstanding IT/manager tasks.
3. **Offboarding controls** — upcoming last working days, access-revocation task status, equipment recovery completion.
4. **Service performance** — average task duration, approval turnaround, overdue trends, workload by owner team.

## Suggested measures (DAX examples)
```DAX
Active Cases =
CALCULATE(COUNTROWS('Lifecycle Case'), 'Lifecycle Case'[Status] <> "Complete")

Completed Tasks =
CALCULATE(COUNTROWS('Lifecycle Task'), 'Lifecycle Task'[Status] = "Completed")

Task Completion % =
DIVIDE([Completed Tasks], COUNTROWS('Lifecycle Task'), 0)

Overdue Tasks =
CALCULATE(
    COUNTROWS('Lifecycle Task'),
    'Lifecycle Task'[Status] <> "Completed",
    'Lifecycle Task'[Due Date] < TODAY()
)
```

## Model and governance
Use a star-schema reporting model with lifecycle case and task facts, employee/team/date dimensions. Apply row-level security where required; expose aggregated operational measures rather than unnecessary personal employee details. Validate measure names against the actual semantic model before use.
