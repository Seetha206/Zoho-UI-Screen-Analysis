> Scribe Source: https://scribehow.com/viewer/Edit_Role_in_Zoho_CRM__YMGhlp7FShaS0TUB1gdNRg
> Recorded By: Sri
> Duration: ~2 minutes
> Total Steps: 7
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Edit Role in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **editing a Role** in Zoho CRM's Settings panel, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a CRM administrator navigates to the Roles settings page and interacts with the role editing interface — 7 UI interactions in approximately 2 minutes.

> **Roles** in Zoho CRM define the organisational hierarchy and control data visibility across the team. A user's role determines which records they can see, edit, and delete — particularly important in a sales team where a Manager should see all Telecaller records, but Telecallers should only see their own assigned leads. For Kurinjee Promoters, roles structure the access levels across the sales hierarchy (Admin → Manager → Telecaller).

> **Note:** This is the **first Settings/Admin flow** in the recording series — all 17 previous flows operated within CRM modules (Leads, Contacts, Accounts, Deals, Tasks, Home). This flow enters the **Setup / Administration** section of Zoho CRM, which is restricted to users with Administrator-level access.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–7)                                 |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Settings / Admin panel — Role management                            |
| Module          | Setup → Users & Control → Roles (Settings section)                 |
| Notable pattern | Highest proportion of unlabeled steps — 6 out of 7 are "Click here"; Settings UI relies heavily on icon/action buttons without visible text labels |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Roles Settings Page

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/settings/roles` |
| Section         | Settings → Users & Control → Roles |
| Access Level    | Administrator only |

**Screenshot Analysis:**
- The recorder navigates directly to the **Roles settings page** via URL — bypassing the Setup home and navigating straight to `/settings/roles`
- This is the **first Settings-section URL** captured across all 18 flows:

  | URL Pattern              | Section |
  |--------------------------|---------|
  | `/tab/{Module}/`         | CRM module (Leads, Contacts, etc.) |
  | `/settings/{section}`    | Admin Setup ← new in this flow |

- The Roles settings page layout:

  ```
  ┌─────────────────────────────────────────────────────────────┐
  │  Setup                                                      │
  ├──────────────────┬──────────────────────────────────────────┤
  │  SETUP MENU      │  ROLES                                   │
  │  ─────────────── │  ──────────────────────────────────────  │
  │  General         │  ┌──────────────────────────────────┐   │
  │  Users & Control │  │  CEO / Administrator             │   │
  │   • Users        │  │    └── Manager          [✎][⋮]  │   │
  │   • Roles   ←    │  │         └── Telecaller  [✎][⋮]  │   │
  │   • Profiles     │  └──────────────────────────────────┘   │
  │   • Groups       │  [+ Add Role]                           │
  │  Modules         │                                          │
  │  Automation      │                                          │
  └──────────────────┴──────────────────────────────────────────┘
  ```

- The Roles page displays the **organisational hierarchy** as a tree structure — showing role names and their parent-child relationships
- For Kurinjee Promoters, the role hierarchy (inferred from Flow 15 "2 Roles" and Flow 17 Telecaller/Approver pattern):

  | Role Level    | Role Name (inferred)   | Users |
  |---------------|------------------------|-------|
  | Top level     | CEO / Administrator    | Sri   |
  | Mid level     | Manager                | Manager Testing account |
  | Field level   | Telecaller             | Sumathi, others |

---

### Step 2 — Click "Here" (First Unlabeled — Role Selection or Edit Trigger)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Role row entry / edit icon / action trigger |
| Location     | Roles page — role hierarchy tree |

**Screenshot Analysis:**
- The first click on the Roles page is on an **unlabeled element** — most likely:
  - Clicking directly on a **role name** in the hierarchy tree to select/open it
  - Clicking the **edit (✎) icon** next to a specific role
  - Clicking an **expand arrow** to open the role detail panel
- In Zoho CRM's Roles page, each role in the tree has:
  - A clickable role name (navigates to role detail)
  - An edit icon (✎) — opens the role edit form inline or as a modal
  - A more options (⋮) menu — for duplicate, delete, add sub-role
- This step selects or targets the role to be edited

---

### Step 3 — Click "Here" (Second Unlabeled — Role Detail or Edit Panel)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Role edit panel element / field or section |
| Location     | Role detail / edit panel |

**Screenshot Analysis:**
- After the initial role selection (Step 2), the recorder clicks another unlabeled element
- This second click likely:
  - Opens the **role edit form** (if Step 2 selected the role and Step 3 clicks the Edit button)
  - Interacts with a **field or section** within the already-open edit form
  - Navigates into a **sub-panel** of the role configuration (e.g., data sharing settings)

---

### Step 4 — Click "Here" (Third Unlabeled — Role Configuration Section)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Configuration section / permission toggle / field |
| Location     | Role edit form or configuration panel |

**Screenshot Analysis:**
- The third consecutive unlabeled click progresses deeper into the role editing interface
- Zoho CRM's role edit form includes multiple configurable sections:

  ```
  ┌────────────────────────────────────────────────────────────┐
  │  Edit Role: [Role Name]                               [×]  │
  ├────────────────────────────────────────────────────────────┤
  │  Role Name:         [__________________________]           │
  │  Reports To:        [Parent Role ▾]                        │
  │  Description:       [__________________________]           │
  │  ────────────────────────────────────────────────────────  │
  │  DATA SHARING SETTINGS                                     │
  │  Share data with peers: [ ] Yes  [✓] No                   │
  │  ────────────────────────────────────────────────────────  │
  │  [Save]   [Cancel]                                         │
  └────────────────────────────────────────────────────────────┘
  ```

---

### Step 5 — Click "Here" (Fourth Unlabeled — Permission or Field Interaction)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Toggle, checkbox, dropdown, or text field within role edit |
| Location     | Role edit form — configuration field |

**Screenshot Analysis:**
- A fourth "Click here" step indicates the recorder is interacting with a **specific field or setting** within the role edit form
- Possible interactions at this stage:
  - Changing the **Role Name** (clicking the name input field)
  - Changing the **Reports To** hierarchy (clicking the parent role dropdown)
  - Toggling **data sharing settings** (sharing with peers on/off)
  - Enabling/disabling specific **module-level permissions**

---

### Step 6 — Click "Here" (Fifth Unlabeled — Continuation)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Form field or action button |
| Location     | Role edit form — continued interaction |

**Screenshot Analysis:**
- The fifth unlabeled click continues the role editing interaction
- At this stage, the recorder may be:
  - Interacting with a **second field** in the role edit form (e.g., after editing Role Name, now clicking the Reports To dropdown)
  - Clicking a **confirm or apply** button for a specific section
  - Navigating to a **related settings panel** (e.g., Module Permissions linked to this role)

---

### Step 7 — Click This Field (Final Interaction)

| Property     | Detail |
|--------------|--------|
| Action       | Click field |
| Target       | Field element (Scribe: "Click this field") |
| Element Type | Text input / dropdown / save button |
| Location     | Role edit form — final field or save action |

**Screenshot Analysis:**
- The final step is clicking a **field** in the role edit interface — Scribe captured this as "Click this field" (slightly more specific than "Click here", indicating a form input element)
- This is likely one of:
  - The **Role Name** text field — to type or confirm the edited role name
  - The **Save** button — completing the role edit
  - The **Description** field — adding a description to the role
- The recording ends at this click — whether the role was ultimately saved is not confirmed

---

## Zoho CRM Roles — Architecture for Kurinjee Promoters

### Role Hierarchy (Inferred from All 18 Flows)

```
                    ┌─────────────────────┐
                    │   Administrator     │
                    │   (Sri — recorder)  │
                    └──────────┬──────────┘
                               │
              ┌────────────────┴─────────────────┐
              │                                  │
    ┌─────────┴──────────┐           ┌───────────┴──────────┐
    │      Manager       │           │    (other roles?)    │
    │  (Manager Testing) │           └──────────────────────┘
    └─────────┬──────────┘
              │
    ┌─────────┴──────────┐
    │     Telecaller     │
    │  (Sumathi, others) │
    └────────────────────┘
