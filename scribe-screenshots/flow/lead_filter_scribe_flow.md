> Scribe Source: https://scribehow.com/viewer/Filter_in_Leads_List_View__162JA0TtTgOb6w3THkMqSw
> Recorded By: Sri Gnanathesigan
> Duration: ~24 seconds
> Total Steps: 8
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Filter in Leads List View — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **applying a filter on the Leads List View** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how to open the filter panel, search for a field containing "lead", select a field, set the operator to `is not empty`, and apply the filter — 8 UI interactions in approximately 24 seconds.

> This is the first recording in the series that focuses on **list-level data operations** rather than individual record CRUD. Filtering is a core daily workflow for Telecallers managing 2,077+ leads.

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–8)                               |
| Screenshot style | Max-height 600px, max-width 720px per screenshot                 |
| Flow type       | List View operation — no record detail view opened               |
| Filter panel    | Slides in from the right side of the Leads list view             |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1` |
| View Type       | Custom List View (ID: `955332000000441406`) |
| Pagination      | Page 1 (no `per_page` param — uses default or session setting) |
| Module          | Leads |

**Screenshot Analysis:**
- The Zoho CRM **Leads module** opens in the same custom list view used across all five recordings
- This time the URL uses only `?page=1` without `&per_page=100` — the per-page count defaults to the CRM's session or user setting (typically 25 or 50 records)
- The list view shows the leads in tabular format with column headers, action buttons in the toolbar, and the custom view selector visible
- The **filter panel is closed** at this stage — the list shows unfiltered records from the custom view

---

### Step 2 — Click "Resize Handle Right" to Open Filter Panel

| Property     | Detail |
|--------------|--------|
| Action       | Click UI handle / toggle |
| Element Label | `Resize handle Right` |
| Element Type  | Panel toggle / expand handle |
| Location     | Right edge of the Leads list view |

**Screenshot Analysis:**
- The **"Resize handle Right"** is a clickable control on the **right edge of the Leads list view** — it toggles open the **Advanced Filter panel**
- In Zoho CRM's list view, the filter panel is a **collapsible right-side drawer** that slides in over or beside the list
- Before click: the filter panel is hidden; the leads list occupies the full content width
- After click: the **filter panel slides in from the right**, reducing the list width and revealing a search-based field selector
- The handle itself is typically a thin vertical bar or arrow icon (`›` / `‹`) at the right border of the list area
- This is the entry point to Zoho CRM's **Advanced Filter / Criteria-Based Filter** feature (distinct from the simple column sort/filter dropdowns)

---

### Step 3 — Click the "Search" Field Inside Filter Panel

| Property     | Detail |
|--------------|--------|
| Action       | Click text input |
| Field Label  | `Search` |
| Field Type   | Text search input |
| Location     | Top of the filter panel (right-side drawer) |

**Screenshot Analysis:**
- The filter panel is now open on the right side of the screen
- At the top of the filter panel is a **"Search" input field** — used to search through all available Lead fields by name
- The search field allows users to quickly find a specific field to filter by, rather than scrolling through the full field list
- The field list below the search box shows all available Lead module fields (standard + custom), likely organized alphabetically or by field group
- The filter panel UI structure:

  ```
  ┌─────────────────────────────┐
  │  [Search field]             │
  ├─────────────────────────────┤
  │  Field list:                │
  │  • Annual Revenue           │
  │  • City                     │
  │  • Client Location          │
  │  • Company                  │
  │  • ...                      │
  └─────────────────────────────┘
  ```

- Clicking the search field focuses it and prepares it for text input

---

### Step 4 — Type "lead" in Search Field

| Property     | Detail |
|--------------|--------|
| Action       | Keyboard input |
| Value Typed  | `lead` |
| Field        | Filter panel search input |
| Purpose      | Filter the field list to show only fields containing "lead" in their name |

**Screenshot Analysis:**
- The text `lead` is typed into the filter panel's search input
- The field list below **dynamically filters** to show only fields whose names contain the word "lead"
- Fields that would appear in search results for "lead":

  | Field Name              | Type       | Standard / Custom |
  |-------------------------|------------|-------------------|
  | Lead Owner              | Lookup     | Standard          |
  | Lead Source             | Dropdown   | Standard          |
  | Lead Status             | Dropdown   | Standard          |
  | Lead Type               | Dropdown   | Custom (Kurinjee) |
  | Lead Quality            | Dropdown   | Standard          |

- The recorder is narrowing down to a specific "lead" field to use as a filter criterion
- The dynamic search reduces the field list in real-time as each character is typed

---

### Step 5 — Click to Select a Field ("Click here")

| Property     | Detail |
|--------------|--------|
| Action       | Click field selection |
| Instruction  | `Click here` (no label captured — screenshot-only in Scribe) |
| Field Type   | One of the "lead" search results — likely `Lead Status` or `Lead Source` |
| Location     | Within the filtered field list in the filter panel |

**Screenshot Analysis:**
- After typing "lead", the filtered field list shows matching fields
- The recorder clicks on one of the field names to **select it as the filter criterion**
- The exact field selected is not captured in the Scribe text extraction (screenshot-only step)
- Based on the subsequent operator (`is not empty`) and common Zoho CRM filter usage, the most likely candidates are:
  - **`Lead Status`** — checking which leads have a status assigned
  - **`Lead Source`** — checking which leads have a source recorded
  - **`Lead Owner`** — checking which leads are assigned to an owner
- After selection, the field name appears as a **filter row** in the criteria builder with operator and value dropdowns alongside it

---

### Step 6 — Click "is" — Open Operator Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Dropdown Label | `is` (current/default operator) |
| Field Type   | Operator selector dropdown |
| Location     | Second column of the filter criteria row |

**Screenshot Analysis:**
- A filter criteria row is now visible in the panel:
  ```
  [Field Name]  |  [is ▾]  |  [Value input]
  ```
- The **operator dropdown** currently shows `is` as the default operator
- Clicking opens the full list of available filter operators for the selected field
- Standard Zoho CRM filter operators for dropdown/text fields:

  | Operator        | Meaning |
  |-----------------|---------|
  | `is`            | Exact match — equals value |
  | `is not`        | Does not equal value |
  | `contains`      | Value includes the text |
  | `does not contain` | Value excludes the text |
  | `starts with`   | Value begins with text |
  | `ends with`     | Value ends with text |
  | `is empty`      | Field has no value |
  | `is not empty`  | Field has any value (not blank) |

- The recorder opens this dropdown to change the operator from `is` to `is not empty`

---

### Step 7 — Select "is not empty" Operator

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Option Label | `is not empty` |
| Field Type   | Operator condition selector |

**Screenshot Analysis:**
- The operator dropdown is open with all available operators listed
- The recorder selects **"is not empty"** — this operator requires **no value input** (no third column needed)
- `is not empty` means: return all Lead records where the selected field **has any value assigned** (is not blank/null)
- After selecting `is not empty`:
  - The value input column in the criteria row disappears or becomes disabled (no value needed)
  - The filter criteria row now reads: `[Field Name]  is not empty`
- **Business meaning:** This filter is used to find leads where a key field has been filled in — e.g., "show me all leads that have a Lead Status assigned" or "show leads where Lead Source is recorded"
- This is a common data-quality or workflow filter — identifying leads that have been properly qualified vs. those with empty key fields

---

### Step 8 — Click "Apply Filter"

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Apply Filter` |
| Button Style | Blue filled primary action button |
| Location     | Bottom of the filter panel |

