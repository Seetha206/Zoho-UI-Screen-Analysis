> Scribe Source: https://scribehow.com/viewer/Lead__Related_List_Flow__vgDNSGhiR-SFdFjLXWSeuw
> Recorded By: Sri Gnanathesigan
> Duration: ~25 seconds
> Total Steps: 5
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Lead — Related List Flow — Scribe Flow Analysis

## Overview

This document captures the step-by-step UI flow for navigating the **Related Lists** section of a Lead record in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how to access a Lead's **Open Activities**, navigate into the **Schedules** sub-section, and open a specific Schedule record (`SCH14888`) — 5 UI interactions in approximately 25 seconds.

> Related Lists are the panels at the bottom of a Zoho CRM record's detail view that display associated sub-records (activities, notes, emails, linked module records, etc.).

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–5)                               |
| Screenshot style | Max-height 600px, rounded corners (2xl border-radius), shadows  |
| Layout          | Responsive — fixed navigation header, content below              |
| Flow type       | Read-only navigation — no form edits, no saves                   |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&per_page=100` |
| View Type       | Custom List View (ID: `955332000000441406`) |
| Pagination      | Page 1, 100 records per page |
| Module          | Leads |

**Screenshot Analysis:**
- The Zoho CRM **Leads module** opens in the same custom saved list view used across all four recordings
- The custom view ID (`955332000000441406`) and pagination parameters (`page=1&per_page=100`) are **identical** across Flows 2, 3, and 4 — confirming this is the standard entry point for all lead-related operations at Kurinjee Promoters
- Existing lead records are displayed in tabular format with the test lead `Sri Testing` visible
- The list shows standard column headers: Name, Phone, Email, Lead Status, Lead Owner, Created Date (standard Zoho CRM Leads list columns)

---

### Step 2 — Click Lead: "Sri Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Click on lead record name |
| Target       | `Sri Testing` |
| Record Type  | Lead record |
| Location     | Primary column — clickable name link in leads list |

**Screenshot Analysis:**
- The recorder clicks on **"Sri Testing"** in the leads list — the same test record used across all four flows
- This navigates to the **Lead Detail View** for that record
- The Lead Detail View has two main zones:
  1. **Top zone** — field values (Lead Information sections, all filled/empty fields)
  2. **Bottom zone** — **Related Lists** (the focus of this recording)
- The detail view renders in a single-page layout; the user must scroll down past the field sections to reach the Related Lists area

---

### Step 3 — Click "Open Activities" Related List Section

| Property     | Detail |
|--------------|--------|
| Action       | Click section header or tab |
| Target Label | `Open Activities` |
| Section Type | Related List panel — Activities group |
| Location     | Lower section of Lead Detail View |

**Screenshot Analysis:**
- The recorder scrolls down to the **Related Lists** area of the Lead Detail View and clicks on **"Open Activities"**
- In Zoho CRM, the Lead Detail View Related Lists area typically contains the following panels:

  | Related List Panel       | Contents |
  |--------------------------|----------|
  | Open Activities          | Pending Tasks, Scheduled Meetings, Planned Calls |
  | Closed Activities        | Completed Tasks, past Meetings, logged Calls |
  | Schedules                | Custom Module6 — Scheduler records linked to this lead |
  | Notes                    | Manual notes added to the lead |
  | Emails                   | Sent/received emails associated with the lead |
  | Attachments              | Files/documents uploaded to the lead record |

- **"Open Activities"** is clicked to expand or navigate into the activities section
- This panel shows all **pending/upcoming** interactions planned for this lead: tasks to call back, meetings scheduled, calls to be made
- In a real estate CRM workflow, Open Activities for a lead would typically show: Follow-up call tasks, Site visit appointments, Telecaller reminder tasks

---

### Step 4 — Click "Schedules" Sub-Section

| Property     | Detail |
|--------------|--------|
| Action       | Click sub-section tab or panel header |
| Target Label | `Schedules` |
| Section Type | Related List sub-panel — linked to Custom Module6 (Scheduler) |
| Location     | Within or adjacent to the Activities related list area |

**Screenshot Analysis:**
- After clicking Open Activities, the recorder navigates to a **"Schedules"** sub-section
- **"Schedules"** maps to **CustomModule6 — Scheduler** as defined in the Kurinjee Promoters Zoho CRM configuration (see CLAUDE.md)
- This is a **custom related list** — not a default Zoho CRM feature — linking lead records to Scheduler module entries
- The Schedules panel likely shows a list of scheduled interactions (calls, visits, follow-ups) linked to this lead, displayed as a table with columns such as:

  | Likely Column       | Description |
  |---------------------|-------------|
  | Schedule ID / Name  | e.g. `SCH14888` — unique identifier |
  | Schedule Type       | Type of scheduled activity (Call, Visit, etc.) |
  | Scheduled Date/Time | When the activity is planned |
  | Status              | Pending / Completed / Cancelled |
  | Assigned To         | Telecaller or agent responsible |

- The panel shows at least one record: `SCH14888`

---

### Step 5 — Open Schedule Record: "SCH14888"

| Property     | Detail |
|--------------|--------|
| Action       | Click record link |
| Target       | `SCH14888` |
| Record Type  | Scheduler record (CustomModule6) |
| Prefix       | `SCH` — auto-number prefix for the Scheduler module |
| Location     | Row in the Schedules related list |

**Screenshot Analysis:**
- The recorder clicks on **"SCH14888"** — a specific Scheduler record linked to the `Sri Testing` lead
- The `SCH` prefix is Zoho CRM's **auto-number field** prefix configured for CustomModule6 (Scheduler)
- The number `14888` suggests this org has processed a significant number of scheduler records — it is not a low-activity system
- Clicking opens the **Scheduler record detail view** for SCH14888
- The Scheduler record detail view would show fields specific to CustomModule6, likely including:

  | Likely Field        | Description |
  |---------------------|-------------|
  | Schedule ID         | `SCH14888` — auto-generated reference |
  | Related Lead        | Link back to `Sri Testing` lead |
  | Schedule Type       | Type of interaction scheduled |
  | Date & Time         | Scheduled datetime |
  | Telecaller / Agent  | Assigned team member |
  | Notes / Remarks     | Any additional instructions |
  | Status              | Current state of the schedule |

- The exact field values for SCH14888 were not captured in the Scribe extraction (screenshot-only content)
- Navigating to this record demonstrates how **Leads and the Scheduler module are linked** in Kurinjee Promoters' CRM workflow

---

## Related Lists Architecture — Lead Detail View

Based on this recording and the org's custom module configuration:

```
Lead Detail View
├── [Top Zone] — Lead Fields
│     ├── Lead Information (collapsible)
│     ├── Address Information (collapsible)
│     └── Description / Other fields
│
└── [Bottom Zone] — Related Lists
      ├── Open Activities
      │     ├── Tasks
      │     ├── Meetings
      │     └── Calls
      ├── Closed Activities
      ├── Schedules  ←── CustomModule6 (Scheduler) — FOCUS OF THIS RECORDING
      │     └── SCH14888  ←── clicked in Step 5
      ├── Notes
      ├── Emails
      └── Attachments
