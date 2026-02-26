# Zoho CRM UI Screen Analysis

**Organisation:** Kurinjee Promoters (Org ID: `60043078423`)
**Industry:** Real Estate — Property Sales (South India)
**Platform:** Zoho CRM (`crm.zoho.in`)
**Scan Date:** 2026-02-26

---

## Purpose

This repository documents the complete UI layout, DOM structure, field definitions, navigation flows, and creation forms of every Zoho CRM screen used by Kurinjee Promoters. The documentation is intended for:

- **Reverse engineering** — reconstructing CRM configuration from documentation alone
- **Automation development** — building integrations, bots, or scripts against the CRM UI or API
- **Onboarding** — new team members understanding the system without live CRM access
- **Audit and QA** — verifying that live CRM configuration matches business requirements

There is no executable code in this repository. All files are structured documentation in Markdown, YAML, and PlantUML formats.

---

## Actual File Tree

```
Zoho UI-Screen Analysis/
│
├── home/
│   ├── home_lifecycle.puml
│   ├── home_overview.md
│   ├── home_screen.yml
│   ├── reporting_standardization.yaml
│   └── zoho_crm_home_dom_scan.md
│
├── leads/
│   ├── leads_detailed_documentation.md
│   ├── leads_full_structure.yaml
│   ├── leads_lifecycle.puml
│   ├── leads_overview.md
│   ├── reporting_standardization.yaml
│   └── leads_creation/
│       ├── flow.md
│       └── screens.yaml
│
├── contacts/
│   ├── contacts_detailed_documentation.md
│   ├── contacts_full_structure.yaml
│   ├── contacts_overview.md
│   └── reporting_standardization.yaml
│
├── accounts/
│   ├── accounts_full_structure.yaml
│   ├── accounts_lifecycle.puml
│   ├── accounts_overview.md
│   ├── reporting_standardization.yaml
│   └── zoho_crm_accounts_page_scan.yaml   (original DOM scan — list view only)
│
├── deals/
│   ├── Dealsflow.md
│   ├── deals_full_structure.yaml
│   ├── deals_lifecycle.puml
│   ├── deals_overview.md
│   └── reporting_standardization.yaml
│
├── task/
│   ├── task_lifecycle.puml
│   ├── tasks_full_structure.yaml
│   ├── tasks_overview.md
│   ├── Tasks.md
│   └── reporting_standardization.yaml
│
├── employ-porfolio/
│   ├── EmployeePortfolio.md
│   ├── employee_portfolio_full_structure.yaml
│   ├── employee_portfolio_overview.md
│   └── reporting_standardization.yaml
│
├── projects-porfolio/
│   ├── projects_porfolio.puml
│   ├── ProjectsPortfolio.md
│   ├── projects_portfolio_overview.md
│   └── reporting_standardization.yaml
│
├── Sellbot-plan/
│   └── SellBot_Developer_Specific.yml     ⚠️ NOT linked to any screen — see note below
│
├── AUDIT_REPORT.md
├── CLAUDE.md
└── README.md
```

---

## File Types — What Each Does

| File | Purpose |
|---|---|
| `{screen}_screen.yml` / `{screen}_full_structure.yaml` | Machine-readable layout — page metadata, list view columns, filter panel, toolbar actions, create form fields with types and defaults |
| `{screen}_detailed_documentation.md` / `{screen}.md` / `{screen}flow.md` | Full DOM scan — numbered sections: page identity, layout, sidebar, filter panel, records list, create form, interaction map, module context |
| `{screen}_lifecycle.puml` | PlantUML state diagram — list → create → detail flow, status transitions, cross-module links. **Exists in `home/`, `leads/`, `accounts/`, `deals/`, `task/`, `projects-porfolio/`** |
| `{screen}_overview.md` | Business context — why the module exists, who uses it, workflow position, URL reference table |
| `reporting_standardization.yaml` | Audience-split view of the module — Business Owner / Promoter / Internal Team sections |
| `{screen}_creation/flow.md` | Step-by-step create form walkthrough — all fields, types, required markers, defaults, save / cancel behavior |
| `{screen}_creation/screens.yaml` | Machine-readable create form — field IDs, types, defaults, navigation results per button |

---

## Module Quick Reference

