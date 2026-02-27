# Zoho CRM — Contacts Module: Full Reverse Engineering Documentation

## 1. Module Overview

**Module Name:** Contacts
**URL Base:** `/crm/org60043078423/tab/Contacts`
**Total Records Observed:** 26
**Primary Purpose:** Store individual customer/person records. Contacts can be created manually or converted from Leads. Each contact links to an Account and can be associated with Deals, Tasks, Meetings, Emails, and Workflows.
**Layout ID:** `955332000000425339`
**Account ID:** `955332000000406001`
**Subscription Status:** 1 user license (Limit Reached)

---

## 2. Screen-by-Screen Breakdown

### 2.1 Contacts List View

**URL:** `/crm/org60043078423/tab/Contacts/custom-view/955332000000441440/list?page=1`

#### Layout Structure

The list view is a tri-zone layout:

- **Left sidebar (~240px):** Filter panel ("Filter Contacts by") with search box, System Defined Filters, Website Activity filters, Filter By Fields, and Filter By Related Modules.
- **Top bar:** Custom view tabs (My Contacts + "..."), followed by a toolbar row (Filter, Sort, view switchers, Create Contact, Actions "...").
- **Main grid:** Column-based record rows with checkboxes, activity date badges, and row-level actions.

#### Custom View Tabs

- My Contacts (active, custom_view_id: `955332000000441440`)
- "..." dropdown exposes: New Custom View, Manage Custom View, Show custom views as Dropdown.

#### View Switchers (toolbar icons, left to right)

List View (active), Kanban / Split View, Table / Grid View, Canvas / Clock View, Custom List View, Tile View, and a dropdown chevron for more views.

#### Columns Visible

Checkbox (select), Row options (hover), Activity date badge (red — last activity), Contact Name (with "All" filter chip and sort), Account Name (sortable), Email (sortable, clickable mailto). A column-settings icon appears at the far right of the header row.

#### Row Indicators

- Red date badge: last activity date (e.g., "Dec 11, 2025", "Nov 4, 2025").
- No badge: no recent activity recorded.

#### Filter Panel

Opens as a left sidebar. Sections include:

- **System Defined Filters:** Touched Records, Untouched Records, Record Action, Related Records Action, Locked, Latest Email Status, Activities, Cadences.
- **Website Activity:** Average Time Spent (Minutes), Days Visited, First Page Visited, First Visit, Most Recent Visit, Number Of Chats, Referrer, Visitor Score.
- **Filter By Fields:** 70+ fields including Account Name, Contact Name, Email, Mobile, Lead Source, Date of Birth, City, Country, IP Address, GA/UTM tracking fields, and more.
- **Filter By Related Modules:** Calls, Contacts (Reporting Contacts), Deal Contact Role, Deals, Emails, Invitees (Invited Meetings), Leads (Connected), Leads (Converted), Meetings, Notes, Tasks.

#### Toolbar Actions

- **Filter** button — opens/closes left filter panel.
- **Sort** button — opens sort criteria selector.
- **View switcher icons** — toggle between list, kanban, table, canvas, custom list, tile views.
- **Refresh Custom View** — reloads current list view.
- **Create Contact** — blue primary split button (main action + ▼ dropdown for secondary options).
- **Actions (...)** — overflow menu with: Import Contacts, Mass Delete, Mass Update, Manage Tags, Drafts, Mass Email, Autoresponders, Approve Contacts, Deduplicate Contacts, Create Client Script, Export Contacts, Zoho Sheet View, Print View.

#### Records Table

Displays 10 records per page (26 total, 3 pages). Contacts visible on page 1:

| Row | Contact Name | Last Activity | Account | Email |
|---|---|---|---|---|
| 1 | Prasanth | Dec 11, 2025 | — | — |
| 2 | Amsa | Nov 4, 2025 | — | — |
| 3 | sakthi kumar | Nov 6, 2025 | — | — |
| 4 | Baskar | Sep 11, 2025 | — | — |
| 5 | wasil | Oct 26, 2025 | — | — |
| 6 | Hemamurugan | Sep 25, 2025 | mul m | mubarak798@gmail.com |
| 7 | Krishnan | — | — | — |
| 8 | Bala | Sep 4, 2025 | — | — |
| 9 | Tsk. kaarthick | Aug 21, 2025 | — | — |
| 10 | Srinivashaperumal | — | — | — |