```

### Role Properties in Zoho CRM

| Property            | Description |
|---------------------|-------------|
| Role Name           | Display name of the role |
| Reports To          | Parent role in the hierarchy |
| Description         | Optional notes about the role's purpose |
| Data Sharing        | Whether this role shares data with peer roles |
| Users in Role       | CRM users assigned to this role |

### Data Visibility by Role (Standard Behaviour)

| Role          | Can See Own Records | Can See Subordinates' Records | Can See All Records |
|---------------|---------------------|-------------------------------|---------------------|
| Administrator | ✓                   | ✓                             | ✓                   |
| Manager       | ✓                   | ✓ (Telecallers)               | ✗ (unless shared)   |
| Telecaller    | ✓                   | ✗                             | ✗                   |

---

## Settings URL — First Admin-Section Flow

| URL Pattern | Section | First Seen |
|-------------|---------|------------|
| `/tab/Leads/...` | Leads module | Flow 1 |
| `/tab/Contacts/...` | Contacts module | Flow 11 |
| `/tab/Accounts/...` | Accounts module | Flow 13 |
| `/tab/Potentials/...` | Deals module | Flow 16 |
| `/tab/Tasks/...` | Tasks module | Flow 17 |
| `/tab/Home/begin` | Home Dashboard | Flow 15 |
| **`/settings/roles`** | **Setup → Roles** | **Flow 18 ← first Settings URL** |

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
       |
       v
[Click role entry / edit trigger — unlabeled (Step 2)]
       |
       v
[Click role detail / edit panel element — unlabeled (Step 3)]
       |
       v
[Click role configuration section — unlabeled (Step 4)]
       |
       v
[Click permission / field — unlabeled (Step 5)]
       |
       v
[Click form field / action — unlabeled (Step 6)]
       |
       v
[Click target field — "Click this field" (Step 7)]
       |
       v  ← Recording ends here
[Role edit completed / saved — not confirmed]
```

