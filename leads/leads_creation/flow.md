# Lead Creation Flow

## Source

Scanned from: `https://crm.zoho.in/crm/org60043078423/tab/Leads/create?layoutId=955332000000425337&redirect=false`
Layout ID: `955332000000425337`

---

## Entry Points

### Primary Entry: Create Lead Button

- **Location:** Leads list view — top-right toolbar
- **Label:** `Create Lead`
- **Type:** Split button (primary action + dropdown arrow)
- **Primary button ref:** `ref_79`
- **Dropdown arrow ref:** `ref_80` (label: "More")
- **Color:** Blue (solid fill)
- **Position:** Right of `Refresh Custom View` button; left of `Actions` (three-dot) button
- **Navigation result:** Navigates to `/tab/Leads/create?layoutId=955332000000425337&redirect=false`
- **Page title changes to:** `Create Lead - Zoho CRM`

---

## Create Lead Form Screen

### Page Header

- **Breadcrumb/module label:** `Leads` (top-left, above form title)
- **Form title:** `Create Lead`
- **Secondary link:** `Edit Page Layout` (inline, right of form title; links to `/crm/org60043078423/settings/modules/Leads/layouts/955332000000425337`)
- **Action buttons (top-right, "Form Controls" region):**
  - `Save` — blue, solid, primary; ref `ref_405`
  - `Save and New` — white/outline; ref `ref_407`
  - `Cancel` — white/outline; ref `ref_409`

### Right-panel utility

- `Client Script` — tab/label visible on far-right edge (vertical orientation)

---

## Form Structure — Sections

The form has **11 sections**, rendered as collapsible regions:

1. Lead Information
2. Requirement Assessment
3. Lead Assessment
4. Address Information
5. Description Information
6. Qualification Form
7. Client Feedback
8. Team Lead Section
9. Site Visit Information
10. Site Completion Form Submission
11. Referral Information
12. Centilio Tracking
13. Internal Use
    > Sections 9–13 are visible on the form but contain fields primarily populated post-creation (site visit, tracking, etc.).

---

## Section 1: Lead Information

