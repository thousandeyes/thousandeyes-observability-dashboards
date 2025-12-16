# New Relic Setup Guide

Follow these steps to import the ThousandEyes dashboard into New Relic and configure it for your account.

## 1. Import the dashboard
- Sign in to the New Relic UI and open the Dashboards section.
- Choose **Import** → **JSON** and paste the contents of `newRelic/ThousandEyesDashboard.json` from this repository.
- Save the new dashboard.

## 2. Replace the placeholder account ID
The dashboard JSON now uses a placeholder for the `accountIds` field inside each NRQL query:

```
"accountIds": [
  "{{AccountId}}"
],
```

Update this placeholder before or immediately after importing the dashboard:
1. Locate your numeric New Relic account ID from the account switcher in the top-right of the UI (the value shown under your account name).
2. Replace every `{{AccountId}}` placeholder in `newRelic/ThousandEyesDashboard.json` with that number. If you already imported the dashboard, edit each widget inside the New Relic UI and set the account to your ID.
3. Re-save the file (or dashboard) so all NRQL queries point to the correct account.

## 3. Provide ThousandEyes variables
The dashboard expects these template variables:
- `StreamId`
- `Test`
- `Agent`

Adjust the variable defaults or selections in the dashboard UI to match the ThousandEyes tests you want to visualize.

Once the placeholders and variables are configured, the widgets will begin populating with your ThousandEyes telemetry stored in New Relic.


