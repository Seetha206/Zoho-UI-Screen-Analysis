# Step 11 — Client Feedback & Success Capture
# SellBot UI Implementation Plan

> SellBot Step: 11 of 14
> Zoho CRM Source: /contacts/contacts_full_structure.yaml (post-conversion contact) + /deals/deals_full_structure.yaml (closed deal)
> Trigger: After booking/registration is confirmed (Deal status = Closed Won)

---

## 1. SellBot Objective

After a client completes registration (booking confirmed), the BDM or Registration
Executive collects comprehensive feedback via a 28-question structured form.
This captures marketing first impression, CRM experience, site visit quality,
legal/technical confidence, registration process, overall satisfaction, and
testimonial/referral data. Feeds into Step 12 (Referral Program).

---

## 2. Source Zoho CRM Analysis

Post-conversion flow: Lead → Contact → Deal (Closed Won) pattern confirmed from:
- `contacts_full_structure.yaml` (post-lead conversion contact record)
- `deals_full_structure.yaml` (Deal stages ending in Closed Won)
- Contact detail view related lists: Deals, Leads, Notes, Activities

---

## 3. Trigger

```
Trigger: Deal Status → Closed Won (booking confirmed)
Actor: BDM or Registration Executive opens form
URL: /sellbot/deals/{deal_id}/client-feedback/create
Access: BDM, Registration Executive, TL
```

---

## 4. Customer Feedback Form Design

### Header (read-only auto-fill)
| Field | Source |
|---|---|
| Project Name | Deal.Project |
| Customer Name | Contact.Name |
| Mobile Number | Contact.Mobile |
| Date of Registration | Deal.Closing_Date |
| BDM / Executive Name | Deal.BDM_Assigned / current user |

---

### Section A — Marketing First Impression

| Q# | Question | Type | Options |
|---|---|---|---|
| Q1 | How did you first hear about our project? | Single-select | Facebook/Instagram / Google/Website / Real Estate Portal / Referral / Others |
| Q2 | Rate your experience with our marketing materials | Rating scale | 1 (Poor) – 5 (Excellent) |
| Q3 | How clear and informative were the ads/materials? | Single-select | Confusing / Average / Clear / Very Clear |
| Q4 | Did marketing team respond promptly to initial enquiry? | Single-select | Yes / No / Somewhat |

---

### Section B — CRM / Telecalling Experience

| Q# | Question | Type | Options |
|---|---|---|---|
| Q5 | How was your experience with our CRM / telecalling team? | Single-select | Poor / Fair / Good / Excellent |
| Q6 | Did CRM executive explain all project details clearly? | Single-select | Yes / No / Partially |
| Q7 | Was the follow-up frequency appropriate? | Single-select | Too Many Calls / Just Right / Too Few |
| Q8 | How polite and professional was the communication? | Rating scale | 1–5 |

---

### Section C — Site Visit Experience

| Q# | Question | Type | Options |
|---|---|---|---|
| Q9 | Who handled your site visit? (BDM Name) | Open text | — |
| Q10 | Rate your experience at the site visit | Rating scale | 1–5 |
| Q11 | Was the site visit scheduled and coordinated smoothly? | Single-select | Yes / No |
| Q12 | Did you feel any pressure or discomfort during the visit? | Single-select | Yes / No / Slightly |
| Q13 | What impressed you most about the project during your visit? | Open text | — |
| Q14 | What improvements would you suggest for our site visit process? | Open text | — |

---

### Section D — Engineering / Technical Team

| Q# | Question | Type | Options |
|---|---|---|---|
| Q15 | Did our engineering/site team address your queries (layout, soil, approvals)? | Single-select | Yes / No / Partially |
| Q16 | Rate your confidence in the technical quality of the project | Rating scale | 1–5 |
| Q17 | Were you shown/explained project approvals and documents properly? | Single-select | Yes / No / Partially |
| Q18 | Additional comments on technical / site team | Open text | — |

