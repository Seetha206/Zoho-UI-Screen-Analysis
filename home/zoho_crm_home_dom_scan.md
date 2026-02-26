# 🔍 Full DOM Scan — Zoho CRM Home Screen
Source: Live DOM scan via read_page tool + screenshot capture Date of scan: 26/02/2026, 12:21 PM Tab: 953964971

## A) 📋 SCREEN SUMMARY (Structured)
### 1️⃣ Page Identity

| Field | Value |
| --- | --- |
| Page Name | Home |
| Module | Home Dashboard |
| URL Pattern | /crm/org60043078423/tab/Home/begin |
| Organization | Kurinjee Promoters (Org ID: 60043078423) |
| Logged-in User | Kurinjee (Profile avatar: "K", red circle) |
| Active Dashboard | Kurinjee Promoters's Home |


### 2️⃣ Layout Structure
Top Header — Fixed bar at top, full width, dark background
Left: Zoho CRM logo + app name
Center-left: Page title "Home" (plain text)
Center: Search records bar
Right: Create (+) button, Ask Zia (ZA), Signals (bell), Calendar, Marketplace, Setup (gear), Profile (K), App Switcher (grid icon) Sidebar Navigation — Left panel (~210px wide), dark theme
App branding at top: "Zoho CRM" logo + collapse toggle
Primary nav items (4): Home, Reports, Analytics, My Requests
Teamspace section: "CRM Teamspace" with expand arrow + "..." more options
Search box within sidebar
Module list (14 items, scrollable)
Bottom: Chats, Channels, Contacts icons Main Content Area — Right of sidebar, full height
Welcome banner: "Welcome Kurinjee Promoters" with refresh + dashboard switcher
4 KPI summary widgets (top row)
2 list/table widgets (middle row): My Open Tasks + My Meetings
2 chart/data widgets (bottom row): My Pipeline Deals By Stage + My Deals Closing This Month Widgets Section — 6 widgets total (described in §5) Footer — Bottom toolbar (persistent)
Left: Chats, Channels, Contacts
Center: Smart Chat bar ("Here is your Smart Chat (Ctrl+Space)")
Right: Toolbar icons — Screen Share, Visitors Online, Feedback on New UI (highlighted purple), Announcements (megaphone), Mail, Motivator, Sticky Notes, Zia, Activity Reminders, Recent Items, Accessibility

### 3️⃣ Sidebar Analysis
Primary Navigation Items (top group):

| # | Label | Link/URL | Type |
| --- | --- | --- | --- |
| 1 | Home | /tab/Home/begin | Primary Nav (Active/Highlighted) |
| 2 | Reports | /tab/Reports | Primary Nav |
| 3 | Analytics | /tab/Dashboards | Primary Nav |
| 4 | My Requests | /tab/Requesters | Primary Nav |
| CRM Teamspace (section header with dropdown): |  |  |  |

Button: "CRM Teamspace" with expand (▾) and "..." more-actions
More actions menu: New Teamspace, Create Folder, Associate Modules, Manage CRM Teamspace, View All Teamspace Module List (under Teamspace, scrollable): | # | Module Label | URL Pattern | Note | |---|---|---|---| | 1 | Leads | /tab/Leads | + More Actions | | 2 | Workqueue ✨ | /tab/Workqueue | AI-enhanced (sparkle icon) | | 3 | Contacts | /tab/Contacts | + More Actions | | 4 | Accounts | /tab/Accounts | + More Actions | | 5 | Deals | /tab/Potentials | + More Actions | | 6 | Projects Portfolio | /tab/CustomModule3 | Custom Module | | 7 | Employee Portfolio | /tab/CustomModule5 | Custom Module | | 8 | Customer Feedback | /tab/CustomModule7 | Custom Module | | 9 | Tasks | /tab/Tasks | + More Actions | | 10 | Meetings | /tab/Events | + More Actions | | 11 | Calls | /tab/Calls | + More Actions | | 12 | Prospecting Leads | /tab/CustomModule1 | Custom Module | | 13 | Logs | /tab/CustomModule4 | Custom Module | | 14 | Scheduler | /tab/CustomModule6 | Custom Module | | 15 | Voice of the Customer | /tab/Voice of the Customer | Custom Module | Bottom bar icons: Chats, Channels, Contacts

