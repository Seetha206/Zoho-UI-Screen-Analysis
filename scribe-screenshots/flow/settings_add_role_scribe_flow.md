> Scribe Source: https://scribehow.com/viewer/Create_a_New_Role_in_Zoho_CRM__JwpIwIBsT4Ol-UFLj7qQgQ
> Recorded By: Sri
> Duration: ~24 seconds
> Total Steps: 7
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Add / Create a New Role in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **creating a new Role** in Zoho CRM's Settings panel, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a CRM administrator navigates to the Roles settings page, clicks "New Role", fills in the role creation form fields (name, configuration, description, parent role), and submits — 7 UI interactions in approximately 24 seconds.

> This flow is the **direct complement to Flow 18 (Edit Role)** — both operate on the same `/settings/roles` page. Where Flow 18 edited an existing role, Flow 19 creates a brand new role from scratch. Together, they document the complete Role CRUD lifecycle (Create + Read + Update) in the Zoho CRM Settings panel for Kurinjee Promoters.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–7)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Settings / Admin panel — Role creation form                         |
| Module          | Setup → Users & Control → Roles                                     |
| Notable pattern | Same URL as Flow 18 (Edit Role); both flows are in the Settings section |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Roles Settings Page

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/settings/roles` |
| Section         | Setup → Users & Control → Roles |
| Access Level    | Administrator only |

**Screenshot Analysis:**
- Identical starting URL to Flow 18 (Edit Role) — the Roles settings page at `/settings/roles`
- The Roles page displays the existing role hierarchy before the new role is created:

  ```
  ┌─────────────────────────────────────────────────────────────┐
  │  Setup → Users & Control → Roles                            │
  ├─────────────────────────────────────────────────────────────┤
  │  ROLES                                    [+ New Role]      │
  │  ─────────────────────────────────────────────────────────  │
  │  ┌──────────────────────────────────────────────────────┐  │
  │  │  CEO / Administrator                      [✎] [⋮]   │  │
  │  │      └── Manager                          [✎] [⋮]   │  │
  │  │              └── Telecaller               [✎] [⋮]   │  │
  │  └──────────────────────────────────────────────────────┘  │
  └─────────────────────────────────────────────────────────────┘
  ```

- The **"+ New Role"** button is visible in the top-right of the Roles section — the entry point for the next step

---

### Step 2 — Click "New Role"

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `New Role` |
| Element Type | Primary action button — role creation trigger |
| Location     | Roles settings page — top-right toolbar |

**Screenshot Analysis:**
- The recorder clicks the **"New Role"** button — opening the role creation form
- In Zoho CRM, clicking "New Role" opens either:
  - An **inline form** that expands within the Roles hierarchy page
  - A **modal dialog** overlaying the Roles page
  - A **dedicated creation page** navigating to `/settings/roles/new` or similar
- The New Role form structure:

  ```
  ┌────────────────────────────────────────────────────────────┐
  │  New Role                                             [×]  │
  ├────────────────────────────────────────────────────────────┤
  │  Role Name *:       [________________________________]      │
  │                                                            │
  │  Reports To *:      [Please select one role from the list ▾]│
  │                                                            │
  │  Description:       [________________________________]      │
  │                     [________________________________]      │
  │                                                            │
  │  Share data with peers in this role: [ ] Yes  [✓] No      │
  ├────────────────────────────────────────────────────────────┤
  │  [Save]   [Cancel]                                         │
  └────────────────────────────────────────────────────────────┘
  ```

---

### Step 3 — Click First Text Field (Role Name)

| Property     | Detail |
|--------------|--------|
| Action       | Click text input |
| Target       | First text field — Role Name |
| Element Type | `<input type="text">` — mandatory Role Name field |
| Location     | New Role form — first field |

**Screenshot Analysis:**
- The recorder clicks the **first text field** in the New Role form — which is the **Role Name** field
- Role Name is a **mandatory field** (marked with `*`) in Zoho CRM's role creation form
- Clicking places the cursor in the field, ready for the role name to be typed
- The recorder does not type in this step — the typing may have been captured as a separate Scribe step that was consolidated, or the name was entered and not captured by Scribe
- In the Kurinjee Promoters context, a new role being added might be:
  - A new hierarchical level (e.g., `Senior Telecaller`, `Team Lead`)
  - A functional role (e.g., `Site Visit Coordinator`, `Accounts Manager`)
  - A test role (consistent with other test records in the series)

---

### Step 4 — Click Designated Field (Additional Configuration)

| Property     | Detail |
|--------------|--------|
| Action       | Click field |
| Target       | Designated field for additional configuration |
| Element Type | Text field / toggle / configuration input |
| Location     | New Role form — second or third field |

**Screenshot Analysis:**
- The recorder clicks a **second field** in the New Role form for "additional configuration"
- This is likely the **Description** field — an optional free-text area where the role's responsibilities or scope can be documented:
  - Example: `"Responsible for initial lead qualification calls and follow-ups"`
  - Example: `"Manages Telecaller team; approves task outcomes"`
- Alternatively, this could be a **data-sharing configuration toggle** — determining whether users in this role can see each other's records

---

### Step 5 — Click Another Text Field (Further Role Details)

| Property     | Detail |
|--------------|--------|
| Action       | Click text field |
| Target       | Another text field — further role details |
| Element Type | Text input — description or secondary name field |
| Location     | New Role form — third field area |

**Screenshot Analysis:**
- A third text field interaction — the New Role form in Zoho CRM has limited text fields (Role Name + Description), so this step likely represents either:
  - Clicking back into the **Role Name** field to confirm or correct the entry
  - Clicking the **Description** text area (which may span multiple lines and be captured as a separate field from Role Name)
  - Clicking a **secondary input** within the form (e.g., a search field within the parent role dropdown)

---

### Step 6 — Click Parent Role Dropdown ("Please select one role from the list")

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Target       | `Please select one role from the list` |
| Element Type | Dropdown — Reports To / Parent Role selector |
| Location     | New Role form — Reports To field |
| Placeholder  | `Please select one role from the list` |

**Screenshot Analysis:**
- The recorder clicks the **"Reports To"** dropdown — labeled with the placeholder **"Please select one role from the list"**
- This is the most informative step in the flow — the exact placeholder text **"Please select one role from the list"** is captured, confirming:
  - The field label is **"Reports To"** (standard Zoho CRM role hierarchy field)
  - The dropdown was in its **unselected default state** when clicked
  - The dropdown opens to show the existing roles in the Kurinjee Promoters hierarchy

- The Reports To dropdown would display:

  ```
  ┌────────────────────────────────────────────┐
  │  Please select one role from the list  ▾  │
  ├────────────────────────────────────────────┤
  │  CEO / Administrator                       │
  │  Manager                                   │
  │  Telecaller                                │
  └────────────────────────────────────────────┘
  ```

- The **"Reports To"** field determines where the new role sits in the hierarchy — the new role will be a **subordinate** of whichever role is selected here
- Which role was selected from the dropdown is not captured by Scribe in this step

---

### Step 7 — Click Final Button (Save / Create Role)

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | Final button — Save / Create |
| Element Type | Primary submit button |
| Location     | New Role form — action button row |

**Screenshot Analysis:**
- The recorder clicks the **final button** to complete role creation — this is the **Save** or **Create Role** button
- After clicking Save:
  1. The new role is validated (Role Name must be filled, Reports To must be selected)
  2. The role is created in the CRM system
  3. The Roles hierarchy page refreshes to display the new role in its correct position in the tree
  4. The new role is immediately available for assignment to CRM users

- Post-save state on the Roles page (example — if a new "Team Lead" role was created under Manager):

  ```
  ┌──────────────────────────────────────────────────────────┐
  │  CEO / Administrator                          [✎] [⋮]   │
  │      └── Manager                             [✎] [⋮]   │
  │              ├── Telecaller                  [✎] [⋮]   │
  │              └── [New Role]       ← newly added         │
  └──────────────────────────────────────────────────────────┘
  ```

---

## Role Creation Form — Field Summary

| Field           | Type       | Mandatory | Placeholder / Default | Captured Value |
|-----------------|------------|-----------|----------------------|----------------|
| Role Name       | Text       | **Yes**   | (empty)              | Not captured   |
| Reports To      | Dropdown   | **Yes**   | `Please select one role from the list` | Not captured (Step 6) |
| Description     | Text Area  | No        | (empty)              | Not captured   |
| Share with peers | Toggle    | No        | No (default)         | Not captured   |

---

## Flows 18 & 19 — Edit vs Create Role: Side-by-Side

| Aspect              | Flow 18 — Edit Role            | Flow 19 — Add Role              |
|---------------------|-------------------------------|----------------------------------|
| Operation           | Edit existing role             | Create new role                  |
| Entry point         | Click edit (✎) on existing role | Click "New Role" button          |
| Steps               | 7                              | 7                                |
| Duration            | ~2 minutes                     | ~24 seconds                      |
| Starting URL        | `/settings/roles`              | `/settings/roles`                |
| Role name captured  | No                             | No                               |
| Parent role field   | Not specifically identified    | Confirmed: "Please select one role from the list" |
| Save confirmed      | Not confirmed                  | Not confirmed (recording ends at click) |
| Notable difference  | Slow (~17s/step) — reading existing config | Fast (~3.4s/step) — filling new form |

---

## URL Reference

| Element               | Value |
|-----------------------|-------|
| CRM Base URL          | `https://crm.zoho.in/crm/org60043078423/` |
| Roles Settings URL    | `https://crm.zoho.in/crm/org60043078423/settings/roles` |
| Section               | Setup → Users & Control → Roles |
| Access Required       | Administrator |
| Org ID                | `60043078423` |

