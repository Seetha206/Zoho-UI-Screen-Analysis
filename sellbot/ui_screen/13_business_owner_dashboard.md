# Step 13 — Business Owner Master Dashboard
# SellBot UI Implementation Plan

> SellBot Step: 13 of 14
> Zoho CRM Source: All modules (analytics layer)
> Extends: Step 10 View 4 (Business Owner Summary) with deeper drill-downs

---

## 1. SellBot Objective

Provide the promoter/director with a single easy-to-read real-time interface
showing the full sales and marketing ecosystem health — from lead generation to
site visit, booking, referral, and team performance — updated live.

---

## 2. Dashboard URL & Access

```
URL: /sellbot/dashboard/owner
Roles: Owner / Director (full access) | TL / Department Head (filtered team view)
Update frequency: Real-time (API) or every 1 hour sync
Auto-delivery: Daily 8 AM email + WhatsApp to Owner | Friday 6 PM weekly digest to Team
```

---

## 3. Navigation Structure

```
Left Navigation Tabs:
  [Marketing] [Sales] [People] [Projects] [Finance] [Forecast]

Top bar:
  Quick Filter: [Project ▼] [Date Range ▼] [Source ▼]
  Search bar: leads / contacts / deals by name
```

---

## 4. Section 1 — Executive Snapshot (Home Tab)

Visible immediately on login. 6 large KPI cards:

```
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│ Total Leads  │ │ Site Visits  │ │ Bookings     │
│ This Month   │ │ This Month   │ │ This Month   │
│  247  ↑12%   │ │   38   ↑5%  │ │    9   ↑2    │
└──────────────┘ └──────────────┘ └──────────────┘
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│ Revenue      │ │ Marketing    │ │ Active Hot   │
│ Generated    │ │ Spend        │ │ Leads        │
│ ₹1.8 Cr      │ │ ₹45,000      │ │   23         │
└──────────────┘ └──────────────┘ └──────────────┘
```

Color coding per card: 🟢 on/above target | 🟡 70–89% | 🔴 below 70%

---

## 5. Section 2 — Marketing Engine Health (Marketing Tab)

```
Metrics:
  - Lead Source Breakdown (%)
  - Cost Per Lead by Platform
  - ROI per Platform
  - CPL Trend (month over month — last 6 months)
  - Best Performing Campaign

Visualizations:
  - Pie chart: Lead source mix
  - Bar chart: ROI per platform
  - Trend line: CPL drop over months
  - Table: Top 5 campaigns by conversion
```

---

## 6. Section 3 — Sales Funnel Performance (Sales Tab)

```
Funnel stages (horizontal bar):
  Leads Captured → Leads Qualified → Site Visits Booked
  → Site Visits Completed → 60-Day Follow-Up Active → Bookings Confirmed

Color coding per stage:
  Active: Green
  Pending: Orange
  Dropped: Red

Drill-down: click stage → filtered lead list at that stage
```

---

## 7. Section 4 — People & Team Performance (People Tab)

```
Top Performer Widget:
  🏆 [Name] – [Role]
  KPI Score: [N%]

Performance Table:
  Employee | Role | Leads | Visits | Conversions | KPI %
  ──────────────────────────────────────────────────────
  [Name]   | CRM  | 45    | 12     | 3           | 87%
  [Name]   | BDM  | —     | 18     | 5           | 92%
  [Name]   | MKT  | —     | —      | —           | 78%

Auto-Alert (sent to TL + HR):
  Staff below 60% KPI threshold → "Performance Alert: [Name]"

Training Reminder Widget:
  List of employees pending sales training review (if KPI < 70% for 2+ months)
```

---

## 8. Section 5 — Project-wise Sales Tracker (Projects Tab)

```
Table per project:
  Project Name | Units Available | Units Sold | Units Booked | Revenue
  ──────────────────────────────────────────────────────────────────────
  Mettupalayam | 40              | 12         | 5            | ₹18L
  Mullai Nagar | 60              | 28         | 8            | ₹67L
  Eswara Nagar | 35              | 8          | 3            | ₹25L

Bar chart (units sold % by project):
  >75% sold     → 🟢 Green
  50–75% sold   → 🟡 Yellow
  <50% sold     → 🔴 Red

Click project name → detailed SellBot analytics for that project
```

