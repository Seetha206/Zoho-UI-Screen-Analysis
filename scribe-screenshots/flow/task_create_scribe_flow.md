> Scribe Source: https://scribehow.com/viewer/Create_a_New_Task_in_Zoho_CRM__Xm-2tDfLRoyy3IfffP40Tg
> Recorded By: Sri
> Duration: ~45 seconds
> Total Steps: 14
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Create a New Task in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **creating a new Task record** in Zoho CRM's Tasks module, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user navigates to the Tasks list view, opens the Create Task form, fills in the Subject, assigns a Telecaller and Approver, sets the Status to "Attempt", picks a due date, links an Account, and saves the record — 14 UI interactions in approximately 45 seconds.

> **Tasks** in Zoho CRM are activity records used to track follow-up actions — calls to make, site visits to schedule, documents to collect, or approvals to obtain. At Kurinjee Promoters, Tasks are customised with additional fields (**Telecaller**, **Approver**, custom **Status** values) to support the real estate sales workflow where a Telecaller initiates the task and a Manager/Approver oversees or approves the action.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–14)                                |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Tasks module — record creation form                                 |
| Module          | Tasks (first Tasks module creation flow in the series)              |
| Notable pattern | Custom fields confirmed: Telecaller, Approver; custom Status value "Attempt" |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Tasks List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Tasks/custom-view/955332000000435996/list?page=1` |
| Module          | Tasks |
| View Type       | Custom List View (ID: `955332000000435996`) |
| Pagination      | `page=1` |

**Screenshot Analysis:**
- The Zoho CRM Tasks module opens in custom list view **`955332000000435996`**
- The Tasks custom view ID `955332000000435996` (suffix `435996`) is notably **lower** than the four module IDs documented in Flow 16:

  | Module        | Custom View ID Suffix | Relative Age |
  |---------------|-----------------------|--------------|
  | Tasks         | `435996`              | Older — created first |
  | Leads         | `441406`              | Newer |
  | Accounts      | `441417`              | Newer |
  | Potentials    | `441430`              | Newer |
  | Contacts      | `441440`              | Newest |

  - The lower ID confirms that the Tasks module custom view was created **before** the Lead/Account/Potential/Contact custom views in the Kurinjee Promoters CRM setup
  - Gap between Tasks and Leads: `441406 − 435996 = 5410` — a significant gap, suggesting the Tasks customisation was done in a separate, earlier session

- Tasks list view layout:

  ```
  ┌─────────────────────────────────────────────────────────────┐
  │  Tasks  ▾ [View Name]   [+New Task]   [Actions ▾]          │
  ├─────────────────────────────────────────────────────────────┤
  │ ☐  Subject ↕    Due Date ↕   Status ↕   Owner ↕  Telecaller│
  ├─────────────────────────────────────────────────────────────┤
  │ ☐  [Task 1]     [date]       [status]   Sri      [name]    │
  │ ☐  [Task 2]     [date]       [status]   ...      ...       │
  │    ...                                                      │
  └─────────────────────────────────────────────────────────────┘
  ```

---

### Step 2 — Click "Create Task"

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `Create Task` |
| Element Type | Primary action button (CTA) |
| Location     | Top-right of the Tasks list view toolbar |

**Screenshot Analysis:**
- The recorder clicks the **"Create Task"** button — the primary creation entry point in the Tasks list view
- Clicking opens the **Task Creation Form** — a modal or full-page form with standard and custom fields
- The Task creation form structure for Kurinjee Promoters:

  ```
  ┌──────────────────────────────────────────────────────────┐
  │  Create Task                                        [×]  │
  ├──────────────────────────────────────────────────────────┤
  │  Subject *:        [________________________]            │
  │  Due Date:         [dd/mm/yyyy  🗓]                       │
  │  Status:           [-None- ▾]                            │
  │  Priority:         [-None- ▾]                            │
  │  Telecaller:       [-None- ▾]   ← custom field          │
  │  Approver:         [-None- ▾]   ← custom field          │
  │  Account:          [Search... 🔍]                        │
  │  Type:             [-None- ▾]                            │
  │  Repeat:           [-None- ▾]                            │
  │  Auto Close:       [ ] Toggle                            │
  │  Reminder:         [-None- ▾]                            │
  │  Description:      [________________________]            │
  ├──────────────────────────────────────────────────────────┤
  │  [Save]   [Save and New]   [Cancel]                      │
  └──────────────────────────────────────────────────────────┘
  ```

---

### Step 3 — Type "Testing Task"

| Property     | Detail |
|--------------|--------|
| Action       | Keyboard text entry |
| Target       | Subject field |
| Input value  | `Testing Task` |
| Element Type | Text input — mandatory Subject field |

**Screenshot Analysis:**
- The recorder types **"Testing Task"** into the **Subject** field — the only mandatory field in Task creation
- Subject is the task title — the primary identifier shown in the Tasks list view
- "Testing Task" is a test/dummy task name consistent with the "Sri Testing" pattern used in other flows
- In the real estate workflow, typical task Subject values would be:
  - `"Call Prasanth re: Site Visit"`
  - `"Follow up — Budget confirmation"`
  - `"Send brochure to [Lead Name]"`
  - `"Schedule site visit — [Project Name]"`

---

### Step 4 — Click "-None-" (Telecaller Dropdown)

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Target       | `-None-` (Telecaller field) |
| Element Type | Custom dropdown field — Telecaller selector |
| Location     | Task creation form — Telecaller field |

**Screenshot Analysis:**
- The recorder clicks the **Telecaller** dropdown — currently showing the default `-None-` value
- **Telecaller** is a **custom field** added to the Tasks module by Kurinjee Promoters — not present in standard Zoho CRM Tasks
- This field assigns a specific Telecaller team member to the task — linking the task to the person responsible for executing it (making the call, following up, etc.)
- Clicking opens a dropdown list of available Telecaller users in the system

---

### Step 5 — Click "Sumathi"

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Target       | `Sumathi` |
| Element Type | Dropdown list item — Telecaller user selection |
| Location     | Telecaller dropdown — Task creation form |

**Screenshot Analysis:**
- The recorder selects **"Sumathi"** from the Telecaller dropdown — assigning this task to Sumathi
- **Sumathi** is a **real team member** at Kurinjee Promoters — a Telecaller in the sales team
- This is the first time a team member name other than "Sri" (the recorder) appears as an assignee in any of the 17 flows
- In the Kurinjee Promoters workflow, Telecallers are responsible for:
  - Making initial contact calls to new leads
  - Following up on Blueprint stage transitions
  - Scheduling site visits
  - Maintaining call logs

---

### Step 6 — Click "-None-" (Approver Dropdown)

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Target       | `-None-` (Approver field) |
| Element Type | Custom dropdown field — Approver selector |
| Location     | Task creation form — Approver field |

**Screenshot Analysis:**
- The recorder clicks the **Approver** dropdown — another **custom field** added to Tasks by Kurinjee Promoters
- **Approver** designates a manager or senior team member who oversees or approves the task outcome
- This field supports a **maker-checker workflow** in the sales process:
  - Telecaller (Sumathi) executes the task
  - Approver (Manager) reviews and signs off on the outcome
- Clicking opens the Approver dropdown showing available manager-level users

---

### Step 7 — Click "Manager Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Target       | `Manager Testing` |
| Element Type | Dropdown list item — Approver user selection |
| Location     | Approver dropdown — Task creation form |

**Screenshot Analysis:**
- The recorder selects **"Manager Testing"** from the Approver dropdown
- "Manager Testing" appears to be a **test/dummy manager account** — a CRM user created for testing the Approver workflow (similar to "Sri Testing" used as a test record name in other flows)
- The naming pattern `[Role] Testing` confirms this is a test user, not a real manager's name
- In production use, the Approver would be a real manager name (e.g., the sales manager or team lead at Kurinjee Promoters)

  | Telecaller (Executor) | Approver (Reviewer) |
  |-----------------------|---------------------|
  | Sumathi (real user)   | Manager Testing (test account) |

---

### Step 8 — Click "-None-" (Status Dropdown)

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Target       | `-None-` (Status field) |
| Element Type | Standard dropdown field — Task Status selector |
| Location     | Task creation form — Status field |

**Screenshot Analysis:**
- The recorder clicks the **Status** dropdown — the task's current state indicator
- Standard Zoho CRM Task Status values: `Not Started`, `Deferred`, `In Progress`, `Completed`, `Waiting for Input`
- However, Step 9 reveals that Kurinjee Promoters has added a **custom Status value** — "Attempt" — to the Tasks module

---

### Step 9 — Click "Attempt"

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Target       | `Attempt` |
| Element Type | Dropdown list item — custom Task Status value |
| Location     | Status dropdown — Task creation form |

**Screenshot Analysis:**
- The recorder selects **"Attempt"** as the task status — a **custom status value** added by Kurinjee Promoters
- "Attempt" is not a standard Zoho CRM task status — it has been added to reflect the real estate telecalling workflow:

  | Status Value    | Meaning in Telecalling Context |
  |-----------------|-------------------------------|
  | `Attempt`       | A call attempt was made — phone rang but no answer, or busy |
  | `Not Started`   | Task not yet begun |
  | `In Progress`   | Task is actively being worked on |
  | `Completed`     | Task fully done |
  | `Deferred`      | Postponed to a later date |

- "Attempt" captures the intermediate state where a Telecaller has tried to reach a lead/contact but has not yet connected — common in high-volume real estate lead management
- The full custom Status dropdown for Kurinjee Promoters Tasks likely includes:

  ```
  [-None-]
  Not Started
  Attempt          ← custom
  In Progress
  Completed
  Deferred
  Waiting for Input
  ```

---

### Step 10 — Click Due Date Field ("dd/mm/yyyy")

| Property     | Detail |
|--------------|--------|
| Action       | Click date input |
| Target       | `dd/mm/yyyy` field |
| Element Type | Date picker input — Due Date field |
| Location     | Task creation form — Due Date field |
| Date format  | `DD/MM/YYYY` (Indian date format — consistent with Zoho India instance) |

**Screenshot Analysis:**
- The recorder clicks the **Due Date** field — displaying the placeholder `dd/mm/yyyy`
- The `DD/MM/YYYY` format confirms the CRM instance uses **Indian date format** (day-month-year), consistent with `crm.zoho.in` (Zoho India data centre)
- Clicking the date field opens an inline **calendar date picker**

---

### Step 11 — Click "21" (Date Selection)

| Property     | Detail |
|--------------|--------|
| Action       | Click calendar date |
| Target       | `21` |
| Element Type | Calendar day cell — date picker |
| Location     | Due Date calendar picker |
| Date selected | 21st of the current month (February 2026 → 21/02/2026) |

**Screenshot Analysis:**
- The recorder clicks **"21"** on the calendar — setting the due date to the **21st**
- Given the recording date of 2026-02-27, the selected date of the 21st is **in the past** (21/02/2026 — 6 days before the recording date)
- This confirms this is a **test task** — a real task would have a future due date
- After clicking, the Due Date field populates with `21/02/2026` (or the current month's 21st)

---

### Step 12 — Click "Account" (Account Lookup Field)

| Property     | Detail |
|--------------|--------|
| Action       | Click lookup field |
| Target       | `Account` |
| Element Type | Lookup field — Account association |
| Location     | Task creation form — Account field |

**Screenshot Analysis:**
- The recorder clicks the **Account** field — a lookup that links this Task to an Account record
- In Zoho CRM, Tasks can be associated with:
  - A **Contact** (person) — most common for follow-up tasks
  - An **Account** (company) — for tasks related to a business entity
  - A **Deal/Potential** — for stage-specific tasks
- Clicking "Account" may open a search/lookup dialog to select an existing Account record from the Accounts module
- The field label `Account` displayed as the click target suggests this may be clicking the field label to focus the input, or clicking an already-populated lookup showing the account name "Account" (unlikely — more likely the field placeholder or label)

---

### Step 13 — Click Form Summary (Review State)

| Property     | Detail |
|--------------|--------|
| Action       | Click form area |
| Target       | Form summary containing all entered fields |
| Element Type | Form body — review/confirmation state |
| Location     | Task creation form — full form view |
| Fields visible | Subject, Type, Attempt, Due Date, Status, Priority, Telecaller, Approver, Account, Repeat, Auto Close, Reminder |

**Screenshot Analysis:**
- Scribe captures a click on the **form summary** showing all filled-in fields — this is likely the recorder clicking on the form body to dismiss a dropdown or confirm the current state
- The fields listed in the Scribe label confirm the **complete Task form field set** for Kurinjee Promoters:

  | Field        | Value Entered      | Type    |
  |--------------|--------------------|---------|
  | Subject      | `Testing Task`     | Text *  |
  | Type         | (not specified)    | Dropdown |
  | Status       | `Attempt`          | Dropdown (custom) |
  | Due Date     | `21` (date selected) | Date  |
  | Priority     | (not specified)    | Dropdown |
  | Telecaller   | `Sumathi`          | Dropdown (custom) |
  | Approver     | `Manager Testing`  | Dropdown (custom) |
  | Account      | (clicked)          | Lookup  |
  | Repeat       | (not specified)    | Dropdown |
  | Auto Close   | (not specified)    | Toggle  |
  | Reminder     | (not specified)    | Dropdown |

- This step reveals the **full field inventory** of the Kurinjee Promoters Task form — the most comprehensive field list captured for the Tasks module in any flow

---

### Step 14 — Click Save Button

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | Save button (Scribe: "Click button field") |
| Element Type | Primary save action button |
| Location     | Task creation form — action button row |

**Screenshot Analysis:**
- The recorder clicks the **Save** button — submitting the completed Task form
- After saving:
  1. The "Testing Task" record is created in the Tasks module
  2. Assigned to Telecaller: **Sumathi**, Approver: **Manager Testing**
  3. Status: **Attempt**, Due Date: **21st**
  4. The user is navigated to either the Task detail view or back to the Tasks list view
- The saved Task record URL would follow: `https://crm.zoho.in/crm/org60043078423/tab/Tasks/{record_id}`

