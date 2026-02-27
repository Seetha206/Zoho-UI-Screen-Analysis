# SellBot-360™ Complete Field Inventory
# All modules + all fields required for implementation

> Source: SellBot_Developer_Specific.yml + Zoho CRM reverse-engineering
> Prepared: 2026-02-27

---

## 1. Leads Module — Complete Field List

### Existing Zoho Fields (confirmed via leads_full_structure.yaml)
| Field | Type | Notes |
|---|---|---|
| Lead Name | Text | Mandatory |
| Company | Text | — |
| Title | Picklist | — |
| Phone | Phone | — |
| Mobile | Phone | — |
| Email | Email | — |
| Secondary Email | Email | — |
| Website | URL | — |
| Lead Source | Picklist | Facebook/Google/Referral etc. |
| Lead Status | Picklist | New/Working/Qualified etc. |
| Industry | Picklist | — |
| Annual Revenue | Currency | — |
| No of Employees | Number | — |
| Description | Long text | — |
| Street | Text | — |
| City | Text | — |
| State | Text | — |
| Zip Code | Text | — |
| Country | Text | — |
| Lead Owner | User Lookup | — |
| Created Time | DateTime | Auto |
| Modified Time | DateTime | Auto |
| Created By | User | Auto |
| Modified By | User | Auto |
| Last Activity Time | DateTime | Auto |
| Tag | Multi-select | — |

### Confirmed Custom Fields (from scribe flows + DOM scan)
| Field | Type | Source |
|---|---|---|
| Telecaller | Picklist | lead_create_scribe_flow |
| Language Preference | Picklist | Tamil/English/Telugu/Hindi |
| Client Location | Text | DOM scan |
| Estimated Budget | Currency | DOM scan |

### New Fields Required for SellBot
| Field | Type | Step | Notes |
|---|---|---|---|
| Campaign Name | Text | Step 2 | Ad campaign tracking |
| Property Type Preference | Picklist | Step 2 | Plot/Villa/Apartment/Commercial |
| Budget Range | Picklist | Step 2 | <10L / 10–25L / 25–50L / 50L–1Cr / 1Cr+ |
| Purchase Purpose | Picklist | Step 2 | Self-use / Investment / Both |
| Purchase Timeline | Picklist | Step 2 | Immediate / 3mo / 6mo / 1yr+ |
| Financing Plan | Picklist | Step 2 | Cash / Home Loan / Mix |
| Room Preference | Picklist | Step 2 | 1BHK / 2BHK / 3BHK / Open Plot |
| Lead_Score_Total | Number (hidden) | Step 5 | BANT score: 0–80 |
| Lead_Type | Picklist | Step 5 | Hot / Warm / Cold / Junk |
| TL_Approved_for_Closure | Checkbox | Steps 4,5 | Yes/No |
| Attach_from_Project_Assets | Multi-select | Step 4 | Brochure/Video/Map/Profile/Website |
| Score_Revision_Log | Long text | Step 5 | Audit trail: timestamp+old+new+reason |
| Visit_Status | Picklist | Step 6 | Booked/Rescheduled/Completed/Missed/Cancelled |
| Calendar_Event_ID | Text | Step 6 | Google Calendar event ID |
| Site_Visit_Date | Date | Step 6 | Scheduled visit date |
| Site_Visit_Time | Time | Step 6 | Scheduled visit time |
| BDM_Assigned | Lookup → Employee | Step 6 | BDM handling the visit |
| Reminder_Count | Integer | Step 7 | 0–8 (visit reminders sent) |
| Visit_Verified | Picklist | Step 8 | Yes / Pending |
| Objection_Status | Picklist | Step 8 | Captured / None |
| Objection_Types | Multi-select | Step 8 | 9 objection categories |
| Urgency_Level | Picklist | Step 8 | High / Medium / Low / Not Decided |
| Next_Committed_Step | Picklist | Step 8 | 7 options |
| Referral_Source | Text | Step 12 | "Referrer Name — Phone" |
| In_Nurture_Program | Checkbox | Step 9 | Yes if in 60-day cycle |
| Nurture_Track | Picklist | Step 9 | 7 objection tracks |
| Unsubscribed | Checkbox | Step 14 | Yes if STOP keyword received |
| Unsubscribed_Time | DateTime | Step 14 | Auto on STOP |
| Reactivated | Checkbox | Step 14 | Yes if replied YES to 90-day check-in |

