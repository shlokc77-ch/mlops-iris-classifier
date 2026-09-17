# Version Control Workflow — MLOps Iris Classifier

## 1. Overview

This document describes the Git-based version control workflow used for this
Machine Learning project, developed as part of MLOps Lab Experiment 2.

- **Repository:** https://github.com/shlokc77-ch/mlops-iris-classifier
- **Primary language:** Python
- **Maintainer:** Shlok Parag Chavan

## 2. Branching Strategy

| Branch | Purpose |
|---|---|
| `main` | Stable project code |
| `develop` | Integration branch for development |
| `feature/<name>` | Individual features developed and merged into `develop` |
| `conflict-demo-*` | Branches created for merge conflict practice |

**Rule:** Changes should not be committed directly to `main`.
The normal flow is:

`feature/* → Pull Request → develop → main`

## 3. Commit Convention

Commits follow a short, imperative style with a type prefix:

- `feat:` — Add new functionality
- `fix:` — Correct a bug
- `docs:` — Documentation changes
- `chore:` — Tooling, configuration, or maintenance changes
- `refactor:` — Code restructuring without changing behavior
- `test:` — Adding or modifying tests

### Examples

```text
feat: add classification report to training script
docs: update README title
chore: initialize project structure with baseline training script
merge: resolve README conflict between version A and B