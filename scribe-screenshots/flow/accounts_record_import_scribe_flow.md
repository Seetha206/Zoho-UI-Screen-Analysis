> Scribe Source: https://scribehow.com/viewer/Module_Record_Import_in_CRM_Accounts__Twz5-RybQgu5mUlD49YU-w
> Recorded By: Sri
> Duration: ~17 seconds
> Total Steps: 4
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Module — Record Import (Accounts) — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **importing records into the Accounts module** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user navigates to the Accounts list view, accesses the Actions menu, selects "Import Accounts", and reaches the file upload field — 4 UI interactions in approximately 17 seconds.

> **Record Import** in Zoho CRM allows users to bulk-upload records from a CSV or Excel file into any CRM module. The import wizard maps file columns to CRM fields, handles duplicates, and creates or updates records in batch. For the Accounts module at Kurinjee Promoters, this flow would be used to bulk-load company/builder/developer accounts (e.g., a list of housing projects or real estate developers) without manual one-by-one entry.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–4)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Module list view — Actions menu → Import wizard                     |
| Module          | Accounts (first Accounts module flow in the series)                 |
| Notable pattern | Recording ends at file upload field — full import wizard not captured |

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
- The Zoho CRM Accounts module opens in custom list view **`955332000000441417`**
- This is the **first Accounts module URL** revealed across all 13 recorded flows — a new module in the series
- Custom view IDs across all three modules now confirmed:

  | Module   | Custom View ID         | ID Suffix |
  |----------|------------------------|-----------|
  | Leads    | `955332000000441406`   | `441406`  |
  | Accounts | `955332000000441417`   | `441417`  |
  | Contacts | `955332000000441440`   | `441440`  |

  - All three IDs are sequential within a narrow range (`441406` → `441417` → `441440`), confirming they were created together during the same Kurinjee Promoters CRM customisation session
  - Accounts sits between Leads (`406`) and Contacts (`440`) in the ID sequence

- Accounts module list view layout:

  ```
  ┌─────────────────────────────────────────────────────────┐
  │  [Header: Search | Quick Add | Nav Icons]               │
  ├─────────────────────────────────────────────────────────┤
  │  Accounts  ▾ [View Name]  [+New]  [Actions ▾]  [⚙]    │
  ├─────────────────────────────────────────────────────────┤
  │ ☐  Account Name ↕   Phone ↕   Website ↕   Owner ↕     │
  ├─────────────────────────────────────────────────────────┤
  │ ☐  [Account 1]      ...        ...         Sri         │
  │ ☐  [Account 2]      ...        ...         ...         │
  │    ...                                                  │
  └─────────────────────────────────────────────────────────┘
  │  Showing 1–[N] of [total] Accounts                      │
  └─────────────────────────────────────────────────────────┘
  ```

- The Accounts module in Zoho CRM represents **companies, organisations, or business entities** — in the real estate context of Kurinjee Promoters, these would be:
  - Property developers / builders
  - Corporate clients making bulk bookings
  - Channel partner agencies
  - Housing projects or residential societies

---

### Step 2 — Click the Actions / Import Button

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | Unlabeled button (Scribe: "Click this button") |
| Element Type | Toolbar button — Actions dropdown trigger |
| Location     | Accounts list view toolbar — top-right area |

**Screenshot Analysis:**
- The recorder clicks an **unlabeled button** — Scribe captured it as "Click this button" without a text label, indicating an icon-only button or a button whose label was not captured
- In the Zoho CRM module list view toolbar, the standard import entry point is accessed via:
  - **`Actions ▾`** — a dropdown button in the list toolbar that reveals bulk operations
  - **`⚙` (gear/settings icon)** — in some layouts, module-level settings including import
  - **`Import` link** — occasionally shown as a direct link when no records exist

- The **Actions dropdown** in Zoho CRM list views contains:

  ```
  ┌──────────────────────────────────┐
  │  Actions                     ▾  │
  ├──────────────────────────────────┤
  │  Mass Update                     │
  │  Mass Delete                     │
  │  Mass Convert                    │
  │  ─────────────────────────────── │
  │  Import Accounts      ← target   │
  │  Export Accounts                 │
  │  ─────────────────────────────── │
  │  Deduplicate                     │
  └──────────────────────────────────┘
  ```