---

## Task Form — Complete Field Architecture (Kurinjee Promoters)

### Standard Zoho CRM Task Fields

| Field        | Type       | Mandatory | Notes |
|--------------|------------|-----------|-------|
| Subject      | Text       | **Yes**   | Task title / name |
| Due Date     | Date       | No        | Format: DD/MM/YYYY |
| Status       | Dropdown   | No        | Standard + custom values |
| Priority     | Dropdown   | No        | High, Normal, Low |
| Type         | Dropdown   | No        | Call, Meeting, Email, etc. |
| Repeat       | Dropdown   | No        | Recurring task settings |
| Auto Close   | Toggle     | No        | Auto-complete on activity |
| Reminder     | Dropdown   | No        | Pre-due reminder timing |
| Account      | Lookup     | No        | Linked Account record |
| Description  | Text Area  | No        | Task notes |

### Custom Fields — Kurinjee Promoters (Tasks Module)

| Field       | Type     | Values Known     | Purpose |
|-------------|----------|------------------|---------|
| Telecaller  | Dropdown | Sumathi, (others) | Assigns task to a Telecaller |
| Approver    | Dropdown | Manager Testing, (others) | Assigns manager oversight |

### Custom Status Values — Kurinjee Promoters

| Status Value    | Type    | Notes |
|-----------------|---------|-------|
| `Attempt`       | Custom  | Call attempted, no connection |
| `Not Started`   | Standard | Default initial state |
| `In Progress`   | Standard | Actively being worked |
| `Completed`     | Standard | Fully done |
| `Deferred`      | Standard | Postponed |
| `Waiting for Input` | Standard | Blocked on external input |

