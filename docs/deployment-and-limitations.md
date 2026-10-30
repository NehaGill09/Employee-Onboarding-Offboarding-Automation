# Deployment guide and limitations

## Run the demo
1. Clone or download this repository.
2. Open `index.html` in a current browser.
3. Create sample onboarding/offboarding cases and complete tasks.
4. Use Export CSV to download the current demo cases.
5. Reset local demo state by clearing site data for this page.

## Optional GitHub Pages
In repository Settings → Pages, choose **Deploy from a branch**, select `main` and `/ (root)`, then save. Wait for GitHub Pages to publish and verify the URL in Settings → Pages. A workflow file can be added later if Actions-based deployment is preferred.

## Microsoft environment implementation
Import/create a solution in a development Power Platform environment; create Dataverse tables and choices from the data model; build the canvas app; create the flows from the specifications; configure Copilot Studio knowledge and topics; create Power BI measures/reports; test with synthetic accounts; deploy through managed solutions and environment-specific connection references.

## Known limitations
- The web app uses localStorage and synthetic data; it is not a multi-user application.
- No Microsoft tenant connections or live Microsoft integrations are configured.
- Power Fx is illustrative and must be adapted to actual table/column logical names.
- Flow documents describe intended flow behavior; no exported flow package is included.
- Copilot Studio document is a design specification, not a published agent.
- No real identity provisioning or account deactivation is performed.
