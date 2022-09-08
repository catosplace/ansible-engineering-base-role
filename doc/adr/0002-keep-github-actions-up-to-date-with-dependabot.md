# 2. Keep GitHub Actions up to date with Dependabot

Date: 2022-09-08

## Status

Accepted

## Context

Actions are often updated with bug fixes and new features to make automated processes more reliable, faster, and safer. This role would like to benefit from these capabilities.

Dependabot can help ensure that references to actions in a repository's `workflow.yml` file are kept up to date.

## Decision

This role will use [Dependabot](https://docs.github.com/en/code-security/dependabot/working-with-dependabot/keeping-your-actions-up-to-date-with-dependabot) to ensure the action's references the latest versions.

Example `dependabot.yml` file for GitHub Actions

```
# Set update schedule for GitHub Actions

version: 2
updates:

  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      # Check for updates to GitHub Actions every weekday
      interval: "daily"

```

## Consequences

This role will require a `dependabot.yml` file configured with the `package-ecosystem` specified as `github-actions`. This file should be located in the `.github` directory of the repository.

Dependabot will send a `pull request` that updates the references in the workflow to the latest version, so a contributor will need to review and merge this request.