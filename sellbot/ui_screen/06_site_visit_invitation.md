# Step 6 — Site Visit Invitation
# SellBot UI Implementation Plan

> SellBot Step: 6 of 14
> Zoho CRM Source: /deals/deals_full_structure.yaml (Blueprint stages) + /task/tasks_full_structure.yaml

---

## 1. SellBot Objective

For Hot/Warm qualified leads, the CRM Executive invites the client to visit the site.
A "Book Site Visit" button on the lead record opens a booking form. On confirmation,
Google Calendar event is created and 3 WhatsApp alerts are sent (to client, BDM, TL).

---

## 2. Source Zoho CRM Analysis

From `deals_full_structure.yaml` — Blueprint stages include "Site Visit" as a stage.
From `tasks_full_structure.yaml` — Call Followup pattern with due dates.
The pattern of date-based task creation (Days 1–8) is already documented.

---

## 3. "Book Site Visit" Button

### 3.1 Location on Lead Record
```
Lead Detail View → Header area (next to Edit button)
Button: [Book Site Visit]  (visible only when Lead_Type = Hot or Warm)
Color: Blue (primary)
```

### 3.2 Site Visit Booking Form
```
URL: /sellbot/leads/{lead_id}/book-site-visit
```

| Field | Type | Required | Notes |
|---|---|---|---|
| Lead Name | Text (read-only) | — | Auto-populated |
| Project Name | Picklist | Yes | Select active project |
| Preferred Date | Date | Yes | Calendar picker; min = tomorrow |
| Preferred Time | Time | Yes | 9 AM – 6 PM; 30-min slots |
| BDM Assigned | User Lookup | Yes | Populated from Employee Portfolio (Type = BDM) |
| Visit Notes | Long text | No | CRM Exec notes for BDM |
| Send WhatsApp Confirmation | Checkbox | Yes | Default: checked |

### 3.3 Form Actions
```
[Confirm & Book Site Visit]  [Cancel]
```
On confirm:
1. Google Calendar event created
2. Visit_Status → "Booked"
3. Calendar_Event_ID stored on lead
4. 3 WhatsApp messages sent (client / BDM / TL)
5. Task created: "Site Visit — [Lead Name]" (due = selected date)
6. Toast: "Site visit booked successfully"

---

## 4. Google Calendar Integration

```
Event Title: "Site Visit — [Lead Name] — [Project Name]"
Date/Time: selected slot
Location: Project Google Map Link (from Project Assets)
Attendees: BDM email + Client email (if available)
Organiser: CRM Executive

Fields stored on Lead:
  Visit_Status = Booked
  Calendar_Event_ID = [Google Calendar event ID]
  Site_Visit_Date = selected date
  Site_Visit_Time = selected time
  BDM_Assigned = selected BDM
```

---

## 5. WhatsApp Templates — Site Visit Booking

### Template 1: Client Confirmation
```
Name: site_visit_invitation_client

🏠 Hi {{Lead Name}}, your site visit is confirmed!

📅 Date: {{Visit Date}}
⏰ Time: {{Visit Time}}
📍 Location: {{Google Map Link}}
👨 Your Guide: {{BDM Name}} ({{BDM Phone}})

Please arrive 10 minutes early for the best experience.
Need to reschedule? Reply RESCHEDULE and we'll arrange another slot.

Looking forward to welcoming you! 🌟
[Company Name]
```

### Template 2: BDM Notification
```
Name: site_visit_confirmation_bdm

📋 New Site Visit Assigned — Action Required

Client: {{Lead Name}} ({{Mobile}})
Date: {{Visit Date}} at {{Visit Time}}
Project: {{Project Name}}
Lead Type: {{Lead_Type}} ({{Lead_Score_Total}} pts)
Notes from CRM: {{Visit Notes}}

Please confirm your availability by replying CONFIRMED.
CRM Dashboard: {{Lead URL}}
```

### Template 3: Team Leader Alert
```
Name: site_visit_confirmation_tl

📊 Site Visit Booked — FYI

Client: {{Lead Name}}
Lead Type: {{Lead_Type}}
Visit: {{Visit Date}} at {{Visit Time}}
BDM: {{BDM Name}}
Project: {{Project Name}}
Booked by: {{CRM Executive Name}}

No action required unless BDM is unavailable.
```

---

## 6. Visit_Status Field — Values & Transitions

```
Field: Visit_Status
Type: Picklist
Values:
  (blank)     → lead not yet invited
  Booked      → visit confirmed
  Rescheduled → original slot changed (see Step 7)
  Completed   → BDM marked visit done (triggers Step 8)
  Missed      → lead did not attend (triggers Step 7 reminder cycle)
  Cancelled   → lead cancelled and not rescheduled
```

---

## 7. List View — Site Visits Dashboard (Filter)

Quick filter on Leads list view:
```
Filter: Visit_Status = Booked → shows upcoming visits
Filter: Visit_Status = Missed → shows missed visits
Filter: BDM_Assigned = [current user] → BDM's own visits
```

Dashboard cards (Step 10):
- Upcoming Visits (next 7 days)
- Missed Visits (Visit_Status = Missed)
- Visits Completed (this week)
- Visit → Booking Conversion Rate

---

## 8. Reschedule Flow (Basic — full detail in Step 7)

```
Trigger: Client replies RESCHEDULE to WhatsApp
         OR CRM Exec clicks "Reschedule" on Lead detail view
Action:
  1. Open Reschedule form (same as booking form, pre-filled)
  2. On confirm:
     a. Update Calendar_Event_ID (cancel old event, create new)
     b. Tag old event: "Rescheduled by Client"
     c. Visit_Status → Rescheduled
     d. Send new confirmation WA to client + BDM
```

---

## 9. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| "Book Site Visit" button | Not present (manual task creation) | Dedicated button on Lead detail view |
| Visit_Status field | Not present | New picklist (Booked/Rescheduled/Completed/Missed) |
| Calendar_Event_ID field | Not present | New text field storing Google Calendar event ID |
| Google Calendar integration | Not in Zoho CRM directly | New: Google Calendar API on booking confirmation |
| 3 WhatsApp alerts | Not in Zoho | WATI templates: client + BDM + TL |
| Site Visit task auto-creation | Manual in Zoho | Auto-created on booking (Subject: "Site Visit — [Lead Name]") |
| BDM assignment on visit | Through Employee Portfolio lookup | Same — dropdown from Employee Portfolio (Type=BDM) |
