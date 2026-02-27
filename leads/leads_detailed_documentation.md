# Zoho CRM — Leads Module: Full Reverse Engineering Documentation

## 1. Module Overview

**Module Name:** Leads  
**URL Base:** `/crm/org60043078423/tab/Leads`  
**Total Records Observed:** 2,077  
**Primary Purpose:** Capture, qualify, and convert prospective real estate buyers into Contacts and Deals.  
**Blueprint Active:** Yes — "Lead Qualification" Blueprint governs state transitions and automated actions.

---

## 2. Screen-by-Screen Breakdown

### 2.1 Leads List View

**URL:** `/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list`

#### Layout Structure

The list view is a tri-zone layout:

- **Left sidebar (~300px):** Filter panel ("Filter Leads by") with search box, System Defined Filters, Website Activity filters, and Filter By Fields.
- **Top bar:** Custom view tabs (All Leads, Open Leads, Site Visit Scheduled Leads, "..."), followed by a toolbar row (Filter, Sort, view switchers, Create Lead, Actions "...").
- **Main grid:** Column-based record rows with checkboxes, row indicators, and inline call icons.

#### Custom View Tabs

- All Leads (active), Open Leads, Site Visit Scheduled Leads
- "..." dropdown exposes: Created By Me group (Arthi-View, Cold Leads, Hot Leads, Junk Lead, Nurturing Leads, Pranesj, Site Visit Scheduled Leads, Telecaller Leads, Warm Leads) and Public Views group (All Leads, All Locked Leads, Converted Leads, Junk Leads, Mailing Labels, My Converted Leads, My Leads).
- "New Custom View" and "Manage Custom View" links are available.
- "Show custom views as Dropdown" toggle is available.
- **"Today's Leads"** — additional confirmed custom view (not in tab bar; accessed via view selector). Filter criteria: `Created Time = Today`. Dynamic — auto-updates daily. Primary Telecaller entry point for fresh leads.

#### Custom View Selector Panel

Accessed by clicking the view name dropdown / "Resize handle" toggle at the top-left of the list. Panel shows:
- System Views (All Leads, My Leads, Recently Created, Converted, Junk, Unread)
- Custom Views (Created By Me + Public Views groups)
- Switching views: may require up to three click interactions on the target view name (hover → select → navigate)

#### View Switchers (toolbar icons, left to right)

List View (active), Kanban View, Table View, Activity View, Map View, Compact View, and a dropdown chevron for more views.

#### Columns Visible

Lead Name (with "All" filter chip and sort), Lead Source, Mobile (with inline call icon), Lead Status, BDM. A column-settings icon (arrows icon) appears in the header row top-right.

#### Row Indicators

- Green date badge (e.g., "Feb 27", "Feb 28"): upcoming follow-up date.
- Orange "Today" badge: task/action due today.
- Small document icon on some rows: indicates notes/activity attached.
- Phone icon in Mobile column: inline click-to-call.

#### Filter Panel

Two separate filter mechanisms exist:

**1. Left sidebar filter panel**
- Triggered by: `Filter` button in the toolbar (left side)
- Opens as a left sidebar panel (~300px)
- Sections:
  - **System Defined Filters:** Touched Records, Untouched Records, Record Action, Related Records Action, Locked, Latest Email Status, Activities, Cadences.
  - **Website Activity:** Average Time Spent (Minutes), Days Visited, First Page Visited, First Visit, Most Recent Visit, Number Of Chats, Referrer, Visitor Score.
  - **Filter By Fields:** Scrollable list of all module fields.

**2. Right-side advanced filter drawer**
- Triggered by: `Resize handle Right` — a handle/toggle on the right edge of the list view
- Opens as a right-side sliding panel, narrowing the list width
- Contains a **Search** field — type a field name to filter the field list dynamically (e.g., typing "lead" shows: Lead Owner, Lead Quality, Lead Source, Lead Status, Lead Type)
- Filter criteria row structure: `[Field] | [Operator ▾] | [Value input]`
- Confirmed operators: `is`, `is not`, `is empty`, `is not empty`, `contains`, `does not contain`, `starts with`
- **`Apply Filter`** button (blue, primary) at bottom — applies criteria and refreshes list
- Single or multi-condition filtering supported

