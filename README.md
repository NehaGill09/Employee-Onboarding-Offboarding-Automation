# Employee Onboarding & Offboarding Automation Hub

A portfolio-ready HR operations hub demonstrating employee lifecycle workflows. It includes a working browser prototype, sample data, data model, Power Apps/Power Fx examples, Power Automate flow specifications, Copilot Studio design, test cases, and visual test evidence.

## Run locally
Open `index.html` in a modern browser. No build step or dependencies are required. Demo records persist in browser localStorage; use **Reset demo data** to restore the sample dataset.

## Prototype capabilities
- Onboarding and offboarding case creation
- Lifecycle dashboard with status and overdue indicators
- Search, filter, assign, and update lifecycle tasks
- Task completion and activity history
- Employee details, department, manager, start/last day, and equipment/access checklist
- CSV export and local persistence
- HR FAQ helper with clearly labeled demo responses

## Project structure
- `index.html`, `styles.css`, `app.js` — runnable prototype
- `data/sample-employees.csv` — sample employee records
- `architecture/data-model.md` and `architecture/schema.sql` — logical model
- `power-apps/` — screen plan and Power Fx examples
- `power-automate/` — flow definitions and trigger/action mapping
- `copilot-studio/` — topic and knowledge-source design
- `tests/` — manual test plan and test evidence images
- `docs/` — architecture, security, deployment, and limitations

## Technology mapping
| Technology | Demonstration in this repo |
|---|---|
| Power Apps | Screen plan, control names, Power Fx examples |
| Power Automate | Flow specifications for onboarding, approvals, reminders, offboarding |
| SharePoint / Dataverse | Logical data model and SQL reference schema |
| Copilot Studio | HR FAQ topic design, sample utterances, escalation rules |
| Microsoft Copilot | Suggested AI-assisted summaries and drafting use cases |
| Power BI | KPI definitions and dashboard layout guidance |

## Important implementation boundary
The browser prototype is a standalone simulation. It does **not** connect to a Microsoft tenant, SharePoint, Dataverse, Power Apps, Power Automate, Copilot Studio, Entra ID, or Power BI. The accompanying implementation assets are build-ready examples/specifications, not deployed Microsoft flows or live connectors. Use a development tenant, least-privilege permissions, and approved HR data before implementing real integrations.

## Visual test evidence
See [tests/evidence](tests/evidence/) for UI-state illustrations covering the dashboard, onboarding form, task checklist, and offboarding flow. These are illustrative design/test artifacts, not captured screenshots of a live Microsoft tenant.
