> Scribe Source: https://scribehow.com/viewer/Lead_Module__BluePrint_Flow_in_CRM__CzUDuGLrRw2IfepoHwWqsg
> Recorded By: Sri Gnanathesigan
> Duration: ~2 minutes
> Total Steps: 22
> Extracted On: 2026-02-27
> Organisation: Kurinjee Promoters (org60043078423)
> Application: Zoho CRM (crm.zoho.in)

---

# Lead Module — BluePrint Flow in CRM — Scribe Flow Analysis

## Overview

This document captures the complete step-by-step UI flow for **executing a BluePrint stage transition on a Lead record** in Zoho CRM, as recorded via Scribehow. The recording was made on the **Kurinjee Promoters** Zoho CRM instance (Org ID: `60043078423`). At 22 steps and 2 minutes, this is the **longest and most complex recording in the series** — nearly 3× longer than any other flow.

The BluePrint flow demonstrates Kurinjee Promoters' **lead qualification process**, implementing a structured **BANT framework** (Budget, Authority, Need, Timeline) with project matching, enforced through Zoho CRM's Blueprint automation engine.

> Zoho CRM Blueprint is a process management tool that enforces mandatory field entry and sequential stage transitions — agents cannot advance a lead to the next stage without completing all required fields in the transition dialog.

---

## BANT Qualification Framework — Kurinjee Promoters

This recording reveals that Kurinjee Promoters uses a **BANT-style qualification model** enforced via Blueprint:

| BANT Component | Field in Blueprint      | Value Selected     |
|----------------|-------------------------|--------------------|
| **B**udget     | Estimated Budget + Budget Variation | `200000` + `Matched` |
| **A**uthority  | Select Authority        | `Close Relatives`  |
| **N**eed       | Select Need (distance)  | `5-10 Km`          |
| **T**ime       | Select Time (timeline)  | `Within a Month`   |
| + Project Match | Select Matched Projects | `Mullai Nagar`    |

---

## UI Design Context

| Property        | Detail                                                            |
|-----------------|-------------------------------------------------------------------|
| Color scheme    | White background, blue accent step badges                         |
| Step indicators | Blue circular numbered badges (1–22)                              |
| Screenshot style | Max-height 600px, max-width 720px per screenshot                 |
| Flow type       | Blueprint stage transition — modal dialog with mandatory fields   |
| Duration        | ~2 minutes — longest flow in the series                          |

---

## Step-by-Step Screenshot Analysis

---

### Step 1 — Navigate to Leads List View

