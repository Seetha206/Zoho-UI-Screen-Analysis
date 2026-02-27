# Step 12 — Referral Program Activation
# SellBot UI Implementation Plan

> SellBot Step: 12 of 14
> Zoho CRM Source: /leads/leads_full_structure.yaml (new lead from referral source) + /contacts/contacts_full_structure.yaml

---

## 1. SellBot Objective

Automatically invite every satisfied customer (Score ≥ 4 or "Definitely recommend")
to refer friends/family. Track referrals through a dedicated sub-module. Auto-trigger
reward confirmation when a referral converts to a booking. Run recognition loop
quarterly to sustain referral momentum.

---

## 2. Source Zoho CRM Analysis

From `leads_full_structure.yaml`:
- Lead Source field confirmed: Referral is a valid Lead Source value
- Referral_Source field: New custom field needed (stores referrer name/mobile)

From `contacts_full_structure.yaml`:
- Post-conversion contacts have Related Leads, Deals, Notes, Activities
- Referral tracking fits as a related module on Contact record

---

## 3. Trigger

```
Condition: Client Feedback submitted (Step 11)
           AND (Overall_Satisfaction_Score ≥ 4 OR Q24 = "Definitely")
Timing: Within 24 hours of registration
Actions:
  1. Send WhatsApp: referral_invitation template
  2. Send Email: welcome_referral_email
  3. Create task: "Referral Follow-Up — [Customer Name]" (due: 3 days)
```

---

## 4. Referral Invitation Messages

### WhatsApp: referral_invitation
```
🌟 Hello {{CustomerName}}, thank you for trusting {{CompanyName}} and completing
your registration with {{ProjectName}}!
We're thrilled to have you in our community 🙏

If you know a friend, colleague, or relative looking for a property like yours,
simply share their number — and we'll take care of the rest.
Every confirmed referral earns exclusive rewards 🎁

Reply REFER NOW to get started or fill the form:
🔗 {{ReferralFormLink}}
```

### Email: welcome_referral_email
```
Subject: Share Your Experience — Earn Rewards for Referrals 🌟

Hi {{CustomerName}},
We're delighted to have you as part of the {{ProjectName}} family!

When someone you refer books with us, you'll receive a special reward —
cash bonus, vouchers, or gold coin (based on project policy).

👉 Click here to refer: {{ReferralFormLink}}

Our CRM executive will personally connect with your referrals.
Thank you for being part of {{CompanyName}}.

Warm regards,
Customer Delight Team, {{CompanyName}}
```

---

## 5. Referral Capture Form

```
URL: /sellbot/referral/submit (accessible via referral link)
Access: Any customer with referral link
```

| Field | Type | Required |
|---|---|---|
| Referrer Name | Text (auto-fill from link) | Yes |
| Referrer Mobile | Phone (auto-fill from link) | Yes |
| Referral Name | Text | Yes |
| Referral Mobile | Phone | Yes |
| Referral Email | Email | No |
| Relationship | Picklist | Yes: Friend / Colleague / Family / Neighbour / Other |
| Project Interested In | Picklist | Yes (from Project Assets Library) |
| Submit | Button | — |
```
On submit: Thank you message + create referral lead in CRM
```

---

## 6. Referral Module (CRM Sub-Module)

```
Module Name: Referral Management
Relations: Contact (referrer) → Referral → Lead (new lead from referral)
```

### Referral Record Fields
| Field | Type | Notes |
|---|---|---|
| Referral ID | Auto-number | — |
| Referrer Name | Lookup → Contact | — |
| Referrer Mobile | Phone | — |
| Referral Name | Text | New prospect |
| Referral Mobile | Phone | — |
| Referral Email | Email | Optional |
| Relationship | Picklist | Friend/Colleague/Family/Neighbour/Other |
| Project Interested In | Picklist | — |
| Referral Status | Picklist | New / In Progress / Confirmed / Rewarded |
| Lead Created | Lookup → Lead | Auto-linked on referral lead creation |
| Reward Type | Text | Cash / Gold Coin / Voucher / Discount |
| Reward Status | Picklist | Pending / Processing / Delivered |
| Reward Amount | Currency | — |
| Referred Date | Date | Auto: today |

