> Scribe Source: https://scribehow.com/viewer/Module_Clone_Flow_in_Zoho_CRM_Contant__qcO_Tqb7QEmg88qVuQTWTA
> Recorded By: Sri
> Duration: ~8 seconds
> Total Steps: 4
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Module — Clone Flow (Contact) — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **cloning an existing Contact record** in Zoho CRM's Contacts module, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user selects an existing contact ("Prasanth"), accesses the record action menu, and triggers the Clone function — 4 UI interactions in approximately 8 seconds.

> **Clone** in Zoho CRM creates a duplicate of an existing record — copying all field values into a new blank-slate record that the user can then modify. It is faster than creating from scratch when a new record shares most of the same details as an existing one (same lead source, same company, same owner, etc.). For a real estate company, cloning is useful when entering multiple members of the same family or business group who have the same contact details except for name and mobile number.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–4)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Record action menu — Clone operation                                |
| Module          | Contacts                                                            |
| Notable pattern | Shortest recorded flow overall — 4 steps, 8 seconds; near-instant operation |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Contacts List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Contacts/custom-view/955332000000441440/list?page=1&per_page=10` |
| View Type       | Custom List View (ID: `955332000000441440`) |
| Pagination      | `page=1` |
| Records per page | `per_page=10` |
| Module          | Contacts |

**Screenshot Analysis:**
- The Zoho CRM Contacts module opens in custom list view `955332000000441440` — the same view used in Flow 11 (Save and New)
- New URL parameter here: **`per_page=10`** — explicitly showing 10 records per page
  - In Flow 11 (Save and New), the URL was `?page=1` without a `per_page` parameter, meaning the default was in use
  - Here, `per_page=10` confirms the user (or a previous Manage Columns / Record Limit action — see Flow 7) set the page size to 10 contacts per page
- Contacts module list view content:

  ```
  ┌───────────────────────────────────────────────────────┐
  │  Contacts  ▾ [View Name]   [+New]  [Actions ▾]       │
  ├───────────────────────────────────────────────────────┤
  │ ☐  Name ↕         Phone ↕    Email ↕     Owner ↕     │
  ├───────────────────────────────────────────────────────┤
  │ ☐  Prasanth       ...        ...         Sri  ← row  │
  │ ☐  [Contact 2]    ...        ...         ...          │
  │    ...                                                │
  └───────────────────────────────────────────────────────┘
  │  Records 1–10 of 26                                   │
  └───────────────────────────────────────────────────────┘
  ```

- "Prasanth" is visible in the list — a real contact record in the Kurinjee Promoters Contacts module

---

### Step 2 — Click on Contact "Prasanth"

| Property     | Detail |
|--------------|--------|
| Action       | Click record name |
| Target       | `Prasanth` |
| Element Type | Contact record row — hyperlinked record name |
| Location     | Contacts list view — Name column |

**Screenshot Analysis:**
- The recorder clicks on **"Prasanth"** — an existing contact record in the Contacts module
- Clicking the record name navigates to the **Contact Detail View** for Prasanth
- The Contact Detail View layout:

  ```
  ┌─────────────────────────────────────────────────────────┐
  │  Prasanth                                    [⋮ More]   │
  │  [Edit]  [Send Email]  [Convert]  [Delete]  [More ▾]   │
  ├───────────────────────────────┬─────────────────────────┤
  │  CONTACT INFORMATION          │  RELATED LISTS          │
  │  • First Name: Prasanth       │  • Activities           │
  │  • Last Name: [surname]       │  • Open Activities      │
  │  • Phone: [number]            │  • Emails               │
  │  • Email: [email]             │  • Deals                │
  │  • Account: [company]         │  • Cases                │
  │  • Lead Source: [source]      │  • WorkDrive            │
  │  • Owner: Sri                 │  • Notes                │
  │  • Estimated Budget ₹: [amt]  │                         │
  └───────────────────────────────┴─────────────────────────┘
  ```

- "Prasanth" is a **real contact** — not a test record — with actual field data
- The record detail view URL would follow the pattern:
  `https://crm.zoho.in/crm/org60043078423/tab/Contacts/{record_id}`

