# Zoho CRM UI Screen Analysis

**Organisation:** Kurinjee Promoters (Org ID: `60043078423`)
**Industry:** Real Estate — Property Sales (South India)
**Platform:** Zoho CRM (`crm.zoho.in`)
**Scan Date:** 2026-02-27 (updated)

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
│   ├── contacts_lifecycle.puml
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
│   ├── employee_porfolio.puml
│   ├── employee_portfolio_full_structure.yaml
│   ├── employee_portfolio_overview.md
│   └── reporting_standardization.yaml
│
├── projects-porfolio/
│   ├── projects_porfolio.puml
│   ├── ProjectsPortfolio.md
│   ├── projects_portfolio_full_structure.yaml   ← NEW (2026-02-27)
│   ├── projects_portfolio_overview.md
│   └── reporting_standardization.yaml
│
├── scribe-screenshots/
│   ├── screenshot-link-url.txt             (all 19 ScribeHow viewer URLs)
│   └── flow/                               (19 Scribe flow files — step-by-step screenshots)
│       ├── lead_creation_scribe_flow.md
│       ├── lead_update_scribe_flow.md
│       ├── lead_delete_scribe_flow.md
│       ├── lead_related_list_scribe_flow.md
│       ├── lead_filter_scribe_flow.md
│       ├── lead_sort_scribe_flow.md
│       ├── lead_manage_columns_record_limit_scribe_flow.md
│       ├── lead_blueprint_scribe_flow.md
│       ├── lead_custom_view_scribe_flow.md
│       ├── module_link_flow_lead_scribe_flow.md
│       ├── contact_save_and_new_scribe_flow.md
│       ├── contact_clone_scribe_flow.md
│       ├── accounts_record_import_scribe_flow.md
│       ├── accounts_record_export_scribe_flow.md
│       ├── home_customize_homepage_scribe_flow.md
│       ├── deals_record_print_preview_scribe_flow.md
│       ├── task_create_scribe_flow.md
│       ├── settings_edit_role_scribe_flow.md
│       └── settings_add_role_scribe_flow.md
│
├── Sellbot-plan/
│   └── SellBot_Developer_Specific.yml     (14-step automation blueprint — 95KB)
│
├── sellbot/
│   └── ui_screen/                          ← NEW (2026-02-27) — SellBot UI Implementation Plan
│       ├── 00_overview.md                  (master map: Zoho module → SellBot step, patterns, template registry)
│       ├── 01_project_setup.md             (Step 1: Project Assets Library)
│       ├── 02_lead_capture.md              (Step 2: Lead Capture Form)
│       ├── 03_welcome_automation.md        (Step 3: Auto Welcome WhatsApp + Email)
│       ├── 04_lead_assignment.md           (Step 4: Lead Assignment + 5 Call Attempt Tasks)
│       ├── 05_lead_qualification.md        (Step 5: BANT 8-Question Scoring + Lead_Type)
│       ├── 06_site_visit_invitation.md     (Step 6: Site Visit Booking + Google Calendar)
│       ├── 07_site_visit_reminders.md      (Step 7: 24hr Reminder + 8-Week Cycle)
│       ├── 08_post_visit_feedback.md       (Step 8: Mobile Proof Form + Objection Capture)
│       ├── 09_60day_nurturing.md           (Step 9: 7 Objection Tracks × 8 Weekly WA Templates)
│       ├── 10_crm_dashboard.md             (Step 10: 4 Dashboard Views + Monthly PDF)
│       ├── 11_client_feedback.md           (Step 11: 28-Question Post-Registration Form)
│       ├── 12_referral_program.md          (Step 12: Referral Capture + Reward Automation)
│       ├── 13_business_owner_dashboard.md  (Step 13: 10-Section Master Dashboard)
│       ├── 14_longterm_engagement.md       (Step 14: Festival Broadcasts + 90-Day Re-activation)
│       └── field_inventory.md              (All fields: Leads/Tasks/Feedback/Referral/Feedback/Projects)
│
├── VERIFIED_REPORT.md                      ← NEW (2026-02-27) — full coverage audit (avg 68%)
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
| `{screen}_lifecycle.puml` | PlantUML state diagram — list → create → detail flow, status transitions, cross-module links |
| `{screen}_overview.md` | Business context — why the module exists, who uses it, workflow position, URL reference table |
| `reporting_standardization.yaml` | Audience-split view of the module — Business Owner / Promoter / Internal Team sections |
| `{screen}_creation/flow.md` | Step-by-step create form walkthrough — all fields, types, required markers, defaults, save / cancel behavior |
| `{screen}_creation/screens.yaml` | Machine-readable create form — field IDs, types, defaults, navigation results per button |
| `scribe-screenshots/flow/*.md` | Scribe flow files — extracted step-by-step screenshots confirming exact UI labels, button names, field values, and navigation paths |

