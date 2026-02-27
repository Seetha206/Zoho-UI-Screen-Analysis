> Scribe Source: https://scribehow.com/viewer/Export_Module_Records_in_CRM_Accounts__3K4_k1k4TqWsZYdqsdKO7Q
> Recorded By: Sri
> Duration: ~23 seconds
> Total Steps: 5
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Module — Record Export (Accounts) — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **exporting records from the Accounts module** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user navigates to the Accounts list view, accesses the Actions menu, selects "Export Accounts", chooses between field export options ("Fields from custom view" vs "All Fields"), and finalises the export — 5 UI interactions in approximately 23 seconds.

> **Record Export** in Zoho CRM allows users to download all records from a module as a CSV file. The export dialog gives control over which fields to include — either only the columns visible in the current list view (custom view fields) or the complete set of all available module fields. For Kurinjee Promoters, exporting Accounts would produce a spreadsheet of all real estate developer/client companies for offline analysis, reporting, or sharing with external teams.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–5)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Module list view — Actions menu → Export dialog                     |
| Module          | Accounts                                                            |
| Notable pattern | Paired with Flow 13 (Import) — Import and Export are complementary operations on the same module and list view |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Accounts List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Accounts/custom-view/955332000000441417/list` |
| View Type       | Custom List View (ID: `955332000000441417`) |
| Module          | Accounts |

**Screenshot Analysis:**
- Identical starting point to Flow 13 (Import) — the Accounts module opens in custom list view **`955332000000441417`**
- The Accounts list view is displayed with the toolbar showing the **Actions** button:

  ```
  ┌─────────────────────────────────────────────────────────┐
  │  Accounts  ▾ [View Name]  [+New]  [Actions ▾]  [⚙]    │
  ├─────────────────────────────────────────────────────────┤
  │ ☐  Account Name ↕   Phone ↕   Website ↕   Owner ↕     │
  ├─────────────────────────────────────────────────────────┤
  │ ☐  [Account 1]      ...        ...         Sri         │
  │ ☐  [Account 2]      ...        ...         ...         │
  │    ...                                                  │
  └─────────────────────────────────────────────────────────┘
  ```

- No `page`, `per_page`, or sort parameters in the URL — same clean list URL as Flow 13
- This is the **second consecutive Accounts module flow**, confirming the recorder's intention to document the full Import/Export pair for the Accounts module

---

### Step 2 — Click "Actions"

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `Actions` |
| Element Type | Dropdown trigger button |
| Location     | Accounts list view toolbar — top-right |

**Screenshot Analysis:**
- Unlike Flow 13 (Import) where the button was unlabeled ("Click this button"), Scribe correctly captured the label **"Actions"** here
- This confirms the element in Flow 13 Step 2 was also the **Actions** button — the same control
- Clicking "Actions" opens the **Actions dropdown menu** for the Accounts module list:

  ```
  ┌──────────────────────────────────┐
  │  Actions                     ▾  │
  ├──────────────────────────────────┤
  │  Mass Update                     │
  │  Mass Delete                     │
  │  ─────────────────────────────── │
  │  Import Accounts                 │
  │  Export Accounts      ← target   │
  │  ─────────────────────────────── │
  │  Deduplicate                     │
  └──────────────────────────────────┘
  ```

- Both Import and Export are grouped together in the Actions menu, accessible via the same toolbar button

---

### Step 3 — Click "Export Accounts"

| Property     | Detail |
|--------------|--------|
| Action       | Click menu item |
| Target       | `Export Accounts` |
| Element Type | Dropdown menu item |
| Location     | Actions dropdown — Accounts list view |

**Screenshot Analysis:**
- The recorder clicks **"Export Accounts"** from the Actions dropdown
- This opens the **Export Dialog** — a lightweight modal (not a full wizard like Import):

  ```
  ┌────────────────────────────────────────────────────────┐
  │  Export Accounts                                  [×]  │
  ├────────────────────────────────────────────────────────┤
  │                                                        │
  │  Select the fields to export:                          │
  │                                                        │
  │  ○ Fields from custom view        ← Step 4 target     │
  │  ○ All Fields                     ← Step 5 target     │
  │                                                        │
  ├────────────────────────────────────────────────────────┤
  │  [Export]                              [Cancel]        │
  └────────────────────────────────────────────────────────┘
  ```

- The Export dialog presents a **radio button choice** for field scope — the key decision in the export configuration

---

### Step 4 — Click "Fields from Custom View"

| Property     | Detail |
|--------------|--------|
| Action       | Click radio button option |
| Target       | `Fields from custom view` |
| Element Type | Radio button — export field scope selector |
| Location     | Export Accounts dialog |

**Screenshot Analysis:**
- The recorder first clicks **"Fields from custom view"** — the first radio button option in the Export dialog
- **"Fields from custom view"** exports only the columns currently visible in the active custom view (`955332000000441417`):
  - These are the fields the user has chosen to display in the list (configured via Manage Columns — Flow 7)
  - Typically includes: Account Name, Phone, Website, Owner, and any custom columns
  - The export CSV will have **fewer columns** but only the fields relevant to the current working context
- This click **selects** the "Fields from custom view" option — the radio button is now filled
- However, the recorder **does not stop here** — they proceed to Step 5 to switch to "All Fields", suggesting they evaluated both options before making their final choice

---

### Step 5 — Click "All Fields"

| Property     | Detail |
|--------------|--------|
| Action       | Click radio button option |
| Target       | `All Fields` |
| Element Type | Radio button — export field scope selector |
| Location     | Export Accounts dialog |

**Screenshot Analysis:**
- The recorder clicks **"All Fields"** — switching the selection from "Fields from custom view" to "All Fields"
- **"All Fields"** exports every available field in the Accounts module — both standard and custom fields:

  | Field Category      | Examples |
  |---------------------|----------|
  | Standard fields     | Account Name, Phone, Mobile, Website, Email, Fax |
  | Address fields      | Billing Address, Shipping Address (Street, City, State, Zip, Country) |
  | Business fields     | Industry, Account Type, Annual Revenue, No. of Employees |
  | CRM fields          | Owner, Created By, Modified By, Created Time, Modified Time |
  | Custom fields       | Any fields added by Kurinjee Promoters (e.g., Estimated Budget ₹) |

- With "All Fields" selected, the exported CSV will contain the **maximum available data** for each Account record
- The recording ends here — the final **"Export"** button click is not captured; however, clicking Export would:
  1. Generate the CSV file server-side
  2. Trigger a browser **file download** (`.csv`) of all Accounts records
  3. Show a success notification: "Your export is ready" or auto-download

---

## Export vs Import — Side-by-Side Comparison

| Aspect              | Import (Flow 13)                  | Export (Flow 14)                   |
|---------------------|-----------------------------------|------------------------------------|
| Direction           | External file → CRM               | CRM → External file                |
| Entry point         | Actions → Import Accounts         | Actions → Export Accounts          |
| Steps recorded      | 4 (ends at file picker)           | 5 (ends at field scope selection)  |
| Duration            | ~17 seconds                       | ~23 seconds                        |
| Field control       | Field mapping (CSV col → CRM field) | Field scope (view fields / all fields) |
| File format (input) | .csv, .xls, .xlsx                 | — (no upload)                      |
| File format (output)| — (no download)                   | .csv (download)                    |
| Duplicate handling  | Yes — Add / Update / Add+Update   | N/A                                |
| Completion captured | No (file browser opens)           | No (Export button click not shown) |
| Starting URL        | Same — `custom-view/955332000000441417/list` | Same |

---

## Export Field Scope — Decision Guide

| Option                   | Use Case | Output Size |
|--------------------------|----------|-------------|
| **Fields from custom view** | Quick extract for daily work — only the columns you use | Smaller CSV (fewer columns) |
| **All Fields**           | Full data backup, migration, or detailed analysis — every field | Larger CSV (all columns) |

For Kurinjee Promoters, **"All Fields"** (the recorder's final choice) is appropriate when:
- Exporting for data backup before a CRM migration
- Sharing full account details with an external team
- Analysing all custom fields including Estimated Budget ₹ in a spreadsheet

---

## URL Reference

| Element                   | Value |
|---------------------------|-------|
| CRM Base URL              | `https://crm.zoho.in/crm/org60043078423/` |
| Accounts List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Accounts/custom-view/955332000000441417/list` |
| Custom View ID (Accounts) | `955332000000441417` |
| Module                    | Accounts |
| Org ID                    | `60043078423` |
| Export Format             | CSV (`.csv`) |

---

## Workflow Summary

```
[Accounts List View — custom-view/955332000000441417/list]
       |
       v
