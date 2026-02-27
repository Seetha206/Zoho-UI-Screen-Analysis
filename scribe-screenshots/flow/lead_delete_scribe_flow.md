> Scribe Source: https://scribehow.com/viewer/How_to_Delete_a_Lead_in_Zoho_CRM__QYcZwYelSda4EbSDpH_HwA
> Recorded By: Sri Gnanathesigan
> Duration: ~22 seconds
> Total Steps: 5
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Delete Lead Record in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **deleting an existing Lead record** in Zoho CRM as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates the deletion of the test lead `Sri Testing` — the same record created and updated in the prior two recordings. The flow covers navigation from Leads list → Lead detail view → Delete action → Confirmation dialog — 5 discrete UI interactions in approximately 22 seconds.

> This is the shortest and simplest of the three recorded flows (22s / 5 steps vs 37s / 10 steps for Update and 47s / 13 steps for Create).

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–5)                               |
| Screenshot style | Max-height 600px, max-width 720px, per screenshot                |
| Navigation path | Leads list → Lead detail → More Actions menu → Delete → Confirm  |
| Confirmation    | Two-stage delete: menu click + confirmation dialog click          |

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
- The Zoho CRM **Leads module** opens in the identical custom list view used across all three recordings
- URL parameters `page=1&per_page=100` are consistent with the Update recording — same view, same pagination
- The custom view ID (`955332000000441406`) is the same saved filtered view across all three flows, confirming this is the primary working view for Kurinjee Promoters' Telecallers
- The lead list shows existing records in tabular format with the test lead `Sri Testing` present and accessible

---

### Step 2 — Click Lead: "Sri Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Click on lead record |
| Target       | `Sri Testing` |
| Record Type  | Lead — the same test record from the Create and Update flows |
| Location     | Lead list row — clickable name link in primary column |

**Screenshot Analysis:**
- The recorder clicks directly on **"Sri Testing"** in the leads list
- This is the same test record that was:
  - Created in Flow 1 (First Name: `Sri Testing`, Phone: `8190970216`)
  - Updated in Flow 2 (Lead Quality set to `Junk`, Lead Status and date modified)
  - Now being **deleted** in this flow
- Clicking the name link navigates to the **Lead Detail View** for that record
- The list view highlights the selected row on hover before click
- Other lead records remain visible in the background list

---

### Step 3 — Click the Action/More Options Button

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Button Label | Not explicitly labeled — "Click this button" in Scribe instruction |
| Button Type  | More Actions / Kebab menu (`⋮`) or dropdown action button |
| Location     | Top of Lead Detail View — action bar / toolbar |

**Screenshot Analysis:**
- The **Lead Detail View** for `Sri Testing` is open, showing the record's field values
- The recorder clicks an **unlabeled action button** — in standard Zoho CRM, this is the **"More Actions"** button (three vertical dots `⋮` or a down-arrow dropdown) in the detail view toolbar
- The Zoho CRM Lead detail toolbar typically contains:

  | Button      | Type    | Position |
  |-------------|---------|----------|
  | Edit        | Primary | Left     |
  | Send Email  | Action  | Center   |
  | Convert     | Action  | Center   |
  | More (⋮)   | Dropdown | Right   |

- Clicking the **More / `⋮`** button opens a dropdown menu containing additional actions including **Delete**
- This is a two-step delete process (menu open → confirm) — a deliberate UX safety measure in Zoho CRM to prevent accidental deletion

---

### Step 4 — Click "Delete" from Dropdown Menu

| Property     | Detail |
|--------------|--------|
| Action       | Click menu option |
| Option Label | `Delete` |
| Menu Type    | Dropdown / context menu from More Actions button |
| Position     | Within the More Actions dropdown |

**Screenshot Analysis:**
- The **More Actions dropdown** is open, showing available record actions
- The recorder clicks **"Delete"** from the menu options
- Standard Zoho CRM More Actions menu options for a Lead record typically include:

  | Menu Option          | Action |
  |----------------------|--------|
  | Delete               | Initiates deletion flow |
  | Convert              | Converts lead to Contact/Deal |
  | Mass Update          | Bulk field update |
  | Print                | Print record |
  | Add to Campaign      | Associate with campaign |

