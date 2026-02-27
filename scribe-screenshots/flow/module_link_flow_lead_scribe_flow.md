> Scribe Source: https://scribehow.com/viewer/Module__Link_Flow_Lead__IrDZtKcKSYmqnroEdZnHhA
> Recorded By: Sri
> Duration: ~23 seconds
> Total Steps: 2
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Module — Link Flow (Lead) — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **linking a Lead record to Zoho WorkDrive** from within the Zoho CRM Leads module, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user accesses the WorkDrive integration panel from a Lead record detail view — 2 UI interactions in approximately 23 seconds.

> The **Link Flow** in Zoho CRM refers to the integration between CRM module records and **Zoho WorkDrive** — Zoho's cloud document management platform. From any CRM record (Lead, Contact, Deal, etc.), users can access the "WorkDrive" section in the record's detail view to attach, view, or browse files and folders associated with that record. This allows sales teams to attach brochures, site visit notes, property documents, or client communications directly to the lead.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–2)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Record detail view — WorkDrive integration access                   |
| Notable pattern | Shortest captured flow — 2 steps, 23 seconds; entirely navigation-based |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Click on Lead Record "Sri Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Click record name |
| Target       | `Sri Testing` |
| Element Type | Lead record row / hyperlinked record name in list view |
| Location     | Leads list view — record name column |
| Module       | Leads |

**Screenshot Analysis:**
- The recorder clicks on a lead record named **"Sri Testing"** in the Leads list view
- "Sri Testing" is a **test lead record** created by the recorder (Sri) during earlier flows — identified by first name in the Name column
- Clicking the record name navigates from the list view to the **Lead Detail View** for "Sri Testing"
- The Lead Detail View layout in Zoho CRM:

  ```
  ┌─────────────────────────────────────────────────────┐
  │  [Lead Name: Sri Testing]                           │
  │  [Lead Stage] [Owner] [Phone] [Email]               │
  ├──────────────────────────┬──────────────────────────┤
  │  INFORMATION             │  RELATED LIST            │
  │  • Lead Source           │  • Activities            │
  │  • Company               │  • Open Activities       │
  │  • Phone / Mobile        │  • Emails                │
  │  • Email                 │  • Attachments           │
  │  • Lead Status           │  • WorkDrive  ← target   │
  │  • Rating                │  • Scheduler (Custom)    │
  │  • Annual Revenue        │  • Notes                 │
  └──────────────────────────┴──────────────────────────┘
  ```

- The **WorkDrive** section appears in the right panel or as a tab/related list section within the record detail view
- After clicking the record name, the URL changes to a pattern like:
  `https://crm.zoho.in/crm/org60043078423/tab/Leads/{record_id}`

---

### Step 2 — Click "Workdrive"

| Property     | Detail |
|--------------|--------|
| Action       | Click integration link / section |
| Target       | `Workdrive` |
| Element Type | Related list section label / WorkDrive integration panel toggle |
| Location     | Lead detail view — related list / sidebar area |
| Integration  | Zoho WorkDrive ↔ Zoho CRM |

**Screenshot Analysis:**
- From the Lead detail view of "Sri Testing", the recorder clicks the **"Workdrive"** link/panel
- In Zoho CRM, WorkDrive integration appears as:
  - A **related list section** in the right panel of the record detail view (labeled "WorkDrive" or "Documents")
  - A **tab** within the record if the WorkDrive widget has been configured in the page layout
  - A **button** labeled "Link to WorkDrive" or similar if the record has not yet been linked to a WorkDrive folder
- Clicking "Workdrive" opens one of these states:

  | State | Description |
  |-------|-------------|
  | **Already linked** | Opens the associated WorkDrive folder — shows files/subfolders for this lead |
  | **Not yet linked** | Shows a "Link" dialog — prompts user to select or create a WorkDrive folder to associate |
  | **WorkDrive panel** | Expands the WorkDrive section inline — shows folder contents within the CRM record |

- For the **Kurinjee Promoters** real estate context, WorkDrive folders linked to leads would typically contain:

  | File Type         | Purpose |
  |-------------------|---------|
  | Property brochures (PDF) | Shared with lead during enquiry |
  | Site visit notes (Doc)   | Recorded after physical visits |
  | Pricing sheets (Sheet)   | Budget and unit comparison |
  | Call recordings (Audio)  | For quality monitoring |
  | Booking forms (PDF)      | When lead converts to Deal |

