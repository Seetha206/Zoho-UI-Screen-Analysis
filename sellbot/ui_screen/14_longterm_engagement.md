# Step 14 — Long-Term Automation & Brand Engagement
# SellBot UI Implementation Plan

> SellBot Step: 14 of 14
> Zoho CRM Source: /leads/leads_full_structure.yaml (Cadences confirmed in filter panel) + /contacts/contacts_full_structure.yaml

---

## 1. SellBot Objective

Keep the SellBot brand alive in every buyer's and unclosed lead's mind — forever.
Run automated WhatsApp and email broadcasts on a schedule (festival greetings,
market updates, new launches, investment education) to past clients and unresponsive
leads. Every 90 days, auto-check-in with inactive leads for re-activation.

---

## 2. Source Zoho CRM Analysis

From `leads_full_structure.yaml` (filter_panel):
- "Cadences" is a confirmed system filter in Zoho CRM leads
- "Latest Email Status" is a confirmed system filter
From `contacts_full_structure.yaml`:
- Contacts module is the post-conversion home for buyers → long-term list

---

## 3. Target Audiences

```
Audience 1: Past Clients (registered buyers)
  Source: Contacts module (Deal status = Closed Won)
  List Name: "SellBot VIP Clients"

Audience 2: Unclosed Leads (Cold + Junk with TL closure)
  Source: Leads module (Lead_Type = Cold / Junk; TL_Approved_for_Closure = Yes)
  List Name: "SellBot Nurturing List"

Combined List Name: "SEO-Bot Nurturing List" (per spec)
```

---

## 4. Campaign Types & Schedule

### 4.1 Festival Greetings (Annual Calendar)

| Festival | Approximate Date | Channel |
|---|---|---|
| Pongal | January 14–17 | WhatsApp + Email |
| Republic Day | January 26 | WhatsApp |
| Valentine's Day | February 14 | WhatsApp |
| Ugadi / Tamil New Year | April 14 | WhatsApp + Email |
| Diwali | October/November | WhatsApp + Email (Double Reward if referral) |
| New Year | December 31 | WhatsApp + Email |
| Other regional festivals | As scheduled | WhatsApp |

**Festival Template Pattern:**
```
🎊 Happy {{Festival Name}}, {{Name}}!
Warm wishes from the entire team at {{CompanyName}}.
May this festival bring you joy, peace, and prosperity to your new home 🏡
[Company Name]
```

### 4.2 Market Updates (Monthly)

Content:
- Real-Estate Tips (1 per month)
- Area-wise Price Updates (quarterly)
- Infrastructure News (as available)

**Template Pattern:**
```
📊 Hi {{Name}}, here's your monthly real estate update!

🏗️ [Area/Project]: Infrastructure update [X]
📈 Property values in [Area]: Increased by [Y]% this quarter
💡 Tip of the month: [Tip]

Want to know how this affects your investment?
Reply CALL ME and our advisor will update you personally.
[Company Name]
```

### 4.3 New Project Launches

```
Triggered manually by Admin when new project is added (Step 1)
```

**Template:**
```
🚀 Exciting News, {{Name}}!

We're thrilled to announce our new project: [New Project Name] at [Location].
As a valued member of our community, you get EARLY BIRD ACCESS.

[Key highlights: Price / Location / BHK]
📎 Brochure attached (or): View details: [Link]

Interested? Reply PREVIEW and our team will call you with exclusive details.
[Company Name]
```

### 4.4 Investment Education (Quarterly)

Content:
- Investment ROI Comparisons (plots vs FD vs stocks)
- Rent vs Buy Educational Content
- Area Appreciation Data (with charts)

**Template:**
```
💡 Investment Insight from {{CompanyName}}

Did you know? Plots in [Area] have appreciated [X]% over the last 3 years —
outperforming Fixed Deposits and matching top equity funds.

[Data point or chart link]

Want a personalised investment analysis for your property?
Reply ANALYSIS and our expert will connect with you.
[Company Name]
```

### 4.5 Client Success Stories (Monthly)

