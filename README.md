# Catosplace Engineering Base Role
This [Ansible][1] role is used by Catosplace Engineering team members to install some common tooling.

[![Actions Status](https://github.com/catosplace/catosplace-engineering-base-role/actions/workflows/main.yml/badge.svg)](https://github.com/catosplace/catosplace-engineering-base-role/actions)

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-catosplace.engineering_base-blue.svg?label=Ansible%20Galaxy)](https://galaxy.ansible.com/catosplace/engineering_base)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/60076?label=Quality%20Score)](https://galaxy.ansible.com/catosplace/engineering_base)

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

| Variable                | Required | Default | Choices                   | Comments                                 |
|-------------------------|----------|---------|---------------------------|------------------------------------------|
| foo                     | no       | false   | true, false               | example variable                         |
| bar                     | yes      |         | eggs, spam                | example variable                         |

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

```
- hosts: all
  roles:
    - catosplace.engineering_base
```

## License

See license.md

## Author Information

### Useful Information

* [CyVerse Ansible Role Template](https://github.com/CyVerse-Ansible/ansible-role-template)

[1]: https://www.ansible.com