Each row supports: checkbox (multi-select), hover ellipsis (more options), click Contact Name (navigate to detail view), click Email (mailto link).

#### Pagination

- Total: 26 records | Per page: 10 | Pages: 3
- Previous / Next buttons present.

---

### 2.2 Contact Detail View

**URL Pattern:** `/crm/org60043078423/tab/Contacts/{record_id}`

Not directly scanned in list view, but accessible by clicking any Contact Name. Tabs available on the detail view:

- Overview
- Related Deals
- Activities
- Email History
- Workflow

---

### 2.3 Create Contact Form

**URL:** `/crm/org60043078423/tab/Contacts/create?layoutId=955332000000425339&redirect=false`

See `contacts_creation/` folder for full form scan and field-level documentation.

---

## 3. Header (Global — All Contacts Pages)

- **Page Title:** Contacts (h1)
- **Search Bar:** "Search records" — center, full-width style. Shortcut: `Ctrl + /`. Supports app-scoped search (#mail, #cliq), person search (@john), fine-grained filters.
- **Quick Create (+):** Opens quick-create dialog modal (does not navigate away).
- **Ask Zia:** AI assistant icon.
- **Signals:** Notification bell.
- **Calendar:** `/crm/org60043078423/calendar?date=26-02-2026&viewType=day`
- **Marketplace:** `/crm/org60043078423/settings/extensions/all`
- **Setup:** `/crm/org60043078423/settings/index`
- **Profile (K):** Red circle avatar — org: Kurinjee Promoters, status: Available.
- **App Grid (Waffle):** Cross-app navigation.
- **Hide Menu toggle:** Collapses/expands left sidebar.

---

## 4. Sidebar Navigation

| # | Label | URL | Type |
|---|---|---|---|
| — | Home | /tab/Home/begin | Primary Nav |
| — | Reports | /tab/Reports | Primary Nav |
| — | Analytics | /tab/Dashboards | Primary Nav |
| — | My Requests | /tab/Requesters | Primary Nav |
| — | CRM Teamspace | (dropdown) | Workspace header |
| 1 | Leads | /tab/Leads | Module (has more actions) |
| 2 | Workqueue ✨ | /tab/Workqueue | Module (AI badge) |
| 3 | Contacts | /tab/Contacts | Module — **active** |
| 4 | Accounts | /tab/Accounts | Module (has more actions) |
| 5 | Deals | /tab/Potentials | Module (has more actions) |
| 6 | Projects Portfolio | /tab/CustomModule3 | Custom Module |
| 7 | Employee Portfolio | /tab/CustomModule5 | Custom Module |
| 8 | Customer Feedback | /tab/CustomModule7 | Custom Module |
| 9 | Tasks | /tab/Tasks | Module (has more actions) |
| 10 | Meetings | /tab/Events | Module (has more actions) |
| 11 | Calls | /tab/Calls | Module (has more actions) |
| 12 | Prospecting Leads | /tab/CustomModule1 | Custom Module |
| 13 | Logs | /tab/CustomModule4 | Custom Module |
| 14 | Scheduler | /tab/CustomModule6 | Custom Module |

Sidebar search input: placeholder "Search", scope: in-CRM module search.

CRM Teamspace dropdown options: New Teamspace, Create Folder, Associate Modules, Manage CRM Teamspace, View All Teamspace.

---

## 5. Contacts Module — Data & Associations

### Data Creation Methods
- Manual: "Create Contact" button → form
- Lead conversion (Lead Conversion flow)
- **Save and New** (Scribe confirmed) — saves current record + immediately opens fresh blank form for batch entry
- **Clone** (Scribe confirmed) — duplicate existing record; Contact detail view → `⋮ More` → Clone

### Record Creation — Save Actions (Scribe Confirmed)

| Button | Behavior |
|---|---|
| `Save` | Save record, navigate to detail view |
| `Save and New` | Save record, open fresh blank form (batch entry mode) |
| `Cancel` | Discard form, return to list view |

### Custom Fields in Create Form (Scribe Confirmed)

| Field | Type | Notes |
|---|---|---|
| Estimated Budget ₹ | Currency | Visible in form section header "Title / Last Name / Estimated Budget ₹ / Lead Source..." |

### Key Associations
- Assign to Account (Account Name field — lookup)
- Track communications: Calls, Emails, Meetings
- Add Tasks and Events
- Link to Deals
- Connected To: Leads (lookup field in create form)

### Known Real Contact Records

| Name | Context |
|---|---|
| Prasanth | Real client — used in Clone flow (Scribe); also linked to Deal "Prasanth" (₹25,00,000 Closed Won) |

### Visible Data Points in List View
- Contact Name (clickable → detail view)
- Account Name
- Email (clickable mailto)
- Last Activity Date (red date badge)
- Record ID (embedded in href URL)

### Sample Record IDs (Page 1)
| Contact Name | Record ID |
|---|---|
| Prasanth | 955332000004403606 |
| Amsa | 955332000003267006 |
| sakthi kumar | 955332000003013075 |
| Baskar | 955332000002929038 |
| wasil | 955332000002819016 |
| Hemamurugan | 955332000001978012 |
| Krishnan | 955332000001907012 |
| Bala | 955332000001254034 |
| Tsk. kaarthick | 955332000001149007 |
| Srinivashaperumal | 955332000001100136 |

---

## 6. Bottom Status Bar (Persistent Widgets)

Always visible across all CRM pages.

| Widget | Type | Notes |
|---|---|---|
| Visitors Online | Live visitor counter | Filter: All Accounts / Kurinjee |
| Feedback on New UI | Feedback trigger | Highlighted purple |
| Announcements | Notification list | — |
| Mail | Inbox shortcut | — |
| Motivator | Sales gamification / leaderboard | — |
| Sticky Notes | Quick note widget | — |
| Zia | AI assistant panel | — |
| Activity Reminders | Reminder list | Count: 0 ("No Activity Reminders found.") |
| Recent Items | Recently viewed records | — |
| Accessibility | Settings panel | — |

Bottom chat bar: Chats | Channels | Contacts | Smart Chat input (`Ctrl+Space`)

---

## 7. Full Interaction Map

### Header
- Search records input (Ctrl+/)
- Quick create (+) modal
- Ask Zia, Signals, Calendar, Marketplace, Setup, Profile, App Grid, Hide Menu

### Sidebar
- Global: Home, Reports, Analytics, My Requests
- CRM Teamspace dropdown
- All 14 module links
- Sidebar search input

### Toolbar
- Filter, Sort, 6 view toggle icons, view chevron
- Refresh Custom View
- Create Contact (primary CTA + ▼ dropdown)
- Actions overflow (...): 13 bulk/utility actions

### Custom View
- My Contacts tab
- More Custom Views (...)
- New Custom View → `/tab/Contacts/custom-views/create`
- Manage Custom View → `/tab/Contacts/custom-views/manage?category=all_custom_views`

### Filter Panel
- Search input within filters
- 8 System Defined Filter toggles
- 8 Website Activity toggles
- 70+ Field-level filter toggles
- 11 Related Module filter toggles

### Table
- Per-row: checkbox, hover more options, click name, click email
- Column header sorts: Contact Name, Account Name, Email
- Column config icon (⇌)
- View Settings button

### Actions Menu (overflow)
| Action | URL |
|---|---|
| Import Contacts | /settings/import?module=Contacts&step=1 |
| Mass Delete | /tab/Contacts/actions/mass-tools?type=mass_delete |
| Mass Update | /tab/Contacts/actions/mass-tools?type=mass_update |
| Manage Tags | /settings/manage-tags?module=Contacts |
| Drafts | /tab/Contacts/actions/draft?module=Contacts |
| Mass Email | /settings/manage-mass-mail?module=Contacts |
| Autoresponders | /settings/auto-responders?module=Contacts |
| Approve Contacts | /tab/Contacts/actions/approvals |
| Deduplicate Contacts | (in-page action) |
| Create Client Script | (in-page action) |
| Export Contacts | (in-page action) |
| Zoho Sheet View | (in-page action) |
| Print View | (in-page action) |

### Pagination
- Previous page, Next page

### Bottom Bar
- 10 widget icons + Chats, Channels, Contacts, Smart Chat input

---

## 8. System Alerts Observed

| Alert | Details |
|---|---|
| Limit Reached | "You Cannot Add More Users" |
| Subscription | "You have activated all of your organisation's user licenses (subscription total: 1)." |
| Upgrade prompt | "Upgrade Now!" button visible |
