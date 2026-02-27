# SellBot-360™ UI Implementation Overview
# Mapping Zoho CRM Reverse-Engineering → SellBot CRM Build

> Organisation: Kurinjee Promoters (org60043078423)
> Source Analysis: /leads/, /contacts/, /deals/, /task/, /accounts/, /employ-porfolio/, /projects-porfolio/
> SellBot Spec: Sellbot-plan/SellBot_Developer_Specific.yml
> Prepared: 2026-02-27

---

## 1. Architecture Summary

SellBot-360™ is a 14-step WhatsApp-driven real estate lead management system.
Every screen, field, and workflow in SellBot maps directly to one or more modules
already reverse-engineered from Kurinjee Promoters' live Zoho CRM instance.

This document is the master index. Each step has a dedicated implementation file
in this folder (`01_project_setup.md` → `14_longterm_engagement.md`).

---

## 2. Zoho CRM Module → SellBot Screen Mapping

| SellBot Step | Title | Source Zoho Module(s) | New in SellBot |
|---|---|---|---|
| Step 1 | Project Setup | Projects Portfolio (CustomModule3) | Digital asset upload fields, video/map links |
| Step 2 | Lead Capture Form | Leads module (create form) | Buyer Preferences section, Campaign_Name field |
| Step 3 | Auto Welcome Message | Leads (automation triggers) | WhatsApp template wiring, email template |
| Step 4 | Lead Assignment & Call Attempts | Tasks (Telecaller/Approver), Employee Portfolio | 5-task auto-creation, Day N WhatsApp per task |
| Step 5 | Lead Qualification (BANT) | Leads (Blueprint, custom fields) | BANT 8-question form, Lead_Score_Total, Lead_Type field |
| Step 6 | Site Visit Invitation | Deals (Blueprint stages), Tasks | Visit_Status field, Google Calendar API, BDM/TL WA alerts |
| Step 7 | Site Visit Confirmation & Reminders | Tasks (Call Followup pattern), Leads | Reminder_Count field, 8-week auto-tasks, reschedule flow |
| Step 8 | Post-Visit Feedback | Deals (detail view), Contacts (sub-form pattern) | Site_Visit_Feedback sub-module, camera-only proof, geo-lock |
| Step 9 | 60-Day Nurturing | Tasks (8-task pattern), Leads | Objection-track WhatsApp sequences (7 tracks × 8 weeks) |
| Step 10 | CRM Dashboard Reporting | Reports/Analytics | 4 dashboard views, KPI cards, PDF auto-export |
| Step 11 | Client Feedback & Success | Contacts (post-conversion), Deals | 28-question feedback form, testimonial + referral capture |
| Step 12 | Referral Program | Leads (new source), Contacts | Referral Management sub-module, reward automation |
| Step 13 | Business Owner Dashboard | All modules (analytics layer) | 10-section master panel, business health score formula |
| Step 14 | Long-Term Engagement | Leads (nurture list), Contacts | 90-day re-activation, festival broadcast automation |

---

## 3. Core Module Architecture

```
PROJECT ASSETS (Step 1)
    │
    ▼
LEADS MODULE ──────────────────────────────────── EMPLOYEE PORTFOLIO
  ├── Lead Capture Form (Step 2)                   ├── CRM Executives
  ├── Auto Welcome (Step 3)                        ├── BDMs
  ├── Assignment + 5 Tasks (Step 4)                └── Telecallers
  ├── BANT Qualification (Step 5)
  ├── Lead_Type: Hot/Warm/Cold/Junk
  └── Blueprint Stages
         │
         ▼ (Hot/Warm leads)
SITE VISIT MODULE (Steps 6–7)
  ├── Google Calendar booking
  ├── Visit_Status field
  └── 8-week reminder cycle
         │
         ▼ (Visit completed)
SITE VISIT FEEDBACK (Step 8)
  ├── Proof capture (photo/geotag)
  ├── Objection capture
  └── → Enroll in Step 9 if objection
         │
         ▼
60-DAY NURTURING TASKS (Step 9)
  └── 8 weekly tasks + objection WhatsApp tracks
         │
         ▼ (Booking confirmed)
DEALS MODULE
  └── Booking → Registration → Closed Won
         │
         ▼
CLIENT FEEDBACK (Step 11) → REFERRAL PROGRAM (Step 12)

DASHBOARDS (Step 10 + Step 13) — overlay entire pipeline
LONG-TERM ENGAGEMENT (Step 14) — runs in parallel forever
```

