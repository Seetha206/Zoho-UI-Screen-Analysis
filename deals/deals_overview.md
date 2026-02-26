# Deals Module — Overview & Context

## What Is This Module?

The **Deals** module (internally called **Potentials**) in Zoho CRM tracks sales opportunities from initial interest through to closure. A Deal represents a specific property purchase opportunity associated with a Contact (buyer) and potentially an Account (family/company). Deals move through defined stages — from "Visit Pending" to "Closed Won" — allowing the sales team to track pipeline health and forecast revenue.

---

## Why Does This Module Exist?

In real estate sales, not every interested buyer is ready to purchase immediately. The Deals module exists to:

1. **Track sales opportunities** — Each Deal represents a potential property transaction with an estimated value and closing date.
2. **Visualize pipeline progression** — Stages (Visit Pending, Visit Completed, Booking Completed, Closed Won) show where each opportunity stands.
3. **Forecast revenue** — By tracking Amount and Closing Date, managers can predict monthly/quarterly sales performance.
4. **Link buyers to properties** — Deals connect Contacts (people) to specific property opportunities, creating a clear sales trail.
5. **Measure sales performance** — Deal Owner, Stage duration, and conversion rates help evaluate BDM effectiveness.

Without a Deals module, sales teams would lack visibility into their pipeline — unable to answer critical questions like "How many deals are closing this month?" or "What's the total value of opportunities in progress?"

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **BDM (Business Development Manager)** | Owns deals, progresses stages, logs site visits, negotiates closures |
| **Telecaller** | Schedules site visits, follows up on pending deals, updates deal status |
| **Manager / Admin** | Reviews pipeline reports, monitors deal velocity, approves discounts/closures |
| **Sales Leadership** | Forecasts revenue, analyzes conversion rates, identifies bottlenecks |

---

## How It Fits in the CRM Workflow

```
[Lead Qualified]
       ↓
[Lead Converted] ──→ Contact + Account + Deal Created
                              ↓
                    [Deal Stages Progression]
                              ↓
              ┌───────────────┼───────────────┐
              ↓               ↓               ↓
       Visit Pending   Visit Completed   Booking Completed
              ↓               ↓               ↓
              └───────────────┼───────────────┘
                              ↓
                    [Closed Won / Closed Lost]
                              ↓
                    [Revenue Recognized]
```

The Deals module is **bottom-of-funnel** — it represents opportunities where the buyer has moved beyond interest and is actively considering a purchase. A Deal without a Contact is incomplete; a Contact without a Deal is a relationship being nurtured for future opportunities.

---

## Deal Stages (Kurinjee Promoters)

| Stage | Description | Typical Duration |
|---|---|---|
| **Visit Pending** | Site visit scheduled but not yet completed | 1–14 days |
| **Visit Completed** | Buyer has visited the site; follow-up in progress | 1–30 days |
| **Booking Completed** | Token amount paid; documentation in progress | 7–45 days |
| **Closed Won** | Deal successfully closed; payment received | — |
| **Closed Lost** | Deal lost (reason tracked: price, location, timing, etc.) | — |

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Contacts** | A Deal is associated with a Contact (the buyer); "Contact Name" field links to Contact record |
| **Leads** | "Converted Leads" related list shows the original Lead that created this Deal |
| **Accounts** | Deals can be linked to Accounts (family/company purchasing entity) |
| **Tasks** | Follow-up tasks (calls, emails) are logged against the Deal |
| **Meetings** | Site visits and consultation meetings are linked to the Deal |
| **Calls** | Phone conversations about the deal are tracked in the Calls related list |
| **Emails** | Email correspondence regarding pricing, documentation, etc. |
| **Notes** | Negotiation details, client concerns, and internal comments |
| **Projects Portfolio** | "Site Visit Location" links deal to a specific project |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total deals observed | 9 |
| Layout ID | 955332000000425340 |
| Active view | All Deals (custom_view_id: 955332000000441430) |
| Internal module name | Potentials |

### Deal Distribution (Observed)

