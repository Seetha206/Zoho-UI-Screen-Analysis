# Home Dashboard — Overview & Context

## What Is This Screen?

The **Home Dashboard** is the landing screen when users log into Zoho CRM. It serves as a centralized command center, displaying key performance indicators (KPIs), pending activities, and quick-access widgets that give users an at-a-glance view of their sales pipeline and daily tasks.

Unlike other modules that store records (Leads, Contacts, Deals), the Home screen **aggregates and summarizes data** from across the entire CRM to help users prioritize their work.

---

## Why Does This Screen Exist?

Sales professionals need to quickly understand their workload and performance without navigating through multiple modules. The Home Dashboard exists to:

1. **Surface critical metrics immediately** — Open Deals, Untouched Deals, Calls Today, Total Leads
2. **Centralize pending activities** — Shows tasks and meetings that need attention today or soon
3. **Enable quick navigation** — From widgets, users can drill down into filtered lists (e.g., click "My Open Deals" to see only those records)
4. **Support dashboard customization** — Users can add, remove, or reorder components based on their role
5. **Provide pipeline visibility** — Funnel charts show deal progression through stages

Without a Home Dashboard, users would need to manually navigate to each module and apply filters to understand their priorities — wasting time and potentially missing important follow-ups.

---

## Who Uses This Screen?

| Role | Usage |
|---|---|
| **BDM (Business Development Manager)** | Monitors personal pipeline, reviews pending tasks/meetings, tracks call activities |
| **Telecaller** | Checks daily call schedule, reviews assigned leads, tracks follow-up tasks |
| **Manager / Admin** | May view team dashboards (e.g., "Manager's Home") to monitor team performance |
| **All CRM Users** | Landing page on login — first point of interaction with the CRM |

---

## Screen Layout Structure

```
┌─────────────────────────────────────────────────────────────┐
│  HEADER: Logo | Search | Create (+) | Zia | Setup | Profile │
├──────────┬──────────────────────────────────────────────────┤
│ SIDEBAR  │  MAIN CONTENT AREA                               │
│          │  ┌────────────────────────────────────────────┐  │
│ Modules  │  │ Welcome Banner + Dashboard Controls        │  │
│          │  └────────────────────────────────────────────┘  │
│          │  ┌────────────────────────────────────────────┐  │
│          │  │ KPI Summary Widgets (4 columns)            │  │
│          │  │ My Open Deals | Untouched | Calls | Leads  │  │
│          │  └────────────────────────────────────────────┘  │
│          │  ┌──────────────────┐ ┌────────────────────────┐ │
│          │  │ My Open Tasks    │ │ My Meetings            │ │
│          │  │ (10 rows, table) │ │ (3 rows, table)        │ │
│          │  └──────────────────┘ └────────────────────────┘ │
│          │  ┌──────────────────┐ ┌────────────────────────┐ │
│          │  │ Pipeline Deals   │ │ Deals Closing This     │ │
│          │  │ By Stage (funnel)│ │ Month (empty)          │ │
│          │  └──────────────────┘ └────────────────────────┘ │
├──────────┴──────────────────────────────────────────────────┤
│ FOOTER: Chats | Channels | Smart Chat | Toolbar Icons       │
└─────────────────────────────────────────────────────────────┘
```

---

## Widget Breakdown

### Row 1 — KPI Summary Cards

| Widget | Purpose | Observed Value |
|---|---|---|
| My Open Deals | Count of deals not yet closed | 6 |
| My Untouched Deals | Deals with no activity yet | 0 |
| My Calls Today | Scheduled/completed calls | 0 |
| My Leads | Total leads owned | 2,076 |

### Row 2 — Activity Tables

| Widget | Columns | Rows Visible | Purpose |
|---|---|---|---|
| My Open Tasks | Subject, Due Date, Status, Priority, Related To, Contact Name | 10 | Track pending tasks |
| My Meetings | Title, From, To, Related To, Contact Name | 3 | View upcoming/past meetings |