---

## 9. Section 6 — Objection & Follow-Up Analytics

```
Widgets:
  - Avg Follow-Ups per Lead: [N]
  - Follow-Up Compliance (%): [N%]
  - Leads Exceeding 60-Day Rule: [N] (links to TL review list)
  - Top 3 Objection Types This Month: bar chart (budget / location / family)
  - Objection Resolution Rate: [N%]
```

---

## 10. Section 7 — Customer Experience & Referrals

```
Metrics:
  - Average Customer Satisfaction Score: [N.N] / 5
  - Total Referrals Submitted: [N]
  - Referral Conversions: [N]
  - Pending Rewards: ₹[amount]

Feature:
  Click "Referrals" → Referral leaderboard + pending rewards table
```

---

## 11. Section 8 — Financial Overview (Finance Tab)

```
KPI:
  - Revenue Booked This Month: ₹[N]
  - Revenue Collected: ₹[N]
  - Expected Collection (next 30 days): ₹[N]
  - Ad Spend vs Revenue: [N]%
  - Pending Registration Value: ₹[N]

Visualization:
  3-month trend lines for all financial KPIs
```

---

## 12. Section 9 — Forecast & Business Health Meter

```
Business Health Score Gauge:
  ┌─────────────────────────────────────────┐
  │           BUSINESS HEALTH               │
  │  ○─────────────────⬤──────────────○   │
  │  0          60  74  80           100    │
  │       🔴         🟡      🟢              │
  │           Score: 74 — Moderate          │
  └─────────────────────────────────────────┘

Formula: (Conversion Rate × 30%) + (Follow-Up Compliance × 25%)
        + (Marketing ROI × 25%) + (Feedback Index × 20%)

Threshold labels:
  80–100: 🟢 Excellent
  60–79:  🟡 Moderate
  <60:    🔴 Action Needed

Expected Revenue Next 30 Days: ₹[calculated from pipeline]
```

---

## 13. Section 10 — Alerts & Actionable Insights Panel

```
┌──────────────────────────────────────────────────┐
│  🔔 ALERTS                                        │
├──────────────────────────────────────────────────┤
│  🔴 Leads not followed in 48 hrs: 7              │
│     [View → filtered lead list]                   │
│  🟡 Bookings awaiting registration: 3            │
│     [View → Deal list filter]                     │
│  🟡 Overdue site visits (rescheduled >3x): 2    │
│     [View → Visit list filter]                    │
├──────────────────────────────────────────────────┤
│  💡 RECOMMENDED FOCUS                             │
│  "Improve follow-up speed for Hot Leads           │
│   (avg response: 4.2 hrs → target: <2 hrs)"      │
├──────────────────────────────────────────────────┤
│  📅 Next Team Review Meeting: [Date]              │
└──────────────────────────────────────────────────┘
```

---

## 14. Automation & Auto-Delivery

| Delivery | Timing | Recipients | Format |
|---|---|---|---|
| Daily Snapshot | 8 AM | Owner (email + WhatsApp) | Top 6 KPI cards |
| Weekly Digest | Friday 6 PM | TL + Department Heads | Summary table |
| Monthly PDF | Last day 7 PM | Owner + CRM Head + Marketing Head + BDM Lead | Full PDF |
| Alert: Hot Lead unattended | >48 hrs no action | CRM Exec + TL | WhatsApp |
| Alert: Low follow-up compliance | <80% this week | TL | WhatsApp |
| Alert: Performance below 60% | Monthly KPI review | TL + HR | Email |

---

## 15. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Home dashboard | KPI summary (home_screen.yml) | Extend with 10 sections + 6-tab navigation |
| Business Health Score | Not present | New formula gauge with threshold coloring |
| Project-wise sales tracker | Not structured | Bar chart by project with % sold coloring |
| Forecast widget | Not in Zoho | Expected Revenue (30 days) from pipeline |
| Performance badges | Not in Zoho | Gold/Silver/Bronze + auto-alert <60% |
| Daily WhatsApp digest | Not in Zoho | WATI message: Top 6 KPIs at 8 AM |
| Drill-down from charts | Limited in Zoho | Click → filtered module list at that stage |
| Left nav tabs | Not in Zoho home | Marketing / Sales / People / Projects / Finance / Forecast |
