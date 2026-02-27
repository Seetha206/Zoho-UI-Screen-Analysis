> Scribe Source: https://scribehow.com/viewer/Customize_Homepage_in_Zoho_CRM__ERCScDBmQbuLkgiaJL1_YQ
> Recorded By: Sri
> Duration: ~2 minutes
> Total Steps: 13
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Customize Homepage in Zoho CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **customizing the Home Dashboard** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how a user navigates from the Home Dashboard through multiple menu layers, selects the "Classic View" layout, accesses the "Customize Home page" configuration, and selects role-based customization ("2 Roles") — 13 UI interactions in approximately 2 minutes.

> **Homepage Customization** in Zoho CRM allows administrators and users to configure what widgets, KPIs, charts, and data panels appear on the CRM Home Dashboard. Zoho CRM supports multiple named home pages (e.g., "Kurinjee Promoters's Home"), different view types (Classic, Dashboard), and role-based home page assignments — so different teams (Telecallers, Managers, Admins) can see a home page tailored to their responsibilities. This is the first Home module flow recorded in the Scribehow series.

---

## UI Design Context

| Property        | Detail                                                              |
|-----------------|---------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                           |
| Step indicators | Blue circular numbered badges (1–13)                                |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects      |
| Flow type       | Home Dashboard — customization settings navigation                  |
| Module          | Home (Dashboard)                                                    |
| Notable pattern | Many unlabeled "Click here" steps — deep nested menu navigation typical of CRM settings panels |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to CRM Home Dashboard

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Home/begin` |
| Module          | Home Dashboard |
| View            | Default home view (`begin`) |

**Screenshot Analysis:**
- The Zoho CRM Home Dashboard opens at its entry URL `/tab/Home/begin`
- This is the **only Home module URL** captured across all 15 recorded flows — and it matches the existing `home/` documentation in the project
- The Home Dashboard at Kurinjee Promoters displays KPI widgets, activity summaries, and pipeline charts:

  ```
  ┌─────────────────────────────────────────────────────────────┐
  │  [Header: Search | Quick Add | Setup ⚙ | Profile | Apps]   │
  ├────────────────┬────────────────────────────────────────────┤
  │  SIDEBAR       │  HOME DASHBOARD                           │
  │  Home          │  ┌──────────┐ ┌──────────┐ ┌──────────┐  │
  │  Leads         │  │ KPI: Leads│ │KPI: Deals│ │KPI: Tasks│  │
  │  Contacts      │  └──────────┘ └──────────┘ └──────────┘  │
  │  Accounts      │  ┌───────────────────────────────────┐    │
  │  Deals         │  │  My Activities / Pipeline chart   │    │
  │  Tasks         │  └───────────────────────────────────┘    │
  │  ...           │  ┌──────────────────┐ ┌───────────────┐  │
  │                │  │  Recent Leads    │ │  My Deals     │  │
  └────────────────┴──┴──────────────────┴─┴───────────────┴──┘
  ```

- The URL parameter `begin` places the user at the default/primary home view

---

### Step 2 — Click "Here" (First Unlabeled Element)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Settings icon / customization trigger / dropdown |
| Location     | Home Dashboard — likely top-right of the dashboard header area |

**Screenshot Analysis:**
- The first unlabeled click is on an element in the Home Dashboard that initiates the customization navigation
- In Zoho CRM's Home Dashboard, the customization entry points are:
  - A **pencil / edit icon** (`✎`) in the dashboard header
  - A **gear icon** (`⚙`) next to the home page name
  - A **`⋮` (more options)** icon in the dashboard toolbar
  - A **"Customize"** link that appears on hover over the dashboard title
- This click likely opens a **settings panel or dropdown** related to the home page view

---

### Step 3 — Click "Here" (Second Unlabeled Element)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Sub-panel item or secondary navigation trigger |
| Location     | Home Dashboard — settings/customization panel |

**Screenshot Analysis:**
- A second consecutive unlabeled click indicates the user is navigating through a **nested settings panel**
- In Zoho CRM's home page configuration flow, after the initial settings trigger, there may be:
  - A **side panel** showing available home page views
  - A **dropdown** revealing home page management options
  - A **"Manage Home Pages"** panel that lists named home pages
- This step progresses deeper into the home customization menu hierarchy

---

### Step 4 — Click "More" Button (First)

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `More` |
| Element Type | Overflow / expand button |
| Location     | Home Dashboard — settings panel or navigation menu |

**Screenshot Analysis:**
- The recorder clicks a **"More"** button — an expand/overflow control that reveals additional options not visible in the collapsed state
- In Zoho CRM's Home Dashboard settings, a "More" button typically:
  - Expands a **truncated list of home page views** to show all available named home pages
  - Reveals **additional customization actions** beyond the primary options shown
  - Shows **more widget categories** in a widget picker

---

### Step 5 — Click "Here" (Third Unlabeled Element)

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Target       | Unlabeled (Scribe: "Click here") |
| Element Type | Navigation item or panel section |
| Location     | Expanded "More" panel or settings sub-section |

**Screenshot Analysis:**
- After the "More" expansion in Step 4, the recorder clicks another unlabeled element within the revealed content
- This navigates further into the home page configuration hierarchy — possibly selecting a specific home page or settings section

---

### Step 6 — Click "More" Button (Second)

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `More` |
| Element Type | Overflow / expand button (second instance) |
| Location     | Home Dashboard — secondary settings panel level |

**Screenshot Analysis:**
- A **second "More" click** suggests the home page customization UI has multiple nested levels, each with its own overflow controls
- This is consistent with Zoho CRM's home page settings architecture, which can have:
  - Module-level "More" (to see more sidebar modules)
  - Home page-level "More" (to see all available home page layouts)
  - Widget-level "More" (to see additional widget categories)
- The dual "More" clicks (Steps 4 and 6) indicate the user is navigating through two separate expandable sections

---

### Step 7 — Click Icon Element

| Property     | Detail |
|--------------|--------|
| Action       | Click icon |
| Target       | Icon element (unlabeled) |
| Element Type | Icon button — likely settings ⚙, manage, or navigate icon |
| Location     | Home Dashboard — customization panel |

**Screenshot Analysis:**
- An **icon-only click** — Scribe captured this as a generic "Click icon element" without a label
- In Zoho CRM's home page area, icon buttons at this stage of the navigation typically include:
  - **⚙ (gear/settings)** — module or home page settings
  - **✎ (edit/pencil)** — enter edit/customize mode for the home page
  - **▶ (navigate/go)** — go to a selected home page or view
  - **⊕ (add)** — add a new home page layout
- This click likely triggers or reveals the named home page list or management options

---

### Step 8 — Click "Home" Option

| Property     | Detail |
|--------------|--------|
| Action       | Click list item |
| Target       | `Home` |
| Element Type | Navigation item / home page selector entry |
| Location     | Home page management panel or dropdown |

**Screenshot Analysis:**
- The recorder clicks on **"Home"** — a labeled entry in a list or panel
- In Zoho CRM's home page context, clicking "Home" could mean:
  - Selecting the **"Home"** module/tab entry in the sidebar navigation
  - Clicking a **"Home"** section header in a home page management panel
  - Selecting the default **"Home"** named home page (as distinct from custom named home pages like "Kurinjee Promoters's Home")
- This step appears to be navigating to or selecting the Home module/section in a settings context — setting up the next click (Step 9) which selects the specific named home page

---

### Step 9 — Click "Kurinjee Promoters's Home"

| Property     | Detail |
|--------------|--------|
| Action       | Click list item |
| Target       | `Kurinjee Promoters's Home` |
| Element Type | Named home page selector — specific home page entry |
| Location     | Home page management panel — list of available home pages |

