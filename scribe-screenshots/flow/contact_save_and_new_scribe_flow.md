> Scribe Source: https://scribehow.com/viewer/Module_Save_with_New_Flow_in_Zoho_CRMContact__xkCXbj56Q_Sadha20WRGDQ
> Recorded By: Sri
> Duration: ~20 seconds
> Total Steps: 6
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Module — Save and New Flow (Contact) — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **creating a new Contact record and saving it using the "Save and New" action** in Zoho CRM's Contacts module, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates the rapid entry pattern where a user creates a contact, fills in the name, and uses "Save and New" to immediately open a blank form for the next record — 6 UI interactions in approximately 20 seconds.

> **"Save and New"** is a batch-entry pattern in Zoho CRM. Unlike "Save" (which saves and returns to the list view) or "Save and Close" (which saves and closes the form), **Save and New** saves the current record and immediately presents a fresh blank creation form — enabling users to quickly add multiple records in sequence without navigating back to the list between each entry. This is especially valuable for Telecallers at Kurinjee Promoters who need to bulk-enter contacts converted from multiple lead sources.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–6)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Contact record creation — Save and New batch pattern                |
| Module          | Contacts (not Leads — first Contact module flow in the series)      |
| Notable pattern | First appearance of Contacts module; uses custom view ID `955332000000441440` |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Contacts List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Contacts/custom-view/955332000000441440/list?page=1` |
| View Type       | Custom List View (ID: `955332000000441440`) |
| Pagination      | `page=1` |
| Module          | Contacts |

**Screenshot Analysis:**
- The Zoho CRM Contacts module opens in a custom list view with ID **`955332000000441440`**
- This is the **first Contacts module URL** revealed across all recorded flows — the custom view ID `955332000000441440` is the Contacts module equivalent of `955332000000441406` (used for Leads in Flows 1–9)
- Contacts list view layout mirrors the Leads list view:

  ```
  ┌───────────────────────────────────────────────────────┐
  │  [Header: Search | Quick Add | Nav Icons]             │
  ├────────────────────────────────────────────────────────┤
  │  Contacts  ▾ [View: Custom View 441440]  [+New]       │
  │  ┌─────────────────────────────────────────────────┐  │
  │  │ ☐ Name          | Phone       | Email  | Owner  │  │
  │  │ ☐ Prasanth      | ...         | ...    | Sri    │  │
  │  │ ☐ [Contact 2]   | ...         | ...    | ...    │  │
  │  │ ...                                             │  │
  │  └─────────────────────────────────────────────────┘  │
  │  Showing 1-[N] of 26 contacts                         │
  └───────────────────────────────────────────────────────┘
  ```

- Kurinjee Promoters has **26 contacts** in CRM (as documented in the project overview)
- The Contacts module represents customers who have been converted from Leads or directly entered

---

### Step 2 — Click "Create Contact"

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `Create Contact` |
| Element Type | Primary action button (CTA) |
| Location     | Top-right of the Contacts list view toolbar |
| Equivalent   | The `+New` button or `Create Contact` CTA in the module header |

**Screenshot Analysis:**
- The recorder clicks the **"Create Contact"** button — this is the primary creation entry point in the Contacts list view
- In Zoho CRM, the creation button for Contacts is labeled either:
  - `+ New` (generic module button in the header)
  - `Create Contact` (contextual label specific to the Contacts module)
- Clicking opens the **Contact Creation Form** — a modal or full-page form
- The Contact creation form structure:

  ```
  ┌────────────────────────────────────────────────────┐
  │  Create Contact                              [×]   │
  ├────────────────────────────────────────────────────┤
  │  First Name: [Mr. ▾] [__________]                  │
  │  Last Name:  [__________] *                        │
  │  Account Name: [__________]                        │
  │  Title:      [__________]                          │
  │  Email:      [__________]                          │
  │  Phone:      [__________]                          │
  │  Mobile:     [__________]                          │
  │  Lead Source: [Dropdown ▾]                         │
  │  Department: [__________]                          │
  │  ...                                               │
  ├────────────────────────────────────────────────────┤
  │  [Save]  [Save and New]  [Cancel]                  │
  └────────────────────────────────────────────────────┘
  ```

---

### Step 3 — Click Text Field (Name Input)

| Property     | Detail |
|--------------|--------|
| Action       | Click text input |
| Target       | Text input field (name field — First Name or Last Name) |
| Element Type | `<input type="text">` — text field |
| Location     | Contact creation form — name section |

**Screenshot Analysis:**
- The recorder clicks into the text input field to place the cursor and enable typing
- In Zoho CRM's Contact creation form, the first interactive field is typically the **First Name** field (with a salutation prefix dropdown: Mr., Ms., Mrs., Dr., Prof.)
- The **Last Name** field is the only mandatory field for Contact creation in standard Zoho CRM — marked with an asterisk (`*`)
- Clicking the field:
  - Places cursor inside the input
  - May show a placeholder hint text disappear (e.g., `Enter first name`)
  - Activates the field for keyboard input

---

### Step 4 — Type "Sri Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Keyboard text entry |
| Target       | Active text field (name input) |
| Input value  | `Sri Testing` |
| Element Type | Text input — name field |

**Screenshot Analysis:**
- The recorder types **"Sri Testing"** — the consistent test record name used across all flows in this recording series
- As text is typed, the field displays each character in sequence
- "Sri Testing" in the Contact module context:
  - First Name: `Sri` | Last Name: `Testing`
  - OR entered as a single string in the Last Name field: `Sri Testing`
  - The Scribe tool captured this as a single type action, suggesting it may have been entered into the Last Name field or First Name field

  | Field     | Value (inferred split) |
  |-----------|------------------------|
  | First Name | `Sri`                 |
  | Last Name  | `Testing`             |

- This is a **test/dummy contact** — not a real Kurinjee Promoters customer — used to demonstrate the Save and New flow without entering real client data

---

### Step 5 — Click Expanded Field Section

| Property     | Detail |
|--------------|--------|
| Action       | Click expandable section / multi-field area |
| Target       | `Title  Last Name  Estimated Budget ₹  Lead Source...` |
| Element Type | Expandable form section / additional fields panel |
| Location     | Contact creation form — below primary name fields |

**Screenshot Analysis:**
- The Scribe tool captured this action with a label containing multiple field names: **`Title  Last Name  Estimated Budget ₹  Lead Source...`**
- This label indicates the recorder clicked on a **section header or expandable panel** that reveals additional contact fields — a common Zoho CRM form pattern where secondary fields are collapsed by default
- The presence of **"Estimated Budget ₹"** is notable — this is a **custom field** added to the Contacts module for Kurinjee Promoters, representing the prospect's property budget in Indian Rupees (₹)
- Fields revealed in this expanded section:

  | Field              | Type     | Notes |
  |--------------------|----------|-------|
  | Title              | Text     | Job title / designation |
  | Last Name          | Text *   | Mandatory — may already have "Testing" entered |
  | Estimated Budget ₹ | Currency | Custom field — Kurinjee Promoters specific |
  | Lead Source        | Dropdown | Where the contact came from |
  | ...                | ...      | Additional standard/custom fields |

- **"Estimated Budget ₹"** confirms that the Contacts module has been customized for Kurinjee Promoters' real estate sales process — matching the Lead module which also tracks budget/property preferences
- The recorder may have clicked this section to scroll to or reveal additional fields before saving — or it may represent a click on the section container that Scribe captured as an interaction

---

### Step 6 — Click "Save and New"

| Property     | Detail |
|--------------|--------|
| Action       | Click action button |
| Target       | `Save and New` |
| Element Type | Secondary save action button |
| Location     | Bottom of the Contact creation form — action button row |

**Screenshot Analysis:**
- The recorder clicks **"Save and New"** — the batch-entry save action
- In Zoho CRM's form action bar, the standard button sequence is:

  ```
  ┌─────────────────────────────────────────────┐
  │  [Save]   [Save and New]   [Cancel]          │
  └─────────────────────────────────────────────┘
  ```

- **"Save and New"** behavior:
  1. Validates the form (mandatory fields — Last Name must be filled)
  2. Saves the new Contact record to the database
  3. Assigns it a Zoho CRM Record ID (e.g., `955332000000XXXXXX`)
  4. **Immediately opens a fresh, blank Contact creation form** — ready for the next entry
  5. Does NOT navigate to the list view or the record detail view
- After the click:
  - The "Sri Testing" contact record is created and saved
  - The form resets to empty state
  - The user can immediately begin entering the next contact
- Contrast with other save actions:

  | Button         | Behavior After Save |
  |----------------|---------------------|
  | `Save`         | Navigate to the saved record's detail view |
  | `Save and New` | Open a fresh blank creation form — stay in create mode |
  | `Cancel`       | Discard form — return to list view |

---

## Contact Creation Form — Field Architecture

### Standard Contact Fields (Zoho CRM Default)

| Field           | Type       | Mandatory | Notes |
|-----------------|------------|-----------|-------|
| Salutation      | Dropdown   | No        | Mr., Ms., Mrs., Dr., Prof. |
| First Name      | Text       | No        | |
| Last Name       | Text       | **Yes**   | Only mandatory field |
| Account Name    | Lookup     | No        | Links to Accounts module |
| Title           | Text       | No        | Job title |
| Email           | Email      | No        | Primary email |
| Phone           | Phone      | No        | |
| Mobile          | Phone      | No        | |
| Lead Source     | Dropdown   | No        | Campaign / channel |
| Department      | Text       | No        | |
| Date of Birth   | Date       | No        | |

### Custom Fields — Kurinjee Promoters (Contacts Module)

| Field              | Type     | Notes |
|--------------------|----------|-------|
| Estimated Budget ₹ | Currency | Property purchase budget — custom field |

---

## Module Comparison: Lead vs Contact Custom View IDs

| Module   | Custom View ID         | URL Pattern |
|----------|------------------------|-------------|
| Leads    | `955332000000441406`   | `/tab/Leads/custom-view/955332000000441406/list` |
| Contacts | `955332000000441440`   | `/tab/Contacts/custom-view/955332000000441440/list` |

- IDs `441406` and `441440` are close together — both custom views were likely created during the same CRM customisation session for Kurinjee Promoters
- Difference: `441440 − 441406 = 34` — consistent with Zoho's sequential ID increment pattern

---

## URL Reference

| Element                   | Value |
|---------------------------|-------|
| CRM Base URL              | `https://crm.zoho.in/crm/org60043078423/` |
| Contacts List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Contacts/custom-view/955332000000441440/list?page=1` |
| Custom View ID (Contacts) | `955332000000441440` |
| Module                    | Contacts |
| Org ID                    | `60043078423` |
| Test Record Name          | `Sri Testing` |

---

## Workflow Summary

```
[Contacts List View — custom-view/955332000000441440/list, page=1]
       |
       v