---

## Scribe Flows — All 19 Documented

Scribe flows are screen recordings that confirm exact UI behaviour. Each flow file in `scribe-screenshots/flow/` maps to a ScribeHow viewer link below.

| # | Title | Module | Local File | ScribeHow Link |
|---|---|---|---|---|
| 1 | Lead Create Record | Leads | `lead_creation_scribe_flow.md` | [View](https://scribehow.com/viewer/Create_New_Lead_Record_in_Zoho_CRM__Hkm4hw2XTB6w3-sbh_Wmgg) |
| 2 | Lead Update Record | Leads | `lead_update_scribe_flow.md` | [View](https://scribehow.com/viewer/Update_Lead_in_Zoho_CRM__z7bhcBkxSbeu2TgL1vuegQ) |
| 3 | Lead Delete Record | Leads | `lead_delete_scribe_flow.md` | [View](https://scribehow.com/viewer/How_to_Delete_a_Lead_in_Zoho_CRM__QYcZwYelSda4EbSDpH_HwA) |
| 4 | Lead Related List | Leads | `lead_related_list_scribe_flow.md` | [View](https://scribehow.com/viewer/Lead__Related_List_Flow__vgDNSGhiR-SFdFjLXWSeuw) |
| 5 | Lead Filter Flow | Leads | `lead_filter_scribe_flow.md` | [View](https://scribehow.com/viewer/Filter_in_Leads_List_View__162JA0TtTgOb6w3THkMqSw) |
| 6 | Lead Sort Flow | Leads | `lead_sort_scribe_flow.md` | [View](https://scribehow.com/viewer/Sort_By_Flow_in_Zoho_CRMLead__y3uy3X_kSwGGCPJwnA9R7g) |
| 7 | Manage Columns and Record Limit | Leads | `lead_manage_columns_record_limit_scribe_flow.md` | [View](https://scribehow.com/viewer/Manage_Columns_and_Record_Limit_in_Zoho_CRM__WLwf_7s1Tni7Pol1RQOEKg) |
| 8 | Lead Blueprint Flow | Leads | `lead_blueprint_scribe_flow.md` | [View](https://scribehow.com/viewer/Lead_Module__BluePrint_Flow_in_CRM__CzUDuGLrRw2IfepoHwWqsg) |
| 9 | Lead Custom View | Leads | `lead_custom_view_scribe_flow.md` | [View](https://scribehow.com/viewer/Lead__Custom_View__VAC1y59USAyVSDfMyKlRFA) |
| 10 | Module Link (Lead → WorkDrive) | Leads | `module_link_flow_lead_scribe_flow.md` | [View](https://scribehow.com/viewer/Module__Link_Flow_Lead__IrDZtKcKSYmqnroEdZnHhA) |
| 11 | Save and New Flow (Contact) | Contacts | `contact_save_and_new_scribe_flow.md` | [View](https://scribehow.com/viewer/Module_Save_with_New_Flow_in_Zoho_CRMContact__xkCXbj56Q_Sadha20WRGDQ) |
| 12 | Clone Flow (Contact) | Contacts | `contact_clone_scribe_flow.md` | [View](https://scribehow.com/viewer/Module_Clone_Flow_in_Zoho_CRM_Contant__qcO_Tqb7QEmg88qVuQTWTA) |
| 13 | Record Import (Accounts) | Accounts | `accounts_record_import_scribe_flow.md` | [View](https://scribehow.com/viewer/Module_Record_Import_in_CRM_Accounts__Twz5-RybQgu5mUlD49YU-w) |
| 14 | Export Records (Accounts) | Accounts | `accounts_record_export_scribe_flow.md` | [View](https://scribehow.com/viewer/Export_Module_Records_in_CRM_Accounts__3K4_k1k4TqWsZYdqsdKO7Q) |
| 15 | Customize Homepage | Home | `home_customize_homepage_scribe_flow.md` | [View](https://scribehow.com/viewer/Customize_Homepage_in_Zoho_CRM__ERCScDBmQbuLkgiaJL1_YQ) |
| 16 | Record Print Preview (Deals) | Deals | `deals_record_print_preview_scribe_flow.md` | [View](https://scribehow.com/viewer/Module_Record_Print_Preview_in_Zoho_CRM__yue5DQAESPa0fGEmHaoG-Q) |
| 17 | Create a New Task | Tasks | `task_create_scribe_flow.md` | [View](https://scribehow.com/viewer/Create_a_New_Task_in_Zoho_CRM__Xm-2tDfLRoyy3IfffP40Tg) |
| 18 | Edit Role | Settings | `settings_edit_role_scribe_flow.md` | [View](https://scribehow.com/viewer/Edit_Role_in_Zoho_CRM__YMGhlp7FShaS0TUB1gdNRg) |
| 19 | Add Role | Settings | `settings_add_role_scribe_flow.md` | [View](https://scribehow.com/viewer/Create_a_New_Role_in_Zoho_CRM__JwpIwIBsT4Ol-UFLj7qQgQ) |

### Key Confirmations from Scribe Flows

| Finding | Confirmed By |
|---|---|
| `Save and New` button in Contact create form | Flow 11 |
| `Estimated Budget ₹` custom currency field in Contact form | Flow 11 |
| Clone path: Detail View → ⋮ More → Clone | Flow 12 |
| `per_page=10` in list view URL params | Flow 12 |
| Accounts `Actions` button label (toolbar overflow) | Flow 14 |
| Export dialog: "Fields from custom view" / "All Fields" radio options | Flow 14 |
| Import wizard: CSV/XLS/XLSX, 5MB max, 30,000 records max | Flow 13 |
| Home page named "Kurinjee Promoters's Home", view type: Classic View | Flow 15 |
| Home page assigned to 2 Roles | Flow 15 |
| "Customize Home page" as primary CTA button label | Flow 15 |
| Print Preview: Detail View → ⋮ More → Print Preview (Deals) | Flow 16 |
| `/tab/Potentials/` as Deals internal URL | Flow 16 |
| Task Status "Attempt" — custom value (not standard Zoho) | Flow 17 |
| Telecaller: Sumathi, Approver: Manager Testing | Flow 17 |
| Role hierarchy: Administrator → Manager → Telecaller (Sumathi) | Flows 18–19 |
| `/settings/roles` URL and "New Role" button label | Flows 18–19 |

---

## Module Quick Reference

| Module | Folder | Internal Name | Records | Lifecycle Diagram | Scribe Flows | Reverse Eng. Ready |
|---|---|---|---|---|---|---|
| Home Dashboard | `home/` | Home | — | ✅ `home_lifecycle.puml` | ✅ Flow 15 | ✅ 90% |
| Leads | `leads/` | Leads | 2,077 | ✅ `leads_lifecycle.puml` | ✅ Flows 1–10 | ✅ 98% |
| Contacts | `contacts/` | Contacts | 26 | ✅ `contacts_lifecycle.puml` | ✅ Flows 11–12 | ✅ 95% |
| Accounts | `accounts/` | Accounts | 11 | ✅ `accounts_lifecycle.puml` | ✅ Flows 13–14 | ⚠️ 75% — create form not scanned |
| Deals | `deals/` | Potentials | 9 | ✅ `deals_lifecycle.puml` | ✅ Flow 16 | ✅ 96% |
| Tasks | `task/` | Tasks | 4,276 | ✅ `task_lifecycle.puml` | ✅ Flow 17 | ✅ 99% |
| Employee Portfolio | `employ-porfolio/` | CustomModule5 | 8 | ✅ `employee_porfolio.puml` | ❌ None | ✅ 96% |
| Projects Portfolio | `projects-porfolio/` | CustomModule3 | 3 | ✅ `projects_porfolio.puml` | ❌ None | ✅ 94% |
| Settings — Roles | (see `home/home_screen.yml`) | — | 3 roles | — | ✅ Flows 18–19 | ✅ 90% |

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
| Role Hierarchy | Administrator (Sri/CEO) → Manager → Telecaller (Sumathi) |

---

## Audit Status

Full details in `VERIFIED_REPORT.md` (updated 2026-02-27, supersedes `AUDIT_REPORT.md`).

**Repository Average Coverage: 68%** (12-dimension × 8-module audit)

| Module | Coverage | Status |
|---|---|---|
| Leads | 92% | ✅ Ready for Reverse Engineering (10 Scribe flows) |
| Contacts | 75% | ✅ Ready |
| Deals | 78% | ✅ Ready |
| Accounts | 72% | ⚠️ Create form inferred — not directly scanned |
| Tasks | 68% | ✅ Ready (1 Scribe flow) |
| Home | 65% | ✅ Ready (1 Scribe flow) |
| Employee Portfolio | 42% | ⚠️ No Scribe flows recorded |
| Projects Portfolio | 45% | ⚠️ No Scribe flows recorded |

**Critical Gaps Remaining:**
- Employee Portfolio + Projects Portfolio: 0 Scribe flows (3 flows each pending)
- Approval workflows: undocumented across all modules
- Automation rules inventory: not yet captured

---

## SellBot-360™ — UI Implementation Plan

`Sellbot-plan/SellBot_Developer_Specific.yml` is a 14-step WhatsApp-driven sales
automation design for real estate lead management (WhatsApp via WATI, Google Calendar,
Zoho Analytics). **As of 2026-02-27, this blueprint is fully mapped to the Zoho CRM
reverse-engineering in `sellbot/ui_screen/`.**

### What `sellbot/ui_screen/` Contains

Each of the 14 SellBot steps has a dedicated implementation file that specifies:
- Which Zoho CRM module(s) and screens it maps to
- Exact field definitions (new fields + existing Zoho fields)
- Screen layout, form sections, and interaction states
- WhatsApp template text and merge fields
- Automation triggers and conditions
- Implementation delta — what changes from Zoho vs what is new in SellBot

### Key SellBot Sub-Modules (New — Not in Live Zoho)

| Sub-Module | Purpose | Step |
|---|---|---|
| Project Assets Library | Digital asset storage (brochure, videos, map, posters) | Step 1 |
| BANT Qualification Form | 8-question scoring → Hot/Warm/Cold/Junk | Step 5 |
| Site Visit Booking | Google Calendar integration + Visit_Status field | Step 6 |
| Site Visit Feedback | Mobile proof form (camera-only, geotagged) + objection capture | Step 8 |
| Referral Management | Referral capture, reward tracking, ambassador recognition | Step 12 |
| Client Feedback | 28-question post-registration form with NPS | Step 11 |

### New Fields Added to Leads Module (summary)

`Lead_Score_Total` · `Lead_Type` · `Visit_Status` · `Calendar_Event_ID` ·
`Reminder_Count` · `Visit_Verified` · `Objection_Status` · `Urgency_Level` ·
`TL_Approved_for_Closure` · `Attach_from_Project_Assets` · `Campaign_Name` ·
`Score_Revision_Log` · `Referral_Source` · `In_Nurture_Program` · `Nurture_Track`

**Do not use `Sellbot-plan/` or `sellbot/ui_screen/` as evidence of live Zoho CRM
behaviour.** These are implementation design documents, not confirmed live configuration.

To verify whether SellBot-360 automation is active in the live CRM, scan:
- CRM → Settings → Workflow Rules
- CRM → Settings → Blueprints
- CRM → Settings → Functions
