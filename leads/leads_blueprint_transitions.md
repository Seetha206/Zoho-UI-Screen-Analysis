> Source: Scribe recordings — Lead Module BluePrint Flow in CRM
> Scribe URL: https://scribehow.com/viewer/Lead_Module__BluePrint_Flow_in_CRM__CzUDuGLrRw2IfepoHwWqsg
> Recorded By: Sri Gnanathesigan
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Blueprint Name: Lead Qualification

---

# Lead Module — Blueprint Transitions Documentation

## Overview

Zoho CRM Blueprint enforces that every stage transition requires mandatory fields to be filled before a lead can advance. Agents cannot skip transitions or bypass field entry. This document captures all confirmed transitions, their mandatory field sets, and UI behaviour.

---

## Complete Stage Sequence

```
[*] ──▶ New Lead (Created)
              │
              ▼ Transition: "Enquiry"  [mandatory: Email]
         Enquiry Stage
              │
              ▼ Transition: "Lead"  [mandatory: BANT + Matched Projects]
         Lead Qualification Stage
              │
              ├──▶ Re Attempted
              ├──▶ Contact in Future
              ├──▶ Attempted  ◀── (state documented in DOM scan)
              ├──▶ Site Visit Completed
              ├──▶ Qualify Out
              ├──▶ Junk
              └──▶ Exit Blueprint
```

> **Note:** `Enquiry` and `Lead` are the first two gated transitions on a NEW lead record. The `Attempted` state (with its full transition set) is reached after these early-stage gates are cleared.

---

## Transition 1 — "Enquiry"

| Property | Detail |
|----------|--------|
| Transition name | `Enquiry` |
| Available from state | New Lead (freshly created record) |
| Advances to state | Enquiry stage |
| Location in UI | Blueprint stage bar — top of Lead Detail View, Overview tab |
| Button style | Transition button (colored label) |

### Mandatory Fields in Enquiry Modal

| Field Label | Input Type | Required | Notes |
|-------------|------------|----------|-------|
| Email | Text input | Yes | Captures lead's email address before any qualification |

### Modal UI Structure

```
┌─────────────────────────────────────────┐
│  Enquiry                                │
├─────────────────────────────────────────┤
│  Email *                                │
│  [                                    ] │
├─────────────────────────────────────────┤
│               [ Cancel ]  [ Save ]      │
└─────────────────────────────────────────┘
```

---

## Transition 2 — "Lead" (BANT Qualification)

| Property | Detail |
|----------|--------|
| Transition name | `Lead` |
| Available from state | Enquiry stage |
| Advances to state | Lead Qualification stage |
| Location in UI | Blueprint stage bar — top of Lead Detail View, Overview tab |
| Button style | Transition button (colored label) |

### Mandatory Fields in Lead Transition Modal

| # | Field Label in Modal | Maps to Form Field | Input Type | Required | Confirmed Value (test) |
|---|----------------------|--------------------|------------|----------|------------------------|
| 1 | Enter estimated budget | Estimated Budget | Currency / numeric | Yes | `200000` (₹2,00,000) |
| 2 | Select budget variation | Budget (Lead Assessment) | Single-select dropdown | Yes | `Matched` |
| 3 | Select authority | Authority (Lead Assessment) | Single-select dropdown | Yes | `Close Relatives` |
| 4 | Select need | Need (Lead Assessment) | Single-select dropdown | Yes | `5-10 Km` |
| 5 | Select time | Time (Lead Assessment) | Single-select dropdown | Yes | `Within a Month` |
| 6 | Select matched projects | Preferred Project (Internal Use) | Dropdown / lookup | Yes | `Mullai Nagar` |

> **Label discrepancy:** Blueprint modal uses prefixed labels (`Select authority`, `Select need`, `Select time`, `Select budget variation`) that differ from the form field labels (`Authority`, `Need`, `Time`, `Budget`) in the Lead Assessment section. These are the same underlying fields — only the modal label differs.

### Confirmed Dropdown Options

| Field | Confirmed Options | Notes |
|-------|-------------------|-------|
| Budget Variation | `Matched`, `Not Matched` (inferred), `Negotiable` (inferred) | Only `Matched` confirmed from recording |
| Authority | `Close Relatives`, `Self` (inferred), `Extended Family` (inferred) | Only `Close Relatives` confirmed |
| Need | `5-10 Km`, `0-5 Km` (inferred), `10-20 Km` (inferred), `Any Location` (inferred) | Only `5-10 Km` confirmed |
| Timeline | `Within a Month`, `1-3 Months` (seen in Lead Assessment field), `3-6 Months` (inferred), `6-12 Months` (inferred), `Not Decided` (inferred) | `Within a Month` confirmed; `1-3 Months` seen in DOM |
| Matched Projects | `Mullai Nagar` | Only confirmed project; org has additional projects |

