# GitHub Info

## Mona's editorial angle

Mona's website focuses on practical GitHub guidance backed by official references from:

- docs.github.com
- github.blog
- github.blog/changelog

## Current homepage themes

- GitHub collaboration basics: repositories, branches, pull requests, and merges.
- GitHub Copilot as an AI coding assistant across the IDE, CLI, and GitHub.
- GitHub Actions as the automation layer behind repository workflows.
- Recent GitHub Blog and Changelog stories worth watching.

## Practical workflow example: Daily Issues Report

Source: [Awesome Copilot workflows – Daily Issues Report](https://github.com/github/awesome-copilot/blob/main/workflows/daily-issues-report.md) (`github/awesome-copilot`).

This agentic workflow runs on a weekday schedule and posts a daily summary of open issues as a GitHub issue. It covers:

- New issues opened in the last 24 hours
- Issues closed or resolved
- Stale issues that need attention

Why it's handy: it uses read-only permissions (`contents: read`, `issues: read`) and a `safe-outputs` block that creates a labeled (`report`), prefixed (`[daily-report] `) issue, so output stays easy to review.

Other examples in the same directory include `ospo-stale-repos`, `ospo-org-health`, `ospo-contributors-report`, `ospo-release-compliance-checker`, `relevance-check`, `relevance-summary`, and `weekly-comment-sync`.