[Click "Create Contact" (Step 2)]
       |
       v
[Contact Creation Form opens]
       |
       v
[Click name text field (Step 3)]
       |
       v
[Type "Sri Testing" (Step 4)]
       |
       v
[Click expanded fields section — Title / Last Name / Estimated Budget / Lead Source (Step 5)]
       |
       v
[Click "Save and New" (Step 6)]
       |
       v
[Record saved: "Sri Testing" contact created]
[Fresh blank Contact creation form opens]
[Ready for next contact entry — batch mode active]
```

---

## Comparison: All Eleven Flows

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

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **First Contacts module flow** — Flows 1–10 all operated on the Leads module; this is the first flow recorded in the Contacts module |
| 2 | **Custom field confirmed: "Estimated Budget ₹"** — the presence of this field in Step 5's label confirms that Kurinjee Promoters has added a currency custom field to the Contacts module, matching the real estate sales workflow |
| 3 | **Step 5 label ambiguity** — the concatenated label `Title  Last Name  Estimated Budget ₹  Lead Source...` suggests Scribe captured a click on a form section container rather than a specific field; the exact UI element is a section toggle or the form body area |
| 4 | **Only Last Name filled** — with only "Sri Testing" typed and Save and New clicked, the Last Name field likely contains the full string "Sri Testing"; first name may be empty since only one type action was recorded |
| 5 | **20-second duration** — the fastest multi-step creation flow recorded; demonstrates that Save and New is optimized for rapid entry (no detail view navigation between records) |
| 6 | **Contacts module has 26 records** — after this flow, the count may have incremented to 27 (if "Sri Testing" contact was not later deleted) |
| 7 | **No URL captured post-save** — the URL after clicking "Save and New" (the fresh form URL) is not captured; expected to be the same Contacts creation URL with a new empty form state |