---

## 2. Tasks Module — Complete Field List

### Existing Zoho Fields (confirmed)
| Field | Type | Notes |
|---|---|---|
| Subject | Text | Mandatory |
| Task Owner | User Lookup | — |
| Due Date | Date | DD/MM/YYYY format |
| Start Date | Date | — |
| Status | Picklist | Not Started/Attempt/In Progress/Completed/Deferred/Waiting |
| Priority | Picklist | High / Normal / Low |
| Related To | Lookup | Account or Lead |
| Contact Name | Lookup → Contact | — |
| Description | Long text | — |
| Send Notification | Checkbox | — |
| Hours to Complete | Number | — |
| Task Type | Picklist | — |
| Tag | Multi-select | — |

### Confirmed Custom Fields
| Field | Type | Source |
|---|---|---|
| Telecaller | Picklist | task_create_scribe_flow |
| Approver | Picklist | task_create_scribe_flow |

### New Fields Required for SellBot
| Field | Type | Step | Notes |
|---|---|---|---|
| Task_Category | Picklist | Steps 4,7,9 | Call Attempt / Visit Reminder / Nurture Follow-Up / TL Review |
| Call_Attempt_Number | Integer | Step 4 | 1–5 for call attempt tasks |
| Nurture_Week | Integer | Step 9 | 1–8 for 60-day nurture tasks |
| WA_Sent | Checkbox | Steps 4,7,9 | Yes when WhatsApp triggered |
| WA_Sent_Time | DateTime | Steps 4,7,9 | Auto on WA send |

---

## 3. Site Visit Feedback Sub-Module — All Fields

| Field | Type | Required | Section |
|---|---|---|---|
| Feedback_ID | Auto-number | Auto | — |
| Lead | Lookup → Leads | Yes | (relation) |
| BDM | Lookup → Employee | Yes | Auto |
| Visit_Date | Date | Yes | B |
| Visit_Time | Time | Yes | B |
| Project_Name | Text (auto) | Auto | B |
| Client_Photo_URL | File | Yes | A |
| BDM_Selfie_URL | File | Yes | A |
| Client_Signature_URL | File | No | A |
| Client_Video_URL | File | No | A |
| Visit_Verified | Picklist | Auto | A |
| Geo_Lat | Number | Auto | A |
| Geo_Long | Number | Auto | A |
| Travel_Mode_Notes | Text | No | B |
| Overall_Impression | Picklist | Yes | C |
| Objection_Types | Multi-select | No | D |
| Objection_Notes | Long text | No | D |
| Decision_Influencers | Multi-select | No | E |
| Urgency_Level | Picklist | Yes | F |
| Next_Committed_Step | Picklist | Yes | G |
| Next_Step_Date | Date | No | G |
| BDM_Notes | Long text | No | H |
| Additional_Photos | Multi-file | No | I |
| TL_Override | Checkbox | No | A |
| TL_Override_Reason | Text | No | A |
| TL_Override_By | User | No | Auto |
| Submission_Type | Picklist | Auto | J |

---

## 4. Referral Management Sub-Module — All Fields

| Field | Type | Required | Notes |
|---|---|---|---|
| Referral_ID | Auto-number | Auto | — |
| Referrer | Lookup → Contact | Yes | — |
| Referrer_Name | Text | Yes | — |
| Referrer_Mobile | Phone | Yes | — |
| Referral_Name | Text | Yes | New prospect |
| Referral_Mobile | Phone | Yes | — |
| Referral_Email | Email | No | — |
| Relationship | Picklist | Yes | Friend/Colleague/Family/Neighbour/Other |
| Project_Interested | Picklist | Yes | From Project Assets |
| Referral_Status | Picklist | Auto | New/In Progress/Confirmed/Rewarded |
| Lead_Created | Lookup → Lead | Auto | Auto-linked on lead creation |
| Reward_Type | Text | No | Cash/Gold/Voucher/Discount |
| Reward_Status | Picklist | No | Pending/Processing/Delivered |
| Reward_Amount | Currency | No | — |
| Referred_Date | Date | Auto | Today |