### Modal UI Structure

```
┌──────────────────────────────────────────┐
│  Lead Qualification                      │
├──────────────────────────────────────────┤
│  Estimated Budget *                      │
│  [ ₹                                   ]│
│                                          │
│  Select budget variation *               │
│  [ -None- ▾                            ]│
│                                          │
│  Select authority *                      │
│  [ -None- ▾                            ]│
│                                          │
│  Select need *                           │
│  [ -None- ▾                            ]│
│                                          │
│  Select time *                           │
│  [ -None- ▾                            ]│
│                                          │
│  Select matched projects *               │
│  [ -None- ▾                            ]│
├──────────────────────────────────────────┤
│               [ Cancel ]  [ Save ]       │
└──────────────────────────────────────────┘
```

---

## Transitions Available from "Attempted" State

These transitions are confirmed from the Lead Detail View DOM scan (lead record "Ram", state: Attempted):

| Transition Button | Color | Advances To |
|-------------------|-------|-------------|
| Re Attempted | Yellow/Orange | Re-attempted state |
| Contact in Future | Orange | Contact in Future state |
| Lead | Pink/Red | Lead Qualification stage |
| Site Visit Completed | Blue | Site Visit Completed state |
| Qualify Out | Pink | Qualified Out state |
| Junk | Gray/Red | Junk Lead state |
| Exit Blueprint | Dark Gray | Exits Blueprint entirely |

Additional UI element in Blueprint bar: **"View configured actions"** link (top-right of Blueprint state bar) — opens the Blueprint configuration view.

---

## Blueprint BANT Cross-Reference

The Blueprint transition fields map directly to the Lead Assessment section in the lead form:

| BANT | Blueprint Modal Field | Lead Assessment Field | Lead Form Field (Internal Use) |
|------|-----------------------|-----------------------|-------------------------------|
| B — Budget | `Enter estimated budget` + `Select budget variation` | `Budget` (e.g. Mismatch) | `Estimated Budget` (currency) |
| A — Authority | `Select authority` | `Authority` (e.g. Self) | — (set via Blueprint) |
| N — Need | `Select need` | `Need` (e.g. 5-10 Km) | — (set via Blueprint) |
| T — Time | `Select time` | `Time` (e.g. 1-3 Months) | — (set via Blueprint) |
| + Project | `Select matched projects` | — | `Preferred Project` (Internal Use section) |

> **`Family Decision Involved?`** (Lead Information section) is the free-form field capturing family authority. `Select authority` in the Blueprint modal is the structured classification — both fields capture authority-related information at different stages.

---

## Automated Actions Triggered by Transitions

From Timeline History entries observed in DOM scan:

| Trigger | Automated Action |
|---------|-----------------|
| Any Blueprint transition | `Function RescheduleFollowUps` called |
| Blueprint transition "Attempted" | `Function RescheduleFollowUps` creates Task (e.g., Attempt 2) |
| Blueprint transition | `Function [Leads] Update Mobile Number` called via Workflow Rule |
| Blueprint transition "Attempted" | Note auto-added: "UnAttempted Reason" |
| Lead Created (new record save) | `Update Attempt Field` (field update) |
| Lead Created | `Update Lead Status` (field update) |
| Lead Created | `[Lead] Send Welcome Message` (function — WhatsApp/SMS) |

---

## UI Location — Blueprint Stage Bar

```
Lead Detail View — Overview Tab
┌──────────────────────────────────────────────────────────────┐
│  Current State: [Stage Name]        [View configured actions]│
├──────────────────────────────────────────────────────────────┤
│  [Transition 1] [Transition 2] [Transition 3] ... [Exit]     │
└──────────────────────────────────────────────────────────────┘
```

- Stage bar appears at the top of the Overview tab, above Business Card Details
- Transition buttons are colored (not plain gray) — color encodes urgency/type
- `Lead Status` field in the Edit form has a **lock icon** — it is Blueprint-managed and cannot be freely edited
- All stage changes are logged in **Timeline → History** tab with timestamp, actor, transition name, and Blueprint name
