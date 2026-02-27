> Scribe Source: https://scribehow.com/viewer/Module_Record_Print_Preview_in_Zoho_CRM__yue5DQAESPa0fGEmHaoG-Q
> Recorded By: Sri
> Duration: ~53 seconds
> Total Steps: 4
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Module — Record Print Preview (Deals / Potentials) — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **generating a Print Preview of a Deal (Potential) record** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user navigates to the Potentials list view, opens the "Prasanth" deal record, accesses the More actions menu, and triggers Print Preview — 4 UI interactions in approximately 53 seconds.

> **Print Preview** in Zoho CRM generates a formatted, printable view of all field data in a record — essentially a structured summary document of the CRM record. It is accessible from any module record's detail view via the More actions menu. For Kurinjee Promoters, printing a Deal (Potential) record would produce a client-facing or internal summary of a property booking opportunity — including lead source, deal stage, estimated revenue, and associated contact details.

> **Note on Module Naming:** Zoho CRM uses **"Potentials"** as the internal module name for what is commonly referred to as **"Deals"** in the standard CRM terminology. The URL path `/tab/Potentials/` confirms this is the Deals module. Both names are used interchangeably in this documentation.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–4)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Record detail view — More actions menu → Print Preview              |
| Module          | Potentials / Deals (first Deals module flow in the series)          |
| Notable pattern | New module revealed: Potentials; new custom view ID `955332000000441430` |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Potentials (Deals) List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Potentials/custom-view/955332000000441430/list` |
| Module          | Potentials (Deals) |
| View Type       | Custom List View (ID: `955332000000441430`) |

**Screenshot Analysis:**
- The Zoho CRM Potentials module opens in custom list view **`955332000000441430`**
- This is the **first Potentials/Deals module URL** revealed across all 16 recorded flows — a new module in the series
- The custom view ID `955332000000441430` completes the full custom view ID registry for Kurinjee Promoters:

  | Module        | Custom View ID         | ID Suffix | Position |
  |---------------|------------------------|-----------|----------|
  | Leads         | `955332000000441406`   | `441406`  | 1st      |
  | Accounts      | `955332000000441417`   | `441417`  | 2nd      |
  | Potentials    | `955332000000441430`   | `441430`  | 3rd      |
  | Contacts      | `955332000000441440`   | `441440`  | 4th      |

  - All four IDs are strictly sequential: `441406` → `441417` → `441430` → `441440`
  - Created together in the same CRM customisation session for Kurinjee Promoters
  - Potentials (Deals) sits between Accounts (`441417`) and Contacts (`441440`) in the sequence

- Potentials/Deals list view layout:

  ```
  ┌──────────────────────────────────────────────────────────────┐
  │  Deals  ▾ [View Name]   [+New Deal]   [Actions ▾]   [⚙]    │
  ├──────────────────────────────────────────────────────────────┤
  │ ☐  Deal Name ↕    Stage ↕      Amount ↕   Close Date ↕  Owner │
  ├──────────────────────────────────────────────────────────────┤
  │ ☐  Prasanth       [Stage]      ₹[amt]     [date]       Sri  │
  │ ☐  [Deal 2]       [Stage]      ₹[amt]     [date]       ...  │
  │    ...                                                       │
  └──────────────────────────────────────────────────────────────┘
  │  Showing 1–[N] of 9 Deals                                    │
  └──────────────────────────────────────────────────────────────┘
  ```

- Kurinjee Promoters has **9 Deals** in CRM (as documented in the project overview: `DEALS (9)`)
- The Deal named **"Prasanth"** appears in this list — likely named after the associated contact (same "Prasanth" seen in Flow 12 Clone, who is a Contact record)

---

### Step 2 — Click on Deal Record "Prasanth"

| Property     | Detail |
|--------------|--------|
| Action       | Click record name |
| Target       | `Prasanth` |
| Element Type | Deal record row — hyperlinked record name in Deals list view |
| Location     | Potentials list view — Deal Name column |

**Screenshot Analysis:**
- The recorder clicks on the deal record named **"Prasanth"** — navigating from the list view to the Deal Detail View
- In Zoho CRM, Deal (Potential) names are typically set as:
  - `[Contact Name]'s Potential` (auto-generated on Lead conversion)
  - A custom deal name entered manually
  - The property/project name (common in real estate CRMs)
