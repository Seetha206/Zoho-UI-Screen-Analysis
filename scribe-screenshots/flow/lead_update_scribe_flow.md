> Scribe Source: https://scribehow.com/viewer/Update_Lead_in_Zoho_CRM__z7bhcBkxSbeu2TgL1vuegQ
> Recorded By: Sri Gnanathesigan
> Duration: ~37 seconds
> Total Steps: 10
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Update Lead Record in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **updating an existing Lead record** in Zoho CRM as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates editing a previously created test lead (`Sri Testing`), updating the **Lead Quality** to `Junk`, setting a **Lead Status**, and entering a **date value** — 10 discrete UI interactions across approximately 37 seconds.

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent buttons and step badges             |
| Step indicators | Blue circular numbered badges (1–10)                              |
| Screenshot style | Max-height 600px per screenshot, rounded corners, shadow effect  |
| Form layout     | Inline edit mode within lead detail view                          |
| Navigation      | Leads list → Lead detail view → Edit mode → Save                 |

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
- The Zoho CRM **Leads module** is open in the same custom list view used during lead creation
- The URL includes pagination parameters: `page=1&per_page=100` — the list is set to display up to 100 records per page
- The custom view ID (`955332000000441406`) is consistent with the lead creation recording — same saved filtered view
- Existing lead records are displayed in tabular format
- The target lead (`Sri Testing`) is visible in the list and ready to be selected

---

### Step 2 — Select Lead: "Sri Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Click on lead record |
| Target       | `Sri Testing` |
| Record Type  | Lead — the test record created in the lead creation flow |
| Location     | Lead list row / clickable name cell |

**Screenshot Analysis:**
- The lead list is displayed with records as clickable rows or name links
- The recorder clicks directly on **"Sri Testing"** — the test lead created in the previous recording
- This navigates to the **Lead Detail View** for that specific record
- The list shows lead names in the first/primary column as hyperlinks (standard Zoho CRM list layout)
- Other columns likely visible: Phone, Email, Lead Status, Lead Owner, Created Date — standard Leads list fields

---

### Step 3 — Click "Edit" Button

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Edit` |
| Button Style | Blue or gray secondary action button |
| Location     | Top of Lead Detail View — action bar |

**Screenshot Analysis:**
- The **Lead Detail View** for `Sri Testing` is now open
- The detail view shows all filled and empty field values for the record
- An **"Edit"** button is visible in the top action bar (alongside other options like Delete, Convert, Send Email)
- Clicking "Edit" switches the view from read-only detail mode to **inline edit/form mode**
- All fields become editable inputs — text fields, dropdowns, and date pickers activate
- The form retains the same section structure (Lead Information collapsible blocks) as the creation form

---

### Step 4 — Click Lead Quality Dropdown ("-None-")

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Field Label  | Lead Quality (implied from context) |
| Current Value | `-None-` |
| Field Type   | Single-select dropdown |

**Screenshot Analysis:**
- In edit mode, the **Lead Quality** field (currently set to `-None-`) is clicked
- The dropdown opens to display classification options
- Lead Quality is a **standard Zoho CRM Leads field** used to categorize lead value/intent
- The field is in its default empty state (`-None-`) because this field was not filled during creation
- The dropdown renders as a floating option list over the form
- The active field border highlights in blue on click

---

### Step 5 — Select "Junk" from Lead Quality Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Field Label  | Lead Quality |
| Value Selected | `Junk` |
| Field Type   | Single-select dropdown |

**Screenshot Analysis:**
- The dropdown list is open with Lead Quality options visible
- The option **"Junk"** is selected — this classifies the lead as low quality / not worth pursuing
- Standard Zoho CRM Lead Quality options typically include: `Hot`, `Cold`, `Warm`, `Junk`
- Selecting `Junk` closes the dropdown and sets the field value to `Junk`
- This classification is commonly used in real estate CRM workflows to mark:
  - Wrong numbers
  - Non-serious inquiries
  - Duplicate entries
  - Test records (as is the case here with `Sri Testing`)
- After selection the field visually updates to show `Junk` as the current value

---

### Step 6 — Click "Lead Status" Field

| Property     | Detail |
|--------------|--------|
| Action       | Click field / dropdown |
| Field Label  | `Lead Status` |
| Field Type   | Single-select dropdown |
| Current Value | `Unassigned` (visible in Step 9 context) |

**Screenshot Analysis:**
- The **Lead Status** field is clicked in the edit form
- `Lead Status` is a **standard Zoho CRM field** that tracks where the lead is in the qualification pipeline
- From the Step 9 content snapshot, the current value is `Unassigned` — the default state for a newly created lead with no owner assigned
- Standard Zoho CRM Lead Status values: `Not Contacted`, `Attempted to Contact`, `Contacted`, `Junk Lead`, `Lost Lead`, `Pre-Qualified`
- Custom orgs (like Kurinjee Promoters) may have additional or renamed status values aligned with their sales process
- The dropdown opens on click to show available status options

---

### Step 7 — Click Date Picker Field (DD/MM/YYYY)

| Property     | Detail |
|--------------|--------|
| Action       | Click date input |
| Field Placeholder | `DD/MM/YYYY` |
| Field Type   | Date picker |

**Screenshot Analysis:**
- A **date field** is clicked, displaying the Indian date format placeholder `DD/MM/YYYY`
- This is likely a field such as: `Follow Up Date`, `Last Contacted Date`, or a custom date field
- Clicking opens a **calendar picker widget** — a month/day/year selector
- The calendar shows the current month by default, allowing date selection
- The Indian date format confirms Zoho CRM regional settings are configured for India (IST timezone)

---

### Step 8 — Select Date: Day "18"

| Property     | Detail |
|--------------|--------|
| Action       | Click calendar day |
| Value Selected | Day `18` (month/year not captured) |
| Field Type   | Calendar date picker |

**Screenshot Analysis:**
- The calendar picker widget is open showing a month grid
- The user clicks on day **"18"** to select the date
- The month and year are not explicitly captured in the Scribe extraction — likely the current month at time of recording
- After clicking 18, the calendar closes and the date field populates with the selected date in `DD/MM/YYYY` format
- The selected date appears in the field as e.g. `18/MM/YYYY` (actual month substituted)

---

### Step 9 — Scroll Through Additional Form Fields

| Property     | Detail |
|--------------|--------|
| Action       | Scroll / click through form |
| Visible Content | Extended field list visible in form |

**Screenshot Analysis:**
This step reveals the **most complete view of the Lead edit form fields** visible during the recording. The captured section text reads:

```
Mobile
Lead Source     -None-
Lead Status     Unassigned
Email
Estimated Budget...  (truncated)
```

Full field inventory visible in this step:

| # | Field Label         | Field Type       | Visible Value   |
|---|---------------------|------------------|-----------------|
| 1 | Mobile              | Phone input      | (value not shown) |
| 2 | Lead Source         | Dropdown         | `-None-`        |
| 3 | Lead Status         | Dropdown         | `Unassigned`    |
| 4 | Email               | Email input      | (empty)         |
| 5 | Estimated Budget    | Text / Currency  | (truncated)     |

**Key observations:**
- **`Lead Source`** is a standard Zoho CRM field (Web, Cold Call, Advertisement, etc.) — left at `-None-`
- **`Lead Status = Unassigned`** confirms this is the default value for newly created leads with no owner
- **`Estimated Budget`** is a **custom field** for Kurinjee Promoters — relevant to real estate sales qualification
- The form has multiple sections and requires scrolling to see all fields
- **`Mobile`** appears as a separate field from **`Phone`** (entered in creation flow) — Zoho CRM has both fields in the Leads module

---

### Step 10 — Click "Save" Button

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Save` |
| Button Style | Blue filled primary action button |
| Location     | Top action bar or bottom of form |

**Screenshot Analysis:**
- The **"Save"** button is clicked to commit all changes made during the edit session
- Changes being saved:
  - `Lead Quality` → `Junk`
  - `Lead Status` → (value selected in Step 6)
  - Date field → `18` (of current month)
- Zoho CRM validates required fields before saving
- On successful save, the form returns to the **Lead Detail View** showing updated field values
- A success notification/toast may briefly appear confirming the record was updated

---

## Fields Updated in This Recording

| Field            | Before     | After     | Field Type      |
|------------------|------------|-----------|-----------------|
| Lead Quality     | `-None-`   | `Junk`    | Standard dropdown |
| Lead Status      | `Unassigned` | (selected) | Standard dropdown |
| Date field       | Empty      | `18/MM/YYYY` | Date picker    |

---

## Additional Fields Revealed (Not Updated)

These fields were visible in the edit form but not modified during the recording:

| Field Name        | Type             | Value Seen   | Notes |
|-------------------|------------------|--------------|-------|
| Mobile            | Phone input      | —            | Separate from Phone field used in creation |
| Lead Source       | Dropdown         | `-None-`     | Standard Zoho CRM field |
| Email             | Email input      | Empty        | Not filled in creation or update |
| Estimated Budget  | Text / Currency  | Truncated    | Custom field — Kurinjee Promoters specific |

---

## Custom Fields Confirmed (Kurinjee Promoters Specific)

| Field Name         | Type            | Business Purpose |
|--------------------|-----------------|------------------|
| `Estimated Budget` | Currency / Text | Captures budget range for real estate purchase qualification |

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
[Lead Detail View opens]
       |
       v
[Click "Edit" — switches to edit/form mode]
       |
       ├── Click Lead Quality dropdown (-None-)
       │       └── Select "Junk"
       ├── Click "Lead Status" field
       │       └── Select status value
       ├── Click date field (DD/MM/YYYY)
       │       └── Select day 18
       └── Scroll to view: Mobile, Lead Source, Email, Estimated Budget
       |
       v
[Click "Save"]
       |
       v
[Lead record updated → Returns to Detail View]
```

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Lead Quality = "Junk"** — this is a test record (`Sri Testing`), so Junk is an appropriate classification; but it also demonstrates the disqualification workflow |
| 2 | **Lead Status value not fully captured** — the option selected in Step 6 is not explicitly named in the extraction |
| 3 | **Date field context unknown** — the exact field label for the date picker (Step 7/8) is not captured; likely `Follow Up Date` or a custom date field |
| 4 | **`Estimated Budget` truncated** — a custom currency/text field is partially visible; full label and options not captured |
| 5 | **Mobile vs Phone** — both fields exist in the Leads module; Phone was filled in creation (`8190970216`), Mobile appears separately in the update form |
| 6 | **`Lead Source` left as -None-** — this is a key qualification field that was not filled in either the creation or update flow |
| 7 | **Faster than creation** — 37 seconds vs 47 seconds; fewer fields interacted with in the update flow |