---

### Step 3 — Click "Here" (More Actions Menu / Ellipsis)

| Property     | Detail |
|--------------|--------|
| Action       | Click menu trigger |
| Target       | `here` (Scribe unlabeled — likely the `⋮` More actions button) |
| Element Type | Overflow/kebab menu button or action dropdown |
| Location     | Contact detail view — top action bar |

**Screenshot Analysis:**
- The recorder clicks an **unlabeled element** ("Click here") — this is a standard Scribe limitation where unlabeled or icon-only buttons are captured without a text label
- In Zoho CRM's Contact (and all module) detail view, this is almost certainly the **"More"** actions menu, accessed via:
  - A `⋮` (vertical ellipsis / kebab) icon button in the header action bar
  - A `▾` dropdown on the "More" button
  - A `More Actions` text button

- Clicking this reveals the More Actions dropdown:

  ```
  ┌──────────────────────────┐
  │  Send Email              │
  │  Log a Call              │
  │  Create Task             │
  │  Convert                 │
  │  ─────────────────────── │
  │  Clone           ← next  │
  │  ─────────────────────── │
  │  Delete                  │
  │  Print Preview           │
  └──────────────────────────┘
  ```

- The **Clone** option is typically found in this "More" or overflow actions menu — not in the primary action button row

---

### Step 4 — Click "Clone"

| Property     | Detail |
|--------------|--------|
| Action       | Click menu item |
| Target       | `Clone` |
| Element Type | Dropdown menu item |
| Location     | More actions dropdown — Contact detail view |

**Screenshot Analysis:**
- The recorder clicks **"Clone"** from the More actions dropdown
- In Zoho CRM, clicking **Clone** on a Contact record:
  1. Creates a **duplicate of the current record** in memory
  2. Opens the **Contact creation form** pre-filled with all field values from "Prasanth"
  3. The user can then **modify specific fields** (e.g., change name, mobile number) before saving as a new record
  4. The new record is assigned a **new unique Record ID** upon save

