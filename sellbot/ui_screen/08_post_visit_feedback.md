# Step 8 — Post-Visit Feedback & Objection Capture
# SellBot UI Implementation Plan

> SellBot Step: 8 of 14
> Zoho CRM Source: /deals/deals_full_structure.yaml + /contacts/contacts_full_structure.yaml (sub-form pattern)
> New sub-module: Site_Visit_Feedback (linked to Lead record)

---

## 1. SellBot Objective

The moment a BDM taps "Mark Visit Completed", a mobile-friendly feedback form opens.
The BDM captures: proof photos (camera-only, geotagged), overall impression,
specific objections, urgency level, next committed step, and BDM notes.
This feeds Step 9's 60-day objection-resolution track.

---

## 2. Source Zoho CRM Analysis

Pattern from `deals_full_structure.yaml` (detail view sub-forms) and
`contacts_full_structure.yaml` (related module sub-form approach).
The Site_Visit_Feedback is a new sub-module linked via Related List on the Lead record.
Related list pattern confirmed across all modules (Notes, Activities, Emails).

---

## 3. "Mark Visit Completed" Button

### 3.1 Location
```
Lead Detail View → Site Visit task row (Related Tasks section)
                OR BDM mobile app header button for active visit day
Button: [Mark Visit Completed]  (appears when Visit_Status = Booked and Visit_Date = today)
Color: Green (success)
Role: BDM only
```

### 3.2 Trigger
```
BDM taps "Mark Visit Completed"
→ Visit Feedback Form opens (full-screen mobile)
→ BDM must complete form before navigation away
→ Navigation guard: "Complete visit feedback before leaving this page"
```

---

## 4. Site Visit Feedback Form

### 4.1 URL
```
/sellbot/leads/{lead_id}/visit-feedback/create
Module: Site_Visit_Feedback (sub-module, related to Leads)
Access: BDM (form entry) | CRM Executive (review) | TL (override, audit)
```

### 4.2 Section A — Visit Verification (Proof)

| Field | Type | Required | Capture Method | Notes |
|---|---|---|---|---|
| Client Photo at Site | Camera capture | YES | Device camera only (no gallery) | Geotag + timestamp auto-stored |
| BDM + Client Selfie | Camera capture | YES | Device camera only | Clear faces required |
| Client Signature | Signature pad | No | In-app digital signature | Optional |
| Client Short Video | Video capture | No | Max 20 seconds | Script: "I am [Name]. I visited [Project] today." |
| Auto Proof Status | System field | — | Auto-computed | Verified = both photos present; Pending = missing |

```
Proof Validation Logic:
  IF Client_Photo AND BDM_Selfie both present → Visit_Verified = Yes → allow Save
  ELSE → Visit_Verified = Pending → block Save (show error: "Photos required")
           BDM can tap "Request TL Override" → TL reviews + approves
```

### 4.3 Section B — Visit Meta

| Field | Type | Required | Notes |
|---|---|---|---|
| Visit Date | Date | Yes | Default: today; editable |
| Visit Time | Time | Yes | Default: current time |
| BDM Name | Text (read-only) | — | Auto: current logged-in BDM |
| CRM Executive | Text (read-only) | — | Auto: assigned CRM Exec from Lead |
| Project Name | Text (read-only) | — | Auto: from Lead record |
| Google Map Link | URL (read-only) | — | Auto: from Project Assets |
| Travel Mode / Notes | Text | No | Optional BDM field |

### 4.4 Section C — Overall Impression

```
Field: Overall_Impression
Type: Single-select (large tap buttons — mobile-friendly)
Options:
  🥰 Loved It
  😐 Okay
  😞 Disappointed
  🤷 Couldn't Assess (bad weather / timing / closed)
Required: Yes
```

### 4.5 Section D — Objections Captured

```
Field: Objection_Types
Type: Multi-select + description per selected item
Options (checkboxes):
  □ Location Mismatch         → text: "Describe the concern"
  □ Budget Concern            → text: "State gap or benchmark"
  □ Loan / Bank Issue         → text: "Bank name / doc pending"
  □ Family Discussion         → text: "Who must approve (spouse/parents/other)"
  □ Legal Approvals           → text: "Which doc (RERA/DTCP/EC/Patta/etc.)"
  □ Amenities / Facilities    → text: "Which amenity"
  □ Competing Project         → text: "Project name / point compared"
  □ Timing Delay              → text: "Expected month/quarter"
  □ Other                     → text: "Free text"
Required: At least mark if any objection exists
```

### 4.6 Section E — Decision Influencers

```
Field: Decision_Influencers
Type: Multi-select
Options: Self | Spouse | Parents | Siblings | Friends | Consultant | Other
```

### 4.7 Section F — Urgency Level

```
Field: Urgency_Level (on Lead — updated by this form)
Type: Single-select
Options:
  🔴 High (0–30 days)
  🟡 Medium (1–3 months)
  🔵 Low (3–6 months+)
  ⚫ Not Decided
Required: Yes
```

### 4.8 Section G — Next Committed Step

