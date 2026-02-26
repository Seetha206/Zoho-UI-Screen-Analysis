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
[Lead Qualification Blueprint]
  ├── Re Attempted
  ├── Contact in Future
  ├── Site Visit Scheduled
  ├── Site Visit Completed
  ├── Qualify Out
  └── Junk
       ↓
[Lead Converted] ──→ Contact + Account + Deal
                              ↓
                     [Sales / Deals Pipeline]
```

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
| Custom views in use | Hot Leads, Cold Leads, Warm Leads, Junk Lead, Nurturing Leads, Telecaller Leads, Site Visit Scheduled Leads |
| Key custom fields | Preferred Location, Purpose Of Purchase, Down Payment, Payment Type, Land Area in Cents, Comfortable Price, Rooms in BHK, Up to Price, Requirement Property Type, Client Major Concern on Purchase |

The high lead count (2,077) relative to contacts (26) confirms this is a top-of-funnel module where most enquiries are disqualified or in-progress — not yet converted.

---

## Module URL Reference

| Screen | URL |
|---|---|
| Leads list (default view) | `/crm/org60043078423/tab/Leads` |
| All Leads custom view | `/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list` |
| Create Lead form | `/crm/org60043078423/tab/Leads/create?layoutId=955332000000425337` |
| Lead detail view | `/crm/org60043078423/tab/Leads/{record_id}` |
| Edit layout | `/crm/org60043078423/settings/modules/Leads/layouts/955332000000425337` |
