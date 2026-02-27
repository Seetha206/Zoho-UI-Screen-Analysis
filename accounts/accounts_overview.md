# Accounts Module — Overview & Context

## What Is This Module?

The **Accounts** module stores company-level or household-level records in Zoho CRM. In the context of Kurinjee Promoters (real estate), an Account represents a buyer group, family, or company associated with a property purchase. Accounts act as the organisational anchor — linking multiple Contacts (people), Deals (opportunities), and Leads (converted enquiries) under a single entity.

---

## Why Does This Module Exist?

In real estate sales, a property purchase is often a family or group decision — multiple people (contacts) may be involved in a single deal. The Accounts module exists to:

1. **Group related people** — a family buying a plot can have multiple Contact records all linked to one Account.
2. **Track property-level data** — custom fields like Available Plots, Property Type, Land Area in Cents, and Unit Price are stored at the Account level, enabling property inventory tracking.
3. **Centralise converted lead data** — when a Lead is converted, an Account is optionally created, preserving the relationship between the buyer and the originating enquiry.
4. **Support plot ownership hierarchy** — the "Plots Owned By" relationship allows one Account to be linked as owning plots under another Account (project/property hierarchy).
5. **Enable marketing attribution at account level** — UTM and click-tracking fields (First/Last Click Channel, GA IDs, Pages Visited) are present at the Account level for marketing ROI analysis.

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **BDM / Sales team** | Links deals and contacts to account; tracks property interest and budget |
| **Admin** | Creates accounts on lead conversion; imports and deduplicates account records |
| **Manager / Analytics** | Uses account-level fields for portfolio and revenue reporting |

---

## How It Fits in the CRM Workflow

```
[Lead Converted]
       ↓
[Account Created] ← or pre-existing Account found
       ↓
[Account]
  ├── Contacts (people linked to this account)
  ├── Deals (property opportunities for this account)
  ├── Leads (Converted Leads — original enquiries)
  ├── Accounts (Member Accounts — group sub-accounts)
  ├── Accounts (Plots Owned By — property ownership links)
  └── Emails (communication history at account level)
```