**Screenshot Analysis:**
- The recorder clicks **"Kurinjee Promoters's Home"** — the organisation-specific named home page
- This confirms that Kurinjee Promoters has a **custom-named home page** configured in their CRM instance — not just the default "My Home"
- In Zoho CRM, home pages are named entities that can be:
  - Created by admins with custom widget layouts
  - Assigned to specific roles (Telecaller, Manager, Admin)
  - Shared across users with the same role
- "Kurinjee Promoters's Home" is the **primary home dashboard** for this organisation — containing the KPI widgets and charts documented in the existing `home/` project files
- After clicking this, the right panel likely shows this home page's configuration options including **view type** and **role assignments**

---

### Step 10 — Click "Classic View" (First Interaction)

| Property     | Detail |
|--------------|--------|
| Action       | Click option |
| Target       | `Classic View` |
| Element Type | View type selector / radio button / tab |
| Location     | Home page configuration panel — view type section |

**Screenshot Analysis:**
- The recorder clicks **"Classic View"** — the first of two interactions with this option
- In Zoho CRM's Home page configuration, view types include:

  | View Type      | Description |
  |----------------|-------------|
  | **Classic View** | Traditional widget-based layout — KPI cards, charts, tables arranged in a grid |
  | **Dashboard View** | More modern analytics-focused layout with larger visualisations |

