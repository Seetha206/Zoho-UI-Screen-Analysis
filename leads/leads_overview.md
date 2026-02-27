# Leads Module — Overview & Context

## What Is This Module?

The **Leads** module is Zoho CRM's entry point for capturing and qualifying prospective buyers. A Lead represents a person who has shown interest in a property but has not yet been confirmed as a real customer. Once a lead is qualified and meets the criteria, it is **converted** into a Contact (the person), an Account (the company, if applicable), and a Deal (the sales opportunity).

---

## Why Does This Module Exist?

In real estate sales, a large volume of enquiries arrive from multiple sources — advertisements, referrals, walkins, cold calls, and online campaigns. The Leads module exists to:

1. **Capture every enquiry** in a structured, trackable record before any qualification happens.
2. **Qualify and score** prospects through a defined sales process without polluting the Contacts or Deals pipeline with unverified interest.
3. **Govern transitions** through a Blueprint ("Lead Qualification") so that no stage is skipped and every action is logged.
4. **Convert** only the genuine prospects into Contacts + Deals, keeping downstream modules clean and meaningful.

Without a dedicated Leads module, the Contacts and Deals modules would fill up with junk, cold, and duplicate enquiries — making pipeline forecasting unreliable.

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **BDM (Business Development Manager)** | Owns leads, drives qualification, runs Blueprint transitions, logs site visits |
| **Telecaller** | Makes initial outbound calls, updates call status, moves leads through early stages |
| **Manager / Admin** | Reviews custom views (Hot Leads, Cold Leads, Junk Leads), monitors BDM performance via Reports |

---

## How It Fits in the CRM Workflow

```
[Enquiry Arrives]
       ↓
[Lead Created] ← manual / import / web form / social media
       ↓
[Blueprint: Enquiry transition] ← mandatory: Email captured
       ↓
[Blueprint: Lead transition] ← mandatory: BANT fields + Matched Projects
  (Budget, Budget Variation, Authority, Need, Timeline, Matched Projects)
       ↓
[Attempted state — full transition set available]
  ├── Re Attempted
  ├── Contact in Future
  ├── Site Visit Completed
  ├── Qualify Out
  ├── Junk
  └── Exit Blueprint
       ↓
[Lead Converted] ──→ Contact + Account + Deal
                              ↓
                     [Sales / Deals Pipeline]
```

> See `leads_blueprint_transitions.md` for complete transition field requirements and modal structures.

The Blueprint enforces that a lead cannot jump directly from "New" to "Converted" — every transition must be logged, which creates an audit trail.

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Contacts** | A converted lead becomes a Contact; "Connected To" field on Contact links back to the original Lead |
| **Deals** | Conversion also creates a Deal record for the sales opportunity |
| **Accounts** | Optionally created during conversion for the buyer's company/family |
| **Tasks** | Follow-up tasks are created per lead (e.g., callback, site visit scheduling) |
| **Calls** | Outbound calls logged directly against the lead |
| **Meetings** | Site visits and consultations are tracked as Meetings linked to the lead |
| **Notes** | Sales notes, objections, and qualification comments are stored on the lead |
| **Schedules (CustomModule6)** | Linked via related list on Lead detail view; `SCH` auto-number prefix; 14,888+ records confirmed — heavily used module for scheduling telecaller follow-ups |
| **Projects Portfolio (CustomModule3)** | Linked via `Select matched projects` field in Blueprint `Lead` transition; confirmed project: `Mullai Nagar` |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total leads observed | 2,077 |
| Active Blueprint | Lead Qualification |
| Lead Source examples | Advertisement, referral, walkin, cold call |
| Custom views in use | Hot Leads, Cold Leads, Warm Leads, Junk Lead, Nurturing Leads, Telecaller Leads, Site Visit Scheduled Leads, **Today's Leads** (time-based: Created Time = Today) |
| Key custom fields | Preferred Location, Purpose Of Purchase, Down Payment, Payment Type, Land Area in Cents, Comfortable Price, Rooms in BHK, Up to Price, Requirement Property Type, Client Major Concern on Purchase |
| Key standard fields active | Lead Quality (Hot/Warm/Cold/Junk — standard Zoho CRM field, confirmed active; distinct from custom `Lead Type` field) |

The high lead count (2,077) relative to contacts (26) confirms this is a top-of-funnel module where most enquiries are disqualified or in-progress — not yet converted.

---

---

## Confirmed Automation Triggers (Scribe Evidence)

Triggered on the **Timeline** Blueprint transition (`lead_blueprint_scribe_flow` — observed in the automated actions section of the transition modal):

| Automation Name | Trigger Point | Type |
|---|---|---|
| `RescheduleFollowUps` | Timeline transition | Workflow Rule / Function |
| `Update Mobile Number` | Timeline transition | Workflow Rule / Function |
| `Update Attempt Field` | Timeline transition | Workflow Rule / Function |
| `[Lead] Send Welcome Message` | Timeline transition | Workflow Rule (likely WhatsApp/SMS action) |

> **Note:** These are the only confirmed automation triggers from Scribe recordings. A full automation rule inventory requires a live scan of `/settings/automation/workflow-rules`.

---

## Module URL Reference

| Screen | URL |
|---|---|
| Leads list (default view) | `/crm/org60043078423/tab/Leads` |
| All Leads custom view | `/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list` |
| Create Lead form | `/crm/org60043078423/tab/Leads/create?layoutId=955332000000425337` |
| Lead detail view | `/crm/org60043078423/tab/Leads/{record_id}` |
| Edit layout | `/crm/org60043078423/settings/modules/Leads/layouts/955332000000425337` |