### 4️⃣ Header Analysis

| Element | Description | Ref |
| --- | --- | --- |
| Search Bar | "Search records" text field, full-width style, center of header | ref_122 / ref_123 |
| Create (+) Button | Purple square button with "+" icon for quick record creation | ref_124 |
| Ask Zia | "ZA" icon — AI assistant | navitem ref_126 |
| Signals (Bell) | Notification / signals icon | navitem ref_127 |
| Calendar | Links to /crm/org60043078423/calendar?date=26-02-2026&viewType=day | navitem ref_128 |
| Marketplace | Links to /crm/org60043078423/settings/extensions/all | navitem ref_131 |
| Setup (Gear) | Links to /crm/org60043078423/settings/index | navitem ref_134 |
| Profile | "K" red circle avatar — user profile menu | navitem ref_137 |
| App Switcher | 9-dot grid icon at far right — Zoho app grid | navitem ref_141 |


### 5️⃣ Widgets Analysis
#### Widget 1 — My Open Deals

| Property | Value |
| --- | --- |
| Widget Name | My Open Deals |
| Data Type | KPI / Count |
| Metric Shown | Count of open deals |
| Numeric Value | 6 |
| Clickable | Yes — "Add Filter", "Refresh Now", "More" (Edit, Delete, Download) |

#### Widget 2 — My Untouched Deals

| Property | Value |
| --- | --- |
| Widget Name | My Untouched Deals |
| Data Type | KPI / Count |
| Metric Shown | Deals not yet touched |
| Numeric Value | 0 |
| Clickable | Yes — "Add Filter", "Refresh Now", "More" (Edit, Delete, Download) |

#### Widget 3 — My Calls Today

| Property | Value |
| --- | --- |
| Widget Name | My Calls Today |
| Data Type | KPI / Count |
| Metric Shown | Calls scheduled/made today |
| Numeric Value | 0 |
| Clickable | Yes — "Add Filter", "Refresh Now", "More" (Edit, Delete, Download) |

#### Widget 4 — My Leads

| Property | Value |
| --- | --- |
| Widget Name | My Leads |
| Data Type | KPI / Count |
| Metric Shown | Total leads owned |
| Numeric Value | 2076 |
| Clickable | Yes — "Add Filter", "Refresh Now", "More" (Edit, Delete, Download) |

#### Widget 5 — My Open Tasks

| Property | Value |
| --- | --- |
| Widget Name | My Open Tasks |
| Data Type | List / Table |
| Columns | Subject, Due Date, Status, Priority, Related To, Contact Name |
| Rows Visible | 10 rows (pagination: 1–10, with Prev/Next) |
| Clickable | Subject links → individual Task records; Related To → Lead records |
| Pagination | 1 - 10 shown; < > navigation buttons |
| Task rows visible: |  |
| Subject | Due Date |
| --- | --- |
| Call | 28/02/2026 |
| Call | 01/03/2026 |
| Attempt 1 | 26/02/2026 |
| Followup Task 7 | 15/04/2026 |
| Review Task | 26/02/2026 |
| Review Task | 26/02/2026 |
| Attempt 1 | 26/02/2026 |
| Attempt 1 | 26/02/2026 |
| Followup Task 4 | 25/03/2026 |
| Followup Task 1 | 04/03/2026 |

#### Widget 6 — My Meetings

| Property | Value |
| --- | --- |
| Widget Name | My Meetings |
| Data Type | List / Table |
| Columns | Title, From, To, Related To, Contact Name |
| Rows Visible | 3 (pagination: 1–3) |
| Clickable | Title links → Event records; Related To → Account records; Contact Name → Contact records |
| Meeting rows visible: |  |
| Title | From |
| --- | --- |
| Site Visit with Hello | 18/08/2025 09:00 AM |
| Webinar | 30/06/2025 02:18 AM |
| Webinar | 30/06/2025 01:18 AM |