---

## Workflow Summary

```
[Settings → Roles — /settings/roles]
  Shows: Existing role hierarchy (Administrator → Manager → Telecaller)
       |
       v
[Click "New Role" button (Step 2)]
       |
       v
[New Role creation form opens]
  Fields: Role Name * | Reports To * | Description | Share with peers
       |
       v
[Click Role Name field — first text field (Step 3)]
       |
       v
[Click additional configuration field (Step 4)]
       |
       v
[Click further details text field (Step 5)]
       |
       v
[Click "Please select one role from the list" — Reports To dropdown (Step 6)]
       |
       v
[Parent role dropdown opens — shows existing roles]
       |
       v
[Click Save / Create Role — final button (Step 7)]
       |
       v  ← Recording ends here
[New role created — hierarchy updated]
[New role available for user assignment]
```

---

## Comparison: All Nineteen Flows

| #  | Flow                    | Module / Section | Steps | Duration | Key Operation |
|----|-------------------------|------------------|-------|----------|---------------|
| 1  | Create                  | Lead             | 13    | ~47s     | Form fill + save |
| 2  | Update                  | Lead             | 10    | ~37s     | Field edits + save |
| 3  | Delete                  | Lead             | 5     | ~22s     | Two-click delete |
| 4  | Related List            | Lead             | 5     | ~25s     | Navigate to Scheduler |
| 5  | Filter                  | Lead             | 8     | ~24s     | Criteria-based filter |
| 6  | Sort                    | Lead             | 8     | ~34s     | Sort by Country |
| 7  | Manage Columns          | Lead             | 9     | ~44s     | Column + page limit |
| 8  | Blueprint               | Lead             | 22    | ~2 min   | BANT qualification |
| 9  | Custom View             | Lead             | 5     | ~36s     | Switch to Today's Leads |
| 10 | Module Link (WorkDrive) | Lead             | 2     | ~23s     | Link record to WorkDrive |
| 11 | Save and New            | Contact          | 6     | ~20s     | Batch contact creation |
| 12 | Clone                   | Contact          | 4     | ~8s      | Duplicate existing record |
| 13 | Record Import           | Accounts         | 4     | ~17s     | Bulk import via CSV |
| 14 | Record Export           | Accounts         | 5     | ~23s     | Export all records to CSV |
| 15 | Customize Homepage      | Home             | 13    | ~2 min   | Home page widget editor + role config |
| 16 | Print Preview           | Potentials       | 4     | ~53s     | Print-format record view |
| 17 | Create Task             | Tasks            | 14    | ~45s     | Full task form with custom fields |
| 18 | Edit Role               | Settings → Roles | 7     | ~2 min   | Admin role hierarchy edit |
| 19 | Add Role                | Settings → Roles | 7     | ~24s     | New role creation form |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Paired with Flow 18** — Edit Role and Add Role together document the full role management workflow in Zoho CRM Settings; both use the same `/settings/roles` URL and the same 7-step count |
| 2 | **New role name not captured** — none of the 7 steps reveal what role name was entered; the recorder typed into the Role Name field (Step 3) but Scribe did not capture the typed value |
| 3 | **"Please select one role from the list" — exact placeholder captured** — this is the most specific element label in the flow; confirms the Reports To field is mandatory and was in unselected state when clicked |
| 4 | **Speed contrast with Flow 18** — Flow 18 (Edit) took ~2 minutes for 7 steps; Flow 19 (Add) took only 24 seconds for the same number of steps; editing an existing role requires reading/reviewing current settings, while creating a new one is a straightforward form fill |
| 5 | **Which parent role was selected is unknown** — the dropdown was clicked (Step 6) but which role (Administrator, Manager, or Telecaller) was chosen as parent is not captured |
| 6 | **Save outcome not confirmed** — the recording ends at the Save button click (Step 7); whether the role was successfully created or if validation errors occurred is not shown |
| 7 | **Settings section pattern confirmed** — Flows 18 and 19 establish that Settings flows follow the same structure: navigate to `/settings/{section}` → interact with unlabeled elements → complete action; the Settings UI is consistently less labelled than module-level CRM UI |
