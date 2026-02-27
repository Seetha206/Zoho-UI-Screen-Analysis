# Contacts Module — Overview & Context

## What Is This Module?

The **Contacts** module stores individual person records in Zoho CRM — these are real, verified customers or key persons of interest who have moved beyond the initial enquiry stage. A Contact represents a human being: a buyer, a decision-maker, or any person the organisation actively maintains a relationship with. Contacts are the people attached to Accounts (companies) and linked to Deals (opportunities).

---

## Why Does This Module Exist?

In a CRM workflow, not every enquiry deserves a permanent person record. The Leads module handles unverified prospects. The Contacts module exists to hold only the people who have crossed the qualification threshold — either by being converted from a Lead or by being entered directly as a known customer.

The Contacts module exists to:

1. **Maintain a verified person directory** — every Contact is a real, qualified individual the team actively works with.
2. **Centralise communication history** — all calls, emails, meetings, and notes for a person are stored on their Contact record.
3. **Support deal tracking** — Contacts are linked to Deals so salespeople know exactly which person is associated with which opportunity.
4. **Enable relationship mapping** — a Contact can belong to an Account (company), report to another Contact, and be connected back to the originating Lead.
5. **Enable marketing actions** — mass email, autoresponders, and audience segmentation are run from the Contacts module.

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **Sales team / BDM** | Manages active buyer relationships, logs calls and meetings, links contacts to deals |
| **Admin** | Imports, deduplicates, exports, manages tags and custom views |
| **Marketing** | Sends mass emails, sets up autoresponders, filters by lead source and website activity |
| **Manager** | Reviews contact records, monitors relationship health, uses reports |

---

## How It Fits in the CRM Workflow

```
[Lead Converted]  ──→  [Contact Created]
         OR
[Manual Entry]  ──→  [Contact Created]

[Contact]
  ├── Linked to Account (company/family)
  ├── Linked to Deals (one or more)
  ├── Logs: Calls, Emails, Meetings, Tasks, Notes
  ├── Connected To: original Lead (if converted)
  └── Workflows / Blueprints can act on Contact fields
```

The Contacts module is **mid-funnel** — it sits between the top-of-funnel Leads module and the bottom-of-funnel Deals module. A Contact without a Deal is a relationship being nurtured; a Contact with a Deal is an active sales opportunity.

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Leads** | Lead conversion creates the Contact; "Connected To" field links back to the originating Lead |
| **Accounts** | A Contact belongs to an Account (the buyer's company or household) |
| **Deals** | A Contact is associated with one or more Deal records (the specific property opportunity) |
| **Tasks** | Follow-up tasks are logged on the Contact |
| **Meetings** | Site visits, consultations, and meetings are linked to the Contact |
| **Calls** | All inbound/outbound calls are logged on the Contact record |
| **Emails** | Email correspondence is tracked in the Contact's email history |
| **Notes** | Freeform notes about the person are attached to the Contact |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total contacts observed | 26 |
| Layout ID | 955332000000425339 |
| Subscription | 1 user license (limit reached) |
| Active view | My Contacts (custom_view_id: 955332000000441440) |

The low contact count (26) relative to leads (2,077) is expected in real estate — only a small fraction of enquiries are converted into managed customer relationships. The Contacts module in this org is used to track genuine buyers who are in or past the qualification stage.

Notable Contacts module fields specific to this org:
- **Estimated Budget ₹** (currency) — captures buyer's stated budget; confirmed present in Create Contact form (visible in form section label containing multiple fields)
- **Connected To** (lookup → Leads) — traces back to the original lead
- **Reporting To** — hierarchy within buyer groups or corporate contacts
- **UTM/Click tracking fields** (Last Click Source, First Click Campaign, etc.) — tracks digital marketing attribution for how the contact was acquired

### Known Real Contact Records

| Name | Owner | Significance |
|---|---|---|
| Prasanth | Sri | Appears in Clone flow (Flow 12) and linked to a Deal record; visible on page 1 of 10-per-page list |

### Record Creation Interactions (Scribe Flow Confirmed)

| Interaction | Detail |
|---|---|
| Create button label | `Create Contact` (not just "+New") |
| Form action buttons | `Save` \| `Save and New` \| `Cancel` |
| **Save and New** | Saves current record + immediately opens a fresh blank form for rapid batch entry |
| Only mandatory field | Last Name (`*`) |
| Date format | `DD/MM/YYYY` (Indian date format — Zoho India instance) |
| per_page default | `10` records per page (confirmed via `per_page=10` URL param in Clone flow) |

### Clone Operation (Scribe Flow Confirmed)

Path: **Contact detail view → More actions (`⋮`) → Clone**

| Step | Action |
|---|---|
| 1 | Open Contact detail view (click record name in list) |
| 2 | Click `⋮` (More actions) button in detail view header |
| 3 | Select **Clone** from the dropdown |
| 4 | Contact creation form opens pre-filled with source record's field values |
| 5 | User edits required fields and saves as a new record |

Clone is useful for entering multiple members of the same family who share most contact details (lead source, budget, account).

---

## Module URL Reference

| Screen | URL |
|---|---|
| Contacts list (default view) | `/crm/org60043078423/tab/Contacts` |
| My Contacts custom view | `/crm/org60043078423/tab/Contacts/custom-view/955332000000441440/list` |
| Create Contact form | `/crm/org60043078423/tab/Contacts/create?layoutId=955332000000425339` |
| Contact detail view | `/crm/org60043078423/tab/Contacts/{record_id}` |
| Edit layout | `/crm/org60043078423/settings/modules/Contacts/layouts/955332000000425339` |
| Import Contacts | `/crm/org60043078423/settings/import?module=Contacts&step=1` |
| Manage Tags | `/crm/org60043078423/settings/manage-tags?module=Contacts` |

---

## Scribe Flows Documented

| Flow | Steps | Duration | Key Finding |
|---|---|---|---|
| Save and New (Contact) | 6 | ~20s | `Create Contact` button; form fields including `Estimated Budget ₹`; `Save and New` batch pattern; Last Name only mandatory field |
| Clone (Contact) | 4 | ~8s | Contact detail → `⋮ More` → `Clone`; pre-fills form with source record values; "Prasanth" used as source |
