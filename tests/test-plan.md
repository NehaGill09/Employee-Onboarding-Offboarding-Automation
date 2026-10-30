# Test plan

Use synthetic records only. Record actual execution date, tester, browser and result when running locally.

| ID | Scenario | Steps | Expected result |
|---|---|---|---|
| T01 | Initial dashboard | Open index.html | KPI cards, seeded cases and progress render |
| T02 | Create onboarding | Create a valid onboarding case | Case appears in dashboard and employee list with four tasks |
| T03 | Create offboarding | Create a valid offboarding case | Offboarding-specific checklist is created |
| T04 | Required fields | Submit form with required fields empty | Browser validation blocks submission |
| T05 | Task completion | Open task center and check a task | Task status, progress and activity update |
| T06 | Filter cases | Search employee and choose case type | Only matching cases are shown |
| T07 | Case detail | Open a case | Employee summary and task checklist render |
| T08 | CSV export | Select Export CSV | CSV downloads with case data |
| T09 | Persistence | Refresh browser after changes | Local demo changes remain |
| T10 | FAQ helper | Ask an onboarding/offboarding question | General demo response is shown |
| T11 | Responsive layout | Resize to mobile width | Navigation, cards and forms remain usable |
| T12 | Reset | Clear local site data | Seed data returns on next load |

## Execution record
Not yet executed in a browser automation environment. Mark pass/fail and attach genuine screenshots after running each test locally. SVGs in evidence are illustrative test-state visuals, not proof of executed tests.
