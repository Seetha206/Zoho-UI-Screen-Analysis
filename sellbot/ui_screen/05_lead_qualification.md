# Step 5 — Lead Qualification (BANT Scoring)
# SellBot UI Implementation Plan

> SellBot Step: 5 of 14
> Zoho CRM Source: /leads/leads_full_structure.yaml + /leads/leads_detailed_documentation.md
> Blueprint Stages: Lead Qualification stage confirmed in Zoho leads analysis

---

## 1. SellBot Objective

After at least one successful call, the CRM Executive qualifies the lead using an
8-question BANT framework (Budget, Authority, Need/Location, Timeline). Answers
generate a score (max 80 points) that auto-classifies the lead as Hot/Warm/Cold/Junk
and triggers the correct follow-up automation track.

---

## 2. Source Zoho CRM Analysis

From `leads_full_structure.yaml` (Blueprint section):
- Blueprint stage: "Lead Qualification" confirmed
- Existing custom fields: Estimated Budget, Client Location, Language Preference
- Lead Status values include qualification stages
- BANT framework: Budget Variation, Authority (who decides), Need (location match), Timeline

---

## 3. BANT Qualification Form Design

### 3.1 Access
```
Trigger: CRM Executive opens Lead detail view → clicks "Qualify Lead" button
         (or completes Task "Call Attempt X" and marks as "In Progress")
URL: /sellbot/leads/{lead_id}/qualify
Roles: CRM Executive, Team Leader
```

### 3.2 Section 1 — Budget (B)

| Question | Field | Type | Options | Score |
|---|---|---|---|---|
| Q1: Does the budget match? | Budget_Match | Picklist | Exact Match (+10) / Variation <10% (+8) / Variation 10–20% (+5) / Not Matching (0) | 0–10 |
| Q2: Is financing arranged? | Financing_Status | Picklist | Cash Ready (+10) / Pre-Approved Loan (+8) / Planning Loan (+5) / No Plan (0) | 0–10 |

### 3.3 Section 2 — Authority (A)

| Question | Field | Type | Options | Score |
|---|---|---|---|---|
| Q3: Who is the decision-maker? | Decision_Maker | Picklist | Client Only (+10) / Spouse Together (+8) / Family Consensus (+5) / Not Clear (0) | 0–10 |
| Q4: Is decision-maker involved? | DM_Involved | Picklist | Yes, in call (+10) / Yes, briefed (+7) / No, needs discussion (+3) / Unknown (0) | 0–10 |

### 3.4 Section 3 — Need/Location (N)

| Question | Field | Type | Options | Score |
|---|---|---|---|---|
| Q5: Does location match preference? | Location_Match | Picklist | Exact Match (+10) / Acceptable (+7) / Possible (+4) / Mismatch (0) | 0–10 |
| Q6: Does property type match? | Property_Type_Match | Picklist | Exact Match (+10) / Can Consider (+6) / Unlikely (0) | 0–10 |

### 3.5 Section 4 — Timeline (T)

| Question | Field | Type | Options | Score |
|---|---|---|---|---|
| Q7: Purchase timeline? | Purchase_Timeline | Picklist | Immediate (0–30 days) (+10) / 1–3 months (+8) / 3–6 months (+5) / 6+ months (+2) / Not Decided (0) | 0–10 |
| Q8: Have matched projects? | Matched_Projects | Picklist | 1+ projects match perfectly (+10) / 1 project partially matches (+6) / No match (0) | 0–10 |

**Maximum Score: 80 points**

---

## 4. Scoring Logic

```
Lead_Score_Total = sum of all 8 question scores (0–80)

Lead_Type assignment:
  80–64 (80–100% of 80)  →  Hot   🔴
  63–48 (60–79% of 80)   →  Warm  🟡
  47–32 (40–59% of 80)   →  Cold  🔵
  <32   (<40% of 80)     →  Junk  ⚫

Field: Lead_Score_Total  (hidden — not shown on list view by default)
Field: Lead_Type         (visible — shown in list view column)
```

---

## 5. Lead Type Display

### 5.1 Lead Type Color Coding in List View
```
Hot  → Red badge / tag
Warm → Yellow/Orange badge
Cold → Blue badge
Junk → Grey badge
```