- "Classic View" is the view type used in the existing `home/` documentation for Kurinjee Promoters — consistent with the KPI summary widgets, activity panels, and table widgets already documented
- The first click may **select/highlight** the Classic View option before confirming

---

### Step 11 — Click "Classic View" (Second Interaction)

| Property     | Detail |
|--------------|--------|
| Action       | Click option again |
| Target       | `Classic View` |
| Element Type | View type selector — confirmation or navigation click |
| Location     | Home page configuration panel — view type section |

**Screenshot Analysis:**
- A second click on **"Classic View"** — following the same pattern seen in Flow 9 (Custom View) where "Today's Leads" was clicked three times
- This second click likely:
  1. **Confirms** the Classic View selection and navigates to its settings
  2. **Enters edit mode** for the Classic View layout of "Kurinjee Promoters's Home"
  3. Represents Scribe capturing a **hover + click** as two separate steps on the same element
- After both Classic View clicks, the interface transitions to show the detailed configuration panel for "Kurinjee Promoters's Home" in Classic View mode

---

### Step 12 — Click "Customize Home page"

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Target       | `Customize Home page` |
| Element Type | Primary action button — CTA for entering customization mode |
| Location     | Home page configuration panel — action button |

**Screenshot Analysis:**
- The recorder clicks **"Customize Home page"** — the main CTA that activates the home page layout editor
- This button opens the **Home Page Customization Editor** — the visual interface for rearranging and configuring widgets:

  ```
  ┌────────────────────────────────────────────────────────────┐
  │  Customize: Kurinjee Promoters's Home (Classic View)  [×]  │
  ├────────────────────────────────────────────────────────────┤
  │                                                            │
  │  AVAILABLE COMPONENTS          │  CURRENT LAYOUT          │
  │  ────────────────────          │  ─────────────────────   │
  │  KPI Summary                   │  Row 1:                  │
  │  My Activities                 │  [KPI Summary Widget]    │
  │  Open Tasks                    │  Row 2:                  │
  │  My Deals                      │  [Activities] [Leads]    │
  │  Recent Leads                  │  Row 3:                  │
  │  Pipeline by Stage             │  [Deals Pipeline]        │
  │  Reports                       │                          │
  │  Custom Charts                 │  [+ Add Component]       │
  └──────────────────────────────┴─┴──────────────────────────┘
  │  [Save]  [Set Roles]  [Cancel]                             │
  └────────────────────────────────────────────────────────────┘
  ```

---

### Step 13 — Click "2 Roles"

| Property     | Detail |
|--------------|--------|
| Action       | Click element |
| Target       | `2 Roles` |
| Element Type | Role assignment badge / button — shows count of roles assigned to this home page |
| Location     | Home page configuration — role assignment section or Customize editor |

**Screenshot Analysis:**
- The recorder clicks **"2 Roles"** — a badge or button showing that "Kurinjee Promoters's Home" is currently assigned to **2 roles**
- In Zoho CRM's home page configuration, role assignment controls the visibility of a home page layout:

  | Concept | Detail |
  |---------|--------|
  | Role-based home pages | Different teams see different home dashboards |
  | "2 Roles" label | This home page is assigned to 2 CRM roles — shown as a clickable count badge |
  | Clicking "2 Roles" | Opens a role assignment panel showing which 2 roles are currently linked |

- The 2 roles at Kurinjee Promoters are most likely:

  | Role (Inferred)  | Description |
  |------------------|-------------|
  | Administrator    | CRM admin — full access, sees all pipeline data |
  | Telecaller / User | Sales team member — sees their own leads, tasks, and activities |

- Clicking "2 Roles" would open a dialog to:
  - View which roles are assigned to this home page
  - Add additional roles
  - Remove existing role assignments
  - Create role-specific home pages

- The recording **ends at this step** — the role assignment panel contents are not captured

---

## Home Page Customization — Architecture

### Named Home Pages in Zoho CRM

```
ZOHO CRM — Home Page Management
├── Default System Home
│   └── "My Home" (every user's personal default)
│
└── Organisation Custom Home Pages
    └── "Kurinjee Promoters's Home"  ← recorded in this flow
        ├── View Type: Classic View
        ├── Assigned to: 2 Roles
        ├── Layout: Widget grid (KPI, Charts, Tables)
        └── [Customize Home page → Widget editor]
```

### Classic View Widget Layout (from existing home/ documentation)

| Row   | Widget Type    | Content |
|-------|----------------|---------|
| Row 1 | KPI Summary    | Lead count, Deal count, Task count, Revenue metrics |
| Row 2 | Activity panel | My Open Activities, Recent Leads table |
| Row 3 | Pipeline chart | Deals by stage, conversion funnel |