---

## Team Members Revealed Across All 17 Flows

| Name             | Role        | First Seen | Context |
|------------------|-------------|------------|---------|
| Sri              | Admin/Recorder | Flow 1  | Record owner across all flows |
| Sumathi          | Telecaller  | Flow 17    | Assigned as Telecaller on Task |
| Manager Testing  | Test Manager | Flow 17   | Test account for Approver role |
| Prasanth         | Contact/Client | Flow 12  | Real contact/deal record |

---

## URL Reference

| Element                | Value |
|------------------------|-------|
| CRM Base URL           | `https://crm.zoho.in/crm/org60043078423/` |
| Tasks List URL         | `https://crm.zoho.in/crm/org60043078423/tab/Tasks/custom-view/955332000000435996/list?page=1` |
| Custom View ID (Tasks) | `955332000000435996` |
| Module                 | Tasks |
| Org ID                 | `60043078423` |
| Test Record Name       | `Testing Task` |

---

## Workflow Summary

```
[Tasks List View — custom-view/955332000000435996/list, page=1]
       |
       v
[Click "Create Task" (Step 2)]
       |
       v
[Task Creation Form opens]
       |
       v
[Type "Testing Task" — Subject field (Step 3)]
       |
       v
[Click Telecaller dropdown "-None-" (Step 4)]
       |
       v
[Select "Sumathi" — Telecaller assigned (Step 5)]
       |
       v
[Click Approver dropdown "-None-" (Step 6)]
       |
       v
[Select "Manager Testing" — Approver assigned (Step 7)]
       |
       v
[Click Status dropdown "-None-" (Step 8)]
       |
       v
[Select "Attempt" — custom status set (Step 9)]
       |
       v
[Click Due Date field "dd/mm/yyyy" (Step 10)]
       |
       v
[Click "21" — date selected from calendar (Step 11)]
       |
       v
[Click Account lookup field (Step 12)]
       |
       v
[Click form summary — review all fields (Step 13)]
  Subject: Testing Task | Telecaller: Sumathi | Approver: Manager Testing
  Status: Attempt | Due Date: 21 | Priority: — | Account: —
       |
       v
[Click Save (Step 14)]
       |
       v
[Task "Testing Task" created and saved]
[Assigned to Sumathi (Telecaller) + Manager Testing (Approver)]
```