---

## 4. Confirmed Zoho CRM UI Patterns to Reuse in SellBot

### 4.1 List View Pattern (confirmed across all modules)
- Checkbox column + row options (hover) + sortable columns
- Filter panel (8 operators: is/is not/is empty/is not empty/contains/does not contain/starts with/ends with)
- Sort panel with field selector + Ascending/Descending radio
- Per-page selector: [10, 20, 25, 50, 100, 200]
- Column settings: Manage/Resize/Reset Columns; two-pane Available/Selected layout
- Toolbar: Filter | Sort | Refresh | Create [Module] (split button) | Actions (overflow)

### 4.2 Create/Edit Form Pattern
- Save | Save and New | Cancel buttons (top-right)
- Navigation guard: "You have not saved your changes." → Yes, Leave Page / Stay Here
- Multi-section layout with field groups
- Required fields marked with asterisk (*)
- Lookup fields with user/record selector popup

### 4.3 Detail View Pattern
- Overview tab + Related Lists tab
- Header: Edit | More Options (...) → Clone | Delete | Print Preview
- Delete confirmation modal: title / body / Cancel / Delete (red) buttons
- Toast: "[Module] deleted successfully"
- Recycle bin: record retained 60 days

### 4.4 Delete Confirmation Modal (all modules)
```
Title:  "Delete [Module Name]"
Body:   "Are you sure you want to delete this [module name]?"
Button: Cancel (secondary) | Delete (primary red)
Toast:  "[Module] deleted successfully"
```

### 4.5 Assignment Flow Pattern
- Owner field: user lookup dropdown
- Methods: inline edit (detail view) | edit form | mass update
- Zoho CRM default owner: "Kurinjee Promoters"

---

## 5. SellBot-Specific New Fields (Global Field Inventory)

### Lead Module — New Fields Required
| Field | Type | Values | Step |
|---|---|---|---|
| Lead_Score_Total | Number (hidden) | 0–80 | Step 5 |
| Lead_Type | Picklist | Hot / Warm / Cold / Junk | Step 5 |
| TL_Approved_for_Closure | Checkbox | Yes/No | Step 4 (Day 6) |
| Attach_from_Project_Assets | Multi-select | Brochure/Video/Map/Company Profile/Website | Step 4 |
| Score_Revision_Log | Long text | JSON/Notes | Step 5 |
| Visit_Status | Picklist | Booked / Rescheduled / Completed | Step 6 |
| Calendar_Event_ID | Text | Google Calendar event ID | Step 6 |
| Reminder_Count | Number | 1–8 | Step 7 |
| Visit_Verified | Picklist | Yes / Pending | Step 8 |
| Objection_Status | Picklist | Captured / None | Step 8 |
| Urgency_Level | Picklist | High / Medium / Low / Not Decided | Step 8 |
| Referral_Source | Text | Customer name/mobile | Step 12 |

### Site Visit Feedback Sub-Module — New Fields
| Field | Type | Step |
|---|---|---|
| Client_Photo_URL | File/URL | Step 8 |
| BDM_Selfie_URL | File/URL | Step 8 |
| Client_Signature_URL | File/URL | Step 8 |
| Visit_Date | Date | Step 8 |
| Visit_Time | Time | Step 8 |
| Overall_Impression | Picklist | Step 8 |
| Objection_Types | Multi-select | Step 8 |
| Decision_Influencers | Multi-select | Step 8 |
| Urgency_Level | Picklist | Step 8 |
| Next_Committed_Step | Picklist + Date | Step 8 |
| BDM_Notes | Long text | Step 8 |
| TL_Override | Checkbox | Step 8 |
| TL_Override_Reason | Text | Step 8 |

