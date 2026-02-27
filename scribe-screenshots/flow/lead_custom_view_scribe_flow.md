> Scribe Source: https://scribehow.com/viewer/Lead__Custom_View__VAC1y59USAyVSDfMyKlRFA
> Recorded By: Sri Gnanathesigan
> Duration: ~36 seconds
> Total Steps: 5
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Lead — Custom View — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **navigating to a Custom View ("Today's Leads") on the Leads List View** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). It demonstrates how to access the custom view selector and switch the active list view to **"Today's Leads"** — 5 UI interactions in approximately 36 seconds.

> A Custom View in Zoho CRM is a saved, named combination of filter criteria, visible columns, and sort order — allowing users to switch between pre-configured filtered list perspectives with a single click. "Today's Leads" is a time-based custom view that shows only leads created on the current day.

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–5)                               |
| Screenshot style | Max-height 600px, rounded card containers with shadow effects    |
| Flow type       | List View navigation — switching between saved custom views       |
| Notable pattern | Steps 3, 4, 5 all reference "Today's Leads" — three-stage interaction |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View (with Sort Parameters)

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&sort_order=unsort&sort_by=955332000000427944` |
| View Type       | Custom List View (ID: `955332000000441406`) |
| Pagination      | `page=1` |
| Sort State      | `sort_order=unsort` — no active sort |
| Sort Field Ref  | `sort_by=955332000000427944` — previously used sort field, now cleared |
| Module          | Leads |

**Screenshot Analysis:**
- The Zoho CRM Leads module opens in the standard custom list view (`955332000000441406`)
- URL contains sort state parameters — same pattern as Flow 6 (Sort)
- The `sort_by` field ID here is **`955332000000427944`** — distinct from Flow 6's `955332000000427928`:

  | Flow | sort_by Field ID       | Notes |
  |------|------------------------|-------|
  | 6 (Sort) | `955332000000427928` | Previously sorted field in Sort flow |
  | 9 (Custom View) | `955332000000427944` | Different field ID — different sort reference |

- Both IDs represent internal Zoho CRM field identifiers for Lead module fields — exact field names not confirmed from extraction
- The `sort_order=unsort` state means the list is currently displaying in its default order with no active sort
- The **Custom View selector** is visible in the list view — typically displayed as a dropdown or panel at the top-left of the list showing the currently active view name

---

### Step 2 — Click to Open Custom View Selector ("Click here")

| Property     | Detail |
|--------------|--------|
| Action       | Click UI element |
| Instruction  | `Click here` (no label — screenshot-only in Scribe) |
| Element Type | Custom View selector / dropdown / sidebar toggle |
| Location     | Top-left of the Leads list view — view name area |

**Screenshot Analysis:**
- The recorder clicks an **unlabeled element** to access the custom view selector
- In Zoho CRM's list view, the custom view selector is accessible via:
  - A **dropdown arrow** next to the currently active view name (e.g. clicking the `▾` next to "All Leads")
  - A **view panel / sidebar** that slides in showing all saved custom views
  - A **"Views"** button or icon in the list toolbar
- The Zoho CRM Custom View selector panel structure:

  ```
  ┌──────────────────────────────────────┐
  │  Views                               │
  ├──────────────────────────────────────┤
  │  System Views                        │
  │  • All Leads                         │
  │  • My Leads                          │
  │  • Recently Created Leads            │
  │  • Converted Leads                   │
  │                                      │
  │  Custom Views                        │
  │  • Today's Leads        ← target     │
  │  • [Custom View Name]                │
  │  • [Custom View Name]                │
  │  • 955332000000441406 view           │
  └──────────────────────────────────────┘
  ```

- After clicking, the view selector panel opens showing all available system views and custom views
- The current active view (`955332000000441406`) is highlighted

---

### Step 3 — Click "Today's Leads" — First Interaction

| Property     | Detail |
|--------------|--------|
| Action       | Click view name |
| Target       | `Today's Leads` |
| Element Type | Custom view list item |
| Location     | Inside the custom view selector panel |