#### Toolbar Actions

- **Filter** button — opens/closes left filter panel.
- **Sort** button — opens sort criteria panel (modal/dialog). Panel contains:
  - Field selector dropdown (default: `None`; confirmed sortable field: `Country`)
  - Order: Ascending / Descending radio buttons (default: Ascending)
  - **`Apply`** button (blue) — executes sort; updates list and adds sort arrow `▲/▼` to column header
  - **`Cancel`** button — closes panel; **preserves** any previously applied sort (does not clear it)
  - Sort state encoded in URL: `?sort_order=asc|desc|unsort&sort_by={field_id}`
- **Refresh** (circular arrow) — refreshes the current custom view.
- **Create Lead** (primary blue button, with split dropdown arrow for alternate layouts).
- **Column settings icon** (arrows/grid icon, top-right of header row) — opens dropdown menu:
  - `Manage Columns` — opens two-pane column selector (Available | Selected); drag to reorder; Save button; per-user setting
  - `Resize Columns` — drag-to-resize column widths
  - `Reset Columns` — restores default column configuration
- **Actions (...) menu:** Mass Delete, Mass Update, Mass Convert, Manage Tags, Drafts, Mass Email, Autoresponders, Approve Leads, Deduplicate Leads, Create Client Script ✨, Export Leads, Zoho Sheet View, Print View ✨.

#### Row-Level Actions (hover "..." on row)

Primary: Edit, Send Email, Create Task, Add Tags, Convert, Delete, Copy URL.
More submenu: Create Call (sub: Schedule a call, Log a call), Create Meeting.

#### Pagination

Shows "Total Records 2077" at bottom left. Page navigation at bottom right with Previous (`<`) and Next (`>`) buttons.
**Records per page** is a user-configurable dropdown (not fixed). Confirmed options: 10, 20, 25, 50, 100, 200. Values of 20 and 100 confirmed observed. Setting persists per user session.

### 2.2 Lead Detail View

**URL Pattern:** `/crm/org60043078423/tab/Leads/{leadId}`  
**Sample:** `/crm/org60043078423/tab/Leads/955332000006926001`  
**Lead Name:** Ram

#### Header Zone

- Back button (←), Lead name ("Ram"), "Add Tags" link.
- Last Update timestamp: "Last Update: 10:32 AM".
- Previous/Next record navigation arrows (top right).
- Action buttons: Send Email, Convert, Edit, Fetch Lead Status (split: Fetch Lead Status / New Appointment / Email Booking URL), More Options (...).

#### More Options (...) Menu Items

Clone, Delete, Print Preview, Find and Merge Duplicates, Mail Merge, Run Macro, Customize Business Card, Organize Lead Details, Add Related List, Review History, Enroll to Cadence, Add Kiosk ✨, Create Button, Create Client Script ✨.

#### Left Sidebar — Related List

Notes (1), Connected Records, Open Activities (2), Cadences, Projects, Referrals, Documents, Emails, Closed Activities, Invited Meetings, Schedules (1), Voice of the Customer, Customer Feedback, Add Related List.  
**Links section:** Workdrive, Add Link.

#### Main Content — Tabs

## Two tabs: Overview (default) and Timeline.

### 2.3 Overview Tab

**Sub-sections (top to bottom):**
**Blueprint State Bar**

- Label: "Current State: [Stage Name]" (e.g., `Current State: Attempted`)
- "View configured actions" link (top right of bar)
- Transition buttons depend on current state (see full sequence below)

**Blueprint Stage Sequence — confirmed from Scribe recordings + DOM scan:**

| Stage | Entry Transition | Mandatory Fields in Transition Modal |
|-------|-----------------|--------------------------------------|
| New Lead | (created) | none |
| Enquiry Stage | `Enquiry` button | Email |
| Lead Qualification | `Lead` button | Estimated Budget, Budget Variation, Authority (Select authority), Need (Select need), Timeline (Select time), Matched Projects |
| Attempted | (auto after qualification) | — |