- After clicking this button, the Actions dropdown opens, revealing the "Import Accounts" option

---

### Step 3 — Click "Import Accounts"

| Property     | Detail |
|--------------|--------|
| Action       | Click menu item |
| Target       | `Import Accounts` |
| Element Type | Dropdown menu item |
| Location     | Actions dropdown — Accounts list view |

**Screenshot Analysis:**
- The recorder clicks **"Import Accounts"** from the Actions dropdown
- This triggers the **Zoho CRM Import Wizard** — a multi-step modal dialog for bulk record import
- The Import Wizard for Accounts opens to its **first step — File Upload**:

  ```
  ┌────────────────────────────────────────────────────────┐
  │  Import Accounts                                  [×]  │
  ├────────────────────────────────────────────────────────┤
  │                                                        │
  │  STEP 1 OF 3: Upload File                              │
  │                                                        │
  │  [  Drag and drop your file here  ]                    │
  │  [  or click to browse            ]  ← file field     │
  │                                                        │
  │  Supported formats: .csv, .xls, .xlsx, .vcf, .ics     │
  │  Maximum file size: 5 MB                               │
  │  Maximum records: 30,000 per import                    │
  │                                                        │
  │  Import Type:                                          │
  │  ○ Add as New Records                                  │
  │  ○ Update Existing Records                             │
  │  ○ Add and Update Records                              │
  │                                                        │
  ├────────────────────────────────────────────────────────┤
  │  [Next >]                              [Cancel]        │
  └────────────────────────────────────────────────────────┘
  ```

---

### Step 4 — Click File Upload Field

| Property     | Detail |
|--------------|--------|
| Action       | Click file input |
| Target       | File upload field (Scribe: "Click this file field") |
| Element Type | `<input type="file">` — file browser trigger |
| Location     | Import Wizard — Step 1 (Upload File) |

**Screenshot Analysis:**
- The recorder clicks the **file upload field** — the drag-and-drop zone or browse button in the Import Wizard
- Clicking this field opens the **operating system file browser dialog** — allowing the user to navigate to and select the CSV/Excel file to import
- Zoho CRM's Import Wizard file field accepts:

  | Format | Extension | Notes |
  |--------|-----------|-------|
  | CSV    | `.csv`    | Most common; plain comma/semicolon delimited |
  | Excel  | `.xls`    | Legacy Excel format |
  | Excel  | `.xlsx`   | Modern Excel format |
  | vCard  | `.vcf`    | For Contact imports only |
  | iCal   | `.ics`    | For Activities/Tasks only |

- The recording **ends at this step** — the file selection dialog opening is an OS-level event (not a browser UI interaction), so Scribe cannot capture what file was selected or whether the import was completed

---

## Import Wizard — Full Flow (Beyond Recording)

The 4-step recording captures only the entry path to the import wizard. The complete import process in Zoho CRM continues as:

### Step 1 — Upload File (Recorded — Step 4)
- Select CSV/Excel file from local system
- Choose import type: Add New / Update Existing / Add and Update

### Step 2 — Map Fields (Not recorded)
```
┌──────────────────────────────────────────────────────┐
│  STEP 2 OF 3: Map Fields                             │
├──────────────────────────────────────────────────────┤
│  File Column          │  CRM Field                   │
│  ─────────────────────│──────────────────────────── │
│  Account Name         │  Account Name          ▾    │
│  Phone                │  Phone                 ▾    │
│  Website              │  Website               ▾    │
│  [Custom Column]      │  Estimated Budget ₹    ▾    │
│  [Skip Column]        │  Don't Import          ▾    │
└──────────────────────────────────────────────────────┘
│  [< Back]                              [Next >]      │
└──────────────────────────────────────────────────────┘
```

### Step 3 — Review & Import (Not recorded)
```
┌──────────────────────────────────────────────────────┐
│  STEP 3 OF 3: Preview & Import                       │
├──────────────────────────────────────────────────────┤
│  Records to import: [N]                              │
│  Duplicate handling: Skip / Update                   │
│  Duplicate check field: Account Name                 │
├──────────────────────────────────────────────────────┤
│  [< Back]                         [Import Now]       │
└──────────────────────────────────────────────────────┘
```