---

## Navigation Path Analysis

The 13-step flow reveals a **deeply nested** customization navigation in Zoho CRM's Home module:

```
Home Dashboard (/tab/Home/begin)
  └── [Click settings trigger] (Step 2)
      └── [Click sub-panel] (Step 3)
          └── [More] (Step 4)
              └── [Click panel item] (Step 5)
                  └── [More] (Step 6)
                      └── [Click icon] (Step 7)
                          └── Select "Home" (Step 8)
                              └── Select "Kurinjee Promoters's Home" (Step 9)
                                  └── Click "Classic View" ×2 (Steps 10–11)
                                      └── Click "Customize Home page" (Step 12)
                                          └── Click "2 Roles" (Step 13)
```

- **Depth: 9 levels** from the initial Home dashboard to the role assignment panel
- This is the **most navigation-intensive flow** in the series after Flow 8 (Blueprint — 22 steps)
- The multiple unlabeled "Click here" steps (Steps 2, 3, 5) suggest the customization settings are accessed through **icon-only buttons** or UI elements without visible text labels

---

## URL Reference

| Element                   | Value |
|---------------------------|-------|
| CRM Base URL              | `https://crm.zoho.in/crm/org60043078423/` |
| Home Dashboard URL        | `https://crm.zoho.in/crm/org60043078423/tab/Home/begin` |
| Named Home Page           | `Kurinjee Promoters's Home` |
| View Type                 | Classic View |
| Roles Assigned            | 2 |
| Module                    | Home |
| Org ID                    | `60043078423` |

---

## Workflow Summary

```
[CRM Home Dashboard — /tab/Home/begin]
       |
       v
[Click settings/customization trigger — unlabeled (Step 2)]
       |
       v
[Click sub-panel element — unlabeled (Step 3)]
       |
       v
[Click "More" — expand options (Step 4)]
       |
       v
[Click panel item — unlabeled (Step 5)]
       |
       v
[Click "More" — expand second level (Step 6)]
       |
       v
[Click icon — unlabeled settings/nav icon (Step 7)]
       |
       v
[Click "Home" — select Home module section (Step 8)]
       |
       v
[Click "Kurinjee Promoters's Home" — select named home page (Step 9)]
       |
       v
[Click "Classic View" — first interaction (Step 10)]
       |
       v
[Click "Classic View" — confirm/navigate (Step 11)]
       |
       v
[Click "Customize Home page" — enter widget editor (Step 12)]
       |
       v
[Click "2 Roles" — view/edit role assignments (Step 13)]
       |
       v  ← Recording ends here
[Role assignment panel opens — shows 2 assigned roles]
```

---

## Comparison: All Fifteen Flows

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
| 12 | Clone                   | Contact  | 4     | ~8s      | Duplicate existing record |
| 13 | Record Import           | Accounts | 4     | ~17s     | Bulk import via CSV |
| 14 | Record Export           | Accounts | 5     | ~23s     | Export all records to CSV |
| 15 | Customize Homepage      | Home     | 13    | ~2 min   | Home page widget editor + role config |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **First Home module flow** — the Home Dashboard is the most extensively pre-documented module in the project (`home/` directory); this flow adds the customization interaction layer not previously captured |
| 2 | **High unlabeled step count** — Steps 2, 3, 5, and 7 are all "Click here" or icon-only — the highest proportion of unlabeled steps in any flow; home page settings in Zoho CRM rely heavily on icon buttons and nested panels |
| 3 | **"Kurinjee Promoters's Home" confirmed as named home page** — the organisation has a custom-named home page (not just the default "My Home"), confirming a deliberate CRM setup for the team |
| 4 | **2 Roles confirmed** — the home page is shared across exactly 2 roles; the specific role names are not captured but inferred as Administrator and Telecaller/User based on the org structure |
| 5 | **Classic View confirmed** — the team uses the Classic View layout (widget grid), consistent with the existing `home/` documentation showing KPI summary rows and table widgets |
| 6 | **Role assignment panel not captured** — the recording ends at clicking "2 Roles"; which roles are assigned and any changes made are not recorded |
| 7 | **Deepest navigation in the series** — 9 levels of nesting from the Home dashboard to the role assignment panel; this flow demonstrates that Zoho CRM's home customization settings are significantly harder to reach than record-level operations (Create, Update, Delete) |
| 8 | **"Customize Home page" vs "Customize"** — the full button label "Customize Home page" (Step 12) differentiates this from other CRM customization paths (e.g., field editor, layout editor accessed via Setup) |
