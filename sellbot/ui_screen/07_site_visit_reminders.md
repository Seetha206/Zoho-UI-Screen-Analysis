# Step 7 — Site Visit Confirmation & Reminders
# SellBot UI Implementation Plan

> SellBot Step: 7 of 14
> Zoho CRM Source: /task/tasks_full_structure.yaml (8-task pattern) + /leads/leads_full_structure.yaml

---

## 1. SellBot Objective

After a site visit is booked (Step 6), ensure the lead actually attends. Send a 24-hour
pre-visit reminder. If visit is missed, run an 8-week automated follow-up cycle
(one WhatsApp + one CRM task per week). After 8 weeks, create a TL review task.

---

## 2. Source Zoho CRM Analysis

From `tasks_full_structure.yaml`:
- SellBot_360_integration section: hot_lead_followup = 8 tasks over 60 days
- "Call Followup" tasks (rows 5–10 of records_sample) confirm the daily pattern
- Task create form confirmed: Due Date (DD/MM/YYYY), Priority, Status
- Tasks related list sidebar: Notes only (very limited — reminder tasks work as standalone)

---

## 3. Automation Timeline

```
Visit Booked (Day 0)
    │
    ├── Day of Visit – 1 day: 24hr reminder WhatsApp sent
    │
    └── Visit Day:
            ├── BDM marks "Completed" → triggers Step 8
            └── Visit NOT completed:
                  │
                  └── Next day: "Missed Visit" WhatsApp sent
                        │
                        └── Week 1 task created (CRM Executive)
                              │
                              └── Weeks 2–7: weekly WhatsApp + task
                                    │
                                    └── Week 8: Final reminder + TL Review task
```

---

## 4. Reminder_Count Field

```
Field: Reminder_Count
Type: Integer (auto-incremented by automation)
Initial value: 0
Increments: +1 each time a weekly reminder is sent (Weeks 1–8)
Max: 8
After 8: Create TL Review task; stop weekly automation
```

---

## 5. Pre-Visit Reminder (24 Hours Before)

### Automation Rule
```
Trigger: Visit_Date – 1 day (scheduled)
Condition: Visit_Status = Booked OR Rescheduled
Action: Send WhatsApp → reminder_24hr template
```

### WhatsApp Template: reminder_24hr
```
🌞 Hi {{Lead Name}}, just a reminder about your site visit tomorrow
({{Visit Date}} at {{Visit Time}}).

Please arrive 10 minutes early for a comfortable experience 🚗.
📍 {{Google Map Link}}

Need to change time? Reply RESCHEDULE and we'll sort it immediately.

Looking forward to seeing you! 😊
[Company Name]
```

---

## 6. Missed Visit Flow

### Automation Rule
```
Trigger: End of Visit Date + 3 hours
Condition: Visit_Status ≠ Completed
Action:
  1. Visit_Status → Missed
  2. Send WhatsApp → missed_visit_next_day template
  3. Create Task: "Week 1 Follow-Up — [Lead Name]"
     Due: Tomorrow
     Owner: CRM Executive
     Priority: High
  4. Reminder_Count = 1
```

### WhatsApp Template: missed_visit_next_day
```
👋 Hi {{Lead Name}}, we noticed you couldn't attend your site visit yesterday.
Would you like to book another slot?

Just reply YES and we'll reconfirm immediately. 📅
[Company Name]
```

---

## 7. 8-Week Follow-Up Cycle

### Task Auto-Creation Pattern
Each week creates one task for the CRM Executive:

| Week | Task Subject | Due Date | WhatsApp Template |
|---|---|---|---|
| 1 | Week 1 Follow-Up — [Lead Name] | Missed + 1 day | missed_visit_next_day |
| 2 | Week 2 Follow-Up — [Lead Name] | Missed + 7 days | weekly_reminder_weeks_2_7 |
| 3 | Week 3 Follow-Up — [Lead Name] | Missed + 14 days | weekly_reminder_weeks_2_7 |
| 4 | Week 4 Follow-Up — [Lead Name] | Missed + 21 days | weekly_reminder_weeks_2_7 |
| 5 | Week 5 Follow-Up — [Lead Name] | Missed + 28 days | weekly_reminder_weeks_2_7 |
| 6 | Week 6 Follow-Up — [Lead Name] | Missed + 35 days | weekly_reminder_weeks_2_7 |
| 7 | Week 7 Follow-Up — [Lead Name] | Missed + 42 days | weekly_reminder_weeks_2_7 |
| 8 | Week 8 Final — [Lead Name] | Missed + 49 days | final_reminder_week_8 |
| — | TL Review — [Lead Name] | After Week 8 | (internal WA to TL) |

### Weekly WhatsApp: weekly_reminder_weeks_2_7
```
🌟 Hi {{Lead Name}}, hope you're doing well!

We'd love to welcome you for your site visit to [Project Name] this week.
Reply VISIT to choose a new date 📅.

[Company Name]
```

### Week 8 Final: final_reminder_week_8
```
🙏 Hi {{Lead Name}}, this is our final follow-up for your pending site visit.

If you'd still like to schedule it, reply YES and our team will book it for you.
Otherwise, we'll pause reminders and keep you posted on future projects.

Thank you for considering [Company Name]. 🙏
```

---

## 8. TL Review Task (After Week 8)

```
Condition: Reminder_Count = 8 AND Visit_Status ≠ Completed
Task Subject: "TL Review — Pending Visit (8 Weeks): [Lead Name]"
Task Owner: Team Leader
Due: Week 8 task date + 1 day
Priority: High

TL Options on task:
  - Reschedule (create new visit booking)
  - Move to Nurture (enroll in Step 14 long-term list)
  - Close (Lead_Type → Junk; TL_Approved_for_Closure = Yes)
```

---

## 9. Reschedule via WhatsApp Reply

If client replies RESCHEDULE to any reminder:
```
Incoming keyword: RESCHEDULE
CRM Action:
  1. Create task for CRM Executive: "Client wants to reschedule — [Lead Name]"
     Due: Today
  2. Send WhatsApp: "Hi {{Name}}, noted! Our team will call you shortly to pick a new date."
  3. CRM Exec opens Reschedule form → books new slot
  4. New Google Calendar event created; old event auto-cancelled
  5. Visit_Status → Rescheduled
  6. Reminder_Count reset to 0 (restart 24hr reminder from new date)
```

---

## 10. Dashboard Cards (Step 10 preview)

```
"Upcoming Visits"    → Visit_Status = Booked, Visit_Date ≥ today
"Missed Visits"      → Visit_Status = Missed, Reminder_Count < 8
"Reminders Sent"     → sum of Reminder_Count across all leads
"Conversion Rate"    → Visit Completed / Total Visits Booked × 100
```

---

## 11. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| 24hr reminder | Manual task in Zoho | Auto-trigger from Visit_Date – 1 day |
| Reminder_Count | Not present | New integer field; auto-incremented |
| 8-week task cycle | Hot_lead_followup (8 tasks) confirmed | Triggered by missed visit; weekly spacing |
| WhatsApp per week | Not in Zoho | WATI automation: weekly_reminder template |
| TL Review after 8 weeks | Manual | Auto-create TL review task at Week 8 |
| RESCHEDULE keyword handler | Not in Zoho | WATI keyword → CRM task creation |
| Visit_Status transitions | Not present | Booked → Missed → (per TL decision) |