#### Widget 7 — My Pipeline Deals By Stage

| Property | Value |
| --- | --- |
| Widget Name | My Pipeline Deals By Stage |
| Data Type | Chart (Funnel/Pipeline) |
| Chart Type | Inverted funnel / triangular fill — purple and green |
| Stages Visible | Visit Pending: 5 (purple), Visit Completed: 1 (green) |
| Clickable | Yes — "Add Filter", "Refresh Now", "More" (Edit, Delete, Download) |

#### Widget 8 — My Deals Closing This Month

| Property | Value |
| --- | --- |
| Widget Name | My Deals Closing This Month |
| Data Type | List / Table |
| Content | "No Deals found." (empty state) |
| Clickable | "Refresh Now", "More" (Edit, Delete) |





### 6️⃣ Tables Analysis
#### Table A: My Open Tasks (ref_245)

| Column | Sortable | Sort Direction |
| --- | --- | --- |
| Subject | Yes (link) | Default |
| Due Date | Yes (link) | Asc toggle |
| Status | Yes (link) | — |
| Priority | Yes (link) | — |
| Related To | Yes (link) | — |
| Contact Name | Yes (link) | — |
| Pagination | 1–10 of total | Prev (<) / Next (>) buttons |
| Row Actions | Click subject → navigate to task; Click "Related To" → navigate to Lead |  |

#### Table B: My Meetings (ref_407)

| Column | Sortable |
| --- | --- |
| Title | Yes |
| From | Yes |
| To | Yes |
| Related To | Yes |
| Contact Name | Yes |
| Pagination | 1–3 |
| Row Actions | Title → Event record; Related To → Account; Contact Name → Contact |

#### Table C: My Deals Closing This Month (ref_488)

| Status | Empty State Message |
| --- | --- |
| No data | "No Deals found." |


### 7️⃣ Interaction Mapping — All Clickable Actions
Header:
Search Records (click to type)
+ Create button
Ask Zia icon
Signals/Bell icon
Calendar icon → day view
Marketplace icon → extensions
Setup/Gear icon → settings
Profile (K) icon → profile menu
App Switcher (9-dot grid) Welcome Banner Area:
🔄 Refresh all components (ref_146)
Dashboard switcher dropdown: Classic View / Kurinjee Promoters's Home / Manager's Home (New!) (ref_147–157)
... More options → Add Component, Reorder, View in Full Screen (ref_161–166)
Customize Home page link → /crm/org60043078423/settings/home-customization KPI Widgets (each has):
Add Filter
Refresh Now
More (▾) → Edit / Delete / Download My Open Tasks:
Each task subject → navigate to task detail
Each "Related To" lead → navigate to lead detail
Column header sort links (Subject, Due Date, Status, Priority, Related To, Contact Name)
Pagination: Previous < / Next > (showing 1–10) My Meetings:
Each meeting title → navigate to event detail
Related To account links
Contact Name links
Pagination: Previous / Next (1–3) My Pipeline Deals By Stage:
Add Filter, Refresh Now, More (Edit / Delete / Download)
Funnel segments clickable (Visit Pending: 5, Visit Completed: 1) My Deals Closing This Month:
Refresh Now, More (Edit / Delete) Sidebar:
Home, Reports, Analytics, My Requests
CRM Teamspace expand / more (...)
All 15 module nav links
Sidebar collapse (Hide Menu) toggle
Sidebar search box Footer Toolbar (bottom right):
Visitors Online
Feedback on New UI (purple highlight)
Announcements
Mail
Motivator
Sticky Notes
Zia
Activity Reminders
Recent Items
Accessibility
B) 🌲 UI COMPONENT HIERARCHY (Tree Format)