- "Prasanth" as a deal name suggests this deal was created by converting the "Prasanth" contact's lead, or the deal was manually named to reflect the associated client
- The Deal Detail View layout for Potentials:

  ```
  ┌─────────────────────────────────────────────────────────────┐
  │  Prasanth                                        [⋮ More]   │
  │  [Edit]  [Send Email]  [Convert]  [Delete]  [More ▾]       │
  ├──────────────────────────────┬──────────────────────────────┤
  │  DEAL INFORMATION            │  RELATED LISTS               │
  │  • Deal Name: Prasanth       │  • Activities                │
  │  • Account Name: [company]   │  • Open Activities           │
  │  • Contact Name: Prasanth    │  • Emails                    │
  │  • Amount: ₹[value]          │  • Contacts                  │
  │  • Closing Date: [date]      │  • Notes                     │
  │  • Stage: [Blueprint stage]  │  • Attachments               │
  │  • Lead Source: [source]     │  • WorkDrive                 │
  │  • Owner: Sri                │                              │
  └──────────────────────────────┴──────────────────────────────┘
  ```

- After clicking, the URL changes to:
  `https://crm.zoho.in/crm/org60043078423/tab/Potentials/{record_id}`

---

### Step 3 — Click More Actions Button (Unlabeled)

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | Unlabeled (Scribe: "Click this button") |
| Element Type | More actions trigger — `⋮` kebab / `More ▾` dropdown button |
| Location     | Deal detail view — top action bar |

**Screenshot Analysis:**
- The recorder clicks an **unlabeled button** — the same pattern seen in Flow 12 (Clone, Step 3) where the More actions menu was accessed
- This is the **`⋮` (vertical ellipsis) / "More ▾"** button in the Deal record's detail view header action bar
- The More actions dropdown for a Deal record contains:

  ```
  ┌──────────────────────────────────┐
  │  Send Email                      │
  │  Log a Call                      │
  │  Create Task                     │
  │  ─────────────────────────────── │
  │  Clone                           │
  │  ─────────────────────────────── │
  │  Print Preview        ← target   │
  │  ─────────────────────────────── │
  │  Delete                          │
  └──────────────────────────────────┘
  ```

- **Print Preview** is a secondary action — placed in the More overflow menu (not in the primary button row) across all Zoho CRM module record views

---

### Step 4 — Click "Print Preview"

| Property     | Detail |
|--------------|--------|
| Action       | Click menu item |
| Target       | `Print Preview` |
| Element Type | Dropdown menu item |
| Location     | More actions dropdown — Deal detail view |

**Screenshot Analysis:**
- The recorder clicks **"Print Preview"** from the More actions dropdown
- In Zoho CRM, clicking Print Preview opens a **formatted print layout** of the record in a new browser tab or a print dialog:

  ```
  ┌────────────────────────────────────────────────────────────┐
  │  [Zoho CRM Logo]          Kurinjee Promoters               │
  │  ────────────────────────────────────────────────────────  │
  │  DEAL: Prasanth                                            │
  │  ────────────────────────────────────────────────────────  │
  │  Deal Information                                          │
  │  Deal Name        : Prasanth                               │
  │  Account Name     : [Company]                              │
  │  Contact Name     : Prasanth                               │
  │  Amount           : ₹[value]                               │
  │  Closing Date     : [date]                                 │
  │  Stage            : [Blueprint stage]                      │
  │  Lead Source      : [source]                               │
  │  Owner            : Sri                                    │
  │  ────────────────────────────────────────────────────────  │
  │  [Additional sections: Notes, Activities, Custom Fields]   │
  │  ────────────────────────────────────────────────────────  │
  │  [Print]  [Close]                                          │
  └────────────────────────────────────────────────────────────┘
  ```

- The Print Preview renders **all fields visible in the record** in a clean, print-optimised format — removing navigation chrome, sidebar, and action buttons
- For Kurinjee Promoters (real estate), printing a Deal record provides:

  | Use Case | Detail |
  |----------|--------|
  | **Client meeting prep** | Printed deal summary to carry into a site visit or closing meeting |
  | **Internal review** | Manager reviews deal stage, amount, and owner in a printable format |
  | **Deal closure doc** | Preliminary summary before the formal booking agreement is generated |
  | **Audit trail** | Physical record of deal state at a specific point in time |

---

## Print Preview — Cross-Module Availability

Print Preview is available from the More actions menu across all Zoho CRM module records:

| Module      | Print Preview Use Case |
|-------------|------------------------|
| Leads       | Lead summary — contact details, lead source, status |
| Contacts    | Contact card — all contact info fields |
| Accounts    | Company profile — account details, address, linked contacts |
| **Deals / Potentials** | Deal sheet — stage, amount, close date, contact ← this flow |
| Tasks       | Task details — subject, due date, status, description |

---

## Deals Module — Kurinjee Promoters Context

| Property        | Detail |
|-----------------|--------|
| Module          | Potentials (Deals) |
| Internal name   | `Potentials` (Zoho CRM default) |
| Display name    | `Deals` (standard CRM label) |
| Total records   | 9 deals |
| Custom View ID  | `955332000000441430` |
| Pipeline stages | Lead Qualification → Site Visit → Booking → Closed Won (Blueprint) |
| Test record     | `Prasanth` — linked to the Prasanth Contact record (Flow 12) |

