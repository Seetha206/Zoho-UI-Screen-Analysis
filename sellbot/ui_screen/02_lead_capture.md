# Step 2 — Lead Capture Form
# SellBot UI Implementation Plan

> SellBot Step: 2 of 14
> Zoho CRM Source: /leads/leads_full_structure.yaml + leads_creation/flow.md
> Zoho Module URL: /crm/org60043078423/tab/Leads/create

---

## 1. SellBot Objective

Capture incoming enquiries from all channels (Facebook, Google, portals, walk-ins,
referrals) into a standardised two-section form. Every submission automatically
triggers Step 3 (Auto Welcome Message).

---

## 2. Source Zoho CRM Analysis

From `leads_full_structure.yaml` and Scribe flow `lead_create_scribe_flow`:
- Lead Name is the only mandatory field (confirmed Step 1 of Scribe flow)
- Current sections: Lead Information | Address Information | Description
- Custom fields confirmed: Telecaller (dropdown), Language Preference (picklist),
  Client Location (text), Estimated Budget (currency)
- Date format: DD/MM/YYYY (Indian format confirmed)
- Navigation guard: "You have not saved your changes." — already reverse-engineered
- Form buttons: Save | Save and New | Cancel

---

## 3. SellBot Lead Capture Form Design

### 3.1 URL Pattern
```
/sellbot/leads/create
Layout ID: maps to leads layoutId=955332000000028055 (existing Zoho layout)
```

### 3.2 Section 1 — Basic Lead Information

| Field | Type | Required | Zoho Equivalent | Notes |
|---|---|---|---|---|
| Lead Name | Text | YES | Lead Name | Mandatory — same as Zoho |
| Mobile Number | Phone | YES | Mobile | Add validation: 10-digit Indian mobile |
| Email | Email | No | Email | Standard email format validation |
| Lead Source | Picklist | Yes | Lead Source | Facebook/Google/Portal/Referral/Walk-in/Others |
| Campaign Name | Text | No | (new field) | Maps to active Facebook/Google campaign |
| Date of Enquiry | Date | No | Created Time (auto) | Default: today; editable |
| CRM Executive Assigned | User Lookup | Yes | Lead Owner | Default: current user |
| Language Preference | Picklist | No | Language Preference (custom) | Tamil / English / Telugu / Hindi |

### 3.3 Section 2 — Buyer Preferences (NEW in SellBot)

| Field | Type | Required | Zoho Equivalent | Notes |
|---|---|---|---|---|
| Preferred Location | Text | No | Client Location (custom) | Area/neighbourhood preference |
| Property Type | Picklist | No | (new field) | Plot / Villa / Apartment / Commercial |
| Budget Range | Picklist | No | Estimated Budget (custom) | <10L / 10–25L / 25–50L / 50L–1Cr / 1Cr+ |
| Purpose of Purchase | Picklist | No | (new field) | Self-use / Investment / Both |
| Purchase Timeline | Picklist | No | (new field) | Immediate / 3 months / 6 months / 1 year+ |
| Financing Plan | Picklist | No | (new field) | Cash / Home Loan / Mix |
| Room Preference | Picklist | No | (new field) | 1BHK / 2BHK / 3BHK / Open Plot |
| Notes | Long text | No | Description | Free text for additional context |

### 3.4 Form Actions (mirrors Zoho pattern exactly)

```
[Save]  [Save and New]  [Cancel]
```
- **Save**: saves record → redirects to Lead detail view → triggers Step 3 automation
- **Save and New**: saves → opens fresh Lead create form
- **Cancel**: navigation guard modal → "Yes, Leave Page" / "Stay Here"

---

## 4. Lead List View Columns (SellBot default)

```
Columns: Lead Name | Mobile | Lead Source | CRM Executive | Lead Type | Status | Date of Enquiry
Sorted by: Date of Enquiry (descending — newest first)
```

### 4.1 Filter Panel — SellBot Required Filters

#### System Filters (mirrors Zoho pattern)
- Touched Records
- Untouched Records
- Record Action
- Related Records Action
- Locked
- Latest Email Status
- Activities
- Cadences

#### Filter by Fields (minimum required)
- Lead Name
- Mobile Number
- Lead Source
- Lead Type (Hot/Warm/Cold/Junk)
- CRM Executive Assigned
- Lead Status
- Date of Enquiry
- Preferred Location
- Budget Range
- Campaign Name
- Created Time
- Modified Time
- Tag

---

## 5. Lead Source Picklist Values

| Value | Channel |
|---|---|
| Facebook | Facebook Ads |
| Instagram | Instagram Ads |
| Google | Google Ads / SEO |
| Real Estate Portal | 99acres / MagicBricks / Housing |
| Referral | Customer referral (Step 12) |
| Walk-in | Direct office/site visit |
| WhatsApp | WhatsApp enquiry |
| Website | Organic website form |
| Others | All other sources |

---

## 6. Mandatory Field Validation

Following Zoho pattern (confirmed via lead_create_scribe_flow):
- Required fields show red asterisk (*)
- Save blocked if required field empty
- Inline red border + error message below field
- Error message pattern: "Please fill in [Field Name]"

---

## 7. Post-Create Automation Trigger

On successful Lead save:
1. Lead record created with unique ID
2. `Created Time` auto-stamped
3. **Step 3 automation fires** → sends Auto Welcome WhatsApp + Email
4. Lead appears in list view (sorted by Created Time descending)
5. Toast message: "Lead created successfully"

---

## 8. Implementation Delta vs Zoho Leads Module

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Section 2 (Buyer Preferences) | Partial (Estimated Budget, Client Location) | Full section: Property Type, Budget Range, Purpose, Timeline, Financing, BHK |
| Campaign Name field | Not present | Add as Text field (for ad campaign tracking) |
| Lead Source values | Generic Zoho defaults + some custom | Real estate specific: Facebook/Google/Portal/Referral/Walk-in |
| Mobile validation | No strict validation confirmed | Add: 10-digit Indian mobile format |
| Auto-trigger on save | Separate automation rule in Zoho | Same pattern — trigger on record creation |