**Screenshot Analysis:**
- The custom view selector panel is open, showing available views
- The recorder clicks on **"Today's Leads"** for the first time
- This first click is likely **selecting/highlighting** the "Today's Leads" view in the list — showing a preview or hover state
- In Zoho CRM's view selector, the first click on a view name may:
  - **Highlight** it in the list (selection state)
  - Show a **preview** of the view's criteria
  - Begin a **navigation** to that view (if single-click navigate is configured)
- "Today's Leads" is a **time-based custom view** — its filter criteria would be:

  | Filter Criterion  | Operator    | Value     |
  |-------------------|-------------|-----------|
  | Created Time      | `is`        | `Today`   |

  or alternatively:

  | Filter Criterion  | Operator         | Value           |
  |-------------------|------------------|-----------------|
  | Created Time      | `between`        | Today 00:00 – 23:59 |

- This view is critical for Telecallers — it shows all leads that arrived **today**, enabling immediate follow-up on fresh inquiries

---

### Step 4 — Click "Today's Leads" — Second Interaction

| Property     | Detail |
|--------------|--------|
| Action       | Click view name again |
| Target       | `Today's Leads` |
| Element Type | Confirmation click or view navigation |

**Screenshot Analysis:**
- The recorder clicks **"Today's Leads"** a second time
- This second click is the **navigation/confirmation** action — actually switching the active view
- In Zoho CRM, some view selector implementations require:
  - **First click** — selects/highlights the view
  - **Second click** — confirms and navigates to the view
- Alternatively, the Scribe tool may have captured a **hover state + click** as two separate steps on the same element
- After this click, the list view begins transitioning to the "Today's Leads" view — the URL updates to reflect the new custom view ID

---

### Step 5 — Click "Today's Leads" — Third Interaction / View Active

| Property     | Detail |
|--------------|--------|
| Action       | Click or interact with "Today's Leads" |
| Target       | `Today's Leads` |
| Element Type | Active view confirmation or post-navigation interaction |

**Screenshot Analysis:**
- The third "Click Today's Leads" step likely shows one of these states:
  1. **View now active** — the leads list has switched to showing only today's leads; the recorder clicks the view name in the now-updated breadcrumb/header to confirm it's active
  2. **View name in header** — after navigation, the active view name "Today's Leads" appears at the top of the list; clicking it again opens the view selector to confirm the switch
  3. **Scribe duplicate capture** — the Scribe tool captured the same click across multiple screenshots at slightly different UI states (hover, press, release)