[PAGE: Home — Zoho CRM]
│
├── [HEADER]
│   ├── Logo + "Zoho CRM" text
│   ├── Sidebar Collapse Button
│   ├── Page Title: "Home"
│   ├── Search Records [textbox]
│   ├── Create (+) [button]
│   └── Nav Icons
│       ├── Ask Zia (ZA)
│       ├── Signals (Bell)
│       ├── Calendar
│       ├── Marketplace
│       ├── Setup (Gear)
│       ├── Profile (K)
│       └── App Switcher (Grid)
│
├── [SIDEBAR NAVIGATION]
│   ├── Primary Nav
│   │   ├── Home [active]
│   │   ├── Reports
│   │   ├── Analytics
│   │   └── My Requests
│   ├── CRM Teamspace [section]
│   │   ├── Label: "CRM Teamspace" ▾
│   │   └── More (...) → [New Teamspace, Create Folder, Associate Modules, Manage, View All]
│   ├── Search [textbox]
│   └── Module List
│       ├── Leads
│       ├── Workqueue ✨
│       ├── Contacts
│       ├── Accounts
│       ├── Deals
│       ├── Projects Portfolio
│       ├── Employee Portfolio
│       ├── Customer Feedback
│       ├── Tasks
│       ├── Meetings
│       ├── Calls
│       ├── Prospecting Leads
│       ├── Logs
│       ├── Scheduler
│       └── Voice of the Customer
│
├── [MAIN CONTENT AREA]
│   ├── Welcome Banner
│   │   ├── "Welcome Kurinjee Promoters"
│   │   ├── Refresh All [button]
│   │   ├── Dashboard Switcher [combobox]
│   │   │   ├── Classic View
│   │   │   ├── Kurinjee Promoters's Home [selected]
│   │   │   └── Manager's Home [New!]
│   │   └── More Options (...) [combobox]
│   │       ├── Add Component
│   │       ├── Reorder
│   │       └── View in Full Screen
│   │
│   ├── ROW 1 — KPI Widgets (4 columns)
│   │   ├── Widget: My Open Deals → 6
│   │   ├── Widget: My Untouched Deals → 0
│   │   ├── Widget: My Calls Today → 0
│   │   └── Widget: My Leads → 2076
│   │
│   ├── ROW 2 — Table Widgets (2 columns)
│   │   ├── Widget: My Open Tasks [table, 10 rows, paginated]
│   │   │   ├── Columns: Subject | Due Date | Status | Priority | Related To | Contact Name
│   │   │   ├── Rows: 10 task items (all "Not Started", "Normal")
│   │   │   └── Pagination: 1–10 < >
│   │   └── Widget: My Meetings [table, 3 rows, paginated]
│   │       ├── Columns: Title | From | To | Related To | Contact Name
│   │       ├── Rows: Site Visit with Hello, Webinar ×2
│   │       └── Pagination: 1–3 < >
│   │
│   └── ROW 3 — Chart + Table Widgets (2 columns)
│       ├── Widget: My Pipeline Deals By Stage [funnel chart]
│       │   ├── Visit Pending: 5 (purple)
│       │   └── Visit Completed: 1 (green)
│       └── Widget: My Deals Closing This Month [table — empty]
│           └── "No Deals found."
│
└── [FOOTER TOOLBAR]
    ├── Left: Chats | Channels | Contacts
    ├── Center: Smart Chat bar
    └── Right: Visitors Online | Feedback on New UI | Announcements | Mail |
              Motivator | Sticky Notes | Zia | Activity Reminders | Recent Items | Accessibility






## C) 🧭 Navigation Possibilities from this Page