---

## 6. WhatsApp Template Registry

| Template Name | Trigger | Step |
|---|---|---|
| auto_welcome_message_project | Lead creation | Step 3 |
| call_attempt_day_1 | Task: Call Attempt 1 due | Step 4 |
| call_attempt_day_2 | Task: Call Attempt 2 due | Step 4 |
| call_attempt_day_3 | Task: Call Attempt 3 due | Step 4 |
| call_attempt_day_4 | Task: Call Attempt 4 due | Step 4 |
| call_attempt_day_5 | Task: Call Attempt 5 due | Step 4 |
| hot_lead_qualification | Lead_Type = Hot | Step 5 |
| warm_lead_qualification | Lead_Type = Warm | Step 5 |
| cold_lead_nurture | Lead_Type = Cold | Step 5 |
| site_visit_invitation_client | Visit booked | Step 6 |
| site_visit_confirmation_bdm | Visit booked | Step 6 |
| site_visit_confirmation_tl | Visit booked | Step 6 |
| reminder_24hr | Visit_Date – 1 day | Step 7 |
| missed_visit_next_day | Visit missed | Step 7 |
| weekly_reminder_weeks_2_7 | Reminder_Count = 2–7 | Step 7 |
| final_reminder_week_8 | Reminder_Count = 8 | Step 7 |
| post_visit_thankyou | Visit feedback submitted | Step 8 |
| post_visit_nextstep_confirm | Visit feedback submitted | Step 8 |
| nurture_location_week_1..8 | Objection = location | Step 9 |
| nurture_budget_week_1..8 | Objection = budget | Step 9 |
| nurture_loan_week_1..8 | Objection = loan | Step 9 |
| nurture_family_week_1..8 | Objection = family | Step 9 |
| nurture_legal_week_1..8 | Objection = legal | Step 9 |
| nurture_amenities_week_1..8 | Objection = amenities | Step 9 |
| nurture_timing_week_1..8 | Objection = timing | Step 9 |
| referral_invitation | Feedback score ≥ 4 | Step 12 |
| referral_reward_confirmed | Booking confirmed for referral | Step 12 |

---

## 7. File Index

| File | Content |
|---|---|
| `01_project_setup.md` | Step 1 — Projects Portfolio module redesign for SellBot |
| `02_lead_capture.md` | Step 2 — Lead creation form fields + layout |
| `03_welcome_automation.md` | Step 3 — Auto welcome WhatsApp + email triggers |
| `04_lead_assignment.md` | Step 4 — Assignment + 5 call attempt tasks + TL review |
| `05_lead_qualification.md` | Step 5 — BANT 8-question form + scoring + Lead_Type |
| `06_site_visit_invitation.md` | Step 6 — Site visit booking + Calendar + WA templates |
| `07_site_visit_reminders.md` | Step 7 — 24hr reminder + 8-week follow-up cycle |
| `08_post_visit_feedback.md` | Step 8 — Mobile proof form + objection capture |
| `09_60day_nurturing.md` | Step 9 — 60-day objection-resolution + WA tracks |
| `10_crm_dashboard.md` | Step 10 — 4 dashboard views + monthly PDF report |
| `11_client_feedback.md` | Step 11 — 28-question post-registration feedback form |
| `12_referral_program.md` | Step 12 — Referral capture + reward automation |
| `13_business_owner_dashboard.md` | Step 13 — 10-section master dashboard + health score |
| `14_longterm_engagement.md` | Step 14 — 90-day re-activation + festival broadcasts |
| `field_inventory.md` | Complete field list for all SellBot modules |
