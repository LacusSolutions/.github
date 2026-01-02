# Contributing to LacusSolutions Projects

First off, thank you for considering contributing to our projects! We develop developer experience (DX) tools across multiple languages and ecosystems, and community contributions help make these tools better for everyone.

This document provides general guidelines that apply to all LacusSolutions repositories. Please also check for project-specific guidelines in the repository you're contributing to, as individual projects may have additional requirements based on their language, framework, or ecosystem (npm, Packagist, PyPI, Cargo, Maven, etc.).

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before contributing.

## How Can I Contribute?

### Reporting Bugs

Before creating a bug report, please check existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title** for the issue
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples** (code snippets, configuration files, etc.)
- **Describe the behavior you observed and what you expected**
- **Include your environment details** (OS, language version, package version, etc.)
- **Add relevant logs or error messages**

### Suggesting Enhancements

Enhancement suggestions are welcome! When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description** of the proposed functionality
- **Explain why this enhancement would be useful** to most users
- **List any alternatives you've considered**

### Pull Requests

We actively welcome your pull requests! To contribute code:

1. Fork the repository
2. Create your feature branch following our [branching strategy](#branching-strategy-git-flow)
3. Make your changes following the project's coding standards
4. Write or update tests as needed
5. Ensure all tests pass and linting rules are satisfied
6. Commit your changes following our [commit message conventions](#commit-messages-conventional-commits)
7. Push to your fork and submit a pull request

## Branching Strategy (Git Flow)

We follow the [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/) branching model for all our projects:

### Main Branches

- **`main`** (or `master`): Production-ready code. This branch contains the latest stable release.
- **`develop`**: Integration branch for features. This is where the next release is being prepared.

### Supporting Branches

- **`feature/*`**: New features or enhancements
  - Branch from: `develop`
  - Merge back into: `develop`
  - Naming: `feature/short-description` (e.g., `feature/add-validation`)

- **`bugfix/*`**: Bug fixes for the next release
  - Branch from: `develop`
  - Merge back into: `develop`
  - Naming: `bugfix/short-description` (e.g., `bugfix/fix-null-pointer`)

- **`hotfix/*`**: Critical fixes for production
  - Branch from: `main`
  - Merge back into: `main` AND `develop`
  - Naming: `hotfix/short-description` (e.g., `hotfix/security-patch`)

- **`release/*`**: Release preparation
  - Branch from: `develop`
  - Merge back into: `main` AND `develop`
  - Naming: `release/version` (e.g., `release/1.2.0`)

### Branch Workflow Example

```bash
# Start a new feature
git checkout develop
git pull origin develop
git checkout -b feature/my-new-feature

# Work on your feature...
git add .
git commit -m "feat: add new feature"

# Push and create PR to develop
git push origin feature/my-new-feature
```

## Commit Messages (Conventional Commits)

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification for all commit messages. This leads to more readable messages and enables automated changelog generation.

### Commit Message Format

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Types

| Type | Description |
|------|-------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `style` | Changes that do not affect the meaning of the code (formatting, semicolons, etc.) |
| `refactor` | A code change that neither fixes a bug nor adds a feature |
| `perf` | A code change that improves performance |
| `test` | Adding missing tests or correcting existing tests |
| `build` | Changes that affect the build system or external dependencies |
| `ci` | Changes to CI configuration files and scripts |
| `chore` | Other changes that don't modify src or test files |
| `revert` | Reverts a previous commit |

### Scope

The scope is optional and should be a noun describing a section of the codebase (e.g., `parser`, `cli`, `api`).

### Examples

```bash
# Feature with scope
feat(auth): add OAuth2 support

# Bug fix
fix: resolve race condition in event handler

# Breaking change (note the !)
feat!: drop support for Node 14

# Commit with body and footer
fix(api): handle null response from external service

The external service occasionally returns null instead of an empty array.
This change adds proper null checking to prevent runtime errors.

Fixes #123
```

### Breaking Changes

Breaking changes must be indicated by:
- Adding `!` after the type/scope: `feat!: ...` or `feat(scope)!: ...`
- And/or adding `BREAKING CHANGE:` in the footer

## Project-Specific Guidelines

Each project may have additional requirements. Before contributing, please check:

- **README.md**: Project overview and setup instructions
- **CONTRIBUTING.md**: Project-specific contribution guidelines (if different from this document)
- **Linting/Formatting**: Configuration files like `.eslintrc`, `.prettierrc`, `phpcs.xml`, `pyproject.toml`, `rustfmt.toml`, etc.
- **Testing**: Required test coverage and testing frameworks used
- **Dependencies**: How to manage and update dependencies

### Language-Specific Notes

| Ecosystem | Package Manager | Registry | Common Tools |
|-----------|-----------------|----------|--------------|
| JavaScript/TypeScript | npm / yarn / pnpm | npmjs.com | ESLint, Prettier |
| PHP | Composer | packagist.org | PHP_CodeSniffer, PHPStan |
| Python | pip / poetry | pypi.org | Black, Ruff, mypy |
| Rust | Cargo | crates.io | rustfmt, Clippy |
| Java/Kotlin | Maven / Gradle | Maven Central | Checkstyle, SpotBugs |

## Development Setup

General steps to set up a development environment:

1. **Fork** the repository on GitHub
2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/REPO_NAME.git
   cd REPO_NAME
   ```
3. **Add upstream remote**:
   ```bash
   git remote add upstream https://github.com/LacusSolutions/REPO_NAME.git
   ```
4. **Install dependencies** following the project's README
5. **Create a branch** for your work following Git Flow conventions

## Pull Request Process

1. **Update documentation** if you're changing functionality
2. **Add or update tests** for your changes
3. **Ensure CI passes** — all tests, linting, and checks must be green
4. **Fill out the PR template** completely (if provided)
5. **Request review** from maintainers
6. **Address feedback** promptly and push additional commits
7. **Squash commits** if requested by maintainers before merge

### PR Title

PR titles should also follow Conventional Commits format, as they may be used for squash merge commit messages.

## Questions?

If you have questions or need help:

1. Check the project's documentation and existing issues first
2. Open a [Discussion](https://github.com/orgs/LacusSolutions/discussions) (if enabled) or an Issue
3. Be patient — maintainers are often volunteers or have other responsibilities

## License

By contributing to LacusSolutions projects, you agree that your contributions will be licensed under the same license as the project (typically MIT License — see the LICENSE file in each repository).

---

Thank you for contributing! 🎉