---

## Comparison: All Seventeen Flows

| #  | Flow                    | Module      | Steps | Duration | Key Operation |
|----|-------------------------|-------------|-------|----------|---------------|
| 1  | Create                  | Lead        | 13    | ~47s     | Form fill + save |
| 2  | Update                  | Lead        | 10    | ~37s     | Field edits + save |
| 3  | Delete                  | Lead        | 5     | ~22s     | Two-click delete |
| 4  | Related List            | Lead        | 5     | ~25s     | Navigate to Scheduler |
| 5  | Filter                  | Lead        | 8     | ~24s     | Criteria-based filter |
| 6  | Sort                    | Lead        | 8     | ~34s     | Sort by Country |
| 7  | Manage Columns          | Lead        | 9     | ~44s     | Column + page limit |
| 8  | Blueprint               | Lead        | 22    | ~2 min   | BANT qualification |
| 9  | Custom View             | Lead        | 5     | ~36s     | Switch to Today's Leads |
| 10 | Module Link (WorkDrive) | Lead        | 2     | ~23s     | Link record to WorkDrive |
| 11 | Save and New            | Contact     | 6     | ~20s     | Batch contact creation |
| 12 | Clone                   | Contact     | 4     | ~8s      | Duplicate existing record |
| 13 | Record Import           | Accounts    | 4     | ~17s     | Bulk import via CSV |
| 14 | Record Export           | Accounts    | 5     | ~23s     | Export all records to CSV |
| 15 | Customize Homepage      | Home        | 13    | ~2 min   | Home page widget editor + role config |
| 16 | Print Preview           | Potentials  | 4     | ~53s     | Print-format record view |
| 17 | Create Task             | Tasks       | 14    | ~45s     | Full task form with custom fields |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **First Tasks module creation flow** — the Tasks module was previously documented in the project (`task/Tasks.md`) as a DOM scan; this flow adds the live record creation interaction layer |
| 2 | **Two new custom fields confirmed** — `Telecaller` and `Approver` are custom fields added to the Kurinjee Promoters Tasks module; they implement a maker-checker workflow for the telecalling team |
| 3 | **"Attempt" status confirmed as custom** — this is not a standard Zoho CRM task status; it reflects the telecalling reality where a call is dialled but not answered — a distinct state from "Not Started" or "In Progress" |
| 4 | **Sumathi revealed as a real team member** — the first non-Sri, non-test team member named in any flow; Sumathi is a Telecaller at Kurinjee Promoters |
| 5 | **Tasks custom view ID is older** — suffix `435996` vs Lead's `441406` (gap of ~5,410); Tasks module customisation predates the Lead/Contact/Account/Potential custom view setup |
| 6 | **Step 12 Account field ambiguity** — clicking "Account" may mean clicking the Account lookup field label/placeholder, or it may indicate an account was already selected and the click was on the populated field value; the exact account linked is not captured |
| 7 | **Due date is in the past** — 21st in February 2026 (recording date: 2026-02-27) means the due date is 6 days before the recording; confirms this is a test task, not a real work item |
| 8 | **Full field inventory captured via Step 13** — the form summary click (Step 13) is the most data-rich step in the flow, revealing all 11 visible fields in the Kurinjee Promoters Task form |
