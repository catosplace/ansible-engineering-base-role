# 4. Use Pre-Commit Hooks

Date: 2022-09-30

## Status

Accepted

## Context

Prior to submitting code for review we would like to identify and fix simple issues such as formatting and linting problems. By doing this code that is submitted can be reviewed with a focus on the content of the change and not deal with trivial style nitpicks.

## Decision

We have decided we will utilise the [pre-commit](https://pre-commit.com/) as this is an industry standard tool, with plenty of support and a great contribution community.

## Consequences

Contributors to this role will need to be aware of the use of the `pre-commit` package manager, and run a `pre-commit install` to install the Git hook scripts provided.

Contributors should have the [pre-commit](https://pre-commit.com/) tooling installed as part of this package.