- Clone form pre-filled state for "Prasanth":

  | Field              | Cloned Value (from Prasanth) | Typically Modified |
  |--------------------|------------------------------|-------------------|
  | First Name         | Prasanth                     | Yes — new name    |
  | Last Name          | [Prasanth's surname]         | Yes — new name    |
  | Phone              | [Prasanth's phone]           | Yes — new number  |
  | Mobile             | [Prasanth's mobile]          | Yes               |
  | Email              | [Prasanth's email]           | Yes               |
  | Account Name       | [Same company]               | Often kept same   |
  | Lead Source        | [Same source]                | Often kept same   |
  | Estimated Budget ₹ | [Same budget]                | May update        |
  | Owner              | Sri                          | May reassign      |

- After Clone opens the pre-filled form, the flow recording ends — the user would then edit required fields and save
- The cloned record is **not saved** until the user explicitly clicks Save in the clone form

---

## Clone vs Other Record Creation Methods

| Method          | Starting State         | Use Case |
|-----------------|------------------------|----------|
| `Create Contact` | Blank form             | New contact with no prior reference |
| `Save and New`  | Blank form (after save) | Rapid entry of multiple new contacts |
| `Clone`         | Pre-filled copy of existing record | New contact sharing most details with an existing one |
| `Convert Lead`  | Lead fields mapped to Contact | Lead who has been qualified for conversion |
| `Import`        | CSV/Excel batch         | Bulk import from external source |

---

## "Prasanth" Record — Context

| Property        | Detail |
|-----------------|--------|
| Record Name     | Prasanth |
| Module          | Contacts |
| Type            | Real contact record (not a test record) |
| Owner           | Sri (inferred from consistent ownership in recording) |
| Significance    | Used as the source record for the Clone demonstration |
| Position in list | Visible on page 1 of 10-per-page contact list — likely one of the first/most recently added contacts |

---

## URL Reference

| Element                   | Value |
|---------------------------|-------|
| CRM Base URL              | `https://crm.zoho.in/crm/org60043078423/` |
| Contacts List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Contacts/custom-view/955332000000441440/list?page=1&per_page=10` |
| Custom View ID (Contacts) | `955332000000441440` |
| Records Per Page          | `10` |
| Contact Record (source)   | `Prasanth` |
| Module                    | Contacts |
| Org ID                    | `60043078423` |

---

## Workflow Summary

```
[Contacts List View — custom-view/955332000000441440/list, page=1, per_page=10]
       |
       v
[Click record name "Prasanth" (Step 2)]
       |
       v
[Contact Detail View — Prasanth record opens]
  Shows: All contact fields + Related Lists
       |
       v
[Click "⋮ More" / actions menu (Step 3)]
       |
       v
[More Actions dropdown opens]
  Contains: Clone, Delete, Print Preview, etc.
       |
       v
[Click "Clone" (Step 4)]
       |
       v
[Contact creation form opens — pre-filled with Prasanth's data]
  User modifies required fields (name, phone, etc.)
  Clicks Save to create the new cloned record
```

---

## Comparison: All Twelve Flows

| #  | Flow                    | Module   | Steps | Duration | Key Operation |
|----|-------------------------|----------|-------|----------|---------------|
| 1  | Create                  | Lead     | 13    | ~47s     | Form fill + save |
| 2  | Update                  | Lead     | 10    | ~37s     | Field edits + save |
| 3  | Delete                  | Lead     | 5     | ~22s     | Two-click delete |
| 4  | Related List            | Lead     | 5     | ~25s     | Navigate to Scheduler |
| 5  | Filter                  | Lead     | 8     | ~24s     | Criteria-based filter |
| 6  | Sort                    | Lead     | 8     | ~34s     | Sort by Country |
| 7  | Manage Columns          | Lead     | 9     | ~44s     | Column + page limit |
| 8  | Blueprint               | Lead     | 22    | ~2 min   | BANT qualification |
| 9  | Custom View             | Lead     | 5     | ~36s     | Switch to Today's Leads |
| 10 | Module Link (WorkDrive) | Lead     | 2     | ~23s     | Link record to WorkDrive |
| 11 | Save and New            | Contact  | 6     | ~20s     | Batch contact creation |
| 12 | Clone                   | Contact  | 4     | ~8s      | Duplicate existing record |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Fastest flow in the series** — 4 steps in 8 seconds; cloning is a 2-navigation + 2-click operation with no form filling required in the recorded steps |
| 2 | **Clone form not captured** — the flow ends at Step 4 (clicking "Clone"); the pre-filled creation form that opens is not shown; field modifications and the final save action are outside the recording scope |
| 3 | **Step 3 element unlabeled** — "Click here" is a Scribe limitation for icon-only buttons; the `⋮ More` menu trigger is the standard Zoho CRM entry point for Clone and other secondary actions |
| 4 | **"Prasanth" — real record used** — unlike the "Sri Testing" test records in other flows, "Prasanth" is a real contact in the Kurinjee Promoters CRM; the recorder used production data for this demonstration |
| 5 | **`per_page=10` parameter confirmed** — the Contacts list URL explicitly sets `per_page=10`, consistent with the record limit configured in Flow 7 (Manage Columns — which set 10 records per page for the Leads module; same default appears to be active for Contacts) |
| 6 | **Title typo in Scribe** — the Scribehow recording is titled "Module Clone Flow in Zoho CRM (Contant)" — "Contant" is a typo for "Contact"; preserved as-is in this documentation for traceability |
| 7 | **Series transition confirmed** — Flows 11 and 12 both operate on the Contacts module using custom view `955332000000441440`, signalling a shift in the documentation series from Lead-only flows to broader CRM module coverage |
