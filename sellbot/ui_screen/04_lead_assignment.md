# Step 4 — Lead Assignment & Call Attempts
# SellBot UI Implementation Plan

> SellBot Step: 4 of 14
> Zoho CRM Source: /task/tasks_full_structure.yaml + /employ-porfolio/employee_portfolio_full_structure.yaml
> Confirmed Scribe: task_create_scribe_flow (Steps 1–14) | Telecaller field | Approver field | "Attempt" status

---

## 1. SellBot Objective

When a new lead is assigned to a CRM Executive (Telecaller), the system auto-creates
5 sequential call attempt tasks (one per day, Days 1–5). Each task triggers a WhatsApp
message with optional project asset attachments. If all 5 attempts fail, Day 6 creates
a Team Leader review task. TL must approve closure or reassignment.

---

## 2. Source Zoho CRM Analysis

From `tasks_full_structure.yaml`:
- Tasks module: 4,276 records; default sort = Due Date ascending
- Custom fields confirmed: Telecaller (dropdown: Sumathi, Vijayasri), Approver (dropdown)
- Custom status "Attempt" confirmed via scribe flow (Step 28/14)
- Sellbot_360_integration section documents the exact auto-task pattern
- Task create form sections: Task Information | Status & Priority | Related Records | Description
- Assignment flow: Task Owner + Telecaller (distinct fields)

From `employee_portfolio_full_structure.yaml`:
- 8 employees: 5 BDMs, 2 Telecallers (Sumathi, Vijayasri), 1 CEO
- Employee types: BDM / Telecaller / CEO

---

## 3. Lead Assignment Screen Design

### 3.1 Assignment UI (Lead Edit Form)
```
Section: Related Records
Fields:
  - CRM Executive Assigned: [User Lookup] → default: current user
  - Telecaller: [Dropdown] → populated from Employee Portfolio (Type = Telecaller)
  - BDM Assigned: [Dropdown] → populated from Employee Portfolio (Type = BDM)
```

### 3.2 Assignment Trigger
```
Trigger: Lead Owner / CRM Executive field updated + Save
Condition: Lead is newly assigned (CRM_Executive_Assigned changed)
Action: Auto-create 5 Call Attempt Tasks
```

---

## 4. Auto-Task Creation — 5 Call Attempts

When a lead is assigned, SellBot auto-creates the following tasks:

### Task Template (all 5 share same structure)
```
Task Module: Tasks
Task Owner: CRM Executive (assigned)
Related To: Lead record
Telecaller: CRM Executive (same as owner in SellBot)
Approver: Team Leader
Priority: High
Status: Not Started  (changes to "Attempt" when call made per Zoho custom status)
```

| Task # | Subject | Due Date | WhatsApp Template |
|---|---|---|---|
| 1 | Call Attempt 1 | Assignment Day + 0 (today) | call_attempt_day_1 |
| 2 | Call Attempt 2 | Assignment Day + 1 | call_attempt_day_2 |
| 3 | Call Attempt 3 | Assignment Day + 2 | call_attempt_day_3 |
| 4 | Call Attempt 4 | Assignment Day + 3 | call_attempt_day_4 |
| 5 | Call Attempt 5 | Assignment Day + 4 | call_attempt_day_5 |

### Day 6 — TL Review Task (conditional)
```
Condition: All 5 tasks completed with Status = "Attempt" (no answer)
            AND lead not qualified (no BANT form filled)
Task Subject: "TL Review — Unresponsive Lead: [Lead Name]"
Task Owner: Team Leader
Due: Assignment Day + 5
Field Update on Lead: TL_Approved_for_Closure = pending
```

---

## 5. Task Detail View — Per Call Attempt

### 5.1 Task List Columns (SellBot)
```
Subject | Telecaller | Due Date | Status | Priority | Related Lead | Task Owner
```
(Mirrors Zoho Tasks list view exactly — confirmed from tasks_full_structure.yaml)

