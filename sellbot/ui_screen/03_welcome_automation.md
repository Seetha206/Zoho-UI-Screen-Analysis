# Step 3 — Auto Welcome Message
# SellBot UI Implementation Plan

> SellBot Step: 3 of 14
> Zoho CRM Source: /leads/leads_full_structure.yaml (automation_triggers section)
> Confirmed Zoho Trigger: "[Lead] Send Welcome Message" (automation_trigger_on_create)

---

## 1. SellBot Objective

Immediately after a lead is created (Step 2), send a warm branded welcome message
via WhatsApp and Email. No human action required. This sets the first impression
and confirms to the client that their enquiry was received.

---

## 2. Source Zoho CRM Analysis

From `leads_overview.md` (automation_triggers section):
- Confirmed automation: "[Lead] Send Welcome Message" fires on lead creation
- Trigger: Record Creation
- Zoho mechanism: Workflow Rule on Leads module

---

## 3. Automation Trigger Design

### 3.1 Trigger
```
Module:   Leads
Event:    On Record Creation
Condition: Lead Source is not empty  (fire for all new leads)
```

### 3.2 Actions (parallel)
1. Send WhatsApp Template: `auto_welcome_message_project`
2. Send Email Template: `welcome_email_lead`
3. Update field: Lead Status → "New" (if not already set)

---

## 4. WhatsApp Template: auto_welcome_message_project

```
Template Name: auto_welcome_message_project
Platform: WATI (or equivalent WhatsApp Business API)
Category: Transactional

--- Message Body ---
🙏 Hello {{Lead Name}},

Thank you for your interest in [Project Name]!

We're glad to hear from you. Our team will reach you within the next few hours
to answer all your questions and help you find the perfect plot/home.

📞 Our team: [Company Phone]
🌐 Website: [Company Website]
📍 Location: [Project Location]

We look forward to speaking with you!
Warm regards,
[Company Name] Team

--- Footer ---
Reply STOP to unsubscribe
```

### 4.1 WhatsApp Merge Fields
| Merge Field | Source |
|---|---|
| {{Lead Name}} | Lead.Lead_Name |
| [Project Name] | Active Project record |
| [Company Phone] | Organisation settings |
| [Company Website] | Organisation settings |
| [Project Location] | Project.Location |
| [Company Name] | Organisation settings |

---

## 5. Email Template: welcome_email_lead

```
Subject: Welcome to [Project Name] — We're Here to Help!

--- Body ---
Hi {{Lead Name}},

Thank you for enquiring about [Project Name].

We have received your details and our CRM executive will be in touch shortly
to understand your requirements and guide you through the available options.

In the meantime, here's what you can explore:
• Project Brochure: [Brochure Link]
• Virtual Tour: [Video Link]
• Location: [Google Map Link]
• Website: [Website URL]

We are committed to making your property search simple and transparent.

Warm regards,
[CRM Executive Name]
[Company Name]
[Phone Number]
[Email Address]

---
This email was sent because you enquired about [Project Name].
```

### 5.1 Email Merge Fields
| Merge Field | Source |
|---|---|
| {{Lead Name}} | Lead.Lead_Name |
| [Project Name] | Active Project record |
| [Brochure Link] | Project.Brochure_PDF |
| [Video Link] | Project.Intro_Video_Link |
| [Google Map Link] | Project.Google_Map_Link |
| [Website URL] | Project.Website_URL |
| [CRM Executive Name] | Lead Owner / Assigned CRM Exec |
| [Company Name] | Organisation settings |
| [Phone Number] | Organisation phone |
| [Email Address] | Organisation email |

---

## 6. UI Screen — Automation Configuration

### 6.1 Workflow Rule Screen (Admin only)
```
Rule Name: SellBot — Auto Welcome Message
Module: Leads
Trigger: Create (On Record Save for new records)
Conditions: None (fire for all new leads)
Actions:
  1. Send WhatsApp Message (WATI integration) → Template: auto_welcome_message_project
  2. Send Email → Template: welcome_email_lead
  3. Field Update: Lead Status = "New"
```

### 6.2 Visual Flow (in SellBot Admin Panel)
```
[ Lead Created ] ──▶ [ Condition Check ]
                              │
                    Lead Source ≠ empty? YES
                              │
                    ┌─────────┴──────────┐
                    ▼                    ▼
           [Send WhatsApp]       [Send Email]
           Template:              Template:
           auto_welcome_           welcome_email_
           message_project         lead
                    │                    │
                    └─────────┬──────────┘
                              ▼
                  [Update Lead Status = "New"]
```

---

## 7. Delivery Status Tracking

| Status | Display in Lead Record |
|---|---|
| WhatsApp Sent | WA: Delivered ✅ |
| WhatsApp Failed | WA: Failed ❌ (alert to CRM Exec) |
| Email Sent | Email: Sent ✅ |
| Email Bounced | Email: Bounced ❌ |
| Client Replied | WA reply linked to lead + task created |

---

## 8. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Automation trigger | "[Lead] Send Welcome Message" (confirmed) | Same trigger; connect to WATI + branded templates |
| WhatsApp template | Not in Zoho CRM directly | WATI API integration |
| Email template | Zoho CRM email template builder | Branded HTML email template |
| Delivery tracking | Zoho email tracking (basic) | WhatsApp read receipts + email open tracking |
| Brochure/video links in email | Not present | Populated from Project Assets (Step 1) |
