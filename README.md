# Ansible workflows

This repository keeps the [github action workflow](https://github.com/kumvijaya/ansible-workflows/blob/main/.github/workflows/ansible-workflow.yml) code for ansible based deployment.

## Workflow steps
- **Checkout**: Checksout the caller's repository
- **Show changed files**: Shows the list of changed files. Uses [tj-actions](https://github.com/tj-actions/changed-files). This shows only the *.yaml/*.yml file changes 
- **Show diff of changed files**: Shows file diffs for changed files. Uses [git diff](https://git-scm.com/docs/git-diff) This shows only the *.yaml/*.yml file changes
- **Lint ansible files**: Lints the changed ansible playbook files using [ansible-lint-action](https://github.com/ansible/ansible-lint-action)
- **Dry-run**: Dryrun the changed ansible playbook files. It uses [check/dryrun](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_checkmode.html#:~:text=In%20check%20mode%2C%20Ansible%20runs,before%2Dand%2Dafter%20comparisons) mode with [ansible CLI](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installation-guide)

**Note**: 
This uses the common config files from [ansible-config](https://github.com/kumvijaya/ansible-config)

## Caller instructions
The callers to call this workflow using below
```
name: Ansible CICD

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  ansible-cicd:
      uses: kumvijaya/ansible-workflows/.github/workflows/ansible-workflow.yml@main
      secrets: inherit
```

Refer more details
- [Reusing workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows)