# Step 10 — CRM Dashboard & Reporting System
# SellBot UI Implementation Plan

> SellBot Step: 10 of 14
> Zoho CRM Source: All modules (analytics overlay) — Home Dashboard, Leads, Tasks, Deals, Accounts
> Home Dashboard patterns confirmed from /home/home_screen.yml + home_detailed_documentation.md

---

## 1. SellBot Objective

Convert all SellBot automation activities into real-time visual dashboards across
4 role-specific views: Marketing, Sales, People, Business Owner Summary. Auto-generate
monthly PDF reports for stakeholder review.

---

## 2. Source Zoho CRM Analysis

From `home_screen.yml` (Home Dashboard):
- KPI summary widget (row_1): confirmed pattern
- Table widgets + chart widgets confirmed
- Widget types: kpi | kpi_summary | table | chart

---

## 3. Dashboard Architecture

```
SellBot Dashboard (Zoho Analytics / CRM Reports)
├── View 1: Marketing Performance        (Marketing Team)
├── View 2: Sales Conversion             (CRM Executives + TL)
├── View 3: People Performance           (TL + HR + Owner)
└── View 4: Business Owner Summary       (Owner / Director)
```

---

## 4. View 1 — Marketing Performance

```
Role: Marketing Team, TL, Owner
Data Sources: Lead Source field, Campaign Name field, Leads module
```

### KPI Cards (top row — color coded)
| Card | Metric | Color Rule |
|---|---|---|
| Total Leads Generated | Count (this month) | Green ≥90% target, Red <70% |
| Ad Budget Spent | Sum from campaign records | — |
| Cost Per Lead (CPL) | Budget ÷ Total Leads | Green if ↓ vs last month |
| Lead Quality Ratio | (Hot + Warm) % ÷ Total Leads | Green ≥60%, Red <40% |

### Charts
- **Pie chart**: Lead Source breakdown (Facebook / Google / Portal / Referral / Walk-in)
- **Bar chart**: CPL by Platform
- **Trend line**: CPL month-over-month (last 6 months)
- **Table**: Top 5 campaigns by conversion count

### Auto-Alerts
```
Alert: Follow-Up Compliance < 80% → email to TL
Alert: Hot Lead unattended > 2 days → alert to TL + CRM Exec
```

---

## 5. View 2 — Sales Conversion

```
Role: CRM Executives, BDMs, TL
Data Sources: Leads, Tasks, Site_Visit_Feedback, Deals
```

### KPI Cards
| Card | Metric |
|---|---|
| Total Qualified Leads | Lead_Type = Hot + Warm + Cold (count) |
| Site Visits Scheduled | Visit_Status = Booked (count) |
| Site Visits Completed | Visit_Status = Completed (count) |
| Site Visit → Booking Conversion | (Deals Closed / Visits Completed) × 100 |
| Avg Response Time | Lead_Created → First Task Completed (hours) |
| Follow-Up Compliance | Tasks completed on time ÷ Total tasks × 100 |

### Charts
- **Funnel chart**: Leads → Qualified → Visits Booked → Visits Done → Bookings
- **Pie chart**: Objection Distribution (7 objection types)
- **Bar chart**: Conversion rate by BDM
- **Table**: Booking pipeline (Lead Name | Value | Expected Close Date)

### Drill-Down
```
Click on funnel stage → filtered lead list at that stage
Click on booking value → opens Deal record
Click on BDM bar → filtered tasks list for that BDM
```

---

## 6. View 3 — People Performance

```
Role: TL, Owner
Data Sources: Tasks (Telecaller field), Employee Portfolio, Site_Visit_Feedback
```

### CRM Executive Metrics
| KPI | Formula |
|---|---|
| Calls Made / Day | Tasks marked Completed or Attempt ÷ working days |
| Qualified Leads (H/W/C) | Lead_Type count by CRM Exec |
| On-Time Follow-Up Rate | Tasks completed before due date ÷ Total tasks × 100 |
| Client Response Rate | Reply keywords received ÷ WA messages sent × 100 |
| Leads → Site Visit | Visit_Status = Booked count by CRM Exec |

### BDM Metrics
| KPI | Formula |
|---|---|
| Site Visits Conducted | Visit_Status = Completed by BDM |
| Feedback Forms On Time | Forms submitted same day as visit ÷ Total visits |
| Objections Captured Properly | Objection_Types ≠ blank ÷ Total feedback forms |
| Visit → Booking Conversion | Deals closed ÷ Visits conducted (by BDM) |

### Marketing Team Metrics
| KPI | Formula |
|---|---|
| Campaigns Executed | Count of active campaigns |
| CPL vs Target Variance | (CPL – Target_CPL) ÷ Target_CPL × 100 |
| Lead Quality Ratio | (Hot + Warm) ÷ Total leads (this month) |

### Performance Badges
```
🥇 Gold: ≥90% KPI score
🥈 Silver: 75–89%
🥉 Bronze: 60–74%
⚠️ Below Target: <60% → auto-alert to TL
```

### Auto-Reports
```
Daily digest email to TL: 6 PM every day
Content:
  - Total calls today: [N]
  - Leads qualified: [N]
  - Visits completed: [N]
  - Alerts: [list of issues]
```

---

## 7. View 4 — Business Owner Summary

```
Role: Owner / Director only
Data Sources: All modules combined
```

### Top KPI Cards (Executive Snapshot)
```
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐
│ Total    │ │ Site     │ │ Bookings │ │ Revenue  │ │Marketing │ │ Active   │
│ Leads    │ │ Visits   │ │ This     │ │Generated │ │ Spend    │ │ Hot      │
│ (month)  │ │ (month)  │ │ Month    │ │          │ │          │ │ Leads    │
└──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────┘
```

### Full Dashboard Layout
```
ROW 1: KPI Cards (6 cards as above)
ROW 2: [Marketing Engine Health chart] | [Sales Funnel chart]
ROW 3: [People Top/Bottom Performer] | [Project-wise Sales Tracker]
ROW 4: [Objection Analytics] | [Customer Satisfaction + Referrals]
ROW 5: [Financial Overview trend] | [Forecast & Business Health Meter]
ROW 6: [Alerts & Actionable Insights panel]
```

### Business Health Score
```
Formula: weighted average of:
  Conversion Rate         × 30%
  Follow-Up Compliance    × 25%
  Marketing ROI           × 25%
  Customer Feedback Index × 20%

Thresholds:
  80–100 → 🟢 Excellent
  60–79  → 🟡 Moderate
  <60    → 🔴 Action Needed
```

### Project-wise Sales Tracker
```
Columns: Project Name | Units Available | Units Sold | Units Booked | Revenue
Bar chart by project:
  >75% sold → 🟢 Green
  50–75% → 🟡 Yellow
  <50% → 🔴 Red
Click → project SellBot detailed analytics
```

---

## 8. Monthly Review Report (Auto-Email)

```
Trigger: Last day of month at 7 PM
Recipients: Owner, CRM Head, Marketing Head, BDM Lead
Subject: "{{Project Name}} | Monthly Growth Report – {{Month YYYY}}"
Attachment: PDF snapshot (dashboard export)
```

### Report Sections
1. Project Overview (Project Name, Month, Report Date, Prepared by: SellBot-360)
2. Marketing Performance Summary (Leads, Ad Spend, CPL, Source Breakdown, ROI)
3. Sales Performance Summary (Qualified, Visits, Bookings, Conversion, Non-Closure Reasons)
4. People Performance Summary (CRM calls/day, BDM visits, Marketing CPL)
5. Customer Experience Summary (testimonial quotes)
6. Insights & Recommendations (system observations + action plan)
7. Financial Snapshot (Bookings Value, Revenue Collected, Expected 30 days)
8. Upcoming Milestones (Pending Registrations, Scheduled Visits, Project Milestones)

---

## 9. Auto-Alert System

| Alert | Condition | Recipients |
|---|---|---|
| Unattended Hot Lead | Lead_Type = Hot AND no task completed in 48 hrs | CRM Exec + TL |
| Low Follow-Up Compliance | <80% tasks completed on time | TL |
| Pending Proof Visit | Visit_Verified = Pending for >24 hrs | TL |
| Unresponsive Lead TL Review | TL Review task overdue | TL + Owner |
| Bookings Awaiting Registration | Deal status = Booked for >7 days | Owner + TL |
| Overdue Site Visits | Rescheduled >3 times | TL |

---

## 10. Implementation Delta vs Zoho

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Home dashboard KPI cards | Confirmed (home_screen.yml) | Extend with SellBot-specific metrics |
| Reports builder | Zoho CRM Reports (basic) | Zoho Analytics (advanced, connected) |
| Marketing attribution | First Click / Last Click fields (confirmed) | CPL calculation + Campaign ROI |
| People performance | Not structured in Zoho | CRM Exec + BDM + Marketing KPI cards |
| Business Health Score | Not in Zoho | New formula: conversion + compliance + ROI + feedback |
| Monthly PDF auto-email | Not automated in Zoho | Scheduled Zoho Analytics export + email |
| Auto-alerts | Basic Zoho workflow alerts | 6 specific SellBot alert conditions |