### Status Flow
```
New → In Progress → Confirmed (booking) → Rewarded
```

---

## 7. Referral Lead Auto-Creation

```
On Referral form submission:
1. Create new Lead record:
   Lead_Name: Referral Name
   Mobile: Referral Mobile
   Lead_Source: "Referral"
   Referral_Source: "{{ReferrerName}} — {{ReferrerMobile}}"
   CRM_Executive_Assigned: original client's CRM Exec
2. Trigger Step 3 (Auto Welcome Message)
3. Trigger Step 4 (Lead Assignment — 5 call attempts)
4. Notify Referrer: "Your referral {{ReferralName}} has been registered."
```

---

## 8. Internal Task Flow

```
On referral submission:
1. Assign referral lead to CRM Executive (same as original client's CRM Exec)
2. Create task: "Welcome Call — Referral: [Name]" (due: today + 1)
3. Tag lead: Referral_Source = "[Referrer Name]"
4. Notify referrer via WhatsApp:
   "✅ Hi {{CustomerName}}, we've received your referral for [Referral Name].
    Our team will connect with them shortly. Thank you! 🙏 [Company Name]"
```

---

## 9. Reward Trigger — On Booking Confirmed

```
Condition: Referral Status → Confirmed (booking linked to referral)
Actions:
  1. Update Referral record: Status = Confirmed; Reward Type = [project policy]
  2. Send WhatsApp to Referrer: referral_reward_confirmed template
  3. Send Email to Referrer: referral_reward_email
  4. Create task: "Process Reward — [Referrer Name]" for Finance team
```

### WhatsApp: referral_reward_confirmed
```
🎉 Congratulations {{CustomerName}}!
Your referral {{ReferralName}} has successfully booked at {{ProjectName}} 🏡
Thank you for your trust and support ❤️
Your reward ({{RewardType}}) will be processed shortly.

To see your referral status anytime, reply MY REFERRALS.
[Company Name]
```

---

## 10. Referral Tracking Dashboard

```
Widget location: Step 10 View 4 + Step 13 Section 7
```

| Metric | Formula |
|---|---|
| Total Referrals Submitted | Count of Referral records |
| Referrals In Progress | Referral_Status = In Progress |
| Referrals Converted | Referral_Status = Confirmed |
| Rewards Pending | Reward_Status = Pending |
| Rewards Delivered | Reward_Status = Delivered |
| Top Referrers (monthly) | Count of referrals by Referrer (this month) |

---

## 11. Reward Program Configuration (Admin)

```
Admin Panel → Referral Settings → per-project configuration
```

| Reward Type | Default Value | Configurable |
|---|---|---|
| Cash Reward | ₹10,000 – ₹50,000 per booking | Yes |
| Gold Coin / Gift Voucher | Per booking | Yes |
| Upgrade Discount | For repeat buyers | Yes |
| Festive Offer (Diwali/Pongal) | Double reward | Yes |
| Monthly Lucky Draw | All active referrers auto-enter | Yes |

---

## 12. VIP Ambassador Recognition Loop

```
Quarterly: Check top 10 referrers by referral conversion count
Actions:
  1. Send WhatsApp:
     "🏆 Congratulations {{CustomerName}}!
      You're among our Top 10 Referrers this quarter.
      Thank you for helping more families join {{ProjectName}} ❤️"
  2. Add to VIP Broadcast Group (WhatsApp broadcast list)
  3. Tag as "Ambassador" in CRM:
     - Priority notifications for new launches
     - Early bird pricing access
```

---

## 13. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Referral Lead Source | "Referral" value in Lead Source picklist | Retain; add Referral_Source field (referrer details) |
| Referral Management module | Not in Zoho CRM | New sub-module with status flow |
| Reward tracking | Not in Zoho | Reward Type + Status + Amount fields |
| Referral capture form | Not present | Public referral form (no login required) |
| Auto-create lead from referral | Manual in Zoho | Auto-create on form submit |
| Reward automation on booking | Not present | WATI + email trigger on Referral_Status = Confirmed |
| VIP Ambassador recognition | Not present | Quarterly batch: tag + WA broadcast |
| Monthly lucky draw | Not present | Auto-enter all active referrers |
