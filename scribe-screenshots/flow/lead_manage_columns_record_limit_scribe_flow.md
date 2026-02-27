> Scribe Source: https://scribehow.com/viewer/Manage_Columns_and_Record_Limit_in_Zoho_CRM__WLwf_7s1Tni7Pol1RQOEKg
> Recorded By: Sri Gnanathesigan
> Duration: ~44 seconds
> Total Steps: 9
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Manage Columns and Record Limit in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **managing visible columns and setting the record-per-page limit** on the Leads List View in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates two distinct list view customisations:

1. **Manage Columns** — adding/removing the `Lead Owner` column from the list view display
2. **Record Limit** — changing the per-page record count to `20`

9 UI interactions across approximately 44 seconds — the longest of the list-view operation flows.

> This is the third list-level customisation flow (alongside Filter and Sort), covering **how the list view itself is configured** rather than how individual records are managed.

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–9)                               |
| Screenshot style | Max-height 600px, max-width 720px per screenshot                 |
| Flow type       | List View configuration — two separate panels used               |
| Panels used     | Manage Columns panel + Record Limit dropdown                      |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list` |
| View Type       | Custom List View (ID: `955332000000441406`) |
| Pagination      | No params — cleanest URL of all six flows (no `page`, `sort_order`, or `per_page`) |
| Module          | Leads |

**Screenshot Analysis:**
- The Zoho CRM **Leads module** opens in the same custom list view used across all seven recordings
- This is the **bare URL** with no query parameters — the list loads with whatever session-default pagination and sort are currently active
- The list view toolbar is fully visible with all list management controls: New Lead, Import, Export, Actions, Filter, Sort, Columns, Search
- The current column set (before Step 3 changes) shows the default or previously saved column configuration
- The record-per-page count (before Step 9 changes) shows whatever the current session setting is

---

### Step 2 — Click the Columns / Settings Icon

| Property     | Detail |
|--------------|--------|
| Action       | Click icon |
| Icon Type    | Columns management icon — typically a grid/column icon (`⊞` or `|||`) |
| Location     | Top toolbar of the Leads list view, right section |

**Screenshot Analysis:**
- The recorder clicks a **toolbar icon** to access column management options
- In Zoho CRM's list view toolbar, this is the **Columns icon** — visually represented as a grid or parallel lines symbol, positioned to the right of the Sort button
- Toolbar layout reference:

  ```
  [New Lead] [Import] [Export] [Actions ▾] | [Filter] [Sort] [Columns ⊞] | [🔍 Search]
  ```

- Clicking this icon opens a **dropdown menu** containing column management options
- The icon is distinct from the Filter icon (funnel shape) and Sort icon (arrows) — it specifically controls which columns are visible in the list

---

### Step 3 — Select "Manage Columns" from Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click menu option |
| Option Label | `Manage Columns` |
| Menu Type    | Dropdown from Columns icon |

**Screenshot Analysis:**
- A **dropdown menu** opens from the Columns icon click
- The recorder selects **"Manage Columns"** from the menu
- The full dropdown menu from the Columns icon in Zoho CRM typically contains:

  | Menu Option       | Action |
  |-------------------|--------|
  | Manage Columns    | Opens the column selector panel to show/hide fields |
  | Resize Columns    | Allows drag-to-resize column widths |
  | Reset Columns     | Restores default column widths/selection |

- Selecting "Manage Columns" opens the **column selector panel** — a checklist of all available Lead module fields that can be shown or hidden as list columns

---

### Step 4 — Select "Lead Owner" Column in Manage Columns Panel

| Property     | Detail |
|--------------|--------|
| Action       | Click / check field |
| Field Label  | `Lead Owner` |
| Panel Type   | Manage Columns — checkbox field selector |
| Action Type  | Toggle visibility of the Lead Owner column |

**Screenshot Analysis:**
- The **Manage Columns panel** is open, showing all available Lead module fields as a checklist
- Fields with a **checkmark/tick** are currently visible as columns in the list; unchecked fields are hidden
- The recorder clicks on **"Lead Owner"** — either:
  - **Adding it** (checking it) — to make Lead Owner visible as a column if it was hidden
  - **Removing it** (unchecking it) — to hide Lead Owner if it was already showing
- The Manage Columns panel structure in Zoho CRM:

  ```
  ┌─────────────────────────────────────────────┐
  │  Manage Columns                             │
  ├──────────────────┬──────────────────────────┤
  │  Available       │  Selected Columns        │
  │  Fields          │  (drag to reorder)       │
  │                  │                          │
  │  □ Annual Revenue│  ☑ Name                 │
  │  □ City          │  ☑ Company              │
  │  □ Country       │  ☑ Phone                │
  │  □ Description   │  ☑ Lead Source          │
  │  □ Email         │  ☑ Lead Status          │
  │  ☑ Lead Owner    │  ☑ Lead Owner  ← target │
  │  □ Lead Quality  │  ☑ Created Time         │
  │  □ Mobile        │                          │
  │  □ State         │                          │
  └──────────────────┴──────────────────────────┘
  ```

- Standard default columns in Zoho CRM Leads list view:

  | Column Name    | Default Visibility | Standard / Custom |
  |----------------|--------------------|-------------------|
  | Name           | Always visible     | Standard          |
  | Company        | Visible            | Standard          |
  | Phone          | Visible            | Standard          |
  | Email          | Visible            | Standard          |
  | Lead Source    | Visible            | Standard          |
  | Lead Status    | Visible            | Standard          |
  | Lead Owner     | Visible            | Standard          |
  | Created Time   | Visible            | Standard          |
  | Mobile         | Hidden             | Standard          |
  | City           | Hidden             | Standard          |
  | State          | Hidden             | Standard          |
  | Country        | Hidden             | Standard          |
  | Annual Revenue | Hidden             | Standard          |
  | Lead Quality   | Hidden             | Standard          |
  | Client Location| Hidden             | Custom (Kurinjee) |
  | Telecaller     | Hidden             | Custom (Kurinjee) |
  | Language Preference | Hidden        | Custom (Kurinjee) |
  | Estimated Budget | Hidden           | Custom (Kurinjee) |

---

### Step 5 — Confirm "Lead Owner" Selection

| Property     | Detail |
|--------------|--------|
| Action       | Re-click / confirm selection |
| Field Label  | `Lead Owner` |
| Action Type  | Confirmation or finalization of the column selection |

**Screenshot Analysis:**
- The recorder interacts with **"Lead Owner"** a second time — this is either:
  - A **drag-and-drop reorder** — moving Lead Owner to a specific position in the selected columns list
  - A **double-click confirmation** — some Zoho CRM versions require a second click to move a field from Available to Selected
  - A **toggle correction** — unchecking and re-checking to confirm the selection state
- After both Steps 4 and 5, the Lead Owner column is confirmed in the selected columns list
- The column position in the selected list determines its order of appearance in the list view (left to right)

---

### Step 6 — Click "Save" to Apply Column Changes

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Save` |
| Button Style | Blue filled primary action button |
| Location     | Bottom of the Manage Columns panel |