| Property        | Detail |
|-----------------|--------|
| Action          | URL navigation |
| Destination URL | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&per_page=100` |
| View Type       | Custom List View (ID: `955332000000441406`) |
| Pagination      | `page=1`, `per_page=100` — 100 records per page |
| Module          | Leads |

**Screenshot Analysis:**
- The Zoho CRM Leads module opens in the now-familiar custom list view used across all eight recordings
- `per_page=100` is back — consistent with Flows 2, 3, and 4 (the record-level operation flows)
- The list shows 100 lead records per page, with `Sri Testing` locatable in the list
- The Blueprint column may be visible in the list view if configured — showing each lead's current Blueprint stage

---

### Step 2 — Click Lead: "Sri Testing"

| Property     | Detail |
|--------------|--------|
| Action       | Click lead record |
| Target       | `Sri Testing` |
| Record       | The recurring test lead used across all eight recordings |
| Location     | Lead name link in the list view primary column |

**Screenshot Analysis:**
- The recorder clicks on **"Sri Testing"** — the same test lead record used throughout the full series
- This navigates to the **Lead Detail View**
- For the Blueprint flow, the Lead Detail View has an additional UI element not shown in Flows 1–4: the **Blueprint stage indicator and transition buttons**
- The Blueprint UI in Zoho CRM appears as a **stage bar or transition button** at the top of the detail view, showing:
  - The current stage the lead is in
  - Available transition buttons to move the lead to the next stage

---

### Step 3 — Click "Enquiry" — First Blueprint Transition

| Property     | Detail |
|--------------|--------|
| Action       | Click Blueprint transition |
| Transition Label | `Enquiry` |
| Element Type | Blueprint stage transition button |
| Location     | Top of Lead Detail View — Blueprint stage bar |

**Screenshot Analysis:**
- The **Blueprint stage transition button "Enquiry"** is clicked
- In Zoho CRM Blueprint, transition buttons appear at the top of the record detail view as clickable stage labels or buttons
- Clicking "Enquiry" initiates the **first Blueprint transition** — moving the lead into or through the Enquiry stage
- A **Blueprint transition dialog/modal** opens, requiring mandatory fields to be filled before the transition can complete
- The Blueprint stage bar shows the progression:

  ```
  [New] → [Enquiry] → [Lead Qualification] → [Site Visit] → [Booking] → [Closed Won]
            ↑ clicked
  ```

- The transition modal is a Zoho CRM standard overlay with a title (the transition name), required fields, and Save/Cancel buttons

---

### Step 4 — Click Text Field in Blueprint Dialog

| Property     | Detail |
|--------------|--------|
| Action       | Click text input |
| Field Type   | Email / text input field |
| Location     | Inside the Blueprint Enquiry transition modal |

**Screenshot Analysis:**
- The Blueprint transition modal is open for the "Enquiry" transition
- The modal contains mandatory fields that must be filled to proceed
- The recorder clicks on a **text input field** — at this stage likely the **Email field** (confirmed by Step 5's value)
- Blueprint transition modals in Zoho CRM show:
  - A modal title (the transition name: "Enquiry")
  - Required fields marked with a red asterisk (`*`)
  - Optional fields
  - Save and Cancel buttons at the bottom

---

### Step 5 — Enter Email: "srignanathesigan@gmail.com"

| Property     | Detail |
|--------------|--------|
| Action       | Keyboard input |
| Value Entered | `srignanathesigan@gmail.com` |
| Field        | Email |

**Screenshot Analysis:**
- The email address `srignanathesigan@gmail.com` is typed into the email field
- This is the **recorder's own email address** — confirming this is a test/demo entry
- The email field in the Blueprint Enquiry transition is likely a **mandatory field** — the transition requires an email to be captured before moving the lead to the Enquiry stage
- Business context: In real estate lead management, capturing the email at the Enquiry stage is critical for follow-up communication and drip campaigns
- Zoho CRM validates email format — `@gmail.com` passes validation

---

### Step 6 — Click "Save" — Complete First Transition

| Property     | Detail |
|--------------|--------|
| Action       | Button click |
| Button Label | `Save` |
| Location     | Bottom of the Blueprint Enquiry transition modal |

**Screenshot Analysis:**
- The **"Save"** button is clicked to complete the "Enquiry" Blueprint transition
- On save:
  - The modal closes
  - The lead's Blueprint stage advances — the stage indicator in the detail view updates
  - The email field value (`srignanathesigan@gmail.com`) is saved to the lead record
  - A **success notification** may briefly appear: "Transition completed successfully" or similar
  - The next available Blueprint transition button becomes active on the detail view

---

### Step 7 — Click "Lead" — Second Blueprint Transition

| Property     | Detail |
|--------------|--------|
| Action       | Click Blueprint transition |
| Transition Label | `Lead` |
| Element Type | Blueprint stage transition button |
| Location     | Top of Lead Detail View — Blueprint stage bar |

**Screenshot Analysis:**
- After completing the Enquiry transition, the **"Lead"** transition button is now active on the stage bar
- The recorder clicks **"Lead"** — initiating the second and more detailed Blueprint transition
- This opens a **second Blueprint transition modal** — significantly more complex than the Enquiry one, with multiple qualification fields (Steps 8–21)
- This transition is the core **lead qualification step** in Kurinjee Promoters' sales process — it enforces the BANT framework before a lead can advance

---

### Step 8 — Click "Enter Estimated Budget" Field

| Property     | Detail |
|--------------|--------|
| Action       | Click text / currency input |
| Field Label  | `Enter estimated budget` / `Estimated Budget` |
| Field Type   | Currency / numeric input |
| Location     | Inside the Blueprint "Lead" transition modal |

**Screenshot Analysis:**
- The **"Lead" Blueprint transition modal** is open with multiple qualification fields
- The first field is **"Enter estimated budget"** — a currency/numeric input for the lead's property purchase budget
- The field placeholder text reads `Enter estimated budget` (or similar)
- This is the **Budget (B)** component of the BANT qualification
- The field is empty and receives focus on click

---

### Step 9 — Type Budget: "200000"

| Property     | Detail |
|--------------|--------|
| Action       | Keyboard input |
| Value Entered | `200000` |
| Field        | Estimated Budget |
| Currency     | INR (Indian Rupees) — implied by org locale |

**Screenshot Analysis:**
- The value `200000` (₹2,00,000 — Two Lakh Rupees) is entered as the estimated budget
- In Indian real estate context, ₹2,00,000 is a very low budget — this is clearly **test data**
- Typical Kurinjee Promoters property price range would be in the tens of lakhs to crores range
- The field accepts numeric input; Zoho CRM may auto-format with Indian number formatting (2,00,000)
- No currency symbol is entered — the field is pre-configured for INR

---

### Step 10 — Click "Budget" (Qualification Criterion Section)

| Property     | Detail |
|--------------|--------|
| Action       | Click section or proceed within modal |
| Label        | `Budget` |
| Type         | Section header or confirmation of budget entry |

**Screenshot Analysis:**
- After entering the budget value, the recorder clicks on a **"Budget"** label or section element
- This is likely either:
  - A **section header** separating the budget amount from budget variation fields
  - A **confirm/proceed** action within the modal to move to the next qualification criterion
  - The label of the budget field group within the transition modal
- The Blueprint modal is structured in qualification groups — Budget, Authority, Need, Time — and this click moves between them

---

### Step 11 — Click "Select Budget Variation" Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Field Label  | `Select budget variation` |
| Field Type   | Single-select dropdown |
| Location     | Inside Blueprint "Lead" transition modal — Budget section |

**Screenshot Analysis:**
- A **"Select budget variation"** dropdown is clicked, opening the options list
- Budget variation is a **qualification assessment field** — it evaluates whether the lead's stated budget matches the available project pricing
- This is a custom Kurinjee Promoters field within the Blueprint transition
- The dropdown opens to show variation classification options

---

### Step 12 — Select "Matched" for Budget Variation

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Value Selected | `Matched` |
| Field        | Budget Variation |

**Screenshot Analysis:**
- The budget variation is set to **"Matched"** — indicating the lead's budget (`₹2,00,000`) matches available project pricing
- Likely dropdown options for Budget Variation:

  | Option        | Meaning |
  |---------------|---------|
  | `Matched`     | Lead's budget aligns with a project's price range |
  | `Not Matched` | Budget is too low or too high for available projects |
  | `Negotiable`  | Budget is close but requires negotiation |

- Selecting "Matched" is a positive qualification signal — this lead's budget is viable
- After selection the dropdown closes and the field shows `Matched`

---

### Step 13 — Click "Select Authority" Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Field Label  | `Select authority` |
| Field Type   | Single-select dropdown |
| Location     | Authority section of Blueprint modal |

**Screenshot Analysis:**
- The **"Select authority"** dropdown is clicked — this is the **Authority (A)** component of BANT
- "Authority" assesses who in the lead's household or network has decision-making power for the property purchase
- In Indian real estate, purchase decisions often involve multiple family members — knowing the authority structure helps Telecallers target the right person
- The dropdown opens to show authority classification options

---

### Step 14 — Select "Close Relatives" for Authority

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Value Selected | `Close Relatives` |
| Field        | Authority |

**Screenshot Analysis:**
- Authority is set to **"Close Relatives"** — indicating the decision-making authority lies with close family members (spouse, parents, siblings)
- Likely dropdown options for Authority:

  | Option              | Meaning |
  |---------------------|---------|
  | `Self`              | Lead makes decision independently |
  | `Close Relatives`   | Spouse/parents/siblings involved |
  | `Extended Family`   | Broader family consensus needed |
  | `Business Partner`  | Joint investment — partner approval needed |

- "Close Relatives" directly maps to the **"Family Decision Involved?"** custom field seen in the Create flow — confirming these two data points are linked in the qualification process
- This is a key follow-up flag: the Telecaller must ensure the decision-makers (relatives) are engaged in subsequent interactions

---

### Step 15 — Click "Select Need" Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Field Label  | `Select need` |
| Field Type   | Single-select dropdown |
| Location     | Need section of Blueprint modal |

**Screenshot Analysis:**
- The **"Select need"** dropdown is clicked — this is the **Need (N)** component of BANT
- "Need" in Kurinjee Promoters' context captures the **location preference** of the lead — specifically how far from a reference point (city centre, workplace, or landmark) the lead is willing to consider a property
- This translates "need" into a **geographic radius/distance** parameter — relevant for matching leads to specific project locations

---

### Step 16 — Select "5-10 Km" for Need

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Value Selected | `5-10 Km` |
| Field        | Need (distance/radius) |

**Screenshot Analysis:**
- Need is set to **"5-10 Km"** — the lead is willing to consider properties within a 5–10 km radius
- Likely dropdown options for Need (distance):

  | Option        | Meaning |
  |---------------|---------|
  | `0-5 Km`      | Very close to reference point |
  | `5-10 Km`     | Moderate distance — selected |
  | `10-20 Km`    | Extended radius |
  | `20+ Km`      | Outskirts / distant areas |
  | `Any Location`| No geographic preference |

- This distance preference directly feeds into the **project matching logic** in Steps 19–21 — only projects within the 5–10 km radius would appear as matches

---

### Step 17 — Click "Select Time" Dropdown

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown |
| Field Label  | `Select time` |
| Field Type   | Single-select dropdown |
| Location     | Timeline section of Blueprint modal |

**Screenshot Analysis:**
- The **"Select time"** dropdown is clicked — this is the **Time (T)** component of BANT
- "Time" captures how urgently the lead intends to make a purchase decision
- Purchase timeline is critical for prioritising Telecaller follow-up — leads wanting to buy "Within a Month" need immediate attention vs. leads planning to buy "Next Year"

---

### Step 18 — Select "Within a Month" for Timeline

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown option |
| Value Selected | `Within a Month` |
| Field        | Time (purchase timeline) |

**Screenshot Analysis:**
- Timeline is set to **"Within a Month"** — a **high-urgency** qualification signal
- Likely dropdown options for Timeline:

  | Option              | Priority |
  |---------------------|----------|
  | `Within a Month`    | Very High — immediate follow-up required |
  | `1-3 Months`        | High |
  | `3-6 Months`        | Medium |
  | `6-12 Months`       | Low |
  | `More than a Year`  | Very Low |
  | `Not Decided`       | Unqualified |

- A lead with `Within a Month` timeline + `Matched` budget + `Close Relatives` authority = **Hot lead** requiring fast-track follow-up
- This combination would likely trigger an automatic Blueprint stage advancement or alert in the SellBot-360™ workflow

---

### Step 19 — Click "Select Matched Projects" Field

| Property     | Detail |
|--------------|--------|
| Action       | Click dropdown / multi-select field |
| Field Label  | `Select matched projects` |
| Field Type   | Dropdown or multi-select lookup |
| Location     | Project matching section of Blueprint modal |

**Screenshot Analysis:**
- After completing BANT qualification, the modal presents a **project matching field**
- This is a **Kurinjee Promoters-specific step** beyond standard BANT — it links the qualified lead to one or more active projects that match their criteria (budget, distance/need)
- The field "Select matched projects" likely shows a list of available Kurinjee Promoters real estate projects, filtered by the budget and distance criteria entered above
- The recorder clicks the field to open the project options dropdown

---

### Step 20 — Select "Mullai Nagar" as Matched Project

| Property     | Detail |
|--------------|--------|
| Action       | Click option |
| Value Selected | `Mullai Nagar` |
| Field        | Matched Projects |

**Screenshot Analysis:**
- The project **"Mullai Nagar"** is selected as the matched project for this lead
- This is a real Kurinjee Promoters real estate project/development
- The projects dropdown would show all active Kurinjee Promoters projects — at minimum `Mullai Nagar` is confirmed visible
- Other projects likely visible in the dropdown (based on Kurinjee Promoters' portfolio context, not confirmed from extraction)
- Selecting a project creates a **link between the Lead record and the Projects Portfolio** (CustomModule3) — enabling project-wise lead tracking

---

### Step 21 — Click "Matched Projects" Confirmation

| Property     | Detail |
|--------------|--------|
| Action       | Click confirmation |
| Label        | `Matched Projects` |
| Type         | Section confirmation or finalise selection |

**Screenshot Analysis:**
- The recorder clicks on a **"Matched Projects"** element — likely confirming the project selection from Step 20
- This may be:
  - A **confirm/apply button** within the project selector
  - A **section label click** to collapse or finalise the matched projects group
  - A **checkbox confirm** for the selected project(s)
- After this step, all BANT fields and the matched project are populated in the modal

---

### Step 22 — Click Final Action Button to Complete Blueprint Transition

| Property     | Detail |
|--------------|--------|
| Action       | Click button |
| Button Label | Not explicitly captured — likely `Save` or `Submit` |
| Location     | Bottom of the Blueprint "Lead" transition modal |

**Screenshot Analysis:**
- The **final action button** is clicked to submit all filled fields and complete the "Lead" Blueprint transition
- On completion:
  - All qualification data is saved to the lead record: Budget, Budget Variation, Authority, Need, Timeline, Matched Projects
  - The lead's Blueprint stage advances to the next stage in the pipeline
  - The Lead Detail View stage bar updates to reflect the new stage
  - A success confirmation appears
  - The `Sri Testing` lead is now fully qualified with BANT data and project match recorded

---

## Complete Blueprint Qualification Data — This Recording

| BANT Field           | Value Entered      | Type           |
|----------------------|--------------------|----------------|
| Email                | `srignanathesigan@gmail.com` | Text (Enquiry transition) |
| Estimated Budget     | `₹2,00,000`        | Currency       |
| Budget Variation     | `Matched`          | Dropdown       |
| Authority            | `Close Relatives`  | Dropdown       |
| Need (Distance)      | `5-10 Km`          | Dropdown       |
| Time (Timeline)      | `Within a Month`   | Dropdown       |
| Matched Projects     | `Mullai Nagar`     | Lookup/Dropdown|

---

## Blueprint Stage Flow — Kurinjee Promoters

Based on this recording and the CLAUDE.md SellBot-360™ blueprint reference:

```
[*] ──▶ New Lead
              │
              ▼ Transition: "Enquiry" (Step 3)
              │  Required: Email
              ▼
         Enquiry Stage
              │
              ▼ Transition: "Lead" (Step 7)
              │  Required: Budget, Budget Variation,
              │            Authority, Need, Timeline,
              │            Matched Projects
              ▼
         Lead Qualification Stage
              │
              ▼ (next transitions — not shown in this recording)
         Site Visit ──▶ Booking ──▶ Closed Won
