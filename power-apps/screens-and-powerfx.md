# Power Apps implementation guide

## Suggested canvas app screens
1. **scrHome** — KPI cards, active cases gallery, overdue task count, quick-create buttons.
2. **scrCaseForm** — employee lookup, lifecycle type, event date, owner, manager, notes; validation before submit.
3. **scrCaseDetail** — employee summary, progress indicator, related task gallery, approvals, activity timeline.
4. **scrTaskBoard** — filter by assigned team, due date and status; task completion and reassignment.
5. **scrAdmin** — controlled task templates, FAQ publishing and role configuration.

## Example Power Fx
Assume Dataverse tables named 'Lifecycle Cases', 'Lifecycle Tasks' and Employees.

Create a case:
```powerfx
If(
    IsBlank(txtEmployeeEmail.Text) || IsBlank(dpEventDate.SelectedDate),
    Notify("Enter an employee email and event date.", NotificationType.Error),
    Patch(
        'Lifecycle Cases',
        Defaults('Lifecycle Cases'),
        {
            'Case Type': ddCaseType.Selected,
            'Event Date': dpEventDate.SelectedDate,
            'Owner Team': ddOwner.Selected,
            Status: 'Case Status'.Pending,
            Notes: txtNotes.Text
        }
    );
    Notify("Lifecycle case created.", NotificationType.Success)
)
```

Filter assigned tasks:
```powerfx
SortByColumns(
    Filter('Lifecycle Tasks', 'Assigned To'.Email = User().Email && Status <> 'Task Status'.Completed),
    "duedate",
    SortOrder.Ascending
)
```

Complete selected task:
```powerfx
Patch(
    'Lifecycle Tasks',
    galTasks.Selected,
    { Status: 'Task Status'.Completed, 'Completed At': Now() }
);
Notify("Task marked complete.", NotificationType.Success)
```

## Build notes
These are illustrative formulas. Match logical names, choice values, relationship fields and delegation behavior to the actual Dataverse schema. Configure role-based security, environment variables, connection references, and solution-aware deployment. Do not grant broad HR record access by default.
