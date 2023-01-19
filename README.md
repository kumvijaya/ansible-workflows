# Ansible workflows

This repository keeps the [github action workflow](https://github.com/kumvijaya/ansible-workflows/blob/main/.github/workflows/ansible-cd.yml) code for ansible based deployment.

## Workflow steps
- **Checkout**: Checksout the current repository/current commit
- **Show changed files**: Shows the list of changed files. Uses [tj-actions](https://github.com/tj-actions/changed-files). This checkes only the *.yaml/*.yml file changes 
- **Show diff of changed files**: Shows file diffs for changed files. Uses [git diff](https://git-scm.com/docs/git-diff) This checkes only the *.yaml/*.yml file changes
- **Lint ansible files**: Lints the ansible files using [ansible-lint-action](https://github.com/ansible/ansible-lint-action)

Refer more details 
- [run-ansible-playbook](https://github.com/marketplace/actions/run-ansible-playbook)
- [Reusing workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows)