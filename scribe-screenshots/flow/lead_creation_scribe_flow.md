> Scribe Source: https://scribehow.com/viewer/Create_New_Lead_Record_in_Zoho_CRM__Hkm4hw2XTB6w3-sbh_Wmgg
> Recorded By: Sri Gnanathesigan
> Duration: ~47 seconds
> Total Steps: 13
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Create New Lead Record in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for creating a new Lead record in Zoho CRM as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It covers navigation from the Leads list view through form entry to final save — 13 discrete UI interactions across approximately 47 seconds.

---

## UI Design Context

| Property        | Detail                                                     |
|-----------------|------------------------------------------------------------|
| Color scheme    | White background, blue accent buttons, slate-gray text     |
| Form layout     | Centered modal/page form with collapsible sections         |
| Step indicators | Blue circular badges with step numbers                     |
| Header          | Fixed metadata bar — title, creator, step count, duration  |
| Favicon         | Zoho CRM icon in rounded container with shadow + blur      |
| Navigation      | Collapsible section headers expand/collapse field groups   |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View

| Property   | Detail |
|------------|--------|
| Action     | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list` |
| View Type  | Custom List View (ID: `955332000000441406`) |
| Module     | Leads |

**Screenshot Analysis:**
- The Zoho CRM Leads module is open in **list view** with a custom saved view active
- The top navigation bar shows the CRM module tabs (Leads, Contacts, Deals, etc.)
- The list displays existing lead records in a tabular/card layout
- A **"Create Lead"** button is visible in the top-right area of the list header
- The custom view ID (`955332000000441406`) indicates a saved filtered view — not the default "All Leads" view

---

### Step 2 — Click "Create Lead" Button

| Property   | Detail |
|------------|--------|
| Action     | Button click |
| Button Label | `Create Lead` |
| Button Style | Blue filled primary action button |
| Location   | Top-right of Leads list header |

**Screenshot Analysis:**
- The Leads list view is fully visible with existing records loaded
- The **"Create Lead"** button is positioned at the top-right of the module toolbar
- Clicking this opens the new lead creation form (inline or modal)
- No dialog confirmation precedes the form — it opens directly

---

### Step 3 — Click the First Name Text Field

| Property   | Detail |
|------------|--------|
| Action     | Click text field |
| Field Type | Text input |
| Field Label | First Name (implied — first field in lead form) |
| Placeholder | Empty / blank at click time |

**Screenshot Analysis:**
- The **Lead creation form** is now open
- The form has a header section with the **"Lead Information"** collapsible block
- The first visible input field is the **First Name** field (standard Zoho CRM lead form layout)
- Field is empty and in a ready/active state after click
- The form background is white with light gray field borders
- A cursor indicator is visible in the field

---

### Step 4 — Type Lead Name: "Sri Testing"

| Property   | Detail |
|------------|--------|
| Action     | Keyboard input |
| Value Entered | `Sri Testing` |
| Field      | First Name |

**Screenshot Analysis:**
- The text `Sri Testing` is entered into the First Name field
- This is clearly **test data** — not a real lead record
- The field shows the typed value with standard Zoho CRM text styling (dark text on white input)
- No validation error is triggered — the name format is accepted

---

### Step 5 — Expand "Lead Information" Section

| Property   | Detail |
|------------|--------|
| Action     | Click section header |
| Section Label | `Lead Information` |
| Behaviour  | Collapsible accordion — click expands hidden fields |

**Screenshot Analysis:**
- The form uses **collapsible section headers** to group related fields
- The **"Lead Information"** section header is clicked to expand it
- Before expansion: only minimal fields (First Name, possibly Last Name) are visible
- After expansion: additional custom and standard fields are revealed (see Step 8 for full list)
- Section header text is in **slate-gray / dark text** with a chevron/arrow toggle indicator

---

### Step 6 — Click the Phone Number Field

| Property   | Detail |
|------------|--------|
| Action     | Click text field |
| Field Type | Text / Phone input |
| Field Label | Phone (mobile or primary phone) |

**Screenshot Analysis:**
- After expanding Lead Information, a **phone number input field** becomes accessible
- The field is blank at this point and receives focus on click
- Zoho CRM phone fields typically accept numeric input with optional country code prefix
- The field placeholder may show a format hint (e.g., `+91 XXXXXXXXXX`) — not explicitly captured in this recording

---

### Step 7 — Enter Phone Number: "8190970216"

| Property   | Detail |
|------------|--------|
| Action     | Keyboard input |
| Value Entered | `8190970216` |
| Field      | Phone / Mobile |
| Number Type | 10-digit Indian mobile number |

**Screenshot Analysis:**
- The phone number `8190970216` is typed into the phone field
- This is a 10-digit Indian mobile format (no country code prefix entered)
- Zoho CRM accepts this format for Indian phone numbers
- No validation error shown — number passes field format check
- The field remains in focus with the typed value displayed

---

### Step 8 — View Expanded "Lead Information" Section

| Property   | Detail |
|------------|--------|
| Action     | Click / scroll within Lead Information section |
| Section Label | `Lead Information` |

**Screenshot Analysis:**
This is the most information-rich step. The screenshot reveals the **full set of visible fields** in the expanded Lead Information section:

| # | Field Label             | Field Type          | Default Value |
|---|-------------------------|---------------------|---------------|
| 1 | Last Name               | Text input          | Empty         |
| 2 | Lead Type               | Dropdown            | `-None-`      |
| 3 | Client Location         | Text / Dropdown     | Empty         |
| 4 | Company                 | Text input          | Empty         |
| 5 | Telecaller              | Lookup / Text       | Empty         |
| 6 | Manager                 | Lookup / Text       | Empty         |
| 7 | Reason Qualified Out    | Dropdown            | `-None-`      |
| 8 | Language Preference     | Dropdown            | `-None-`      |

> **Note:** Fields like `Telecaller`, `Reason Qualified Out`, `Client Location`, and `Language Preference` are **custom fields** specific to Kurinjee Promoters — they are not part of the default Zoho CRM Leads module.

---

### Step 9 — Interact with "-None-" Dropdown

| Property   | Detail |
|------------|--------|
| Action     | Click dropdown |
| Dropdown Label | `-None-` (collapsed state) |
| Field      | One of: Lead Type, Reason Qualified Out, or Language Preference |

**Screenshot Analysis:**
- A dropdown field currently set to **"-None-"** is clicked
- The dropdown opens to show available options (options not fully captured in extraction)
- This is likely the **Lead Type** dropdown — the first dropdown encountered after entering name and phone
- Zoho CRM renders dropdowns as an inline select or floating option list
- The field border highlights (blue outline) when active

---

### Step 10 — Click "Family Decision Involved?" Field

| Property   | Detail |
|------------|--------|
| Action     | Click field |
| Field Label | `Family Decision Involved?` |
| Field Type  | Checkbox or Yes/No toggle (custom field) |

**Screenshot Analysis:**
- A **custom field** unique to Kurinjee Promoters is clicked: `Family Decision Involved?`
- This is a yes/no or checkbox-style field used to qualify real estate leads
- Business context: In real estate sales, knowing whether a family decision is required helps Telecallers prioritize follow-up
- The field appears in the expanded Lead Information section
- This is a **non-default Zoho CRM field** — confirms custom module configuration

---

### Step 11 — Click the Date Field (DD/MM/YYYY)

| Property   | Detail |
|------------|--------|
| Action     | Click date input |
| Field Placeholder | `DD/MM/YYYY` |
| Field Type  | Date picker |

**Screenshot Analysis:**
- A date picker field is clicked, showing the placeholder format `DD/MM/YYYY`
- This is likely a field such as: `Follow Up Date`, `Lead Source Date`, or `Site Visit Date`
- The Indian date format (`DD/MM/YYYY`) is consistent with Zoho CRM's regional settings for India
- Clicking opens a calendar picker widget (not shown fully in the capture)
- No date is ultimately selected in this recording (step moves on without entering a value)

---

### Step 12 — View Full Form Layout

| Property   | Detail |
|------------|--------|
| Action     | Scroll / click within fully expanded form |
| Visible Content | Full Lead Information section with all fields |

**Screenshot Analysis:**
This step shows the **complete lead creation form layout** as a summary view. The section text captured reads:

```
Lead Information
  Last Name
  Lead Type         -None-
  Client Location
  Company
  Telecaller
  Manager
  Reason Qualified Out   -None-
  Language Preference    -None-
  Bu... (truncated — likely "Budget" or "Business Type")
```

**Key observations:**
- The form uses a **two-column layout** within each section (label left, input right)
- All dropdown fields default to **"-None-"** before user selection
- A truncated field starting with `Bu` is partially visible — likely `Budget Range` or `Business Type` (another custom field)
- The form is scrollable — not all fields fit in a single viewport
- Section collapsing allows users to focus on relevant field groups

---

### Step 13 — Click "Save" Button

| Property   | Detail |
|------------|--------|
| Action     | Button click |
| Button Label | `Save` |
| Button Style | Blue filled primary action button |
| Location   | Bottom of form or top action bar |

**Screenshot Analysis:**
- The **"Save"** button is clicked to finalize and submit the lead record
- Zoho CRM creates the record and redirects to the newly created lead's **detail view**
- Standard Zoho CRM save behavior: validates required fields before saving
- In this recording, only First Name and Phone were filled — other fields left at defaults
- The record is created with: `First Name = Sri Testing`, `Phone = 8190970216`

---

## Custom Fields Identified (Kurinjee Promoters Specific)

These fields appeared in the Scribe recording and are **not part of default Zoho CRM Leads module**:

| Field Name              | Type            | Business Purpose |
|-------------------------|-----------------|------------------|
| `Family Decision Involved?` | Checkbox / Yes-No | Qualifies if a family discussion is required before purchase decision |
| `Client Location`       | Text / Dropdown | Geographic location of the lead / client |
| `Telecaller`            | Lookup          | Assigned telecaller agent for this lead |
| `Manager`               | Lookup          | Supervising manager for the lead |
| `Reason Qualified Out`  | Dropdown        | Reason why a lead was disqualified |
| `Language Preference`   | Dropdown        | Preferred communication language |
| `Bu...` (truncated)     | Unknown         | Possibly `Budget Range` or `Business Type` |

---

## Full URL Reference

| Element           | Value |
|-------------------|-------|
| CRM Base URL      | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL    | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list` |
| Custom View ID    | `955332000000441406` |
| Org ID            | `60043078423` |

---

## Workflow Summary

```
[Leads List View]
       |
       v
[Click "Create Lead"]
       |
       v
[Form Opens]
  ├── Enter First Name: "Sri Testing"
  ├── Expand "Lead Information" section
  ├── Enter Phone: 8190970216
  ├── Interact with Lead Type dropdown (-None-)
  ├── Toggle "Family Decision Involved?" field
  ├── Click date field (DD/MM/YYYY — no value entered)
  └── View full expanded form
       |
       v
[Click "Save"]
       |
       v
[Lead Record Created → Redirect to Detail View]
```

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Last Name not filled** — only First Name (`Sri Testing`) was entered; this may trigger a validation warning in some Zoho CRM configs |
| 2 | **Date field clicked but no value selected** — follow-up or site visit date left blank |
| 3 | **Dropdown values not selected** — Lead Type, Reason Qualified Out, Language Preference all remain `-None-` |
| 4 | **Truncated field (`Bu...`)** — at least one more custom field exists beyond what was captured |
| 5 | **Custom view used** — the recording starts from a saved custom list view, not the default "All Leads" view |
| 6 | **Test record** — `Sri Testing` + `8190970216` is clearly a test entry, not a real lead |