---

## 5. Client Feedback Sub-Module — All Fields

| Field | Type | Notes |
|---|---|---|
| Feedback_ID | Auto-number | — |
| Deal | Lookup → Deals | Post-registration link |
| Contact | Lookup → Contacts | Buyer |
| BDM | Lookup → Employee | Who collected feedback |
| Registration_Date | Date | Auto from Deal |
| Q1_Source | Picklist | — |
| Q2_Marketing_Rating | Integer 1–5 | — |
| Q3_Ad_Clarity | Picklist | — |
| Q4_Response_Time | Picklist | — |
| Q5_CRM_Experience | Picklist | — |
| Q6_Project_Explanation | Picklist | — |
| Q7_Followup_Frequency | Picklist | — |
| Q8_Professionalism | Integer 1–5 | — |
| Q9_BDM_Name | Text | — |
| Q10_Visit_Rating | Integer 1–5 | — |
| Q11_Visit_Scheduling | Picklist | — |
| Q12_Pressure | Picklist | — |
| Q13_Impressed_By | Long text | — |
| Q14_Visit_Improvements | Long text | — |
| Q15_Technical_Queries | Picklist | — |
| Q16_Technical_Confidence | Integer 1–5 | — |
| Q17_Approvals_Explained | Picklist | — |
| Q18_Technical_Comments | Long text | — |
| Q19_Registration_Process | Picklist | — |
| Q20_Registration_Rating | Integer 1–5 | — |
| Q21_Documents_Received | Picklist | — |
| Q22_Registration_Suggestions | Long text | — |
| Q23_Overall_Satisfaction | Integer 1–5 | — |
| Q24_Recommend | Picklist | Definitely/Maybe/No |
| Q25_Future_Updates | Picklist | — |
| Q26_Written_Testimonial | Long text | — |
| Q27_Video_Testimonial | Picklist | Yes/No |
| Q28_Referrals | Picklist | Yes/No |
| Referral1_Name | Text | — |
| Referral1_Phone | Phone | — |
| Referral2_Name | Text | — |
| Referral2_Phone | Phone | — |
| Customer_Signature_URL | File | — |
| BDM_Signature_URL | File | — |
| Submission_Date | Date | Auto |
| Overall_Score_Avg | Decimal | Auto-calculated |
| Site_Visit_Rating_Avg | Decimal | Auto: (Q10+Q16)/2 |
| NPS_Category | Picklist | Promoter/Passive/Detractor |

---

## 6. Projects Portfolio Module — Extended Fields (from Step 1)

### Existing Fields (confirmed from projects_portfolio_full_structure.yaml)
Project Name, Location, Unit Price, Land Area, BHK, Available Plots, Promotor,
Project Features (subform), Competitive Analysis (subform), Target Audience,
Marketing Strategy fields.

### New Fields Required for SellBot
| Field | Type | Notes |
|---|---|---|
| Brochure_PDF | File | 4–6 pages; max 5MB |
| Intro_Video_Link | URL | 1–2 min YouTube/Drive |
| Walkthrough_Video_Link | URL | 2–4 min site tour |
| Google_Map_Link | URL | Direct Maps share link |
| Company_Profile_PDF | File | — |
| Website_URL | URL | — |
| Social_Media_Link_1 | URL | Facebook |
| Social_Media_Link_2 | URL | Instagram |
| Site_Visit_Invitation_Template | Long text | Default WA text |
| Nearby_Project_Comparison_Chart | File | PDF/PNG max 2MB |
| Marketing_Posters | Multi-file | 40–50 images; 1080×1080 |
| Poster_Tags | Multi-select | Festival/Offer/Feature/Update |
| Project_Status | Picklist | Active / Sold Out / Coming Soon |

---

## 7. Employee Portfolio Module — Unchanged (CustomModule5)

All 8 existing employee records retained as-is.
Key fields used by SellBot:
- Employee Name → used in BDM_Assigned and Telecaller dropdowns
- Type → BDM / Telecaller / CEO (determines which dropdown field it populates)
- Mobile → used in WhatsApp templates (BDM Phone)
- Email → used in Google Calendar attendees

No new fields required for Employee Portfolio module.
