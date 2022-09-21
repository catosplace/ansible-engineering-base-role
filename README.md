# Catosplace Engineering Ansible Base Role

[![Actions Status](https://github.com/catosplace/catosplace-engineering-base-role/actions/workflows/main.yml/badge.svg)](https://github.com/catosplace/catosplace-engineering-base-role/actions)

[![Ansible Role](https://img.shields.io/ansible/role/60353?label=Ansible%20Galaxy)](https://galaxy.ansible.com/catosplace/engineering_base)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/60353?label=Quality%20Score)](https://galaxy.ansible.com/catosplace/engineering_base)


This [Ansible][1] role is used by Catosplace Engineering team members to install some common tooling.

## Base Tools

Current Catosplace Engineering base tooling:

* [adr-tools](https://github.com/npryce/adr-tools) - Tool for working with a log of [Architecture Decision Records](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions) (ADRs)

Temporary tooling installed at this time until a Catosplace Engineering Ansible role is implemented:

* [yamllint](https://github.com/adrienverge/yamllint) - Linter for YAML files
* [ansible-lint](https://ansible-lint.readthedocs.io/en/latest/) - Linter for Ansible playbooks, roles and collections

Planned Catosplace Engineering base tooling:

* [Python3 and Python3 Pip](https://www.python.org/downloads/) - Required for several tools used by Catosplace Engineering teams
* [pre-commit](https://pre-commit.com/) - Tool for managing pre-commit hooks
Architecture Decision Records
* [docker](https://docker.com) - Container Runtime
* [docker-compose](https://docs.docker.com/compose/) - Used to run multi-container Docker applications
* [git](https://git-scm.com/) - Distributed version control
* [act](https://github.com/nektos/act) - Used to run GitHub Actions locally

## Requirements

There are no requirements outside Ansible to run this role.

## Role Variables

At this time there is some temporary tooling required to for building this role. These will be moved to other roles as and when they are built. The role enables them to be present or absent using the `temporary_tooling_state` variable.

Each of the core tools installed will have an installation path, version and potentially a verification mechanism which will have defaults but which can also utilise variables.

| Variable                | Required | Default | Choices                   | Comments                                 |
|-------------------------|----------|---------|---------------------------|------------------------------------------|
| temporary_tooling_state | no       | present   | present, absent               | Use Temporary Tools                        |
| adr_tools_install_path | no | /opt/adr-tools | | adr-tools Installation Path
| adr_tools_version       | no       | 3.0.0        |                 | Version of ADR Tools                          |
| adr_tools_sha256 | no | SHA for 3.0.0 | | SHA for ADR Tools

## Example Playbook

Simple Playbook

```
- hosts: 127.0.0.1
  connection: local
  roles:
    - catosplace.engineering_base
```

Specific Version Playbook
```
- hosts: 127.0.0.1
  connection: local
  roles:
    - catosplace.engineering_base
      adr_tools_version: 3.0.0
      adr_tools_sha256: "9490f31a457c253c4113313ed6352efcbf8f924970a309a08488833b9c325d7c"
```
## License

Catosplace Engineering Base Role - Provide Base Tooling for Catosplace Engineering teams

Copyright (C) 2022 Catoplace Engineering

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

See [LICENSE.md](./LICENSE.md)

## Author Information
This role was built and is maintained by the Catosplace Engineering team.

## Architecture Decision Records
This role uses Architecture Decision Records (ADR) to capture significant design decisions. If you are new to the concept of ADRs then it is recommended you read [Documenting Architecture Decision](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions) by Michael Nygard.

 This role uses a lightweight ADR toolset created by Nat Pryce's [adr-tools](https://github.com/npryce/adr-tools). ADRs for this role are stored under the `doc/adr` folder.

 The ADRs for this role can be found in the [ADR.md](ADR.md) document.

 ### Useful Manual ADR Tool Information

Regenerate the [ADR.md](ADR.md)

```
adr generate toc \
  -p doc/adr/ \
  -i doc/adr/intro.md \
  -o doc/adr/outro.md  > ADR.md
```
## Running GitHub Actions Locally
When making changes to the the [GitHub Action](https://github.com/features/actions) in this repository contributors should utilise the [act](https://github.com/nektos/act) tool that enables fast feedback by running actions locally.

### Important Information related to the Yamllint GitHub Action
The [yamllint action](https://github.com/frenck/action-yamllint) used by the GitHub Action performs a build when not run locally which does not appear to work with `act`. To work around this contributors should perform the following action to build a container for use locally.

```
docker build \
  -t act-frenck-action-yamllint-v1-dockeraction:latest \
  ~/.cache/act/frenck-action-yamllint@v1/src
```
**NOTE**: Ensure you use the correct version tag for the action when running this command

### Useful Information

To run current tests
```
ansible-playbook ./tests/test.yml \
  -i tests/inventory \
  --ask-become-pass \
  --check \
  --verbose \
  --tags temporary_tools,adr
```

**Ansible Galaxy Role Id**

To produce the Ansible Galaxy status buttons for this role documentation, the Ansible Galaxy role id is required.

The following command can be used to obtain the Ansible Galaxy role id:

```
ansible-galaxy info \
  catosplace.engineering_base \
  | grep -E 'id: [0-9]' | awk {'print $2'}
```

#### References

* [CyVerse Ansible Role Template](https://github.com/CyVerse-Ansible/ansible-role-template)
* [Testing your Ansible roles with Molecule](https://www.jeffgeerling.com/blog/2018/testing-your-ansible-roles-molecule)
* [Unit Testing Ansible Roles using TDD with Molecule](https://archive.fosdem.org/2021/schedule/event/ansible_tdd_molecule/attachments/slides/4579/export/events/attachments/ansible_tdd_molecule/slides/4579/KYN_FOSDEM_21.pdf)

[1]: https://www.ansible.com