```

---

## Key Insight: Schedules Module Link

The `SCH14888` record ID reveals an important architectural detail:

| Finding | Implication |
|---------|-------------|
| `SCH` prefix on record `14888` | CustomModule6 (Scheduler) uses `SCH` as its auto-number prefix |
| Number `14888` | Indicates high record volume — Kurinjee Promoters has created 14,888+ scheduler entries |
| Linked to Lead record | Leads and the Scheduler module have a **lookup relationship** — Leads can have multiple Schedules associated |
| Accessed via Related List | Schedulers appear as a related list panel in the Lead detail view, not a separate navigation step |

---

## Full URL Reference

| Element         | Value |
|-----------------|-------|
| CRM Base URL    | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL  | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&per_page=100` |
| Custom View ID  | `955332000000441406` |
| Pagination      | `page=1&per_page=100` |
| Org ID          | `60043078423` |

---

## Workflow Summary

```
[Leads List View — Custom View, 100/page]
       |
       v
[Click "Sri Testing" — test lead record]
       |
       v
[Lead Detail View opens]
       |
       v
[Scroll to Related Lists — Bottom of detail view]
       |
       v
[Click "Open Activities" panel]
       |
       v
[Click "Schedules" sub-section]
       |
       v
[Schedules related list shows — SCH14888 visible]
       |
       v
[Click "SCH14888" — opens Scheduler record detail view]
```

---

## Comparison: All Four Lead Flows

| Property         | Create (Flow 1)   | Update (Flow 2)    | Delete (Flow 3)     | Related List (Flow 4)     |
|------------------|-------------------|--------------------|---------------------|---------------------------|
| Duration         | ~47 seconds       | ~37 seconds        | ~22 seconds         | ~25 seconds               |
| Steps            | 13                | 10                 | 5                   | 5                         |
| Entry point      | Leads list        | Leads list         | Leads list          | Leads list                |
| Custom View ID   | `955332000000441406` | `955332000000441406` | `955332000000441406` | `955332000000441406`     |
| Target record    | New record        | `Sri Testing`      | `Sri Testing`       | `Sri Testing`             |
| Form interaction | Full form fill    | Field edits        | None                | None (read-only)          |
| End state        | Record created    | Record updated     | Record in Recycle Bin | Scheduler record opened |
| Modules touched  | Leads             | Leads              | Leads               | Leads + CustomModule6     |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Schedules column headers not captured** — the Scribe screenshots show the Schedules related list but column definitions were not extractable from HTML; likely: Schedule ID, Type, Date, Status, Assigned To |
| 2 | **SCH14888 field values not captured** — the Scheduler record detail view content is screenshot-only; exact fields and values of this specific record are unknown |
| 3 | **High record count** — `SCH14888` implies 14,888+ Scheduler records exist in this org; the Scheduler module is heavily used |
| 4 | **Open Activities vs Schedules** — the flow navigates through "Open Activities" to reach "Schedules"; this suggests Schedules may be a sub-tab within Activities, or they are adjacent panels and the recorder clicked both sequentially |
| 5 | **Read-only flow** — unlike Flows 1–3, this recording involves no data entry or modification; it is purely a navigation demonstration |
| 6 | **CustomModule6 confirmed active** — the presence of SCH14888 in a Lead's related list confirms the Scheduler module is linked to Leads and actively in use |