### 5.2 Task Status Values (confirmed from Zoho)
- Not Started
- **Attempt** (custom — call made, no answer)
- In Progress
- Completed
- Deferred
- Waiting for Input

### 5.3 Task Detail View Actions
```
Header buttons: Edit | Mark as Closed | More Options (...)
More Options: Clone | Delete | Print Preview
```
(Mirrors Zoho detail_view exactly from tasks_full_structure.yaml)

---

## 6. WhatsApp Templates — Call Attempt Days 1–5

### Day 1 Template: call_attempt_day_1
```
Hi {{Lead Name}} 👋,

Thank you for your enquiry about [Project Name]!

Our CRM executive [CRM Executive Name] will be calling you shortly to discuss
your requirements and share details about the project.

📞 Calling from: [Phone Number]
If you'd like to schedule a convenient time, reply CALL BACK.

Warm regards,
[Company Name]
```

### Day 2 Template: call_attempt_day_2
```
Hi {{Lead Name}}, we tried reaching you yesterday regarding [Project Name].

We have some exciting details to share about the project. 🏡
Could we connect today?

Reply CALL ME and our executive will reach you immediately.
[Company Name]
```

### Day 3 Template: call_attempt_day_3 (+ optional attachment)
```
Hi {{Lead Name}} 🌟,

We've been trying to reach you about [Project Name].

Here's a quick preview while we connect:
[Attach: Brochure PDF / Intro Video — selected from Attach_from_Project_Assets]

Interested in knowing more? Reply YES or call us at [Phone Number].
[Company Name]
```

### Day 4 Template: call_attempt_day_4
```
Hi {{Lead Name}}, we don't want you to miss out on [Project Name].

We still haven't been able to reach you — but the opportunity is still open! 🏠
Please call us at [Phone Number] or reply CONNECT.

[Company Name] — Here when you're ready.
```

### Day 5 Template: call_attempt_day_5
```
Hi {{Lead Name}}, this is our final follow-up attempt for [Project Name].

We understand you may be busy. If you're still interested, just reply YES
and our team will be happy to assist.

If not interested, reply STOP and we'll respect your decision.
[Company Name]
```

---

## 7. Asset Attachment Logic

On each call attempt task, the CRM Executive selects attachments via:
```
Field: Attach_from_Project_Assets (multi-select on Lead record)
Options: Brochure PDF | Intro Video | Walkthrough Video | Google Map | Company Profile | Website
Behaviour: Selected assets are auto-appended to Day 3 / Day 4 WhatsApp template
Default: None (CRM Exec manually selects)
```

---

## 8. TL Review Screen (Day 6)

### TL Review Task — Detail View
```
Task Subject: "TL Review — [Lead Name]"
Related Lead: [link to lead]
TL Actions (inline edit on task):
  - Approve Closure → Lead Status = Junk; TL_Approved_for_Closure = Yes
  - Reassign → change CRM Executive → restart 5-task cycle
  - Extend → add 5 more call attempt tasks
```

### TL Dashboard Card (from Step 10)
```
Widget: Unresponsive Leads (TL Review Pending)
Count: N leads
Click: opens filtered task list (Subject contains "TL Review")
```

---

## 9. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Telecaller field | Confirmed custom field on Tasks | Retain; populate from Employee Portfolio lookup |
| Approver field | Confirmed custom field on Tasks | Retain; default to Team Leader |
| "Attempt" status | Confirmed custom status | Retain |
| 5-task auto-creation | SellBot_360_integration documented in YAML | Implement as workflow rule on lead assignment |
| WhatsApp per task | Not in Zoho Tasks directly | WATI automation: on Task Due Date → send template |
| TL Review Task | Manual in Zoho | Auto-create on Day 6 when 5 attempts = Attempt status |
| TL_Approved_for_Closure field | Not in Zoho | New field on Lead module |
| Asset attachment (WA) | Attach_from_Project_Assets field | Multi-select on Lead, used by Days 3–5 WA |