---

### Section E — Registration / Documentation

| Q# | Question | Type | Options |
|---|---|---|---|
| Q19 | Was the registration process smooth and transparent? | Single-select | Yes / No / Delayed |
| Q20 | Rate the coordination during registration | Rating scale | 1–5 |
| Q21 | Did you receive your original documents and receipts promptly? | Single-select | Yes / No |
| Q22 | Suggestions to improve the registration process | Open text | — |

---

### Section F — Overall Experience

| Q# | Question | Type | Options |
|---|---|---|---|
| Q23 | Overall satisfaction (enquiry to registration) | Rating scale | 1 (Very Dissatisfied) – 5 (Highly Satisfied) |
| Q24 | Would you recommend our company/project to others? | Single-select | Definitely / Maybe / No |
| Q25 | Would you like to receive updates on future projects and offers? | Single-select | Yes / No |

---

### Section G — Testimonial & Referral

| Q# | Question | Type | Notes |
|---|---|---|---|
| Q26 | Would you like to give a short written testimonial? | Open text | Optional |
| Q27 | Would you be open to a short video testimonial? | Single-select | Yes / No |
| Q28 | Do you have friends/family interested in similar properties? | Single-select | Yes / No |
| — | Referral 1: Name + Phone | Two text fields | Shown if Q28 = Yes |
| — | Referral 2: Name + Phone | Two text fields | Shown if Q28 = Yes |

---

### Final Acknowledgement
```
Text: "I hereby confirm that the above feedback was given voluntarily and truthfully."
Fields:
  Customer Signature: [digital signature pad]
  BDM / Executive Signature: [digital signature pad]
  Date: [auto: today]
[Submit Feedback]
```

---

## 5. Scoring & Auto-Calculations

```
Overall_Satisfaction_Score: Q23 value (1–5)
Site_Visit_Rating_Avg: average of Q10 + Q16 (1–5)
CRM_Rating_Avg: average of Q5 + Q8 (1–5)
Registration_Rating_Avg: average of Q20 (1–5)
NPS_Indicator: Q24 (Definitely=Promoter, Maybe=Passive, No=Detractor)
```

These scores are stored on the client feedback record and feed into:
- Step 12 referral trigger (satisfaction ≥ 4 OR Q24 = Definitely)
- Step 10 Customer Satisfaction Score widget on dashboard

---

## 6. Post-Submit Automations

```
On form submission:
1. Store numeric scores for analytics
2. If Q27 = Yes → create task: "Schedule Video Testimonial — [Customer Name]"
3. If Q28 = Yes AND referral data entered → create referral lead(s) (Step 12)
4. If Overall_Satisfaction_Score ≥ 4 → trigger Step 12 referral invitation flow
5. Send Thank You WhatsApp to customer:
   "🙏 Thank you for sharing your experience, {{Name}}!
    Your feedback helps us serve better. Wishing you all the best in your new property! 🏡
    [Company Name]"
6. Alert to TL if Overall_Satisfaction_Score ≤ 2 (escalation)
```

---

## 7. Client Feedback Related List

```
On Deal / Contact detail view:
Related List: Client Feedback
Columns: Date | Q23 Score | Q10 Visit Rating | NPS | Referrals Captured | Testimonial
```

---

## 8. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Post-registration feedback | Not structured in Zoho | 28-question form linked to Deal record |
| Numeric score storage | Not present | Q scores stored for dashboard analytics |
| Referral data capture in feedback | Not present | Q28 + referral name/phone → creates referral leads |
| Testimonial capture | Not structured | Q26 (written) + Q27 (video consent) fields |
| Video testimonial task | Not present | Auto-created task if Q27 = Yes |
| NPS tracking | Not present | Q24 → Promoter/Passive/Detractor classification |
| Digital signature on form | Not standard | In-app signature pad for acknowledgement |