**Screenshot Analysis:**
- The **"Save"** button is clicked to commit the column configuration changes
- On saving:
  - The Manage Columns panel closes
  - The Leads list view **refreshes** to reflect the updated column set
  - The **Lead Owner column** is now visible (or updated in position) in the list header
  - The column configuration is **saved to the user's profile** — it persists across sessions for this custom view
  - Other users viewing the same custom view may see a different column configuration (columns are per-user settings in Zoho CRM standard views)
- The list header row updates immediately to show the new column arrangement

---

### Step 7 — Click Another Icon to Access Record Limit

| Property     | Detail |
|--------------|--------|
| Action       | Click icon |
| Icon Type    | Pagination / records-per-page settings icon |
| Location     | Bottom or top pagination area of the Leads list view |

**Screenshot Analysis:**
- After saving column changes, the recorder shifts to a **different control** — the record limit / pagination setting
- This icon is separate from the Columns icon used in Step 2
- In Zoho CRM, the records-per-page control is typically found in the **pagination bar** at the bottom of the list view, or as a small dropdown icon near the page navigation controls
- The pagination bar layout:

  ```
  [← Prev]  Page 1 of 21  [Next →]  |  [20 ▾ per page]  |  Showing 1–20 of 2077
  ```

- The icon/control clicked in Step 7 opens a dropdown to change how many records are displayed per page

---

### Step 8 — Open Record Limit Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Dropdown Label | Records per page selector |
| Current Value | (unknown — depends on session state before recording) |
| Location     | Pagination area — bottom or top of list |

**Screenshot Analysis:**
- A **record limit dropdown** opens, showing all available per-page count options
- Standard Zoho CRM record-per-page options:

  | Option | Records Shown |
  |--------|---------------|
  | `10`   | 10 per page   |
  | `20`   | 20 per page   |
  | `25`   | 25 per page   |
  | `50`   | 50 per page   |
  | `100`  | 100 per page  |
  | `200`  | 200 per page  |

