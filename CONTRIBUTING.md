# Contributing Guide

Thanks for helping improve the ThousandEyes observability dashboards! This guide explains how to plan a contribution, keep the dashboards consistent, and submit a clean pull request.

## 1. Before You Start

- Familiarize yourself with the existing dashboards described in `README.md`.
- Make sure you can import/export dashboards in the observability platform you plan to update (Splunk Observability Cloud, Grafana, DataDog, Dynatrace, New Relic, or Signoz).
- Use a feature branch from `main` for every change.

## 2. Repository Overview

- Each integration lives in its own directory (for example `grafana/`, `datadog/`, `splunk/`) and contains the canonical `ThousandEyesDashboard.json`.
- Platform-specific docs or assets stay alongside the dashboard file (for example `grafana/grafana-setup.md`, `grafana/images/`).
- Global documentation (like this file and `README.md`) belongs at the repository root.

## 3. Workflow at a Glance

1. Open or pick up a GitHub Issue. Describe the platform, the data source, and the motivation.
2. Create a branch named `feature/<short-description>` or `fix/<short-description>`.
3. Make the change, keeping commits focused and well-described.
4. Test the dashboard in the target platform (see section 5).
5. Submit a pull request referencing the issue, including screenshots when visual changes occur.

## 4. Editing Dashboards

- Keep the file name `ThousandEyesDashboard.json` unless there is a strong reason not to; tooling and docs assume that name.
- Preserve backwards compatibility when possible (for example, avoid deleting existing charts unless absolutely necessary).
- Use human-friendly labels, and keep units/descriptions consistent across platforms.
- When adding queries or widgets:
  - Prefer existing ThousandEyes metrics and dimensions before inventing new ones.
  - Document any required tags, variables, or template parameters in a README section or platform-specific doc.
- Run the platform’s JSON formatter/validator so the diff remains readable.

## 5. Testing & Validation

- Import the updated dashboard into the relevant observability backend and verify:
  - All charts render without errors.
  - Variables / template controls resolve correctly against sample data.
  - Thresholds, colors, and legends make sense for ThousandEyes metrics.
- Capture an updated screenshot (`.png`) if the visual layout changes significantly and place it next to the dashboard JSON.

## 6. Documentation & Assets

- Update `README.md` if you add or remove an integration.
- Keep setup instructions in platform-specific Markdown files (for example, `grafana/grafana-setup.md`).
- Store images in an `images/` subdirectory under the platform folder. Use lowercase, hyphenated filenames.

## 7. Pull Request Checklist

- [ ] Dashboard JSON validates / imports without errors.
- [ ] README and setup docs describe any new requirements.
- [ ] Screenshots reflect the new state when visuals change.
- [ ] Tests or manual verification steps are documented in the PR description.
- [ ] Commits are squashed.

## 8. Need Help?

Open a GitHub Discussion or Issue with the details of the observability platform, the ThousandEyes metrics involved, and any errors you encounter. Someone from the maintainers or community will be happy to help.