**Transition buttons for state "Attempted":**
Re Attempted, Contact in Future, Lead, Site Visit Completed, Qualify Out, Junk, Exit Blueprint

> `Enquiry` and `Lead` are the first two gated transitions for a **new** lead. `Attempted` state buttons are what's visible on existing qualified leads.
> See `leads_blueprint_transitions.md` for complete modal structures and confirmed dropdown values.
  **Business Card Details (always visible)**
- Mobile: (988) 421-0274 (call icon)
- Email: —
- Lead Status: Attempted
- Lead Source: Offline Marketing
- Lead Owner: Kurinjee Promoters (pencil icon for inline edit; hover shows popover with role CEO/Administrator, email kurinjeecrm01@gmail.com, phone 9597736066)
  **Next Action Section**
  Shows upcoming tasks linked to this Lead. Example: FEB 27 → Attempt 2, FEB 27 → Attempt 1 (links to Task records).
  **Hide Details Toggle**
  Collapsible row that hides/shows the full field sections below.
  **Lead Information Section** (full edit form fields — see Edit Form section)
  **Requirement Assessment Section**
- Preferred Location, Purpose Of Purchase, 1–3 Preferred Location, Down Payment, Payment Type, Land Area in cents, Comfortable Price, Rooms in BHK, Up to Price, Requirement Property Type, Client Major Concern on Purchase.
  **Lead Assessment Section**
- Budget (Mismatch), Authority (Self), Need (5-10 Km), Time (1-3 Months).
  **Address Information Section**
- Street, City (coimbatore), State (Tamil Nadu), Zip Code, Country.
  **Qualification Form Section**
- Does the lead have the financial capability to purchase? (checkbox), Who is making the decision for this purchase?, Does the project match the lead's location preference?, When is the lead planning to buy?
  **Client Feedback Section**
- Feedback URL, Comments, Client Rating.
  **Team Lead Section**
- Approval for Closure (checkbox).
  **Site Visit Information Section**
- Site Visit URL, Visit Status, Client Comments, Site Visit Location, BDM Form URL, Site Visit Date, When Are You Planning to Start, BDM, Is There is Any Other Specific Concerns.
  **Site Completion Form Submission Section**
- Visit Date, Travel mode/Notes, Client's Overall Impression, Location Mismatch Description, Real Objections, Timing Description, Decision Influencers, Loan Delay/Bank Issue Description, Next Committed Step, Need to Discuss with Family Description, Follow-up date, Competing Project Comparison Description, Visit Verified, Budget Concern Description, Objection Status, Legal/Approvals Clarification Description, Urgency Level, BDM Notes, Amenities/Facility Expectation Description, Other Description.
  **Referral Information Section** (visible on scroll)
  **Scoring Rules Widget** (bottom of overview)
  **Notes Panel**
- "Add a note" text input, note filter dropdown, existing notes listed.
  **Connected Records**
- "Add New" button, "No records found" empty state.
  **Open Activities** (column view)
- Open Tasks (2): Attempt 1, Attempt 2 — shows date, owner, Status: Not Started, Priority: Normal.
- Open Meetings (0): No records found.
- Open Calls: No records found.
- "Add New" dropdown: Task / Meeting / Call (Call sub-options: Schedule a call, Log a call).
- Column View dropdown for display format.
  **Cadences**
- Enroll button, Un-enroll button, No records found.
  **Projects**
- Collapse/expand arrow.
  **Referrals**
- Assign, New, Edit buttons.
  **Documents**
- Table view.
  **Emails**
- Compose Email buttons, Mails / Drafts / Scheduled sub-tabs.
  **Closed Activities**
- Loading state, No records found.
  **Invited Meetings**
- No records found.
  **Schedules**
- Assign, New, Edit buttons; data grid shown.
  **Voice of the Customer**
- Entity Dashboard, sentiment visualization.
  **Customer Feedback**
- Assign, New, Edit buttons.

---

### 2.4 Timeline Tab

**Sub-tabs:** History | Interactions
**History sub-tab:**