- Clicking "Delete" does **not** immediately delete the record — Zoho CRM shows a **confirmation dialog** (Step 5)
- This is the first "Delete" click in the two-click deletion process

---

### Step 5 — Confirm Deletion: Click "Delete" in Confirmation Dialog

| Property     | Detail |
|--------------|--------|
| Action       | Click confirmation button |
| Button Label | `Delete` |
| Dialog Type  | Modal confirmation dialog |
| Location     | Center of screen — overlay modal |

**Screenshot Analysis:**
- A **confirmation modal dialog** appears overlaying the Lead Detail View
- This is Zoho CRM's standard deletion confirmation — designed to prevent accidental data loss
- Standard Zoho CRM Lead deletion dialog structure:

  ```
  ┌─────────────────────────────────────────┐
  │  Delete Lead                            │
  │                                         │
  │  Are you sure you want to delete        │
  │  this lead?                             │
  │                                         │
  │          [ Cancel ]  [ Delete ]         │
  └─────────────────────────────────────────┘
  ```

- The recorder clicks the **"Delete"** button (red or blue filled button) to confirm
- A **"Cancel"** button is also present to abort the deletion
- On confirmation:
  - The lead record `Sri Testing` is **permanently deleted** from Zoho CRM
  - The system redirects back to the **Leads list view**
  - A **success notification/toast** briefly appears: e.g. `"Lead deleted successfully"`
  - The record is moved to the **Recycle Bin** (Zoho CRM retains deleted records for recovery within 60 days)

---

## Deletion Flow — State Changes

| Stage        | Record State                          |
|--------------|---------------------------------------|
| Before Step 1 | Lead `Sri Testing` exists in list    |
| After Step 2  | Lead Detail View open — record visible |
| After Step 3  | More Actions menu open — record intact |
| After Step 4  | Confirmation dialog shown — record intact |
| After Step 5  | Record **deleted** → moved to Recycle Bin |

---

## Two-Click Deletion Safety Pattern

Zoho CRM enforces a **two-step confirmation** for record deletion:

```
[More Actions ⋮]  →  [Delete option]  →  [Confirmation Modal]  →  [Delete button]
     Step 3               Step 4                                        Step 5
```

This prevents accidental deletions from a single misclick. The record is **not permanently destroyed** — it goes to the Recycle Bin and can be restored within 60 days.

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
[Lead Detail View opens — record in read-only state]
       |
       v
[Click More Actions button (⋮)]
       |
       v
[Dropdown menu opens]
       |
       v
[Click "Delete" from menu]
       |
       v
[Confirmation modal dialog appears]
       |
       v
[Click "Delete" to confirm]
       |
       v
[Lead deleted → moved to Recycle Bin → Redirect to Leads list]
```

---

## Comparison: All Three Lead Flows

| Property         | Create (Flow 1)  | Update (Flow 2)    | Delete (Flow 3) |
|------------------|------------------|--------------------|-----------------|
| Duration         | ~47 seconds      | ~37 seconds        | ~22 seconds     |
| Steps            | 13               | 10                 | 5               |
| Entry point      | Leads list       | Leads list         | Leads list      |
| Custom View ID   | `955332000000441406` | `955332000000441406` | `955332000000441406` |
| Target record    | New record       | `Sri Testing`      | `Sri Testing`   |
| Form interaction | Full form fill   | Field edits        | None            |
| Confirmation     | Save button      | Save button        | Two-click Delete modal |
| End state        | Record created   | Record updated     | Record in Recycle Bin |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Step 3 button not labeled** — Scribe captured it as "Click this button"; inferred as the Zoho CRM More Actions (`⋮`) button from standard UI patterns |
| 2 | **Confirmation dialog text not captured** — the exact modal title and body text were not extracted; standard Zoho CRM dialog text used above |
| 3 | **Recycle Bin behavior** — Zoho CRM does not permanently delete records immediately; they are recoverable from the Recycle Bin for 60 days |
| 4 | **Test record lifecycle complete** — `Sri Testing` was created (Flow 1), updated (Flow 2), and deleted (Flow 3), forming a complete CRUD demonstration |
| 5 | **No fields shown** — the delete flow involves no form interaction; it is purely a navigation and confirmation sequence |
| 6 | **Shortest flow** — at 22 seconds / 5 steps, deletion is the simplest operation; fewer UI interactions than create or update |
