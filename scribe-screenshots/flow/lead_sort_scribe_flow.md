> Scribe Source: https://scribehow.com/viewer/Sort_By_Flow_in_Zoho_CRMLead__y3uy3X_kSwGGCPJwnA9R7g
> Recorded By: Sri Gnanathesigan
> Duration: ~34 seconds
> Total Steps: 8
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Sort By Flow in Zoho CRM — Leads List View — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **applying and managing sort order on the Leads List View** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates opening the Sort panel, selecting **Country** as the sort field, applying the sort, reopening the Sort panel, and then cancelling — 8 UI interactions in approximately 34 seconds.

> This recording is the companion to Flow 5 (Filter). Together they cover the two primary list-level data management tools in Zoho CRM's Leads list view: **Filter** (narrow records) and **Sort** (order records).

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–8)                               |
| Screenshot style | Max-height 600px, max-width 720px per screenshot                 |
| Flow type       | List View operation — no record detail view opened               |
| Sort panel      | Dialog/panel accessed from toolbar above the leads list           |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View (with Sort URL Parameters)

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&sort_order=unsort&sort_by=955332000000427928` |
| View Type       | Custom List View (ID: `955332000000441406`) |
| Pagination      | `page=1` |
| Sort State      | `sort_order=unsort` — no active sort applied |
| Sort Field Ref  | `sort_by=955332000000427928` — a field ID (likely a previously used sort field, now cleared) |
| Module          | Leads |

**Screenshot Analysis:**
- The Zoho CRM **Leads module** opens in the same custom list view used across all six recordings
- This URL is the **most information-rich entry URL** of all six flows — it explicitly encodes sort state in query parameters:
  - `sort_order=unsort` — the list is currently **unsorted** (no active sort)
  - `sort_by=955332000000427928` — a field ID that was previously used for sorting (now inactive due to `unsort`)
  - The field ID `955332000000427928` corresponds to a specific Lead module field — exact field name not confirmed from extraction but it is a saved/remembered sort preference
- The list displays records in their default unsorted order (typically insertion/creation order)
- The Sort button is visible in the list toolbar above the records table

---

### Step 2 — Click the "Sort" Button

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Sort` |
| Button Type  | Toolbar action button |
| Location     | Top toolbar of the Leads list view, above the records table |

**Screenshot Analysis:**
- The **"Sort" button** is located in the **toolbar at the top of the Leads list view**, positioned above the records data table
- This is a dedicated sort control — separate from column header click-to-sort (which is a different interaction)
- Clicking "Sort" opens a **sort configuration dialog/panel**
- The toolbar layout in Zoho CRM Leads list view:

  ```
  [New Lead] [Import] [Export] [Actions ▾] | [Filter] [Sort] [Columns] | [Search]
  ```

- The Sort button is in the middle section of the toolbar alongside Filter and Columns controls
- Before clicking, the list is in `sort_order=unsort` state as indicated by the URL

---

### Step 3 — Current Sort = "None" — View Sort Panel

| Property     | Detail |
|--------------|--------|
| Action       | Observe / click "None" |
| Current Value | `None` — no active sort field |
| Element Type  | Sort field selector showing current state |
| Location     | Inside the Sort dialog/panel |

**Screenshot Analysis:**
- The **Sort dialog/panel** opens, showing the current sort configuration
- The current sort field displays **"None"** — confirming no sort is actively applied (consistent with `sort_order=unsort` in the URL)
- The Sort panel structure in Zoho CRM:

  ```
  ┌──────────────────────────────────────┐
  │  Sort By                             │
  ├──────────────────────────────────────┤
  │  Field:    [ None ▾ ]               │
  │  Order:    ( Ascending ) (Descending)|
  ├──────────────────────────────────────┤
  │          [ Cancel ]  [ Apply ]       │
  └──────────────────────────────────────┘
  ```

- The field selector is a dropdown currently showing **"None"**
- The order options (Ascending / Descending) are present but inactive until a field is selected
- An **"Apply"** button and **"Cancel"** button are at the bottom of the panel
- Clicking "None" opens the field selector dropdown to choose a sort field

---

### Step 4 — Select "Country" as Sort Field

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Value Selected | `Country` |
| Field Type   | Standard Zoho CRM Leads text field |
| Location     | Field dropdown within the Sort panel |