- Timeline History with filter icon (funnel).
- "0 Upcoming Automated Actions" (expandable).
- Date-grouped entries (e.g., Feb 26, 2026).
- Entry types observed:
  - Field updates (e.g., "Folder ID was updated from blank value to [ID]")
  - Function calls (e.g., "Function RescheduleFollowUps was called by Kurinjee Promoters through Transition - Attempted in Blueprint - Lead Qualification")
  - Workflow triggers (e.g., "Function [Leads] Update Mobile Number was called via Workflow Rule Update Mobile Number")
  - Task additions (e.g., "Task added - Attempt 2 via Function RescheduleFollowUps")
  - Notes (e.g., "Note added - UnAttempted Reason, Reason - Connected — Call Back Later")
    **Interactions sub-tab:**
- Customer Interactions with filter icon.
- View By: All (dropdown).
- Signals (green dot) and Follow-ups (teal dot) legend.
- Empty state: "No logs available".

---

### 2.5 Edit Lead Form

**URL:** `/crm/org60043078423/tab/Leads/{leadId}/edit`  
**Page Title:** Edit Lead  
**Edit Page Layout** link available.  
**Buttons:** Cancel, Save and New, Save.
All fields listed in the YAML above under `edit_form.sections`.

---

## 3. Assignment Logic

The Lead Owner field is a user lookup field. It can be changed via:

1. **Inline edit on Detail View:** Click hover pencil icon on Lead Owner in Business Card section. Field becomes editable text input. Save auto-applies.
2. **Full Edit Form:** Click "Edit" button → Lead Information section → Lead Owner field → select user → Save.
3. **Mass Update:** List view → select records → Actions → Mass Update → set Lead Owner.
   On hover of Lead Owner (detail view), a popover shows: avatar, name (Kurinjee Promoters), role (CEO, Administrator), email, and phone.

---

## 4. Stage Movement Logic

Stage is governed by the **Lead Qualification Blueprint**. The Lead Status field is **locked** (padlock icon in edit form) — it cannot be freely edited. Stage changes occur only through Blueprint transition buttons.

**Current State** is displayed in a dedicated bar at the top of the Overview tab.

**Full confirmed stage sequence:**

```
New Lead Created
    │
    ▼  [Enquiry transition — mandatory: Email]
Enquiry Stage
    │
    ▼  [Lead transition — mandatory: Estimated Budget, Budget Variation,
    │   Authority, Need, Timeline, Matched Projects]
Lead Qualification Stage
    │
    ▼
Attempted State
    ├── Re Attempted
    ├── Contact in Future
    ├── Lead
    ├── Site Visit Completed
    ├── Qualify Out
    ├── Junk
    └── Exit Blueprint
```

**On new lead creation, automated actions fire immediately:**
- Field Update: `Update Attempt Field`
- Field Update: `Update Lead Status`
- Function: `[Lead] Send Welcome Message` (WhatsApp/SMS notification)

**Each Blueprint transition triggers:**
- Automated functions (e.g., RescheduleFollowUps)
- Workflow rules (e.g., Update Mobile Number)
- Auto-task creation (e.g., Attempt 2)
- Auto-note creation (e.g., UnAttempted Reason)
- Field updates logged in Timeline > History

**History tracking:** All state changes are recorded in Timeline > History with timestamp, actor, transition name, Blueprint name, and date.

---

## 5. Conversion Workflow

**Trigger:** "Convert" button in Lead detail header.  
**URL:** `/crm/org60043078423/tab/Leads/{leadId}/convert`
**Step 1 — Contact Creation:**

- "Create New Contact" label with pre-filled lead name as chip (e.g., "Ram").
- Automatically maps Lead fields to Contact fields (mapping defined in Lead Conversion Mapping).
  **Step 2 — Deal Creation (Optional):**
- Checkbox: "Create a new Deal for this Contact." (default: unchecked).
- When checked, reveals fields: Amount (₹, required), Deal Name (pre-filled with lead name), Closing Date (DD/MM/YYYY), Stage (dropdown, default: Closed Won), Contact Role (dropdown, default: None).
  **Step 3 — Owner Assignment:**
