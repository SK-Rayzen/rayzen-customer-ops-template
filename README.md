# Rayzen Customer Ops Template

> A public template for managing customer IT operations as a Git repository, designed for human engineers and AI agents to work together with minimal friction.

這是 **瑞翔資訊科技有限公司（Rayzen Ltd.）** 用來整理客戶 IT 維運資訊的公開範本。

我們正在把每個客戶的維運資料 repo 化，讓網路、伺服器、Wi-Fi、資安、SOP、工作紀錄與 AI agent 協作規則，都能用一致、可版本化、可交接的方式管理。

- Company: **瑞翔資訊科技有限公司 / Rayzen Ltd.**
- Website: [www.rayzen.com.tw](https://www.rayzen.com.tw/)
- Focus: IT operations, infrastructure consulting, network / server / Wi-Fi / security integration, and AI-assisted operational workflows
- Repository type: Public template only

> This public repository must not contain any real customer data, credentials, IP addressing, VPN information, vendor contacts, or production secrets.

---

## What this repo is

`rayzen-customer-ops-template` is a starter structure for building a private customer operations repository.

The goal is to turn scattered IT knowledge into a structured working base that can be used by:

- Human engineers - to maintain customer environments with clear structure and history
- AI agents - to quickly understand the current environment, rules, constraints, and operating procedures
- Project owners - to keep long-term maintenance work traceable and easier to hand over
- Support teams - to reduce repeated context rebuilding across tickets, chats, meetings, and field work

In simple terms, this is not just a documentation template.

It is a practical operating model for **repo-based IT operations** and **human + AI agent collaboration**.

---

## Why we are doing this

In real-world IT maintenance, customer information often lives in many disconnected places:

- Excel files
- Google Drive / OneDrive / NAS folders
- Engineer notes
- Chat history
- Vendor emails
- Personal memory
- Old project documents

This creates several problems:

- New engineers need too much time to understand the environment
- AI agents cannot safely act without structured context
- Facts become inconsistent across different files
- Operational knowledge is difficult to reuse
- Long-term maintenance becomes dependent on individual memory
- Handover becomes risky when people change roles

This template is our attempt to make customer IT operations more structured, repeatable, and AI-ready.

---

## Design goals

This template is designed around the following principles:

1. **Single source of truth** - Structured facts should live in predictable locations, especially under `inventory/`.
2. **Human-readable first** - Markdown and YAML are preferred because they are easy to read, diff, review, and edit.
3. **AI-agent friendly** - Files should be structured so that Codex, Claude, ChatGPT, or other agents can quickly understand the environment.
4. **Version controlled** - Every operational change can be tracked through Git history.
5. **Private by default for real customers** - This public repo is only a template. Real customer repos should be private.
6. **Secrets separated** - Passwords, API keys, VPN pre-shared keys, and other secrets must not be mixed into general documents.
7. **Operationally practical** - The structure should work in real maintenance scenarios, not only as ideal documentation.

---

## Intended workflow

A typical customer repository based on this template may be used like this:

1. Create a new **private** repo from this template
2. Fill in customer infrastructure facts under `inventory/`
3. Write customer-specific SOPs and runbooks under `docs/`
4. Track operational notes, incidents, and maintenance history under `worklog/`
5. Track repo structure, documentation, and inventory refactoring under `changelog.md`
6. Keep future tasks and decisions under `todo/` or a similar planning area
7. Define AI agent instructions in `AGENTS.md` or equivalent agent entry files
8. Use Git commits and pull requests to keep changes reviewable
9. Gradually connect the repo with automation, monitoring, ticketing, or internal tools

---

## AI agent entry points

This template assumes that different AI coding / operations agents may need different context entry files.

Recommended entry points:

1. `README.md` - General overview for humans and agents
2. `AGENTS.md` - Shared operating rules and context for AI agents
3. `inventory/` - Structured facts about the customer environment
4. `docs/` - SOPs, runbooks, architecture notes, and project documentation
5. `worklog/` - Operational history and maintenance records
6. `changelog.md` - Repo/documentation/inventory change history

The key idea is simple:

> A new AI session should be able to open the repo, read the entry files, and understand how to help without repeatedly asking for basic context.

---

## Suggested directory structure

| Path | Purpose |
|---|---|
| `inventory/` | Structured facts such as customer profile, devices, networks, systems, IP ranges, accounts, and services |
| `docs/` | SOPs, runbooks, architecture notes, project documentation, and decision records |
| `worklog/` | Customer-facing maintenance logs, incident notes, and field work records |
| `changelog.md` | Repo structure changes, documentation refactoring, and inventory normalization history |
| `todo/` | Pending tasks, follow-up items, blockers, and decisions |
| `automation/` | Schedules, scripts, checks, or agent-readable automation definitions |
| `secrets/` | Placeholder location for secret-management notes or transitional local practice; do not use this in a public repo |
| `AGENTS.md` | Shared agent instructions for AI-assisted workflows |

---

## Secrets and sensitive information

This template may include a `secrets/` directory as a placeholder because many real-world IT teams need a transition path from scattered credentials to a more controlled process.

However, this must be understood clearly:

1. Storing plaintext secrets in Git is not the ideal final architecture.
2. Public repositories must never contain real secrets.
3. Production customer repositories should be private and access-controlled.
4. Mature environments should use a dedicated password manager or secrets manager.

Recommended options include:

- 1Password
- Bitwarden / Vaultwarden
- HashiCorp Vault
- Cloud provider secret managers
- Other auditable, access-controlled, and rotatable secret-management platforms

The intended long-term direction is:

> Keep operational structure in Git, but manage real secrets through a dedicated secrets platform whenever possible.

---

## What should never be committed to a public repo

Do not commit the following information to this public template:

1. Real customer names without permission
2. Public or private IP addressing of production environments
3. Passwords, API keys, VPN pre-shared keys, certificates, or tokens
4. Firewall rules from a real customer environment
5. Remote access methods or jump-host details
6. Vendor contacts tied to a customer environment
7. Internal-only contracts, invoices, or support agreements
8. Screenshots exposing customer systems, dashboards, hostnames, or logs

Use sanitized examples only.

---

## Who this is for

This template may be useful for:

- MSPs and IT outsourcing teams
- Internal IT departments
- Infrastructure consultants
- Network / server / Wi-Fi engineers
- Teams experimenting with AI-assisted operations
- Organizations that want to move away from scattered Excel-based maintenance records

---

## Worklog vs changelog

Repositories based on this template should keep these two histories separate:

- `worklog/`
  - customer-facing operational history
  - maintenance visits
  - incidents
  - service changes
  - troubleshooting outcomes
- `changelog.md`
  - repo structure changes
  - documentation cleanup
  - inventory normalization
  - AI/context-entry refactoring
  - non-customer-facing repository maintenance

This separation keeps customer history readable while still preserving the repository's internal evolution.

---

## About Rayzen

**Rayzen Ltd.（瑞翔資訊科技有限公司）** is a Taiwan-based IT consulting and operations company.

We help organizations design, build, maintain, and improve their IT environments, including:

- Network architecture and deployment
- Server and virtualization infrastructure
- Business Wi-Fi planning and troubleshooting
- Firewall, VPN, and security hardening
- IT maintenance and outsourced operations
- Workflow digitization and internal system integration
- AI-assisted operational process design

Our work is not limited to fixing computers or maintaining devices.

We focus on helping businesses turn messy operational reality into systems, processes, documentation, and automation that can actually be maintained over time.

Website: [www.rayzen.com.tw](https://www.rayzen.com.tw/)

---

## Collaboration

This is our first public repository for sharing part of our operational approach.

If you are interested in:

- Repo-based IT operations
- AI-assisted infrastructure maintenance
- MSP workflow design
- Customer operations templates
- Practical documentation standards for AI agents
- Collaboration with Rayzen on IT or AI operations projects

You are welcome to open an issue, submit a pull request, or contact us through our website.

Website: [www.rayzen.com.tw](https://www.rayzen.com.tw/)

---

## License and usage

This repository is published as a public reference template.

Before using it for a real customer, please review and adapt the structure to your own security, compliance, and operational requirements.

Real customer data should only be stored in private repositories with proper access control.

---

## Final note

This project represents a practical direction we believe in:

> Future IT operations will not be managed only by documents, tickets, and memory.  
> They will increasingly be managed through structured operational repositories where human engineers and AI agents can work together safely and efficiently.