### Post-Import Result (Not recorded)
- Import job runs in the background (async for large files)
- A notification banner appears: "Import completed — X records added, Y records updated, Z records failed"
- Failed records downloadable as an error log CSV

---

## Accounts Module — Kurinjee Promoters Context

| Property        | Detail |
|-----------------|--------|
| Module          | Accounts |
| CRM Function    | Companies, organisations, developers linked to Contacts and Deals |
| Custom View ID  | `955332000000441417` |
| Import Use Case | Bulk-load real estate developers, corporate clients, or channel partners |

### Typical Account Record Fields (Zoho CRM Default)

| Field            | Type      | Notes |
|------------------|-----------|-------|
| Account Name     | Text *    | Mandatory — company name |
| Phone            | Phone     | Office phone |
| Website          | URL       | Company website |
| Account Type     | Dropdown  | Analyst, Partner, Customer, etc. |
| Industry         | Dropdown  | Real Estate, Construction, etc. |
| Annual Revenue   | Currency  | Company revenue |
| No. of Employees | Integer   | Headcount |
| Description      | Text Area | Notes about the account |
| Owner            | Lookup    | CRM user responsible |

---

## Custom View ID Registry — All Modules Confirmed

| Module   | Custom View ID         | ID Suffix | Sequence |
|----------|------------------------|-----------|----------|
| Leads    | `955332000000441406`   | `441406`  | 1st      |
| Accounts | `955332000000441417`   | `441417`  | 2nd      |
| Contacts | `955332000000441440`   | `441440`  | 3rd      |

- All three created within the same Zoho CRM customisation session for Kurinjee Promoters
- ID gap between Leads→Accounts: `11`; Accounts→Contacts: `23`
- All follow the prefix `955332000000` — the Zoho CRM record ID namespace for this org

---

## URL Reference

| Element                   | Value |
|---------------------------|-------|
| CRM Base URL              | `https://crm.zoho.in/crm/org60043078423/` |
| Accounts List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Accounts/custom-view/955332000000441417/list` |
| Custom View ID (Accounts) | `955332000000441417` |
| Module                    | Accounts |
| Org ID                    | `60043078423` |

---

## Workflow Summary

```
[Accounts List View — custom-view/955332000000441417/list]
       |
       v
[Click Actions / Import button (Step 2)]
       |
       v
[Actions dropdown opens]
  Contains: Mass Update, Mass Delete, Import Accounts, Export Accounts
       |
       v
[Click "Import Accounts" (Step 3)]
       |
       v
[Import Wizard opens — Step 1: Upload File]
       |
       v
[Click file upload field (Step 4)]
       |
       v
[OS file browser opens — user selects CSV/Excel file]
       |
       v  ← Recording ends here
[Import Wizard Step 2: Map Fields]
       |
       v
[Import Wizard Step 3: Review & Import]
       |
       v
[Import job runs — records created in Accounts module]
```

---

## Comparison: All Thirteen Flows

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

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **First Accounts module flow** — Flows 1–10 were Leads, 11–12 were Contacts; this is the first flow in the Accounts module, expanding the module coverage of the series |
| 2 | **Accounts custom view ID confirmed** — `955332000000441417` is now the third custom view ID identified, completing the Lead/Contact/Account trilogy of default views for Kurinjee Promoters |
| 3 | **Step 2 element unlabeled** — the Actions dropdown trigger is captured as "Click this button" by Scribe; it is the standard `Actions ▾` toolbar button present in all Zoho CRM list views |
| 4 | **Recording ends before file selection** — the import flow is captured only up to the file picker trigger; the file chosen, field mapping, and final import confirmation are not recorded |
| 5 | **Import type not confirmed** — the Import Wizard offers Add New, Update Existing, or Add and Update; the recorder's intent (adding new accounts or updating existing ones) is not captured |
| 6 | **No `per_page` or sort params in URL** — unlike Flows 11–12 (Contacts), the Accounts list URL has no pagination parameters, suggesting the user navigated directly to the default list state |
| 7 | **All 13 flows now documented** — this completes the full set of Scribehow recordings listed in `screenshot-link-url.txt`; all flows across Leads, Contacts, and Accounts modules have been extracted and documented |