**Layout:** 2-column grid (left column labels right-aligned; right column labels right-aligned)
| # | Field Label | Position | Type | Required | Default / Placeholder | Notes |
|---|---|---|---|---|---|---|
| 1 | Last Name | Left col, row 1 | Text input | **YES** (red border on load) | empty | ref `ref_419` |
| 2 | Mobile | Right col, row 1 | Text input | **YES** (red border on load) | empty | ref `ref_484` |
| 3 | Lead Type | Left col, row 2 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `Hot` (red dot), `Warm` (yellow dot), `Cold` (blue dot), `Junk` (grey dot) |
| 4 | Lead Source | Right col, row 2 | Dropdown (picklist, searchable) | No | `-None-` | Options: `-None-`, `Offline Marketing`, `Cold Call`, `99 Acres`, `MagicBicks`, `Housing.Com`, `Employee Referral`, `Inbound Referral`, `External Referral`, `Meta Ads`, `Walkins`, `Google Ads`, `Expo` |
| 5 | Client Location | Left col, row 3 | Text input | No | empty | ref `ref_427` |
| 6 | Lead Status | Right col, row 3 | Dropdown (picklist, searchable) | No | `Lead Bucket` | Options: `-None-`, `Lead Bucket`, `Lead for Initial Sales Process`, `Attempted to Contact`, `Contact in Future`, `Lead Scoring Using BANT`, `Junk Lead`, `Qualified`, `Site Visit Completed`, `Site Visit Scheduled`, `Confirm Site Visit`, `Attempted`, `Advance Payed`, `Deal Closed` |
| 7 | Company | Left col, row 4 | Lookup/autocomplete | No | empty | ref `ref_429` (combobox with search) |
| 8 | Email | Right col, row 4 | Text input | No | empty | ref `ref_498` |
| 9 | Telecaller | Left col, row 5 | Lookup (user picker) | No | empty | Has open-picker icon (📋); ref `ref_434`; "Open Telecaller" button ref `ref_440` |
| 10 | Estimated Budget | Right col, row 5 | Text input (currency) | No | `₹` prefix; info icon (ⓘ) | ref `ref_500` |
| 11 | Manager | Left col, row 6 | Lookup (user picker) | No | empty | Has open-picker icon (📋); ref `ref_442`; "Open Manager" button ref `ref_448` |
| 12 | Preferred Communication Channel | Right col, row 6 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `WhatsApp`, `Phone Call`, `Email` |
| 13 | Reason Qualified Out | Left col, row 7 | Dropdown (picklist) | No | `-None-` | ref `ref_450`; options not yet scanned — `# VERIFY` |
| 14 | Type of Property | Right col, row 7 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `Plot`, `Villa`, `Apartment`, `Commercial` |
| 15 | Language Preference | Left col, row 8 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `English`, `Tamil` |
| 16 | Preferred Size (Sq.Ft or Cents) | Right col, row 8 | Text input | No | empty | ref `ref_514` |
| 17 | Budget Range Min | Left col, row 9 | Text input | No | empty | Has info icon (ⓘ); ref `ref_462` |
| 18 | Family Decision Involved? | Right col, row 9 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `Yes`, `No` |
| 19 | Budget Range Max | Left col, row 10 | Text input | No | empty | Has info icon (ⓘ); ref `ref_464` |
| 20 | Deal Closed Time | Right col, row 10 | Date + Time + AM/PM | No | `DD/MM/YYYY` placeholder; default time `04:00 PM` | Two inputs + combobox; refs `ref_522`, `ref_523`, `ref_524` |
| 21 | Budget Range | Left col, row 11 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `₹5L–₹10L`, `₹10L–₹25L`, `₹25L–₹50L`, `₹50L–₹1Cr`, `Above ₹1Cr` |
| 22 | Social Lead ID | Right col, row 11 | Text input | No | empty | ref `ref_529` |
| 23 | Timeframe to Purchase | Left col, row 12 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `Immediate`, `Within 3 Months`, `3–6 Months`, `6–12 Months`, `Not Decided` |
| 24 | Loan Requirement | Left col, row 13 | Dropdown (picklist) | No | `-None-` | Options: `-None-`, `Yes`, `No`, `Considering` |

---

## Section 2: Requirement Assessment

| #   | Field Label                      | Type                  | Notes                                  |
| --- | -------------------------------- | --------------------- | -------------------------------------- |
| 1   | (Section search/header field)    | Text                  | ref `ref_532` — section-level text     |
| 2   | Preferred Location               | Text input            | ref `ref_534`                          |
| 3   | 1. Preferred Location            | Text input            | ref `ref_536`                          |
| 4   | 2. Preferred Location            | Text input            | ref `ref_538`                          |
| 5   | 3. Preferred Location            | Text input            | ref `ref_540`                          |
| 6   | Comfortable Price                | Text input (currency) | ref `ref_542`                          |
| 7   | Up to Price                      | Text input (currency) | ref `ref_544`                          |
| 8   | Requirement Property Type        | Text input            | ref `ref_546`                          |
| 9   | Client Major Concern on Purchase | Text input            | ref `ref_548`                          |
| 10  | Purpose Of Purchase              | Text input            | ref `ref_550`                          |
| 11  | Down Payment                     | Text input (currency) | ref `ref_552`                          |
| 12  | Payment Type                     | Text input            | ref `ref_554`                          |
| 13  | Land Area in cents               | Text input            | ref `ref_556`                          |
| 14  | Rooms in BHK                     | Text input            | ref `ref_558` # VERIFY: may be numeric |

---

## Section 3: Lead Assessment (BANT)

| #   | Field Label           | Type       | Notes                                                          |
| --- | --------------------- | ---------- | -------------------------------------------------------------- |
| 1   | (Section header text) | Text       | ref `ref_560`                                                  |
| 2   | Budget                | Text input | ref `ref_562`                                                  |
| 3   | Need                  | Text input | ref `ref_564`                                                  |
| 4   | Authority             | Text input | ref `ref_566`                                                  |
| 5   | Time                  | Text input | ref `ref_567` (no separate ref for input visible — `# VERIFY`) |