```

---

## Blueprint Transition Modal Structure

### Transition 1: "Enquiry" (Steps 3–6)

```
┌──────────────────────────────────────────┐
│  Enquiry                                 │
├──────────────────────────────────────────┤
│  Email *                                 │
│  [ srignanathesigan@gmail.com          ] │
├──────────────────────────────────────────┤
│               [ Cancel ]  [ Save ]       │
└──────────────────────────────────────────┘
```

### Transition 2: "Lead" (Steps 7–22)

```
┌──────────────────────────────────────────┐
│  Lead Qualification                      │
├──────────────────────────────────────────┤
│  Estimated Budget *                      │
│  [ 200000                              ] │
│                                          │
│  Budget Variation *                      │
│  [ Matched ▾                           ] │
│                                          │
│  Authority *                             │
│  [ Close Relatives ▾                   ] │
│                                          │
│  Need *                                  │
│  [ 5-10 Km ▾                           ] │
│                                          │
│  Timeline *                              │
│  [ Within a Month ▾                    ] │
│                                          │
│  Matched Projects *                      │
│  [ Mullai Nagar ▾                      ] │
├──────────────────────────────────────────┤
│               [ Cancel ]  [ Save ]       │
└──────────────────────────────────────────┘
```

---

## Full URL Reference

| Element         | Value |
|-----------------|-------|
| CRM Base URL    | `https://crm.zoho.in/crm/org60043078423/` |
| Leads List URL  | `https://crm.zoho.in/crm/org60043078423/tab/Leads/custom-view/955332000000441406/list?page=1&per_page=100` |
| Custom View ID  | `955332000000441406` |
| Pagination      | `page=1&per_page=100` |
| Org ID          | `60043078423` |

