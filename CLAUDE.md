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
└── Sellbot-plan/            # SellBot-360 automation blueprint
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

## Adding a New Screen

1. Create a subdirectory named after the screen.
2. Follow the mature-screen pattern for comprehensive documentation; single-file pattern is acceptable for simpler screens.
3. The DOM scan header must include `Scan Date`, `Source`, and `Organisation`.
4. Use existing files as templates — `leads/` is the most complete reference.