### Row 3 — Charts & Pipeline

| Widget | Type | Content | Purpose |
|---|---|---|---|
| My Pipeline Deals By Stage | Funnel Chart | Visit Pending: 5, Visit Completed: 1 | Visualize deal progression |
| My Deals Closing This Month | Table | "No Deals found." | Track month-end closures |

---

## Key Interactions

### Header Actions
| Element | Action |
|---|---|
| Search Records | Global search across all modules |
| Create (+) | Quick-create modal for any record type |
| Ask Zia | AI assistant for CRM queries |
| Calendar | Navigate to day/week/month calendar |
| Setup | Access CRM settings and customization |

### Dashboard Controls
| Control | Options |
|---|---|
| Refresh All | Reload all widget data |
| Dashboard Switcher | Classic View / Kurinjee Promoters's Home / Manager's Home |
| More Options | Add Component / Reorder / View in Full Screen |

### Widget Drill-Down
| Widget | Clickable Elements | Destination |
|---|---|---|
| My Open Tasks | Task Subject | Task detail view |
| My Open Tasks | Related To | Lead/Contact/Deal detail |
| My Meetings | Meeting Title | Event detail view |
| My Meetings | Related To | Account detail view |
| My Meetings | Contact Name | Contact detail view |
| Pipeline Chart | Funnel Segments | Filtered deal list by stage |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Active Dashboard | Kurinjee Promoters's Home |
| Alternative Dashboards | Classic View, Manager's Home (New!) |
| Total Leads (KPI) | 2,076 |
| Open Deals (KPI) | 6 |
| Pipeline Stages Tracked | Visit Pending, Visit Completed |

The Home Dashboard reflects a **low-activity sales pipeline** — zero calls today, zero untouched deals, and no deals closing this month. This suggests either:
- A slow sales period
- Heavy focus on lead nurturing over closing
- Seasonal variation in real estate activity

The funnel chart showing 5 deals in "Visit Pending" and only 1 in "Visit Completed" indicates the team's primary bottleneck is **converting scheduled visits into completed visits** — a key area for process improvement.

---

## Navigation Destinations from Home

| Destination | Trigger | URL Pattern |
|---|---|---|
| Leads Module | Sidebar: Leads | `/tab/Leads` |
| Contacts Module | Sidebar: Contacts | `/tab/Contacts` |
| Deals Module | Sidebar: Deals | `/tab/Potentials` |
| Tasks Module | Sidebar: Tasks | `/tab/Tasks` |
| Meetings Module | Sidebar: Meetings | `/tab/Events` |
| Reports | Sidebar: Reports | `/tab/Reports` |
| Analytics | Sidebar: Analytics | `/tab/Dashboards` |
| Calendar | Header: Calendar Icon | `/calendar?date={date}&viewType={view}` |
| Settings | Header: Gear Icon | `/settings/index` |
| Task Detail | Click Task Subject | `/tab/Tasks/{id}` |
| Meeting Detail | Click Meeting Title | `/tab/Events/{id}` |
| Lead Detail | Click Related To (in tasks) | `/tab/Leads/{id}` |
| Account Detail | Click Related To (in meetings) | `/tab/Accounts/{id}` |
| Contact Detail | Click Contact Name | `/tab/Contacts/{id}` |

---

## Module URL Reference

| Screen | URL |
|---|---|
| Home Dashboard (default) | `/crm/org60043078423/tab/Home/begin` |
| Home Customization | `/crm/org60043078423/settings/home-customization` |
| Classic View Dashboard | `/crm/org60043078423/tab/Home/classic` |

---

## Related Documentation

| File | Description |
|---|---|
| `home_screen.yml` | Machine-readable layout structure |
| `zoho_crm_home_dom_scan.md` | Full DOM analysis with component hierarchy |
| `home_overview.md` | This file — business context and usage |