- The WorkDrive URL pattern when opened from CRM:
  `https://workdrive.zoho.in/home/teams/{team_id}/ws/{workspace_id}/`

---

## Zoho WorkDrive ↔ CRM Integration — Architecture

### How WorkDrive Integrates with Zoho CRM

```
ZOHO CRM (Lead Record)
       │
       │  "Link to WorkDrive" / "WorkDrive" section
       ▼
ZOHO WORKDRIVE
├── Team Folder: Kurinjee Promoters
│   ├── Workspace: CRM Documents
│   │   ├── Leads/
│   │   │   ├── Sri Testing/          ← Auto-created per record (optional)
│   │   │   │   ├── brochure.pdf
│   │   │   │   └── site_visit.docx
│   │   │   └── [Other Lead Folders]
│   │   ├── Contacts/
│   │   └── Deals/
```

### WorkDrive Related List in CRM Record

| UI Element          | Detail |
|---------------------|--------|
| Section label       | `WorkDrive` or `Documents` |
| Location            | Right panel / Related Lists area of record detail view |
| Trigger             | Click section or "Link" button |
| Action              | Opens WorkDrive folder associated with record |
| Create option       | Ability to create a new folder linked to this record |
| Attach option       | Upload files directly from local system into WorkDrive via CRM |

---

## URL Reference

| Element                | Value |
|------------------------|-------|
| CRM Base URL           | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Leads/` |
| Lead Detail URL (pattern) | `https://crm.zoho.in/crm/org60043078423/tab/Leads/{record_id}` |
| WorkDrive Base URL     | `https://workdrive.zoho.in/` |
| Org ID                 | `60043078423` |
| Test Record Name       | `Sri Testing` |

---

## Workflow Summary

```
[Leads List View]
       |
       v
[Click record name "Sri Testing" (Step 1)]
       |
       v
[Lead Detail View — Sri Testing record opens]
  Shows: Lead info fields + Related Lists
       |
       v
[Click "Workdrive" (Step 2)]
       |
       v
[WorkDrive integration panel opens]
  Shows: Linked folder contents OR Link dialog
  Context: Files/documents associated with this lead
```

---

## Comparison: All Ten Lead/Contact Flows

| #  | Flow                    | Module  | Steps | Duration | Key Operation |
|----|-------------------------|---------|-------|----------|---------------|
| 1  | Create                  | Lead    | 13    | ~47s     | Form fill + save |
| 2  | Update                  | Lead    | 10    | ~37s     | Field edits + save |
| 3  | Delete                  | Lead    | 5     | ~22s     | Two-click delete |
| 4  | Related List            | Lead    | 5     | ~25s     | Navigate to Scheduler |
| 5  | Filter                  | Lead    | 8     | ~24s     | Criteria-based filter |
| 6  | Sort                    | Lead    | 8     | ~34s     | Sort by Country |
| 7  | Manage Columns          | Lead    | 9     | ~44s     | Column + page limit |
| 8  | Blueprint               | Lead    | 22    | ~2 min   | BANT qualification |
| 9  | Custom View             | Lead    | 5     | ~36s     | Switch to Today's Leads |
| 10 | Module Link (WorkDrive) | Lead    | 2     | ~23s     | Link record to WorkDrive |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Only 2 steps captured** — the shortest flow in all 10 recorded sequences; link/WorkDrive access is a 2-click operation from the list view |
| 2 | **"Sri Testing" is the test record** — this is the same record created in Flow 1 (Lead Create) and likely updated in Flow 2 (Lead Update); used consistently as the test lead throughout the recording sessions |
| 3 | **WorkDrive state not confirmed** — it is unknown whether the WorkDrive section was already linked to a folder for "Sri Testing" or whether the click triggered a "Link folder" dialog |
| 4 | **No URL captured for Step 1** — the starting URL of the Leads list is not confirmed; inferred to be the standard custom-view list entry point consistent with other flows |
| 5 | **"Workdrive" vs "WorkDrive"** — Scribe captured the label as `Workdrive` (lowercase d); Zoho's official branding is `WorkDrive` (capital D); both refer to the same integration |
| 6 | **Module Link interpretation** — the title "Module Link Flow" likely refers to the Zoho CRM concept of "linking" a CRM module record to a Zoho WorkDrive resource, rather than cross-module record linking (e.g., Lead → Contact) |