| Module | Folder | Internal Name | Records | Lifecycle Diagram | Reverse Eng. Ready |
|---|---|---|---|---|---|
| Home Dashboard | `home/` | Home | — | ✅ `home_lifecycle.puml` | ✅ 82% (nav only) |
| Leads | `leads/` | Leads | 2,077 | ✅ `leads_lifecycle.puml` | ✅ 93% |
| Contacts | `contacts/` | Contacts | 26 | ❌ Missing | ✅ 90% |
| Accounts | `accounts/` | Accounts | 11 | ✅ `accounts_lifecycle.puml` | ⚠️ 62% — create form not scanned |
| Deals | `deals/` | Potentials | 9 | ✅ `deals_lifecycle.puml` | ✅ 95% |
| Tasks | `task/` | Tasks | 4,276 | ✅ `task_lifecycle.puml` | ✅ 98% |
| Employee Portfolio | `employ-porfolio/` | CustomModule5 | 8 | ❌ Missing | ✅ 96% |
| Projects Portfolio | `projects-porfolio/` | CustomModule3 | 3 | ✅ `projects_porfolio.puml` | ✅ 94% |

### Modules Visible in CRM — Not Yet Documented

| Module | Internal Name |
|---|---|
| Meetings | Events |
| Calls | Calls |
| Customer Feedback | CustomModule7 |
| Prospecting Leads | CustomModule1 |
| Logs | CustomModule4 |
| Scheduler | CustomModule6 |
| Voice of the Customer | (new — appeared 2026-02-26) |

---

## CRM Workflow

```
[Enquiry / Ad / Walkin / Social Media]
               ↓
           [LEADS]
        2,077 records
   Blueprint: Lead Qualification
   Stages: Lead Bucket → Attempted → BANT
           → Site Visit → Qualify Out / Junk
               ↓ converted
    ┌──────────┼──────────┐
    ↓          ↓          ↓
[CONTACTS] [ACCOUNTS]  [DEALS]
 26 records  11 records  9 records
               ↓
 [TASKS] — 4,276 follow-up actions
 Telecallers: Sumathi, Vijayasri
 BDMs: Arun pandian, Dinesh kumar,
       Vinoth kumar, Moorthy, Radhakrishnan
               ↓
 [EMPLOYEE PORTFOLIO] — 8 staff records
 (source of Telecaller + BDM lookups)
               ↓
 [PROJECTS PORTFOLIO] — 3 properties
 (the products being sold:
  Mettupalayam, Mullai Nagar, Eswara Nagar)
```

---

## Key Organisation Facts

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | `60043078423` |
| Base URL | `https://crm.zoho.in/crm/org60043078423/` |
| Admin email | `kurinjeecrm01@gmail.com` |
| Admin phone | `9597736066` |
| CRM Licence | 1 user (limit reached — system alert visible on create forms) |
| Active Blueprint | Lead Qualification |
| Active Telecallers | Sumathi (`955332000005376001`), Vijayasri (`955332000005376006`) |
| Active BDMs | Arun pandian, Dinesh kumar, Vinoth kumar, Moorthy, Radhakrishnan |

---

## Audit Status

Full details in `AUDIT_REPORT.md`.

| Module | Coverage | Verdict |
|---|---|---|
| Home | 82% | Safe — navigation only |
| Leads | 93% | ✅ Safe for Reverse Engineering |
| Contacts | 90% | ✅ Safe for Reverse Engineering |
| Accounts | 62% | ❌ Needs Fix — scan create form first |
| Deals | 95% | ✅ Safe for Reverse Engineering |
| Tasks | 98% | ✅ Safe for Reverse Engineering |
| Employee Portfolio | 96% | ✅ Safe for Reverse Engineering |
| Projects Portfolio | 94% | ✅ Safe for Reverse Engineering |

---

## Sellbot-plan — Disconnected from This Repository

The `Sellbot-plan/` folder contains **`SellBot_Developer_Specific.yml`** — a 14-step WhatsApp-driven sales automation design for real estate lead management (WhatsApp via WATI/Interakt, Google Calendar, Zoho Analytics).

**This blueprint is NOT used anywhere in this repository and is NOT linked to any screen documentation.**

| What it is | What it is NOT |
|---|---|
| A planning / design document | A scanned UI artifact |
| Intended future automation | Confirmed live CRM configuration |
| Self-contained blueprint | Referenced by any screen folder |

**Do not use `Sellbot-plan/` as evidence of live CRM behaviour when reverse engineering.**

To verify whether SellBot-360 automation is active, independently scan:
- CRM → Settings → Workflow Rules
- CRM → Settings → Blueprints
- CRM → Settings → Functions