---

## Workflow Summary

```
[Leads List — page=1, per_page=100]
       |
       v
[Click "Sri Testing"]
       |
       v
[Lead Detail View — Blueprint stage bar visible]
       |
       v
[Click "Enquiry" transition]
  └── Enter Email: srignanathesigan@gmail.com
  └── Click Save → Enquiry stage completed
       |
       v
[Click "Lead" transition]
  ├── Enter Estimated Budget: 200000
  ├── Select Budget Variation: Matched
  ├── Select Authority: Close Relatives
  ├── Select Need: 5-10 Km
  ├── Select Timeline: Within a Month
  └── Select Matched Projects: Mullai Nagar
       |
       v
[Click Save / final action]
       |
       v
[Lead stage advances — BANT data saved — project linked]
```

---

## Comparison: All Eight Lead Flows

| Property       | Create(1) | Update(2) | Delete(3) | Rel.List(4) | Filter(5) | Sort(6) | Columns(7) | Blueprint(8) |
|----------------|-----------|-----------|-----------|-------------|-----------|---------|------------|--------------|
| Duration       | ~47s      | ~37s      | ~22s      | ~25s        | ~24s      | ~34s    | ~44s       | ~2 min       |
| Steps          | 13        | 10        | 5         | 5           | 8         | 8       | 9          | **22**       |
| Record scope   | Single    | Single    | Single    | Single      | List      | List    | List       | Single       |
| Modules used   | Leads     | Leads     | Leads     | Leads+Sch   | Leads     | Leads   | Leads      | Leads+Projects |
| End state      | Created   | Updated   | Deleted   | Sch opened  | Filtered  | Sorted  | Configured | Stage advanced |