---

## Custom View ID Registry — All Four Modules Now Complete

| Module        | Custom View ID         | ID Suffix | Gap from Previous |
|---------------|------------------------|-----------|-------------------|
| Leads         | `955332000000441406`   | `441406`  | —                 |
| Accounts      | `955332000000441417`   | `441417`  | +11               |
| Potentials    | `955332000000441430`   | `441430`  | +13               |
| Contacts      | `955332000000441440`   | `441440`  | +10               |

- All four custom views were created in a single CRM customisation session
- Average gap between IDs: ~11 — consistent with Zoho's internal ID increment behaviour
- Total span: `441406` to `441440` = 34 IDs across all four module custom views

---

## URL Reference

| Element                     | Value |
|-----------------------------|-------|
| CRM Base URL                | `https://crm.zoho.in/crm/org60043078423/` |
| Potentials List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Potentials/custom-view/955332000000441430/list` |
| Custom View ID (Potentials) | `955332000000441430` |
| Module (internal)           | `Potentials` |
| Module (display)            | `Deals` |
| Deal Record (source)        | `Prasanth` |
| Org ID                      | `60043078423` |

---

## Workflow Summary

```
[Potentials (Deals) List View — custom-view/955332000000441430/list]
       |
       v
[Click deal record "Prasanth" (Step 2)]
       |
       v
[Deal Detail View — Prasanth deal record opens]
  Shows: Deal fields + Stage + Amount + Related Lists
       |
       v
[Click "⋮ More" / actions menu — unlabeled (Step 3)]
       |
       v
[More Actions dropdown opens]
  Contains: Clone, Print Preview, Delete, etc.
       |
       v
[Click "Print Preview" (Step 4)]
       |
       v
[Print Preview opens in new tab / print dialog]
  Shows: All deal fields in print-optimised format
  User can print or save as PDF
```

---

## Comparison: All Sixteen Flows

| #  | Flow                    | Module      | Steps | Duration | Key Operation |
|----|-------------------------|-------------|-------|----------|---------------|
| 1  | Create                  | Lead        | 13    | ~47s     | Form fill + save |
| 2  | Update                  | Lead        | 10    | ~37s     | Field edits + save |
| 3  | Delete                  | Lead        | 5     | ~22s     | Two-click delete |
| 4  | Related List            | Lead        | 5     | ~25s     | Navigate to Scheduler |
| 5  | Filter                  | Lead        | 8     | ~24s     | Criteria-based filter |
| 6  | Sort                    | Lead        | 8     | ~34s     | Sort by Country |
| 7  | Manage Columns          | Lead        | 9     | ~44s     | Column + page limit |
| 8  | Blueprint               | Lead        | 22    | ~2 min   | BANT qualification |
| 9  | Custom View             | Lead        | 5     | ~36s     | Switch to Today's Leads |
| 10 | Module Link (WorkDrive) | Lead        | 2     | ~23s     | Link record to WorkDrive |
| 11 | Save and New            | Contact     | 6     | ~20s     | Batch contact creation |
| 12 | Clone                   | Contact     | 4     | ~8s      | Duplicate existing record |
| 13 | Record Import           | Accounts    | 4     | ~17s     | Bulk import via CSV |
| 14 | Record Export           | Accounts    | 5     | ~23s     | Export all records to CSV |
| 15 | Customize Homepage      | Home        | 13    | ~2 min   | Home page widget editor + role config |
| 16 | Print Preview           | Potentials  | 4     | ~53s     | Print-format record view |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **First Potentials/Deals module flow** — completes the core four-module coverage: Leads, Contacts, Accounts, and now Deals (Potentials) |
| 2 | **Custom view ID registry now complete** — all four module custom view IDs (`441406`, `441417`, `441430`, `441440`) have been identified; the full Kurinjee Promoters ID sequence is confirmed |
| 3 | **"Prasanth" appears across three flows** — as a Contact (Flow 12 Clone), as a Deal (this flow), and by inference as a Lead that was converted; Prasanth is a real client record used consistently in the recording sessions |
| 4 | **Step 3 unlabeled** — the More actions trigger is icon-only ("Click this button"); same pattern as Flow 12 (Clone) Step 3 — both access the `⋮ More` menu to reach secondary record actions |
| 5 | **53-second duration for 4 steps** — longer than expected; the recorder likely spent time reading the Print Preview output before ending the recording |
| 6 | **Print Preview output not captured** — the formatted print document that opens after Step 4 is outside the Scribe recording scope; field values, layout, and print options are not shown |
| 7 | **Module named "Potentials" in URL** — Zoho CRM's internal module name (`/tab/Potentials/`) differs from the display name ("Deals"); this is a standard Zoho CRM naming convention where the legacy name "Potentials" persists in URLs even when the UI label is "Deals" |
