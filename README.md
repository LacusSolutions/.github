# Shareable GitHub Resources

This repository centralizes resources to be used in `.github` directories across LacusSolutions' projects.

## Usage

### Self-Assign Pull Request

Automatically assign the Pull Request to its author.

```yml
# or-author-assign.yml
name: Pull Request Author Assignment

on:
  pull_request_target:
    types:
      - opened
      - reopened

permissions:
  pull-requests: write

jobs:
  assign-author:
    runs-on: ubuntu-latest
    steps:
      - uses: LacusSolutions/.github/workflows/self-assign-pr.yml
```
