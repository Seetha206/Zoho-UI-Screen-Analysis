# Step 9 — 60-Day Follow-Up & Nurturing Flow
# SellBot UI Implementation Plan

> SellBot Step: 9 of 14
> Zoho CRM Source: /task/tasks_full_structure.yaml (8-task Sellbot_360 pattern) + /leads/leads_full_structure.yaml

---

## 1. SellBot Objective

After a site visit with objections (Step 8), enroll the lead into a 60-day structured
nurture program. 8 weekly CRM Executive tasks (manual calls) run in parallel with
WhatsApp automation. The track (7 possible) is determined by the primary objection type.
After 60 days, TL decides: Closed / Extended / Move to Long-Term.

---

## 2. Source Zoho CRM Analysis

From `tasks_full_structure.yaml`:
- SellBot_360_integration.hot_lead_followup: 8 tasks over 60 days confirmed
- Tasks list default sort: Due Date ascending (confirmed)
- Task Status: Not Started → Attempt → In Progress → Completed
- Telecaller and Approver custom fields confirmed

---

## 3. Enrollment Trigger

```
Condition: Visit feedback form submitted AND Objection_Status = Captured
Action:
  1. Determine primary objection (first selected in Section D)
  2. Select WhatsApp track (table below)
  3. Create 8 follow-up tasks on Lead record
  4. Set Reminder_Count = 0 (separate from visit reminder count)
  5. Mark Lead: "In 60-Day Nurture Program"
```

---

## 4. Objection → WhatsApp Track Mapping

| Objection Captured | WhatsApp Track | Task Suffix |
|---|---|---|
| Location Mismatch | nurture_location_week_N | "Location Follow-Up" |
| Budget Concern | nurture_budget_week_N | "Budget Follow-Up" |
| Loan / Bank Issue | nurture_loan_week_N | "Loan Follow-Up" |
| Family Discussion | nurture_family_week_N | "Family Follow-Up" |
| Legal Approvals | nurture_legal_week_N | "Legal Follow-Up" |
| Amenities / Facilities | nurture_amenities_week_N | "Amenities Follow-Up" |
| Timing Delay | nurture_timing_week_N | "Timing Follow-Up" |
| Competing Project | (use budget or timing track) | "Comparison Follow-Up" |
| Other | (use timing track) | "General Follow-Up" |

---

## 5. 8-Task Auto-Creation (per Lead, per Enrollment)

```
Task Owner: CRM Executive (assigned to lead)
Related To: Lead record
Telecaller: CRM Executive
Priority: High
Status: Not Started

Schedule:
  Week 1:  Enrollment Day + 0    → "Week 1 [Objection] Follow-Up — [Lead Name]"
  Week 2:  Enrollment Day + 7    → "Week 2 [Objection] Follow-Up — [Lead Name]"
  Week 3:  Enrollment Day + 14   → "Week 3 ..."
  Week 4:  Enrollment Day + 21   → ...
  Week 5:  Enrollment Day + 28   → ...
  Week 6:  Enrollment Day + 35   → ...
  Week 7:  Enrollment Day + 42   → ...
  Week 8:  Enrollment Day + 49   → "Week 8 — Final [Objection] Follow-Up — [Lead Name]"
  After 8: TL Review Task        → "TL 60-Day Review — [Lead Name]"
```

---

## 6. Per-Impression Track Guide (for CRM Executive in-app)

### Track: Loved It
```
Week 1: Confirm next step; share any doc requested; call within 24 hrs
Week 2: Follow up on loan/docs; connect with bank if needed
Week 3: Check family decision; book family visit if needed
Week 4: Share unit options / pricing; negotiate if possible
Week 5: Confirm unit hold; check for new objections
Week 6: Push for booking formality — token amount discussion
Week 7: Follow up on booking paperwork
Week 8: Closure attempt or TL review
```

### Track: Okay
```
Week 1: Understand what was missing; send comparison or updated info
Week 2: Provide clarification (location/amenity/price) via call
Week 3: Share new photos/videos or site progress
Week 4: Offer alternate unit options if possible
Week 5: Reconnect on key objection — address with solution
Week 6: Invite for second visit (soft)
Week 7: Family invite or open house invitation
Week 8: Final attempt or TL review
```

