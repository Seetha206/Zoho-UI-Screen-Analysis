# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This is a **Zoho CRM UI Screen Analysis** documentation project for **Kurinjee Promoters** (Org ID: `60043078423`), a real estate company. It captures layout structures, DOM hierarchies, navigation flows, and field definitions across Zoho CRM screens. There is no executable code — all files are structured documentation in YAML, Markdown, and PlantUML formats.

The project also contains the **SellBot-360™** automation blueprint (`Sellbot-plan/`), a 14-step WhatsApp-driven lead management system.

## Repository Structure

```
Zoho UI-Screen Analysis/
├── home/                    # Home Dashboard (original 3-file format)
├── leads/                   # Leads module + leads_creation/ subdir
├── contacts/                # Contacts module + contacts_creation/ subdir
├── deals/                   # Deals/Potentials module
├── task/                    # Tasks module (single DOM scan file)
├── employ-porfolio/         # Employee Portfolio (CustomModule5)
├── projects-porfolio/       # Projects Portfolio (CustomModule3)
├── Sellbot-plan/            # SellBot-360 automation blueprint (SellBot_Developer_Specific.yml)
├── sellbot/
│   └── ui_screen/           # SellBot UI Implementation Plan — 16 files (Steps 1–14)
├── VERIFIED_REPORT.md       # Full coverage audit (updated 2026-02-27, avg 68%)
└── AUDIT_REPORT.md          # Earlier audit (superseded by VERIFIED_REPORT.md)
```

## File Naming Conventions

File patterns vary by how recently the screen was documented. Two conventions exist:

### Mature screens (home, leads, contacts)
| File | Purpose |
|---|---|
| `{screen}_screen.yml` or `{screen}_full_structure.yaml` | YAML layout / full field list |
| `{screen}_detailed_documentation.md` | Full DOM scan (page identity, field tables, interactions) |
| `{screen}_lifecycle.puml` | PlantUML state diagram of navigation flow |
| `{screen}_overview.md` | Business context, user roles, module relationships |
| `{screen}_creation/flow.md` + `screens.yaml` | Step-by-step record creation flow |

### Newer/lighter screens (task, employ-porfolio, projects-porfolio, deals)
| File | Purpose |
|---|---|
| `Tasks.md` / `EmployeePortfolio.md` / etc. | Combined DOM scan (all sections in one file) |
| `deals_lifecycle.puml` | Navigation flow diagram |
| `deals_overview.md` | Business context |

### SellBot UI Implementation Plan (`sellbot/ui_screen/`)
| File | Purpose |
|---|---|
| `00_overview.md` | Master map: Zoho module → SellBot step, UI patterns, WhatsApp template registry, new field list |
| `01_project_setup.md` – `14_longterm_engagement.md` | One file per SellBot step: screen design, field tables, automation triggers, implementation delta |
| `field_inventory.md` | Complete field list for all 7 SellBot modules |

Each step file structure:
```
## 1. SellBot Objective
## 2. Source Zoho CRM Analysis   — which module(s) this maps to
## 3. Screen / Form Design       — fields, layout, interactions
## 4. Automation Triggers        — conditions and actions
## N. Implementation Delta       — what's new vs existing Zoho patterns
```

## Document Structure Inside DOM Scan Files

DOM scan files open with a metadata header block, then use numbered sections:

```
> Scan Date: YYYY-MM-DD
> Source: Live DOM — read_page + screenshot
> Organisation: Kurinjee Promoters (org60043078423)
> No guesses. No summaries. Only what is visible in the UI.

## 1. Page Identity       — YAML block: page_identity (URL, view IDs, record counts)
## 2. Layout Overview     — Header, sidebar, main content zones
## 3. ...                 — Widget details, field tables, interactions
## N. Component Hierarchy — Indented tree of UI nesting
## N+1. Navigation Map    — Table: Element | Destination | Trigger | Target URL
```

## YAML Screen File Structure

```yaml
page:
  name: Home
  module: Home Dashboard
  url: /crm/org60043078423/tab/Home/begin
  organization: Kurinjee Promoters
  org_id: "60043078423"

layout:
  header: { search_bar: ..., quick_actions: [...], nav_icons: [...] }
  sidebar:
    modules: [{ label: Leads, url: /tab/Leads }]
  main_content:
    widgets:
      row_1: { type: kpi_summary, items: [...] }
  footer: ...
```

Widget types: `kpi | kpi_summary | table | chart`. Each interactive element should include `id`, `label`, `type`, and `link` where applicable.

## PlantUML Navigation Files

Use `.puml` extension with `@startuml`/`@enduml` markers. Skinparam colors: background `#EEF4FF`, border `#4A6CF7`. Show module state transitions from `[*]` through list → detail → edit.

## Organization Context

- **Base URL:** `https://crm.zoho.in/crm/org60043078423/`
- **Standard modules:** Leads, Contacts, Accounts, Deals, Tasks, Meetings, Calls, Reports, Analytics
- **Custom modules:**

| Module | Internal Name | Records |
|---|---|---|
| Projects Portfolio | `CustomModule3` | 3 |
| Employee Portfolio | `CustomModule5` | 8 |
| Customer Feedback | `CustomModule7` | — |
| Prospecting Leads | `CustomModule1` | — |
| Logs | `CustomModule4` | — |
| Scheduler | `CustomModule6` | — |

- **Calendar URL pattern:** `/crm/org60043078423/calendar?date={DD-MM-YYYY}&viewType={view}`

## CRM Workflow

```
LEADS (2,077) ──▶ CONTACTS (26) ──▶ DEALS (9)
Blueprint stages: Lead Qualification → Site Visit → Booking → Closed Won
```

## SellBot-360™ Workflow (14 steps — implementation plan in sellbot/ui_screen/)

```
Step 1: Project Setup → Step 2: Lead Capture → Step 3: Auto Welcome
→ Step 4: Assignment + 5 Call Attempts → Step 5: BANT Qualification
→ Step 6: Site Visit Invitation → Step 7: Visit Reminders (8-week)
→ Step 8: Post-Visit Feedback + Objection Capture
→ Step 9: 60-Day Nurturing (7 objection tracks × 8 WA templates)
→ Step 10: CRM Dashboard → Step 11: Client Feedback
→ Step 12: Referral Program → Step 13: Business Owner Dashboard
→ Step 14: Long-Term Brand Engagement (90-day re-activation)
```

Key new modules: Site_Visit_Feedback · Referral_Management · Client_Feedback · Project_Assets_Library
Key new Lead fields: Lead_Type (Hot/Warm/Cold/Junk) · Lead_Score_Total · Visit_Status · Reminder_Count · Objection_Status

## Adding a New Screen

1. Create a subdirectory named after the screen.
2. Follow the mature-screen pattern for comprehensive documentation; single-file pattern is acceptable for simpler screens.
3. The DOM scan header must include `Scan Date`, `Source`, and `Organisation`.
4. Use existing files as templates — `leads/` is the most complete reference.