Accounts sit **above Contacts and Deals** in the hierarchy — they represent the buyer entity, while Contacts represent the individuals and Deals represent the specific transactions.

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Contacts** | A Contact belongs to an Account (buyer's household or company) |
| **Deals** | Deals are created under an Account (the property opportunity for that buyer) |
| **Leads (Converted Leads)** | When a Lead is converted, it links back to the Account created at conversion |
| **Accounts (Member Accounts)** | Sub-accounts nested under a parent account |
| **Accounts (Plots Owned By)** | Tracks which plots/properties are owned by or linked to this account — real-estate specific relationship |
| **Emails** | Email correspondence tracked at account level |
| **Tasks** | Tasks with "Related To: Account" are linked here |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total accounts observed | 11 |
| Records per page | 10 |
| Active view | All Accounts (custom_view_id: 955332000000441417) |
| Admin user | Kurinjee Promoters (kurinjeecrm01@gmail.com) |
| Admin phone | 9597736066 |
| Subscription | 1 user license (upgrade prompt visible) |

### Current Account Records

| Account Name | Type | Record ID |
|---|---|---|
| Kurinjee Promoters | Real (organisation's own account) | 955332000000669142 |
| King (Sample) | Zoho sample | 955332000000419622 |
| Truhlar And Truhlar (Sample) | Zoho sample | 955332000000419621 |
| Commercial Press (Sample) | Zoho sample | 955332000000419620 |
| Morlong Associates (Sample) | Zoho sample | 955332000000419619 |
| Chapman (Sample) | Zoho sample | 955332000000419618 |
| Printing Dimensions (Sample) | Zoho sample | 955332000000419617 |
| Feltz Printing Service (Sample) | Zoho sample | 955332000000419616 |
| Chemel (Sample) | Zoho sample | 955332000000419615 |
| Chanay (Sample) | Zoho sample | 955332000000419614 |
| *(11th record — page 2)* | — | — |

**Note:** Only 1 real account ("Kurinjee Promoters") exists — the remaining 10 are Zoho-provided sample records. This indicates the Accounts module is lightly used in this org; deals and contacts are typically linked directly to the lead flow rather than through accounts.

### Real Estate Custom Fields (visible in filter panel)

| Field | Purpose |
|---|---|
| Available Plots | Number of plots available under this account/project |
| Land Area In Cents | Plot size in cents (South Indian unit) |
| Property Type | Type of property (Plot, Villa, Apartment, Commercial) |
| Purpose Of Purchase | Buyer's stated purpose (Investment, Self-use, etc.) |
| Room in BHK | Number of bedrooms (for apartment-type properties) |
| Unit Price | Price per unit/plot |
| Promotor | Promoter/developer name |
| Connected To | Links back to the source Lead |
| Estimated Budget | Buyer's budget at account level |

### Marketing Attribution Fields

Full UTM and Google Analytics tracking at the Account level — mirrors the same fields on Leads and Contacts:
- First Click and Last Click: Channel, Campaign, Content, Medium, Referrer, Source, Term, Timestamp, Landing Page, Landing Page URL
- Google Analytics: Client ID, Measurement ID, Session ID, GCLID
- Geo/Device: IP Address, City, Country (from IP), Latitude, Longitude, Browser, Operating System, Pages Visited, Time Zone

---

## Bulk Data Operations (Scribe Flow Confirmed)

### Actions Menu (Toolbar — List View)

The **Actions** dropdown button in the Accounts list view toolbar contains:

| Menu Item | Function |
|---|---|
| Mass Update | Update a field across multiple selected records at once |
| Mass Delete | Delete multiple selected records |
| Import Accounts | Opens the Import Wizard (multi-step) |
| Export Accounts | Opens the Export dialog (single modal) |
| Deduplicate | Find and merge duplicate account records |

### Import Accounts — Wizard Steps

Entry: `Actions → Import Accounts`

| Step | Description |
|---|---|
| Step 1 — Upload File | Drag-and-drop or browse; formats: `.csv`, `.xls`, `.xlsx`; max 5 MB; max 30,000 records |
| Step 2 — Map Fields | Match CSV column headers to CRM fields; skip unwanted columns |
| Step 3 — Preview & Import | Review count, set duplicate handling (Add / Update / Add+Update), click `Import Now` |

Import runs asynchronously for large files. Failed records downloadable as an error CSV.

### Export Accounts — Dialog Options

Entry: `Actions → Export Accounts`

The Export dialog presents a **radio button choice**:

| Option | What is exported |
|---|---|
| **Fields from custom view** | Only the columns visible in the current custom view (`955332000000441417`) |
| **All Fields** | Every available field — standard + custom (full data export) |

File output: `.csv` download. The final "Export" button click triggers the browser download.

### Custom View ID Registry (Cross-Module)

| Module | Custom View ID | Sequence |
|---|---|---|
| Leads | `955332000000441406` | 1st (oldest) |
| Accounts | `955332000000441417` | 2nd |
| Potentials (Deals) | `955332000000441430` | 3rd |
| Contacts | `955332000000441440` | 4th (newest) |

All four IDs were created in a single CRM customisation session (sequential IDs).

---

## Module URL Reference

| Screen | URL |
|---|---|
| Accounts list (default view) | `/crm/org60043078423/tab/Accounts` |
| All Accounts custom view | `/crm/org60043078423/tab/Accounts/custom-view/955332000000441417/list` |
| Create Account form | `/crm/org60043078423/tab/Accounts/create` |
| Account detail view | `/crm/org60043078423/tab/Accounts/{record_id}` |
| Import Accounts (Actions menu → Import Accounts) | `/crm/org60043078423/settings/import?module=Accounts&step=1` |
| Manage Tags | `/crm/org60043078423/settings/manage-tags?module=Accounts` |
| Approve records | `/crm/org60043078423/tab/Accounts/actions/approvals` |
| Export Accounts (Actions menu → Export Accounts) | Via Actions dropdown on list view |
| Drafts | `/crm/org60043078423/tab/Accounts/actions/draft?module=Accounts` |
| Mass Delete | `/crm/org60043078423/tab/Accounts/actions/mass-tools?type=mass_delete` |
| Mass Update | `/crm/org60043078423/tab/Accounts/actions/mass-tools?type=mass_update` |
| Custom Views — create | `/crm/org60043078423/tab/Accounts/custom-views/create` |
| Custom Views — manage | `/crm/org60043078423/tab/Accounts/custom-views/manage?category=all_custom_views` |
| Calendar | `/crm/org60043078423/calendar?date=26-02-2026&viewType=day` |
| Marketplace | `/crm/org60043078423/settings/extensions/all` |
| Setup | `/crm/org60043078423/settings/index` |

---

## Scribe Flows Documented

| Flow | Steps | Duration | Key Finding |
|---|---|---|---|
| Record Import (Accounts) | 4 | ~17s | `Actions → Import Accounts`; 3-step wizard; CSV/XLS/XLSX; 5MB max; 30,000 records max |
| Record Export (Accounts) | 5 | ~23s | `Actions → Export Accounts`; radio choice: Fields from custom view / All Fields; CSV output |