[Click "Actions" button (Step 2)]
       |
       v
[Actions dropdown opens]
  Contains: Import Accounts, Export Accounts, Mass Update, etc.
       |
       v
[Click "Export Accounts" (Step 3)]
       |
       v
[Export Accounts dialog opens]
  Radio options: Fields from custom view | All Fields
       |
       v
[Click "Fields from custom view" (Step 4) — evaluating option]
       |
       v
[Click "All Fields" (Step 5) — final selection]
       |
       v  ← Recording ends here
[Click "Export" button — not recorded]
       |
       v
[CSV file downloaded to local system]
[Contains: all Account records × all fields]
```

---

## Comparison: All Fourteen Flows

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
| 13 | Record Import           | Accounts | 4     | ~17s     | Bulk import via CSV |
| 14 | Record Export           | Accounts | 5     | ~23s     | Export all records to CSV |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **"Actions" label now confirmed** — Step 2 in this flow captures the button as "Actions", retroactively confirming that Flow 13 Step 2's unlabeled "Click this button" was the same Actions dropdown trigger |
| 2 | **Two-step field scope evaluation** — the recorder clicked "Fields from custom view" (Step 4) before switching to "All Fields" (Step 5); this documents the deliberate decision to export all data rather than a filtered subset |
| 3 | **Export button not captured** — the final "Export" click that triggers the CSV download is outside the recording; the flow ends at the field scope selection |
| 4 | **Import/Export pair complete** — Flows 13 and 14 together document the full data portability story for the Accounts module: bulk upload (Import) and bulk download (Export) |
| 5 | **Same starting URL as Flow 13** — both Import (Flow 13) and Export (Flow 14) begin at the identical Accounts list URL with no additional parameters, confirming this is the team's default Accounts module entry point |
| 6 | **Custom view fields unknown** — the specific columns configured in custom view `955332000000441417` have not been captured; the recorder's initial consideration of "Fields from custom view" suggests the view has a meaningful subset of fields configured |