### Track: Disappointed
```
Week 1: Acknowledge concern; apologize if needed; send alternative info
Week 2: Provide detailed clarification on objection type
Week 3: Share third-party validation (legal docs, bank approval)
Week 4: Offer alternate unit / project if available
Week 5: Check if interest recovered
Week 6: One last invite — open house or family visit
Week 7: Final soft follow-up
Week 8: Close or move to long-term nurture (Step 14)
```

---

## 7. CRM Executive Task Detail View (In-App Guide)

Each task in the 60-day cycle shows a context panel:

```
┌──────────────────────────────────────────────────────────┐
│  Week [N] Follow-Up — [Lead Name]                        │
│  Objection: [Budget Concern]   Impression: [Okay]        │
├──────────────────────────────────────────────────────────┤
│  CALL GUIDE:                                             │
│  [Impression-specific script from track above]           │
├──────────────────────────────────────────────────────────┤
│  WhatsApp auto-sent: nurture_budget_week_N ✅            │
│  Reply keyword received: [SHOW OPTIONS / —]              │
├──────────────────────────────────────────────────────────┤
│  After call, update:                                     │
│  [ ] Spoke to client        Date: ______                 │
│  [ ] No answer              Status → Attempt             │
│  [ ] Objection resolved     → Re-qualify (Step 5)        │
│  Notes: _____________________________________________    │
│                                               [Save]     │
└──────────────────────────────────────────────────────────┘
```

---

## 8. WhatsApp Track Summaries

### Location Concern Track (8 weeks — WATI automation)
Week 1: "New schools & road projects near [area]... Reply CALL ME"
Week 2: "Infrastructure growth & travel time improvements... Reply TALK NOW"
Week 3: "Families surprised by area development... Reply YES"
Week 4: "Rapid updates near [Project]... Reply BOOK CALL"
Week 5: "New commercial projects nearby... Reply CALL BACK"
Week 6: "Property values climbing... Reply BOOK CALL"
Week 7: "Area-focus calls for selected clients... Reply JOIN"
Week 8: "Final review call with senior consultant... Reply REVIEW CALL"

### Budget Concern Track (8 weeks)
Week 1: "Flexible options now available... Reply SHOW OPTIONS"
Week 2: "Special offers released... Reply CALL NOW"
Week 3: "Cost vs appreciation discussion... Reply DISCUSS"
Week 4: "Stage-wise payment plans... Reply PLAN CALL"
Week 5: "Bank partnerships active... Reply LOAN HELP"
Week 6: "Price rising after next phase... Reply BOOK CALL"
Week 7: "Custom EMI models... Reply SEND PLAN"
Week 8: "Festive offers coming... Reply PRIORITY CALL"

### Loan / Bank Issue Track (8 weeks)
Week 1: "Finance team can coordinate with your bank... Reply HELP ME"
Week 2: "Missing document? Review in 5 min... Reply CHECK FILE"
Week 3: "Connected with top banks — 48hr approvals... Reply CONNECT"
Week 4: "Hold your unit while loan finalises... Reply HOLD UNIT"
Week 5: "Interest rates revising soon... Reply RATE HELP"
Week 6: "Sanction letter draft preparation... Reply DRAFT CALL"
Week 7: "Approval queues clearing... Reply RESUBMIT"
Week 8: "Bank cleared? Finalise quickly... Reply FINALISE"

### Family Decision Track (8 weeks)
Week 1: "Arrange family visit with CRM... Reply BOOK FAMILY VISIT"
Week 2: "Family seen brochure yet?... Reply TALK TO CRM"
Week 3: "Personalised family walkthroughs... Reply JOIN VISIT"
Week 4: "Consultant for family clarity call... Reply FAMILY CALL"
Week 5: "Explanation in Tamil/English... Reply LANGUAGE CALL"
Week 6: "Hold unit until family finalises... Reply HOLD NOW"
Week 7: "Weekend open house for families... Reply VISIT SLOT"
Week 8: "Whenever family ready, we're here... Reply CONNECT AGAIN"

