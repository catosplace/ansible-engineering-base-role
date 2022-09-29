# 3. Use Python Packages where appropriate

Date: 2022-09-09

## Status

Accepted

## Context

Some tools such as `yamllint` and `ansible-lint` are more commonly installed using Python packages rather than distro packages. Using distro packages often result in older versions of these packages.

These older versions often don't align with the latest versions that other tools using these packages use. This results in differences in versions and behaviours between the local packages and those in GitHub Actions.

When it is more appropriate to use a Python package than a distro package Catosplace engineers should utilise the Python package.

## Decision

Catosplace engineers should utilise the Python packages to install the following packages:

* [pre-commit](https://pre-commit.com/)
* [yamllint](https://github.com/adrienverge/yamllint)
* [ansible-lint](https://github.com/ansible/ansible-lint)

## Consequences

Catosplace engineers will need to have Python and `pip` available to install these packages. As other tools such as `pre-commit` are also more commonly installed using Python packages, which is a base engineering tool, Python and `pip` should be set up in this base role.

Using the Python packages will enable the development versions of these tools to align with those used by GitHub Actions and other tooling.