**Screenshot Analysis:**
- The **"Apply Filter"** button is clicked to execute the filter and apply the criteria to the Leads list
- On applying:
  - The Leads list refreshes to show only records matching the filter: leads where the selected field `is not empty`
  - The **record count** in the list header updates to reflect the filtered result count
  - The filter panel may remain open (showing active filter) or close depending on CRM settings
  - An **active filter indicator** or badge may appear in the list view header showing that a filter is active
  - The URL may update with filter parameters appended
- The filtered list shows leads sorted by the custom view's default sort order, restricted to records matching the criteria
- To clear the filter: users click a "Clear" or "Remove Filter" button, returning to the unfiltered custom view

---

## Filter Criteria Built in This Recording

```
[Selected "lead" field]  is not empty
```

| Component        | Value |
|------------------|-------|
| Field            | A field containing "lead" in its name (Lead Status / Lead Source / Lead Owner) |
| Operator         | `is not empty` |
| Value            | None required — blank check |
| Logical connector | Single condition (no AND/OR shown) |

---

## Filter Panel Architecture — Zoho CRM Leads List

```
Leads List View (full width)
       |
       v  [Click Resize Handle Right]
       |
┌──────────────────────┬────────────────────────┐
│  Leads List          │  Filter Panel          │
│  (narrowed width)    │  ┌──────────────────┐  │
│                      │  │ [Search field]   │  │
│  [Records filtered   │  ├──────────────────┤  │
│   by active criteria]│  │ Field list:      │  │
│                      │  │ > Lead Owner     │  │
│                      │  │ > Lead Quality   │  │
│                      │  │ > Lead Source    │  │
│                      │  │ > Lead Status    │  │
│                      │  │ > Lead Type      │  │
│                      │  ├──────────────────┤  │
│                      │  │ Criteria rows:   │  │
│                      │  │ [Field] [Op] [V] │  │
│                      │  ├──────────────────┤  │
│                      │  │ [Apply Filter]   │  │
│                      │  └──────────────────┘  │
└──────────────────────┴────────────────────────┘
```

