# GitHub Workflows

This folder contains the GitHub Workflows to lint and test the Ansible role. It also contains a release workflow that imports the role to [Ansible Galaxy](https://galaxy.ansible.com/).

## Ansible Galaxy Import
The import utilises this GitHub action https://github.com/robertdebock/galaxy-action which requires the setting of the `git_branch` parameter as it defaults to `master` and the Catosplace Ansible Galaxy API Key provided as a secret.

Importing of the role manually can be done using the following command
```
ansible-galaxy role import \
  --token <TOKEN>
  --branch main \
  --role-name catosplace/engineering_base \
    catosplace \
    ansible-engineering-base-role
```
The `token` is the API Key, and note the use of the `branch` parameter to the command.

### Finding the Ansible Galaxy Role Id
The Ansible Galaxy badges used by this repository require the Ansible Galaxy Role id. The following command can be used to find this:
```
ansible-galaxy info catosplace.engineering_base | grep -E 'id: [0-9]' | awk {'print $2'}
```