---

## Comparison: All Eighteen Flows

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

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **First Settings/Admin flow** — all 17 previous flows operated within CRM module tabs; this is the first flow in the `/settings/` section, confirming the recorder (Sri) has Administrator access |
| 2 | **Highest unlabeled rate** — 6 out of 7 steps are "Click here" or "Click this field"; the Zoho CRM Settings interface relies almost entirely on icon-based controls and unlabeled interactive elements, making Scribe capture less descriptive |
| 3 | **Which role was edited is unknown** — the role being targeted (Administrator, Manager, or Telecaller) is not captured in the Scribe labels; inferred to be the Manager or Telecaller role based on the flow title "Edit Role" (not "Add Role") |
| 4 | **2-minute duration for 7 steps** — the longest per-step duration in any flow (avg 17s per step), suggesting the recorder paused to read/review the role configuration interface before each click |
| 5 | **What was changed is not captured** — none of the 7 steps reveal which field was edited, what value was changed, or whether the edit was saved; the flow documents the navigation path to the role edit interface rather than the edit content itself |
| 6 | **Connects to Flow 15 ("2 Roles")** — in Flow 15, "Kurinjee Promoters's Home" was shown as assigned to "2 Roles"; this Edit Role flow likely involves one of those same 2 roles; the home page customization and role editing flows together confirm a 2-role structure |
| 7 | **Connects to Flow 17 (Telecaller/Approver)** — the custom Task fields (Telecaller, Approver) are role-based assignments; editing the Telecaller or Manager role directly affects how those Task fields are populated |
