# Shareable GitHub Resources

This repository centralizes resources to be used in `.github` directories across LacusSolutions' projects.

## Usage

## Update MIT Licenses Copyright

Updates the copyright yarn of all MIT licenses within a project and create a PR with the changes.

```diff
MIT License

-Copyright (c) 2020-2025 Lacus Solutions
+Copyright (c) 2020-2026 Lacus Solutions

Permission is hereby granted, free of charge, to any person...
```

```yml
# license-update.yml
name: Update License Copyright

on:
  schedule:
    - cron: '0 15 1 1 *' # Run every year on January 1st at 15:00 UTC
  workflow_dispatch: # Allow manual triggering

jobs:
  update-license-year:
    runs-on: ubuntu-latest
    steps:
      - uses: LacusSolutions/.github/.github/workflows/mit-license-update.yml@main
        permissions:
          contents: write
          pull-requests: write

```

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

jobs:
  assign-author:
    runs-on: ubuntu-latest
    steps:
      - uses: LacusSolutions/.github/.github/workflows/self-assign-pr.yml@main
        permissions:
          pull-requests: write
```