| Destination | Trigger | Target URL |
| --- | --- | --- |
| Home (current) | Sidebar: Home | /tab/Home/begin |
| Reports | Sidebar: Reports | /tab/Reports |
| Analytics / Dashboards | Sidebar: Analytics | /tab/Dashboards |
| My Requests | Sidebar: My Requests | /tab/Requesters |
| Leads module | Sidebar: Leads | /tab/Leads |
| Workqueue module | Sidebar: Workqueue | /tab/Workqueue |
| Contacts module | Sidebar: Contacts | /tab/Contacts |
| Accounts module | Sidebar: Accounts | /tab/Accounts |
| Deals module | Sidebar: Deals | /tab/Potentials |
| Projects Portfolio | Sidebar | /tab/CustomModule3 |
| Employee Portfolio | Sidebar | /tab/CustomModule5 |
| Customer Feedback | Sidebar | /tab/CustomModule7 |
| Tasks module | Sidebar: Tasks | /tab/Tasks |
| Meetings module | Sidebar: Meetings | /tab/Events |
| Calls module | Sidebar: Calls | /tab/Calls |
| Prospecting Leads | Sidebar | /tab/CustomModule1 |
| Logs | Sidebar | /tab/CustomModule4 |
| Scheduler | Sidebar | /tab/CustomModule6 |
| Voice of the Customer | Sidebar | /tab/Voice of the Customer |
| Calendar (Day View) | Header Calendar icon | /crm/org60043078423/calendar?date=26-02-2026&viewType=day |
| Marketplace / Extensions | Header Marketplace icon | /crm/org60043078423/settings/extensions/all |
| Setup / Settings | Header Gear icon | /crm/org60043078423/settings/index |
| Home Customization | Dashboard > Customize Home page | /crm/org60043078423/settings/home-customization |
| Individual Task record | Click task Subject | /tab/Tasks/{taskId} |
| Individual Lead record | Click "Related To" in tasks | /tab/Leads/{leadId} |
| Individual Event/Meeting | Click Meeting Title | /tab/Events/{eventId} |
| Individual Account | Click Related To (meetings) | /tab/Accounts/{accountId} |
| Individual Contact | Click Contact Name | /tab/Contacts/{contactId} |
| Ask Zia | Header ZA icon | In-page panel |
| Profile menu | Header K avatar | In-page dialog |

---

## E) 🗺️ UML Navigation — Starting from Home

```
┌─────────────────────────────────────────────────────────────┐
│                        [HOME SCREEN]                        │
│          /crm/org60043078423/tab/Home/begin                 │
└──────────────────────────┬──────────────────────────────────┘
                           │
          ┌────────────────┼────────────────────┐
          │                │                    │
    [HEADER NAV]    [SIDEBAR NAV]        [WIDGET ACTIONS]
          │                │                    │
    ┌─────┴──────┐  ┌──────┴───────┐  ┌───────┴──────────┐
    │            │  │              │  │                   │
  Search     +Create  Primary Nav  Modules   KPI Widgets  Tables
    │            │       │            │           │          │
    │            │  ├─ Reports   ├─ Leads    ├─ Open Deals(6)
    │            │  ├─ Analytics ├─ Workqueue├─ Untouched(0)
    │            │  ├─ My Requests├─ Contacts├─ Calls(0)
    │            │  └─ Home(now) ├─ Accounts └─ Leads(2076)
    │            │               ├─ Deals
    │        ┌─────┴───┐         ├─ Projects Portfolio
    │     New Record   │         ├─ Employee Portfolio
    │    (any module)  │         ├─ Customer Feedback
    │                  │         ├─ Tasks
    │            Header Icons    ├─ Meetings
    │            ├─ Ask Zia ──────► [Zia Panel]
    │            ├─ Signals ──────► [Notification Panel]
    │            ├─ Calendar ─────► [Calendar Day View]
    │            ├─ Marketplace ──► [Extensions Page]
    │            ├─ Setup ────────► [Settings Page]
    │            ├─ Profile ──────► [Profile Dialog]
    │            └─ AppSwitcher ──► [Zoho App Grid]
    │
    └─ [WIDGET DRILL-DOWN]
       ├─ Task Subject ─────► /tab/Tasks/{id}
       ├─ Task Related To ──► /tab/Leads/{id}
       ├─ Meeting Title ────► /tab/Events/{id}
       ├─ Meeting RelatedTo► /tab/Accounts/{id}
       ├─ Meeting Contact ──► /tab/Contacts/{id}
       └─ Pipeline Funnel ──► [Filtered Deal View]

Dashboard Controls:
├─ Refresh All ──────► [Reload all widgets]
├─ Dashboard Switch ─► Classic View / Manager's Home
├─ Add Component ────► [Component Selector Modal]
├─ Reorder ──────────► [Drag-reorder mode]
├─ Full Screen ──────► [Full screen home]
└─ Customize Home ───► /crm/org60043078423/settings/home-customization
```