- The dropdown shows these values as a vertical list; the currently active value is highlighted
- For context: Flow 2, 3, and 4 used `per_page=100` in the URL; Flow 5 and 6 had no per_page param; this flow explicitly changes it to `20`

---

### Step 9 — Select "20" Records Per Page

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Value Selected | `20` |
| Field        | Records per page / pagination limit |

**Screenshot Analysis:**
- The recorder selects **"20"** as the records-per-page count
- On selecting:
  - The dropdown closes
  - The Leads list **reloads** displaying only 20 records per page
  - The pagination bar updates: `Showing 1–20 of 2077`
  - The page count increases: `Page 1 of 104` (2077 ÷ 20 = 103.85 → 104 pages)
  - The URL may update to append `&per_page=20`
- **Business context:** 20 records per page is a common preference for Telecallers who work through leads sequentially — enough to see a manageable batch without excessive scrolling
- This change is saved to the user's session/preference and persists until changed again

---

## Two Distinct Operations in This Flow

This recording covers **two separate list view customisations**:

### Operation 1 — Manage Columns (Steps 2–6)

```
[Columns ⊞ icon] → dropdown → [Manage Columns]
       |
       v
[Manage Columns panel opens]
       |
       v
[Select "Lead Owner" field — Steps 4 & 5]
       |
       v
[Click Save]
       |
       v
[List refreshes — Lead Owner column visible]
```

### Operation 2 — Record Limit (Steps 7–9)

```
[Pagination icon / per-page control]
       |
       v
[Record limit dropdown opens]
       |
       v
[Select "20"]
       |
       v
[List reloads — 20 records per page, pagination updates]
```

---

## Full URL Reference

| Element         | Value |
|-----------------|-------|
| CRM Base URL    | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL  | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list` |
| Custom View ID  | `955332000000441406` |
| Pagination      | No params (bare URL) |
| Org ID          | `60043078423` |

---

## Workflow Summary

```
[Leads List View — bare URL, no params]
       |
       v
[Click Columns icon (⊞) in toolbar]
       |
       v
[Dropdown opens → Click "Manage Columns"]
       |
       v
[Manage Columns panel opens]
  ├── Click "Lead Owner" (Step 4)
  └── Confirm "Lead Owner" (Step 5)
       |
       v
[Click "Save" → list refreshes with Lead Owner column]
       |
       v
[Click pagination/record-limit icon]
       |
       v
[Record limit dropdown opens]
       |
       v
[Select "20"]
       |
       v
[List reloads — 20 records per page]
```

---

## Comparison: All Seven Lead Flows

| Property       | Create (1) | Update (2) | Delete (3) | Rel. List (4) | Filter (5) | Sort (6) | Columns (7)       |
|----------------|------------|------------|------------|---------------|------------|----------|-------------------|
| Duration       | ~47s       | ~37s       | ~22s       | ~25s          | ~24s       | ~34s     | ~44s              |
| Steps          | 13         | 10         | 5          | 5             | 8          | 8        | 9                 |
| Custom View    | ✓          | ✓          | ✓          | ✓             | ✓          | ✓        | ✓                 |
| Record scope   | Single     | Single     | Single     | Single        | List       | List     | List              |
| End state      | Created    | Updated    | Deleted    | Scheduler     | Filtered   | Sorted   | Columns + limit set |
| Panels used    | Form       | Form       | Confirm    | Related list  | Filter     | Sort     | Manage Columns + Pagination |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Full column list not captured** — the complete list of available and selected columns in the Manage Columns panel was not extractable from Scribe; standard + known custom fields listed above as best approximation |
| 2 | **Steps 4 vs 5 distinction unclear** — "Choose Lead Owner" then "Confirm Lead Owner" may represent a two-click drag-and-drop interaction, or simply two screenshots of the same action at different stages |
| 3 | **Step 7 icon not labeled** — the pagination record-limit control icon was not named in the Scribe extraction; inferred from context as the per-page selector |
| 4 | **All per-page options not confirmed** — only "20" is explicitly captured; standard Zoho CRM options (10, 20, 25, 50, 100, 200) listed above based on platform knowledge |
| 5 | **Per-page value before change unknown** — the recording does not show the prior per-page setting; it was likely 100 (consistent with Flows 2–4) or the session default |
| 6 | **Column changes are user-specific** — Manage Columns settings in Zoho CRM standard list views are per-user, not per-view; each user sees their own column configuration |
| 7 | **Longest list-view flow** — at 44 seconds / 9 steps, this is more complex than Filter (24s/8) or Sort (34s/8) because it performs two separate operations |