- After all three "Today's Leads" interactions resolve:
  - The **URL changes** from `custom-view/955332000000441406/...` to `custom-view/{today's_leads_view_id}/...`
  - The **list header** shows "Today's Leads" as the active view name
  - The **records list** refreshes to show only leads created today
  - The **record count** updates — likely a much smaller number than the full 2,077 leads (only today's new leads)
  - The **sort and filter state** resets to the custom view's saved defaults

---

## Custom View Architecture — Zoho CRM Leads

### System Views (built-in, non-editable)

| View Name                | Filter Criteria |
|--------------------------|-----------------|
| All Leads                | No filter — all records |
| My Leads                 | Lead Owner = Current User |
| Recently Created Leads   | Created Time — last 7 days |
| Recently Modified Leads  | Modified Time — last 7 days |
| Converted Leads          | Converted = True |
| Junk Leads               | Lead Quality = Junk |
| Unread Leads             | Read = False |

### Custom Views — Kurinjee Promoters (confirmed)

| View Name        | ID                       | Filter Criteria (inferred) |
|------------------|--------------------------|----------------------------|
| (unnamed default) | `955332000000441406`    | Used across all 9 flows — likely "All Leads" or a Telecaller-specific view |
| Today's Leads    | (ID not captured)        | Created Time = Today |

---

## "Today's Leads" — Business Context

For a real estate company processing 2,077+ leads with an active Telecaller team, "Today's Leads" is one of the most operationally important views:

| Use Case | Detail |
|----------|--------|
| **Morning check-in** | Telecallers start the day by viewing fresh leads that arrived overnight or that morning |
| **Priority calling** | Today's leads are the warmest — contacted within hours of inquiry submission |
| **SLA compliance** | Many real estate orgs target a first-contact SLA of within 1–4 hours of lead creation |
| **Volume tracking** | Managers use "Today's Leads" count to monitor daily lead inflow from campaigns |
| **BluePrint entry** | New leads enter at the first Blueprint stage — "Today's Leads" shows all leads pending their first Enquiry transition |

---

## URL Parameter Analysis — Sort Field IDs Across Flows

Three flows have revealed `sort_by` field IDs in their URLs:

| Flow | sort_by Field ID       | sort_order  | Field Name (inferred) |
|------|------------------------|-------------|------------------------|
| 6 (Sort) | `955332000000427928` | `unsort`    | Unknown — previous sort field |
| 9 (Custom View) | `955332000000427944` | `unsort` | Unknown — different field |

- The difference between IDs (`427928` vs `427944`) suggests these are **adjacent fields** in the CRM's field registry — possibly created in sequence during module customisation
- Both are in `unsort` state at recording time — these are remembered sort preferences that have been cleared

---

## Full URL Reference

| Element              | Value |
|----------------------|-------|
| CRM Base URL         | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL       | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&sort_order=unsort&sort_by=955332000000427944` |
| Custom View ID (start) | `955332000000441406` |
| Custom View (target) | `Today's Leads` (ID not captured) |
| sort_order param     | `unsort` |
| sort_by field ID     | `955332000000427944` |
| Org ID               | `60043078423` |

---

## Workflow Summary

```
[Leads List — custom view 955332000000441406, unsorted]
       |
       v
[Click view selector element (Step 2)]
       |
       v
[Custom view selector panel opens]
  Shows: System Views + Custom Views list
       |
       v
[Click "Today's Leads" — Step 3 (highlight/select)]
       |
       v
[Click "Today's Leads" — Step 4 (navigate/confirm)]
       |
       v
[Click "Today's Leads" — Step 5 (active view confirmed)]
       |
       v
[List refreshes — URL updates to Today's Leads view ID]
[Records: Only leads created today]
[Header: "Today's Leads" shown as active view]
```

---

## Comparison: All Nine Lead Flows

| # | Flow             | Steps | Duration | Scope  | Key Operation |
|---|------------------|-------|----------|--------|---------------|
| 1 | Create           | 13    | ~47s     | Single | Form fill + save |
| 2 | Update           | 10    | ~37s     | Single | Field edits + save |
| 3 | Delete           | 5     | ~22s     | Single | Two-click delete |
| 4 | Related List     | 5     | ~25s     | Single | Navigate to Scheduler |
| 5 | Filter           | 8     | ~24s     | List   | Criteria-based filter |
| 6 | Sort             | 8     | ~34s     | List   | Sort by Country |
| 7 | Manage Columns   | 9     | ~44s     | List   | Column + page limit |
| 8 | Blueprint        | 22    | ~2 min   | Single | BANT qualification |
| 9 | Custom View      | 5     | ~36s     | List   | Switch to Today's Leads |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Steps 3–5 all labeled "Today's Leads"** — three separate clicks on the same label; likely hover + select + navigate captured as distinct Scribe steps; or a two-panel selector requiring multiple interactions |
| 2 | **Step 2 element unlabeled** — the view selector entry point ("Click here") is not identified; inferred as the view dropdown/panel toggle from standard Zoho CRM list view UI |
| 3 | **"Today's Leads" view ID not captured** — the URL after switching views was not extracted; the target view's internal ID is unknown |
| 4 | **Today's Leads filter criteria not confirmed** — inferred as `Created Time = Today`; Zoho CRM supports dynamic date filters that auto-update daily |
| 5 | **Custom view `955332000000441406` identity** — this view has been the entry point for all 9 flows but its name and filter criteria have never been explicitly shown; it is the team's primary working view |
| 6 | **New sort_by field ID revealed** — `955332000000427944` is a second previously-used sort field, different from Flow 6's `955332000000427928`; both remain unresolved to field names |
| 7 | **Shortest list-level flow** — at 5 steps / 36s, switching custom views is faster than Filter (8 steps), Sort (8 steps), or Manage Columns (9 steps) |