```
Content: Testimonial quote from Step 11 + photo (if video testimonial collected)
Channel: WhatsApp broadcast + Email
```

**Template:**
```
🌟 Real Stories from Our Happy Clients

"[Customer Quote from Step 11]"
— [Client Name], [Project Name]

You too can find your perfect property with us.
If you'd like to explore, reply EXPLORE. 🏡
[Company Name]
```

---

## 5. 90-Day Re-Activation Cycle

### Automation Rule
```
Trigger: Scheduled — runs every 90 days
Condition:
  Lead_Type = Cold OR (Lead_Type = Junk AND TL_Approved_for_Closure = Yes)
  AND Last Activity > 90 days ago
  AND Unsubscribed = No

Action:
  1. Send WhatsApp: reactivation_checkin template
  2. Create task: "90-Day Re-Activation — [Lead Name]" for CRM Exec
```

### WhatsApp: reactivation_checkin
```
👋 Hi {{Name}}, it's been a while — hope you're doing great!

We've been making great progress at [Project Name] and have some exciting updates
to share that might be relevant to your plans.

Would you like a quick catch-up call with our team?
Reply YES and we'll connect you within the hour.

No pressure — just staying in touch! 😊
[Company Name]
```

---

## 6. Unsubscribe Management

```
Keyword: STOP
Action:
  1. Set Unsubscribed = Yes on Lead/Contact record
  2. Remove from all automated WhatsApp broadcasts
  3. Remove from email campaigns
  4. Keep CRM record intact (can still make manual calls)
  5. Toast in CRM for CRM Exec: "[Name] unsubscribed from automated messages"
  6. CRM Exec can still manually reach out

Re-subscribe: Lead/Contact can text START at any time
```

---

## 7. Admin — Broadcast List Management

```
URL: /sellbot/broadcasts/manage
Sections:
  ├── Active Broadcast Lists
  │    ├── SellBot VIP Clients
  │    └── SellBot Nurturing List
  ├── Scheduled Campaigns (upcoming)
  ├── Sent Campaigns (history + open/delivery rates)
  └── Unsubscribers (list of opted-out contacts)
```

### Campaign Creation Screen
```
Fields:
  Campaign Name: [text]
  Audience: [SellBot VIP Clients / SellBot Nurturing List / Both]
  Channel: [WhatsApp / Email / Both]
  Message Template: [dropdown from approved templates]
  Attachment: [optional from Project Assets]
  Schedule: [date + time]
  [Preview] [Schedule Campaign]
```

---

## 8. WhatsApp Merge Fields (All Long-Term Templates)

| Field | Source |
|---|---|
| {{Name}} | Lead/Contact.First_Name |
| {{CompanyName}} | Organisation settings |
| {{ProjectName}} | Active Project record |
| {{Area}} | Project.Location |
| {{Festival}} | Campaign.Festival_Name |

---

## 9. Performance Tracking

```
Per campaign (in Step 10 / Step 13 dashboards):
  - Messages Sent: [N]
  - Delivered: [N] ([%])
  - Read: [N] ([%])
  - Replies Received: [N] ([%])
  - Leads Re-Activated: [N] (replied YES + task created)
  - Unsubscribes: [N]
```

---

## 10. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Cadences system | Confirmed filter option in Zoho | Use Zoho Cadences OR WATI scheduled broadcasts |
| Festival broadcast | Manual in Zoho | Automated calendar-triggered WhatsApp |
| 90-day re-activation | Not structured | Scheduled automation rule every 90 days |
| New project announcement | Manual email blast | Triggered automatically when Step 1 project saved |
| Investment education content | Not in Zoho | Quarterly template-based WhatsApp + email |
| Broadcast list management | Zoho Campaigns | Admin screen for VIP Clients + Nurturing List |
| Unsubscribe tracking | Zoho CRM unsubscribe field | Keyword STOP → Unsubscribed = Yes |
| Re-activation tracking | Not present | Lead/Contact marked "Re-Activated" when replies YES |
