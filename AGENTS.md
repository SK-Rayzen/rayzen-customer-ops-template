# Customer Ops Template — AI Agent Guide

This file is the unified entry point for AI agents working with repositories based on this template.

It is intentionally vendor-neutral and can be used by:

- Codex
- Claude
- ChatGPT
- other coding or operations agents

---

## 1. Purpose

This template is designed for repo-based IT operations.

The goal is to let human engineers and AI agents collaborate on a customer environment with:

- clear structure
- low context-rebuild cost
- reviewable operational history
- consistent handling of infrastructure facts

---

## 2. Source of truth

- Structured operational facts should live in `inventory/`
- If `docs/` and `inventory/` conflict, prefer `inventory/`
- Sensitive information should not be mixed into general documentation
- Passwords, API keys, and tokens should be referenced indirectly whenever possible

---

## 3. Directory conventions

- `inventory/` contains structured facts
- `docs/` contains SOPs, runbooks, architecture notes, and project documentation
- `worklog/` contains maintenance history and operational notes
- `changelog.md` contains repo/documentation/inventory change history
- `todo/` contains pending work and decisions
- `automation/` contains schedules and automation-related definitions
- `secrets/` is a placeholder for private customer repos and should not contain real secrets in a public template repo
- `collected/` is for discovery snapshots
- `backups/` is for restorable backups
- `reports/` is for formal reports and generated artifacts

Do not place ad-hoc outputs in the repository root.

---

## 4. Working style for agents

- Read relevant files before answering or editing
- Prefer small, targeted changes
- Keep operational facts structured
- Avoid duplicating the same fact across multiple files
- Treat repo history as part of the operational record
- Prefer human-readable formats such as Markdown and YAML

---

## 5. Security expectations

- This public template must not contain real customer data
- Real customer repositories should be private
- Public repos must not contain real IP plans, credentials, VPN details, or production secrets
- A dedicated secrets manager is preferred over storing plaintext secrets in Git
- If a private customer repo temporarily uses a `secrets/` directory, it should be treated as a transition pattern, not ideal end-state security architecture

---

## 6. AI entry model

When a new AI session starts, the recommended reading order is:

1. `README.md`
2. `AGENTS.md`
3. relevant files in `inventory/`
4. relevant files in `docs/`
5. relevant files in `worklog/` and `todo/`

The intended result is:

> A new AI session should be able to understand the environment and start helping with minimal friction.

---

## 7. Private customer repo customization

A real customer repo may extend this file with:

- customer-specific operating constraints
- maintenance windows
- escalation paths
- environment-specific safety rules
- model-specific notes if absolutely necessary

But the base structure should remain shared across customers whenever possible.

---

## 8. Worklog vs changelog

- `worklog/` is for customer-facing operational history:
  - maintenance work
  - incidents
  - on-site findings
  - actions performed for the customer environment
- `changelog.md` is for repository-facing history:
  - repo structure changes
  - document refactoring
  - inventory normalization
  - AI/context-file restructuring

Agents should avoid mixing these two. If the change is about the repository itself rather than the customer environment, record it in `changelog.md`, not `worklog/`.