**Screenshot Analysis:**
- The field selector dropdown is open showing available Lead module fields for sorting
- The recorder selects **"Country"** as the sort field
- "Country" is a **standard Zoho CRM Leads field** — part of the Address Information section
- In the context of Kurinjee Promoters (a real estate company in India), sorting by Country is likely used to:
  - Separate NRI (Non-Resident Indian) leads from domestic leads
  - Segment international vs. local property inquiries
- Other fields visible in the sort dropdown (standard Zoho CRM Leads sortable fields) would include:

  | Field Name          | Section              |
  |---------------------|----------------------|
  | First Name          | Lead Information     |
  | Last Name           | Lead Information     |
  | Company             | Lead Information     |
  | Lead Owner          | Lead Information     |
  | Lead Status         | Lead Information     |
  | Lead Source         | Lead Information     |
  | Created Time        | System               |
  | Modified Time       | System               |
  | Country             | Address Information  |
  | City                | Address Information  |
  | Annual Revenue      | Lead Information     |

- After selecting "Country", the field selector closes and the Sort panel shows:
  `Sort By: Country | Order: Ascending (default)`

---

### Step 5 — Click "Apply" to Confirm Sort

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Apply` |
| Button Style | Blue filled primary action button |
| Location     | Bottom of the Sort panel |

**Screenshot Analysis:**
- The **"Apply"** button is clicked to execute the sort and apply it to the Leads list
- On applying:
  - The Sort panel closes
  - The Leads list **reorders records alphabetically by Country** (ascending A→Z by default)
  - The **URL updates** to reflect the new sort state — `sort_order` changes from `unsort` to `asc` and `sort_by` updates to the Country field's ID
  - A **sort indicator** (arrow icon) appears in the **Country column header** in the list view, showing the active sort direction
  - The record order in the list visually changes — records with Country values starting with "A" appear first
- The sort persists as long as the user stays in this view or until explicitly changed/cleared

---

### Step 6 — Click "Sort" Button Again

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Sort` |
| Location     | Toolbar — same position as Step 2 |
| Purpose      | Reopen Sort panel to inspect or modify the active sort |

**Screenshot Analysis:**
- The Sort button in the toolbar is clicked a **second time**, reopening the Sort panel
- This time the Sort panel opens with the **previously applied configuration** populated:
  - Field: `Country` (selected in Step 4)
  - Order: `Ascending` (the default direction applied in Step 5)
- The panel shows the current active sort — allowing the user to either:
  - Change the sort field
  - Toggle between Ascending / Descending
  - Clear the sort (set back to None)
  - Cancel without changes
- The sort direction (Ascending/Descending) is visually indicated in the panel — radio buttons or toggle

---

### Step 7 — Click "Cancel" to Dismiss Panel

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Cancel` |
| Button Style | Secondary / outline button |
| Location     | Bottom of the Sort panel |

**Screenshot Analysis:**
- The **"Cancel"** button is clicked, dismissing the Sort panel without making any changes
- **Critical behaviour:** Cancelling does **not** remove the sort applied in Step 5
  - The list remains sorted by **Country (Ascending)** as applied previously
  - Cancel only dismisses the dialog — it does not revert sort state
- The list view returns to showing sorted records with the Country sort indicator still active in the column header
- This step demonstrates the distinction between:
  - **Cancel** — closes the panel, keeps the current sort active
  - **Apply with "None"** — would clear the sort and return to unsorted state

---

### Step 8 — Click "Here" (Unspecified Element)

| Property     | Detail |
|--------------|--------|
| Action       | Click element |
| Instruction  | `Click here` (no label — screenshot-only in Scribe) |
| Location     | Unspecified — within the list view after sort is applied |

**Screenshot Analysis:**
- The final step clicks an unspecified element — Scribe captured only "Click here" with no label
- Based on context, likely candidates:
  1. **A column header** — clicking the Country column header directly (alternative sort trigger)
  2. **A sorted lead record** — clicking through to a specific lead's detail view after sorting
  3. **The sort indicator arrow** — toggling sort direction from Ascending to Descending by clicking the active sort arrow in the column header
  4. **A "Clear Sort" or "Reset" control** — resetting the list to its default unsorted state
- The step concludes the recording — the exact action does not alter any of the previous findings

---

## Sort URL Parameters — Decoded

The Step 1 URL reveals Zoho CRM encodes sort state directly in the URL:

| URL Parameter        | Value                    | Meaning |
|----------------------|--------------------------|---------|
| `sort_order`         | `unsort`                 | No sort currently applied |
| `sort_by`            | `955332000000427928`     | Field ID of a previously used sort field (now cleared) |

After applying sort in Step 5, the URL would update to:

| URL Parameter        | Expected Value           | Meaning |
|----------------------|--------------------------|---------|
| `sort_order`         | `asc` or `desc`          | Sort direction applied |
| `sort_by`            | Country field's ID       | The field currently being sorted on |

**Field ID `955332000000427928`** — this is the internal Zoho CRM field ID for a specific Lead module field that was previously used for sorting (before this recording began). The exact field name for this ID is not confirmed from the extraction.

---

## Sort Panel Architecture — Zoho CRM Leads List

```
Leads List Toolbar
  └── [Sort] button
          |
          v
  ┌──────────────────────────────────────┐
  │  Sort By                             │
  ├──────────────────────────────────────┤
  │  Field:    [ Country ▾ ]            │
  │                                      │
  │  Order:  ● Ascending                 │
  │          ○ Descending                │
  ├──────────────────────────────────────┤
  │          [ Cancel ]  [ Apply ]       │
  └──────────────────────────────────────┘
          |
     [Apply] clicked
          |
          v
  List reorders by Country A→Z
  Column header shows sort arrow ▲
  URL: sort_order=asc&sort_by={country_field_id}