### 5.2 Lead Type Filter (Filter Panel)
```
System filter: "Lead Type" → checkboxes: Hot / Warm / Cold / Junk
Quick filter buttons (toolbar): [Hot] [Warm] [Cold] [Junk]
```

---

## 6. Post-Qualification Automation by Lead Type

### Hot Leads (Score 64–80)
```
Automation: hot_lead_followup
Actions:
  1. Send WhatsApp: hot_lead_qualification template
  2. Create 8 follow-up tasks (one per week, 60 days)
  3. Create Site Visit task immediately (due: today + 2 days)
  4. Notify TL: "Hot lead assigned — [Lead Name]"
  5. Lead Status → "Hot"
```

### Warm Leads (Score 48–63)
```
Automation: warm_lead_followup
Actions:
  1. Send WhatsApp: warm_lead_qualification template
  2. Create 4 follow-up tasks (one per week, 30 days)
  3. Lead Status → "Warm"
```

### Cold Leads (Score 32–47)
```
Actions:
  1. Send WhatsApp: cold_lead_nurture template
  2. Add to long-term nurture list (Step 14)
  3. Lead Status → "Cold"
  4. No immediate tasks; 90-day re-activation (Step 14)
```

### Junk Leads (Score <32)
```
Actions:
  1. Lead Status → "Junk"
  2. TL_Approved_for_Closure: required before final closure
  3. Send polite WhatsApp: "Thank you for your interest..."
  4. Remove from active follow-up queue
```

---

## 7. Knowledge Base Display (in Lead Detail View)

A read-only sidebar panel shows the CRM Executive the scoring guide:

```
┌─────────────────────────────────────────┐
│  BANT Score Reference                   │
├─────────────────────────────────────────┤
│  Q1 Budget Match      → max 10 pts      │
│  Q2 Financing         → max 10 pts      │
│  Q3 Decision Maker    → max 10 pts      │
│  Q4 DM Involvement    → max 10 pts      │
│  Q5 Location Match    → max 10 pts      │
│  Q6 Property Type     → max 10 pts      │
│  Q7 Timeline          → max 10 pts      │
│  Q8 Matched Projects  → max 10 pts      │
├─────────────────────────────────────────┤
│  Hot: 64–80 | Warm: 48–63              │
│  Cold: 32–47 | Junk: <32               │
└─────────────────────────────────────────┘
```

---

## 8. Score Revision Flow

If a CRM Executive needs to revise the score after initial qualification:
```
Button: "Re-Qualify" (on Lead detail view, only visible to TL and CRM Exec)
Action: Opens BANT form pre-filled with previous answers
        After save: appends to Score_Revision_Log field (timestamp + old score + new score + reason)
        Lead_Type updates automatically
```

---

## 9. WhatsApp Templates — Lead Type Notifications

### Hot Lead Template
```
🔥 Hi {{Lead Name}}, great news!

Based on our conversation, we have the perfect property option for you at [Project Name].

Our BDM [BDM Name] will contact you shortly to arrange a personal site visit.
We can't wait to show you the property in person! 🏡

Best regards,
[Company Name]
```

### Warm Lead Template
```
🌟 Hi {{Lead Name}},

Thank you for your time today! We've noted your requirements and have a few
excellent options that may match your needs at [Project Name].

Our team will keep you updated with the best options as they arise.
Feel free to reach out anytime — we're here to help! 😊

[Company Name]
```

### Cold Lead Template
```
👋 Hi {{Lead Name}},

Thank you for your interest in [Project Name].

We'll keep you posted on updates, offers, and new launches that match your
preferences. No pressure — when the time is right, we're here.

Best wishes,
[Company Name]
```

---

## 10. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| BANT form | Not a separate screen; ad-hoc in Zoho | Dedicated 8-question scoring form |
| Lead_Score_Total | Not present | New hidden number field |
| Lead_Type | Not present | New picklist (Hot/Warm/Cold/Junk) with color coding |
| Automation by Lead_Type | Partial (confirmed via leads_overview.md) | Full tracks: Hot (8 tasks/60d), Warm (4 tasks/30d) |
| Knowledge Base display | Not present | BANT score reference sidebar panel |
| Score_Revision_Log | Not present | New long-text field with append-only audit trail |
| Blueprint stage | "Lead Qualification" confirmed | Same stage; BANT form fills it in SellBot |