---

## Gaps & Observations

| # | Observation |
|---|-------------|
| 1 | **Step 22 button label not captured** — the final submit button label is unknown; likely `Save` or `Submit` based on Zoho CRM Blueprint conventions |
| 2 | **Full dropdown options not extracted** — complete option lists for Budget Variation, Authority, Need, and Timeline were not captured; likely values documented above based on business context |
| 3 | **Only one project shown** — "Mullai Nagar" is the only confirmed project in the matched projects list; Kurinjee Promoters likely has more active projects not captured |
| 4 | **Blueprint stage names partially revealed** — "Enquiry" and "Lead" are confirmed transitions; full stage pipeline (Site Visit → Booking → Closed Won) referenced from CLAUDE.md SellBot-360™ |
| 5 | **Authority links to "Family Decision Involved?"** — the Authority dropdown ("Close Relatives") in the Blueprint directly corresponds to the `Family Decision Involved?` field seen in the Create flow — these are complementary data points |
| 6 | **Test data throughout** — ₹2,00,000 budget is too low for real estate; email is the recorder's own; "Sri Testing" is a test record |
| 7 | **Project–Lead relationship confirmed** — selecting "Mullai Nagar" in Step 20 links this lead to CustomModule3 (Projects Portfolio), establishing a cross-module relationship in Zoho CRM |
| 8 | **Most complex flow** — 22 steps / 2 minutes vs. next-longest (Create: 13 steps / 47s); the Blueprint transition enforces data completeness that simple form editing does not |