```

---

## Full URL Reference

| Element              | Value |
|----------------------|-------|
| CRM Base URL         | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL       | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&sort_order=unsort&sort_by=955332000000427928` |
| Custom View ID       | `955332000000441406` |
| sort_order param     | `unsort` (at recording start) |
| sort_by field ID     | `955332000000427928` |
| Org ID               | `60043078423` |

---

## Workflow Summary

```
[Leads List View — unsorted, page=1]
       |
       v
[Click "Sort" button in toolbar]
       |
       v
[Sort panel opens — current field: None]
       |
       v
[Click "None" field selector]
       |
       v
[Select "Country" from field list]
       |
       v
[Click "Apply"]
       |
       v
[List reorders by Country A→Z — sort indicator shows on column header]
       |
       v
[Click "Sort" again — panel reopens showing Country / Ascending]
       |
       v
[Click "Cancel" — panel closes — sort remains active]
       |
       v
[Click unspecified element (Step 8)]
```

---

## Comparison: All Six Lead Flows

| Property       | Create (1) | Update (2) | Delete (3) | Related List (4) | Filter (5) | Sort (6)    |
|----------------|------------|------------|------------|------------------|------------|-------------|
| Duration       | ~47s       | ~37s       | ~22s       | ~25s             | ~24s       | ~34s        |
| Steps          | 13         | 10         | 5          | 5                | 8          | 8           |
| Custom View    | ✓          | ✓          | ✓          | ✓                | ✓          | ✓           |
| Record scope   | Single     | Single     | Single     | Single           | List       | List        |
| End state      | Created    | Updated    | Deleted    | Scheduler opened | Filtered   | Sorted      |
| URL params     | None       | None       | None       | None             | None       | `sort_order` + `sort_by` |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Step 8 element unknown** — "Click here" with no label; most likely a column header click or sort direction toggle |
| 2 | **Sort direction not confirmed** — Ascending is the presumed default after selecting Country; the recording does not explicitly show the order toggle interaction |
| 3 | **Field ID `955332000000427928` unresolved** — this previously-used sort field ID in the URL is not mapped to a field name in the available extraction |
| 4 | **Cancel preserves sort** — important UX distinction documented: Cancel closes the dialog but does not clear the active sort |
| 5 | **Country sort — business relevance** — for a real estate company, sorting leads by Country identifies NRI vs. domestic buyers; a key segmentation for Kurinjee Promoters |
| 6 | **Sort vs Filter distinction** — Sort orders the full list; Filter narrows the list. Both panels are accessed from the same toolbar and work independently or together |
| 7 | **URL encodes sort state** — unique to this flow; Zoho CRM persists sort configuration in the URL via `sort_order` and `sort_by` parameters, making sorted views bookmarkable/shareable |