---

## Section 4: Address Information

| #   | Field Label | Type       |
| --- | ----------- | ---------- |
| 1   | Street      | Text input |
| 2   | State       | Text input |
| 3   | Country     | Text input |
| 4   | City        | Text input |
| 5   | Zip Code    | Text input |

---

## Section 5: Description Information

| #   | Field Label                          | Type                  |
| --- | ------------------------------------ | --------------------- |
| 1   | Description                          | Text input / textarea |
| 2   | Client Feedback after the Site Visit | Text input / textarea |
| 3   | BDM Feedback                         | Text input / textarea |

---

## Section 6: Qualification Form

| #   | Field Label                                                | Type       |
| --- | ---------------------------------------------------------- | ---------- |
| 1   | Does the lead have the financial capability to pur[chase]? | Text input |
| 2   | Does the project match the lead's location prefere[nce]?   | Text input |
| 3   | Who is making the decision for this purchase?              | Text input |
| 4   | When is the lead planning to buy?                          | Text input |

---

## Section 7: Client Feedback

| #   | Field Label   | Type       |
| --- | ------------- | ---------- |
| 1   | Feedback URL  | Text input |
| 2   | Client Rating | Text input |
| 3   | Comments      | Text input |

---

## Section 8: Team Lead Section

| #   | Field Label          | Type       |
| --- | -------------------- | ---------- |
| 1   | Approval for Closure | Text input |

---

## Section 9: Site Visit Information

| #   | Field Label                             | Type       |
| --- | --------------------------------------- | ---------- |
| 1   | Site Visit URL                          | Text input |
| 2   | Client Comments                         | Text input |
| 3   | BDM Form URL                            | Text input |
| 4   | When Are You Planning to Start          | Text input |
| 5   | Visit Status                            | Text input |
| 6   | Site Visit Location                     | Text input |
| 7   | Site Visit Date                         | Text input |
| 8   | BDM                                     | Text input |
| 9   | Is There is Any Other Specific Concerns | Text input |

---

## Section 10: Site Completion Form Submission

| #   | Field Label                                  | Type       |
| --- | -------------------------------------------- | ---------- |
| 1   | Visit Date                                   | Text input |
| 2   | Client's Overall Impression                  | Text input |
| 3   | Real Objections                              | Text input |
| 4   | Decision Influencers                         | Text input |
| 5   | Next Committed Step                          | Text input |
| 6   | Follow-up date                               | Text input |
| 7   | Visit Verified                               | Text input |
| 8   | Objection Status                             | Text input |
| 9   | Urgency Level                                | Text input |
| 10  | BDM Notes                                    | Text input |
| 11  | Amenities / Facility Expectation Description | Text input |
| 12  | Other Description                            | Text input |
| 13  | Travel mode / Notes                          | Text input |
| 14  | Location Mismatch Description                | Text input |
| 15  | Timing Description                           | Text input |
| 16  | Loan Delay / Bank Issue Description          | Text input |
| 17  | Need to Discuss with Family Description      | Text input |
| 18  | Competing Project Comparison Description     | Text input |
| 19  | Budget Concern Description                   | Text input |
| 20  | Legal / Approvals Clarification Description  | Text input |

---

## Section 11: Referral Information

| #   | Field Label           | Type       |
| --- | --------------------- | ---------- |
| 1   | Referred By           | Text input |
| 2   | Referred Date         | Text input |
| 3   | Referrer Relationship | Text input |
| 4   | Referral Form URL     | Text input |

---

## Section 12: Centilio Tracking