- "Owner of the New Records: Kurinjee Promoters" (editable).
  **Buttons:** Convert (primary), Cancel.
  **Quick Links sidebar:** Lead Conversion Mapping, Help.
  **Account creation:** Not shown as an explicit step — may be implicit via mapping or organization settings.
  **Confirmation behavior:** Clicking "Convert" immediately processes the conversion — no additional confirmation modal observed before conversion.

---

## 6. Follow-up Workflow

### 6.1 Add Task

- **Trigger:** Open Activities → Add New → Task
- **Fields:** Subject (required), Due Date, Priority (default: High), Owner (default: current user), Reminder (toggle), Repeat (toggle), More Fields (Telecaller, Type, Approver, Related To, Status, Auto Close, Description)
- **Buttons:** Cancel, Save

### 6.2 Schedule Meeting

- **Trigger:** Open Activities → Add New → Meeting
- **Fields:** Title (default: "New Meeting"), Meeting Venue (default: Client location), Location, All day (checkbox), From date/time (default: current date, 02:00 PM), To date/time (default: current date, 03:00 PM), Meeting From (default: Self), Type Of Visit
- **Link:** "Add more details" opens full meeting form
- **Buttons:** Cancel, Save

### 6.3 Log a Call

- **Trigger:** Open Activities → Add New → Call → Log a call
- **Sections & Fields:**
  - Call Information: Call For (Lead / Ram), Related To (Account), Call Type (Outbound), Outgoing Call Status (Completed, locked), Call Start Time (current date/time), Call Duration (minutes/seconds), Subject (default: "Outgoing call to Ram"), Voice Recording
  - Purpose Of Outgoing Call: Call By (-None-), Call Purpose (-None-)
- **Buttons:** Cancel, Save

### 6.4 Schedule a Call

- **Trigger:** Open Activities → Add New → Call → Schedule a call
- Opens a separate scheduling form (analogous to Log a call but for future calls)

---

## 7. Navigation Tree

```
Home
└── Leads (sidebar nav)
    ├── List View (All Leads / Open Leads / Site Visit Scheduled Leads / Custom Views)
    │   ├── Filter Panel (left sidebar)
    │   ├── View Switchers (List/Kanban/Table/Activity/Map/Compact)
    │   ├── Create Lead → New Lead Form
    │   ├── Actions Menu (Mass Delete/Update/Convert/Email/Export...)
    │   └── Row Actions (Edit / Send Email / Create Task / Convert / Delete / Create Call / Create Meeting)
    │
    └── Lead Detail View (/tab/Leads/{id})
        ├── Send Email → Email compose
        ├── Convert → Convert Lead page (/convert)
        │   ├── Create Contact (auto)
        │   ├── Create Deal (optional checkbox)
        │   └── Set Owner → Convert button
        ├── Edit → Edit Lead Form (/edit)
        │   └── Save / Save and New / Cancel
        ├── Fetch Lead Status (split button)
        ├── More Options (...)
        │   ├── Clone
        │   ├── Delete
        │   ├── Print Preview
        │   ├── Find and Merge Duplicates
        │   ├── Mail Merge
        │   ├── Run Macro
        │   └── Review History
        ├── Overview Tab
        │   ├── Blueprint Transitions (Re Attempted / Contact in Future / Lead / Site Visit Completed / Qualify Out / Junk / Exit Blueprint)
        │   ├── Lead Owner inline edit → User selection
        │   ├── Next Action tasks (links to /tab/Tasks/{id})
        │   ├── All Field Sections (Lead Info / Requirement / Assessment / Address / etc.)
        │   ├── Notes → Add note
        │   ├── Connected Records → Add New
        │   ├── Open Activities → Add New (Task / Meeting / Call)
        │   │   ├── Create Task modal
        │   │   ├── Meeting Information modal
        │   │   └── Log a call / Schedule a call modal
        │   ├── Cadences → Enroll
        │   ├── Emails → Compose Email
        │   └── Schedules / Documents / Referrals / etc.
        └── Timeline Tab
            ├── History (field changes, function calls, workflow triggers, task/note additions)
            └── Interactions (Signals + Follow-ups, View By: All)
```