| Stage | Count | Percentage |
|---|---|---|
| Visit Pending | 5 | 55.6% |
| Closed Won | 2 | 22.2% |
| Booking Completed | 1 | 11.1% |
| Visit Completed | 1 | 11.1% |

### Deal Values (Visible Amounts)

| Deal | Amount | Stage |
|---|---|---|
| Krishnan | ₹ 75,00,000.00 | Booking Completed |
| Prasanth | ₹ 25,00,000.00 | Closed Won |
| Baskar | ₹ 13,26,000.00 | Closed Won |
| Senthilkumar Rangaraj | ₹ 15,00,000.00 | Visit Pending |
| **Total Visible Pipeline** | **₹ 1,28,26,000.00** | — |

**Note:** 5 out of 9 deals have blank Amount fields — indicating early-stage opportunities where pricing discussions haven't occurred yet. This is typical in real estate, where budget is often discussed after the initial site visit.

---

## Key Custom Fields (Kurinjee Promoters)

The Deals module has **130+ fields**, including extensive custom fields for real estate:

### Buyer Preference Fields
| Field | Purpose |
|---|---|
| Preferred Location | Area/locality the buyer is interested in |
| Preferred Project | Specific project name |
| Requirement Property Type | Plot / Villa / Apartment / Commercial |
| Rooms in BHK | 2 BHK, 3 BHK, etc. |
| Preferred Size (Sq.Ft or Cents) | Land/plot size requirement |
| Comfortable Price | Buyer's budget comfort level |
| Up to Price | Maximum budget ceiling |
| Purpose Of Purchase | Self-use / Investment / Rental |
| Payment Type | Cash / Loan / Combination |
| Down Payment | Initial payment capacity |
| Loan Requirement | Home loan needed (Yes/No) |

### Site Visit Tracking Fields
| Field | Purpose |
|---|---|
| Site Visit Date | Scheduled visit date |
| Site Visit Location | Links to Projects Portfolio |
| Site Visit URL | BDM form submission link |
| Client Feedback after the Site Visit | Post-visit comments |
| Client's Overall Impression | Positive/Neutral/Negative sentiment |
| Visit Status | Scheduled / Completed / No-show |
| Visit Verified | TL verification flag |

### Qualification & Scoring Fields
| Field | Purpose |
|---|---|
| Budget | BANT qualification field |
| Authority | Decision-making power |
| Need | Requirement urgency |
| Time | Purchase timeline |
| Budget Range Min / Max | Budget boundaries |
| Client Major Concern on Purchase | Primary objection |
| Real Objections | Actual barriers to closure |
| Objection Status | Resolved / Pending |
| Urgency Level | High / Medium / Low |

### Marketing Attribution Fields
| Field | Purpose |
|---|---|
| Lead Source | Advertisement / Referral / Walk-in / etc. |
| First Click Source | First digital touchpoint |
| Last Click Source | Most recent digital touchpoint |
| First/Last Click Campaign | UTM campaign tracking |
| Pages Visited | Website engagement metric |
| IP Address | Geographic tracking |
| Browser / Operating System | Device information |

---

## Module URL Reference

| Screen | URL |
|---|---|
| Deals list (default view) | `/crm/org60043078423/tab/Potentials` |
| All Deals custom view | `/crm/org60043078423/tab/Potentials/custom-view/955332000000441430/list` |
| Create Deal form | `/crm/org60043078423/tab/Potentials/create?layoutId=955332000000425340` |
| Deal detail view | `/crm/org60043078423/tab/Potentials/{record_id}` |
| Edit layout | `/crm/org60043078423/settings/modules/Potentials/layouts/955332000000425340` |
| Import Deals | `/crm/org60043078423/settings/import?module=Potentials&step=1` |
| Manage Tags | `/crm/org60043078423/settings/manage-tags?module=Potentials` |

---

## Related Documentation

| File | Description |
|---|---|
| `Dealsflow.md` | Full DOM scan with 130+ field definitions, form structure |
| `deals_overview.md` | This file — business context and usage |