### Legal / Documentation Track (8 weeks)
Week 1: "Legal consultant can explain personally... Reply LEGAL CALL"
Week 2: "RERA, DTCP & bank approvals ready... Reply SHARE DOCS"
Week 3: "10-min call with documentation expert... Reply BOOK NOW"
Week 4: "Key approval pages review session... Reply REVIEW CALL"
Week 5: "Verified approvals clarification... Reply VERIFY"
Week 6: "Legal partner available this week... Reply LEGAL SLOT"
Week 7: "Lawyer to call directly... Reply LAW CALL"
Week 8: "Legal papers open for viewing... Reply CONTACT LEGAL"

### Amenities / Facilities Track (8 weeks)
Week 1: "Roads, lighting, park development ongoing... Reply SHOW UPDATE"
Week 2: "Park 50% done & streetlights installed... Reply SITE PHOTOS"
Week 3: "Water, EB, drainage nearing completion... Reply ENGINEER CALL"
Week 4: "Amenity timeline walk-through... Reply AMENITY CALL"
Week 5: "Kids' play area ready soon... Reply PLAN VISIT"
Week 6: "80% infra completed... Reply VIEW PLAN"
Week 7: "Progress video call... Reply VIDEO TOUR"
Week 8: "Amenities almost ready — final viewing... Reply FINAL VISIT"

### Timing Delay Track (8 weeks)
Week 1: "Flexible payment options for your timeline... Reply PLAN CALL"
Week 2: "Festive season deals... Reply DEAL CALL"
Week 3: "Block tentative month — no pressure... Reply BLOCK DATE"
Week 4: "Quick catch-up call... Reply CALL BACK"
Week 5: "Values risen this quarter... Reply REVIEW"
Week 6: "Customise plan whenever ready... Reply DISCUSS PLAN"
Week 7: "Best timing discussion... Reply CALL ME"
Week 8: "Latest updates ongoing... Reply CONTACT TEAM"

---

## 9. Reply Keyword → CRM Action Mapping

| Keyword | CRM Action |
|---|---|
| CALL ME / CALL NOW / TALK NOW | Create "Call Back Request" task for CRM Exec (due: today) |
| SHOW OPTIONS / SEND PLAN | Send options email + create "Share Options" task |
| BOOK CALL / BOOK NOW | Open calendar booking form for CRM call |
| HOLD UNIT | Alert TL + create "Unit Hold Request" task |
| JOIN VISIT / VISIT SLOT | Open site visit booking (Step 6 flow) |
| LEGAL CALL / LEGAL SLOT | Create "Legal Q&A" task for CRM Exec |
| HELP | Send WhatsApp menu of options |
| YES | Create "Positive Response" task for CRM Exec |
| STOP | Unsubscribe from automated messages (keep lead record) |

---

## 10. After 60 Days — TL Review Options

```
TL Review Task: "TL 60-Day Review — [Lead Name]"
TL actions:
  1. Close (Junk)    → Lead_Type = Junk; remove from nurture; archive
  2. Extended Nurture → create 4 more weekly tasks (Weeks 9–12)
  3. Move to Long-Term → enroll in Step 14 (90-day re-activation list)
  4. Re-Qualify       → open BANT form (Step 5) with fresh data
```

---

## 11. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| 8-task follow-up cycle | hot_lead_followup: 8 tasks (confirmed) | Triggered by objection capture; uses objection track |
| Objection-specific WA tracks | Not in Zoho | 7 tracks × 8 templates each = 56 templates |
| Reply keyword → task creation | Not in Zoho | WATI webhook → CRM task auto-create |
| CRM task detail call guide | Not in Zoho | Context panel with impression-specific script |
| 60-day TL review | Manual in Zoho | Auto-create TL review task after Week 8 |
| Re-qualification from nurture | Manual in Zoho | "Objection Resolved" button re-opens BANT form |