---

## Full URL Reference

| Element         | Value |
|-----------------|-------|
| CRM Base URL    | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL  | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1` |
| Custom View ID  | `955332000000441406` |
| Pagination      | `page=1` (no per_page — default count) |
| Org ID          | `60043078423` |

---

## Workflow Summary

```
[Leads List View — Custom View, page=1]
       |
       v
[Click Resize Handle Right — opens filter panel]
       |
       v
[Filter panel slides in from right]
       |
       v
[Click Search field in filter panel]
       |
       v
[Type "lead" — field list filters dynamically]
       |
       v
[Click to select a "lead" field from results]
       |
       v
[Click "is" operator dropdown]
       |
       v
[Select "is not empty"]
       |
       v
[Click "Apply Filter"]
       |
       v
[Leads list refreshes — shows only records where selected field is not empty]
```

---

## Comparison: All Five Lead Flows

| Property         | Create (1)   | Update (2)   | Delete (3)   | Related List (4) | Filter (5)       |
|------------------|--------------|--------------|--------------|------------------|------------------|
| Duration         | ~47s         | ~37s         | ~22s         | ~25s             | ~24s             |
| Steps            | 13           | 10           | 5            | 5                | 8                |
| Entry point      | Leads list   | Leads list   | Leads list   | Leads list       | Leads list       |
| Custom View ID   | `955332000000441406` | `955332000000441406` | `955332000000441406` | `955332000000441406` | `955332000000441406` |
| Target record    | New          | `Sri Testing` | `Sri Testing` | `Sri Testing`   | All records (list level) |
| Form interaction | Full form    | Field edits  | None         | None             | Filter panel     |
| End state        | Created      | Updated      | Recycle Bin  | Scheduler opened | Filtered list    |
| Scope            | Single record | Single record | Single record | Single record   | **Entire list**  |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Field selected in Step 5 unknown** — Scribe captured "Click here" with no label; most likely `Lead Status`, `Lead Source`, or `Lead Owner` based on operator used |
| 2 | **Filter result count not captured** — the number of leads returned after applying the `is not empty` filter was not recorded in the Scribe output |
| 3 | **Single condition filter** — only one criteria row is built; Zoho CRM supports multi-condition filters with AND/OR logic, but this recording demonstrates the basic single-condition pattern |
| 4 | **URL unchanged** — the URL does not visibly reflect the applied filter; Zoho CRM may encode filter state in session/state rather than URL parameters for advanced filters |
| 5 | **Resize handle = filter toggle** — the "Resize handle Right" element is unique to this recording; it is Zoho CRM's collapsed filter panel toggle, not visible in any of the other four flows |
| 6 | **First list-level operation** — all prior recordings focused on individual records; this is the first flow demonstrating bulk list management via filtering |
| 7 | **`per_page` absent from URL** — unlike Flows 2–4, this URL uses only `?page=1`; the per-page count may have been reset to default between sessions |