| #   | Field Label                  | Type |
| --- | ---------------------------- | ---- |
| 1   | First Click Channel          | Text |
| 2   | First Click Campaign         | Text |
| 3   | First Click Term             | Text |
| 4   | First Click Medium           | Text |
| 5   | First Click Content          | Text |
| 6   | First Click Referrer         | Text |
| 7   | First Click Source           | Text |
| 8   | First Click Landing Page     | Text |
| 9   | First Click Landing Page Url | Text |
| 10  | First Click Timestamp        | Text |
| 11  | IP Address                   | Text |
| 12  | City (from IP address)       | Text |
| 13  | Country (from IP address)    | Text |
| 14  | Browser                      | Text |
| 15  | Operating System             | Text |
| 16  | Latitude                     | Text |
| 17  | Longitude                    | Text |
| 18  | Ads Form Name                | Text |
| 19  | Ads Lead Created Time        | Text |
| 20  | Meta Lead Created Time       | Text |
| 21  | Last Click Channel           | Text |
| 22  | Last Click Campaign          | Text |
| 23  | Last Click Term              | Text |
| 24  | Last Click Medium            | Text |
| 25  | Last Click Content           | Text |
| 26  | Last Click Referrer          | Text |
| 27  | Last Click Source            | Text |
| 28  | Last Click Landing Page      | Text |
| 29  | Last Click Landing Page Url  | Text |
| 30  | Last Click Timestamp         | Text |
| 31  | Time Zone                    | Text |
| 32  | GA Client ID                 | Text |
| 33  | GCLID (GA Connector)         | Text |
| 34  | GA Session ID                | Text |
| 35  | GA Measurement ID            | Text |
| 36  | Pages Visited                | Text |
| 37  | All Traffic Sources          | Text |
| 38  | Ads Lead ID                  | Text |
| 39  | Ads Forms ID                 | Text |

---

## Section 13: Internal Use

| #   | Field Label                 | Type            | Notes                                                                    |
| --- | --------------------------- | --------------- | ------------------------------------------------------------------------ |
| 1   | Folder ID                   | Text input      |                                                                          |
| 2   | Folder URL                  | Text input      |                                                                          |
| 3   | Attempt                     | Text input      |                                                                          |
| 4   | Old Created Date            | Text input      |                                                                          |
| 5   | Email Opt Out               | Checkbox        | ref `ref_773`                                                            |
| 6   | Connected To                | Lookup/combobox | ref `ref_776`                                                            |
| 7   | New Contact                 | Toggle/text     | ref `ref_780`                                                            |
| 8   | Lead Owner                  | User lookup     | Has "Open Lead Owner" button; ref `ref_786`; search field "Search Users" |
| 9   | BANT Form URL               | Text input      | ref `ref_797`                                                            |
| 10  | Preferred Project           | Text input      | ref `ref_799`                                                            |
| 11  | Old Status                  | Text input      | ref `ref_801`                                                            |
| 12  | Reason For Unattempted      | Text input      | ref `ref_803`                                                            |
| 13  | Description for Unattempted | Text input      | ref `ref_805`                                                            |

---

## Required Field Validation

- **Last Name** — highlighted with red border on form load (before any interaction)
- **Mobile** — highlighted with red border on form load (before any interaction)
- All other fields: optional (no red border or asterisk visible on load)

---

## Save Behavior

### Save (primary)

- Button label: `Save`
- Color: Blue (solid)
- On click: submits the form
- **Post-save redirect:** Navigates to the newly created Lead's detail view at `/tab/Leads/{record_id}`
- URL observed on list view rows: pattern `/crm/org60043078423/tab/Leads/955332000XXXXXXXXX`

### Save and New

- Button label: `Save and New`
- Color: White / outline
- On click: saves the current record then reloads the blank Create Lead form at same URL

### Cancel

- Button label: `Cancel`
- Color: White / outline
- On click: triggers unsaved changes dialog — "You have not saved your changes. Are you sure you want to move away from this page?" with buttons `Yes, Leave Page` / `Stay Here`
- If confirmed: returns to Leads list view

---

## Post-Creation Automation (triggered by "Welcome" workflow rule)

After save, the following execute automatically:

- Field Update: **Update Attempt Field**
- Field Update: **Update Lead Status**
- Function: **[Lead] Send Welcome Message**