```
Field: Next_Committed_Step
Type: Single-select + date
Options:
  Second Site Visit (family)          → date: in X days
  Loan Discussion / Document Collect  → date: in X days
  Share Legal Documents               → date: in X days
  Price / Unit Options Discussion     → date: in X days
  Hold Unit (tentative)               → date: —
  Open House Invite                   → date: event date
  Follow-up in X Days                 → date: selector
Required: Yes (choose one)
```

### 4.9 Section H — BDM Notes

```
Field: BDM_Notes
Type: Long text (free text)
Placeholder: "Key quotes, emotional cues, special requests..."
Example: "Client liked location but wants 3BHK. Will visit with wife next weekend."
```

### 4.10 Section I — Additional Attachments

```
Field: Additional_Attachments
Type: Multi-file (max 3 photos OR doc snapshot)
Options: Photos (max 3) | Doc snapshot (PAN/Aadhaar/Pre-approval letter)
Required: No
```

### 4.11 Section J — Submission Controls

```
[Save & Send Thank-You]   — triggers all automations (primary action)
[Save Draft]              — TL sees draft on dashboard; no automations fired
[Request TL Override]     — when proof is incomplete; opens TL notification modal
```

---

## 5. Automations on Form Submit

### 5.1 Field Updates on Lead Record
```
Visit_Status → Completed
Visit_Verified → Yes / Pending (per proof logic)
Objection_Status → Captured (if any objections) / None
Urgency_Level → value from form
Next_Committed_Step → value from form
```

### 5.2 Thank-You WhatsApp to Client
```
Template: post_visit_thankyou

🙏 Hi {{Lead Name}}, thank you for visiting [Project Name] today.
We appreciate your time and hope the visit was helpful.
If you'd like to plan a second visit with family, discuss options, or review documents,
just reply HELP and our team will assist right away.
We're here to make this simple and transparent for you. 😊
[Company Name]
```

### 5.3 Next Step Confirmation WhatsApp
```
Template: post_visit_nextstep_confirm

📅 Hi {{Lead Name}}, we've noted your next step: {{Next_Committed_Step}} on {{Date}}.
Our team will call you to coordinate and ensure everything is ready.
If you wish to change the date/time, reply RESCHEDULE.
[Company Name]
```

### 5.4 Internal Notifications

**To CRM Executive:**
```
✅ Site Visit Completed – {{Lead Name}} ({{Mobile}})
Impression: {{Overall_Impression}}
Objection(s): {{Objection_Types}}
Next Step: {{Next_Committed_Step}} by {{Date}}
Proof: {{Visit_Verified}}
Please action the task(s) created.
```

**To Team Leader:**
```
🧭 Visit Logged – {{Lead Name}} / {{Project Name}} by {{BDM Name}}
Proof: {{Visit_Verified}} | Objection: {{Objection_Types}}
SLA Tasks created: [task list]
Review exceptions if any (Pending Proof / TL Override requests).
```

### 5.5 Follow-Up Task Auto-Creation (per Next Committed Step)

| Next Step Selected | Task Created | Due |
|---|---|---|
| Second Site Visit (family) | "Book Family Visit — [Lead Name]" | +2–5 days |
| Loan / Document Collection | "Collect Documents — [Lead Name]" | +2 days |
| Legal Documents Clarification | "Share Legal Pack / Q&A — [Lead Name]" | +2 days |
| Price / Unit Options | "Present 2–3 Alternatives — [Lead Name]" | +2 days |
| Follow-up in X Days | "Scheduled Follow-up — [Lead Name]" | selected date |

### 5.6 Step 9 Enrollment
```
Condition: Any Objection_Types selected (Objection_Status = Captured)
Action: Enroll lead into Step 9 objection-specific track
        Start_Date = form submission date
        Track determined by primary objection type selected
```

---

## 6. Related List on Lead Record

```
Related List Tab: Site Visit Feedback
Shows: all feedback records for this lead (support multiple visits)
Columns: Visit Date | BDM | Overall Impression | Proof Status | Objections | Next Step
```

---

## 7. Geo-Lock Validation (Optional)

```
Warning: if photo geolocation is >300m from project site pin
Alert text: "Photo location is far from site — are you sure you're at [Project Name]?"
Options: [Yes, I'm at site]  [Retake Photo]
TL flag: if BDM overrides geo-lock, flagged for TL review
```

---

## 8. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Site Visit Feedback form | Not in Zoho (ad-hoc notes) | Full sub-module with 10 sections |
| Camera-only photo capture | Not in Zoho CRM | Enforce device camera; block gallery upload |
| Geotag + timestamp | Not in Zoho | Auto-capture on photo save |
| Objection multi-select | Not structured in Zoho | 9 objection categories + free text |
| Auto next-step task creation | Manual in Zoho | 5 next-step options each auto-create a task |
| Step 9 enrollment on objection | Not in Zoho | Auto-trigger: if Objection_Status = Captured |
| TL Override flow | Manual approval in Zoho | Formal override request modal + TL approval |
| Visit_Verified field | Not present | Auto-computed: client photo + BDM selfie = Yes |
