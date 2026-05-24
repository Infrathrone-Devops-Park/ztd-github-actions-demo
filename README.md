# ZTD — GitHub Actions Demo

Teaching repository for **Zero to DevOps Engineer — Phase 3, Week 6 (GitHub Actions)**.

A tiny Python calculator wired up with the full set of Week-6 workflow constructs,
so every lecture demo has a live, green reference.

## What's here

| File | Demonstrates |
|---|---|
| `app/calculator.py`, `tests/` | the app under test (pytest) |
| `.github/workflows/ci.yml` | events (`push`/`pull_request`/`workflow_dispatch`), `needs:` ordering, **matrix** across Python versions, **pip caching**, **artifacts** |
| `.github/workflows/reusable-build.yml` | a **reusable workflow** (`workflow_call`) with an input |
| `.github/workflows/caller.yml` | calling the reusable workflow at the job level |

## Run locally

```bash
pip install -r requirements.txt
flake8 app tests --max-line-length=100
pytest -v
```

## Jenkins → GitHub Actions

This repo is the GitHub Actions counterpart to the Week-5 Jenkins labs. Mental map:

| Jenkins | GitHub Actions |
|---|---|
| `Jenkinsfile` | `.github/workflows/*.yml` |
| Pipeline | Workflow |
| `stage` | `job` (parallel by default) |
| `step` | `step` |
| Agent / node | Runner |
| `triggers { }` | `on:` |
| `agent { label }` | `runs-on:` |
| Plugin | Action (Marketplace) |
| Shared library | Reusable workflow |
| Credentials store | Secrets |
| `environment { }` | `env:` |
