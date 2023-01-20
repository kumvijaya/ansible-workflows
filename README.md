# Ansible workflows

This repository keeps the [github action workflow](https://github.com/kumvijaya/ansible-workflows/blob/main/.github/workflows/ansible-workflow.yml) code for ansible based deployment.

## Workflow steps
- **Checkout**: Checksout the current repository/current commit
- **Show changed files**: Shows the list of changed files. Uses [tj-actions](https://github.com/tj-actions/changed-files). This checkes only the *.yaml/*.yml file changes 
- **Show diff of changed files**: Shows file diffs for changed files. Uses [git diff](https://git-scm.com/docs/git-diff) This checkes only the *.yaml/*.yml file changes
- **Lint ansible files**: Lints the ansible files using [ansible-lint-action](https://github.com/ansible/ansible-lint-action)
- **Dry-run**: Execute the given ansible play file using ansible playbook with [check/dryrun](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_checkmode.html#:~:text=In%20check%20mode%2C%20Ansible%20runs,before%2Dand%2Dafter%20comparisons) mode. This uses [ansible CLI](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installation-guide)

Refer more details
- [Reusing workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows)