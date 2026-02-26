# Projects Portfolio Module — Overview & Context

## What Is This Module?

The **Projects Portfolio** module is a **custom module** (CustomModule3) in Zoho CRM that stores information about real estate development projects. Unlike standard CRM modules (Leads, Contacts, Deals) which track people and opportunities, this module tracks **properties** — the actual land developments, plotted layouts, and real estate projects that Kurinjee Promoters is building and selling.

Each Project Portfolio record represents a development site with comprehensive details: location, approvals, amenities, pricing, marketing strategy, and competitive positioning.

---

## Why Does This Module Exist?

Real estate developers manage multiple projects simultaneously, each with unique characteristics, approval statuses, and marketing requirements. The Projects Portfolio module exists to:

1. **Centralize project information** — All details about a development (location, approvals, amenities, pricing) in one structured record.
2. **Support sales conversations** — BDMs can quickly access project USPs, nearby landmarks, and competitive advantages during customer calls.
3. **Link deals to properties** — When a buyer expresses interest in a specific project, the Deal record references this module via "Site Visit Location."
4. **Track project readiness** — Development stage, completion stage, and approval status help teams understand what's sellable now vs. in the future.
5. **Enable marketing planning** — Budget allocation, target audience, and marketing channels are documented for each project.
6. **Facilitate competitive analysis** — Subform tracks nearby competing projects with strengths/weaknesses comparison.

Without this module, project information would be scattered across documents, spreadsheets, or individual knowledge — making it difficult for the sales team to consistently communicate project value.

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **BDM (Business Development Manager)** | References project details during customer calls, schedules site visits, shares project links |
| **Marketing Team** | Plans campaigns, allocates budgets, tracks digital/offline marketing channels per project |
| **Management / Leadership** | Reviews project pipeline, monitors development progress, approves pricing strategies |
| **Telecaller** | Uses project information to answer buyer queries, shares brochures and location links |
| **Admin** | Maintains project records, updates approval statuses, manages competitive analysis data |

---

## How It Fits in the CRM Workflow

```
[Project Identified]
       ↓
[Project Portfolio Record Created]
       ↓
[Project Details Populated]
  ├── Location & Approvals (RERA, DTCP)
  ├── Amenities & Features
  ├── Pricing & Budget
  ├── Target Audience
  └── Marketing Strategy
       ↓
[Project Linked to Other Modules]
  ├── Leads → Site Visit Location
  ├── Deals → Site Visit Location
  └── Marketing Campaigns → Project Promotion
       ↓
[Ongoing Updates]
  ├── Development Stage Progress
  ├── Completion Percentage
  └── Pricing Revisions
```

The Projects Portfolio module is a **reference/master module** — it doesn't have a lifecycle like Leads or Deals. Instead, it provides context and data that enriches records in other modules. A Project record is created once and updated continuously as the development progresses.

---

## Key Sections in a Project Portfolio Record

### 1. Project Overview
| Field | Purpose |
|---|---|
| Project Portfolio Name | Unique project identifier |
| Budget | Total project investment |
| Project Type | Plots / Villa / Apartment / Mixed Use / Commercial |
| Land Area | Size in Acres |
| No Of Units | Total plots/homes being developed |
| Development Stage | Planning / Launch / Construction / Completion |
| Completion Stage | Percentage or milestone |
| Base Price Per Unit | Starting price per plot/home |
| Estimated Completion Date | Projected handover date |
| Connected To | Links to Lead (if project originated from enquiry) |

### 2. Location
| Field | Purpose |
|---|---|
| Street | Project address |
| City | City name |
| District | District name |
| State | State (default: Tamil Nadu) |
| Pincode | Postal code |
| Nearest NH | National Highway reference |
| Highway Distance | Distance from highway |
| Landmarks | Nearby reference points |

### 3. Location and Accessibility
| Field | Purpose |
|---|---|
| Railway Station Name | Nearest railway station |
| Bus Stop Name | Nearest bus stop |
| Distance from Bus Stop | Walking distance |
| Airport Name | Nearest airport |
| Distance from Airport | Drive time |
| Distance from Railway Station | Drive time |
| Restaurants | Nearby dining options |
| Colleges | Educational institutions |
| Banks | Banking facilities |
| Grocery | Shopping convenience |
| Hospitals | Healthcare access |
| Major Infrastructure Projects | Upcoming developments |
| Approach Roads Condition | Road quality assessment |
| Annual Appreciation Rate | Expected value growth |
| Local Population Growth | Demographic trends |
| Property Value Trends | Market trajectory |
| Job Creation Opportunities | Employment drivers |
| Map Link | Google Maps integration |

### 4. Project Features (Legal & Infrastructure)
| Field | Purpose |
|---|---|
| DTCP Approved | Department of Town and Country Planning approval |
| DTCP Approval Number | Official approval reference |
| RERA Registered | Real Estate Regulatory Authority registration |
| RERA Number | Official RERA registration number |
| Land Ownership Verified | Title clearance status |
| Litigation Risk | Legal risk assessment |
| Gated Community | Secured community (Yes/No) |
| Road Type | Blacktop / Gravel / Concrete |
| Compound Wall | Boundary wall status |
| Road Widths | Street width specifications |
| Water Supply | Water source and availability |
| Storm Water Drainage | Drainage system |
| Electricity Connection | Power availability |
| Solar Street Light | Sustainable lighting |
| Childrens Park | Play area |
| Customization Available | Buyer customization options |
| Monthly Maintenance Fee | Ongoing maintenance cost |
| Unique Selling Points | Key differentiators |

### 5. Competitive Analysis (Subform)
| Column | Purpose |
|---|---|
| Competitor Name | Nearby competing project |
| Competitor Location | Where competitor is located |
| Distance From Highway | Competitor's highway access |
| Price Range Per Cent | Competitor pricing |
| Key Strengths | What competitor does well |
| Key Weaknesses | Competitor vulnerabilities |

### 6. Target Audience
| Field | Purpose |
|---|---|
| Target Professions | Ideal buyer occupations |
| Buyer Age Range Min | Youngest target buyer age |
| Buyer Age Range Max | Oldest target buyer age |
| Income Level Min | Minimum household income |
| Income Level Max | Maximum household income |
| Pain Points Addressed | Customer problems solved |
| Lifestyle Preferences | Target lifestyle segment |

### 7. Marketing and Sales Strategy
| Field | Purpose |
|---|---|
| Digital Marketing Channels | Online channels (Facebook, Google, etc.) |
| Offline Marketing Strategies | Traditional channels (print, hoardings, etc.) |
| Monthly Lead Target | Expected enquiries per month |
| Expected Conversion Rate | Lead-to-customer conversion % |
| Sales Revenue Target | Monthly/quarterly revenue goal |
| Marketing Budget Digital | Online marketing budget |
| Marketing Budget Offline | Traditional marketing budget |
| Marketing Budget Partnerships | Channel partner budget |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total projects observed | 3 |
| Layout ID | 955332000000425393 |
| Internal module name | CustomModule3 |
| Active view | All Projects Portfolio |

### Project Portfolio (Observed)

| Project Name | Budget | Project Type | Created Date |
|---|---|---|---|
| Mettupalayam | ₹ 20,00,000.00 | Plots | 24/11/2025 |
| Mullai Nagar | ₹ 67,00,000.00 | Mixed Use | 29/06/2025 |
| Eswara Nagar | ₹ 25,00,000.00 | Mixed Use | 29/06/2025 |
| **Total Portfolio Value** | **₹ 1,12,00,000.00** | — | — |

### Project Type Distribution

| Type | Count | Percentage |
|---|---|---|
| Mixed Use | 2 | 66.7% |
| Plots | 1 | 33.3% |

**Observation:** The portfolio is heavily weighted toward **Mixed Use** developments, which typically combine residential plots with commercial spaces. This suggests Kurinjee Promoters is focusing on integrated township developments rather than single-format projects.

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Leads** | "Site Visit Location" field links leads to projects; "Connected To" lookup traces project origin |
| **Deals** | "Site Visit Location" field links deals to projects being purchased |
| **Calls** | Calls about specific projects can be filtered via related module |
| **Meetings** | Site visits scheduled at project locations |
| **Tasks** | Project-related follow-ups (documentation, approvals) |
| **Emails** | Project-specific email campaigns and correspondence |
| **Notes** | Internal notes about project progress, issues, updates |

---

## Module URL Reference

| Screen | URL |
|---|---|
| Projects Portfolio list | `/crm/org60043078423/tab/CustomModule3` |
| All Projects Portfolio view | `/crm/org60043078423/tab/CustomModule3/custom-view/955332000000436287/list` |
| Create Project Portfolio | `/crm/org60043078423/tab/CustomModule3/create?layoutId=955332000000425393` |
| Project detail view | `/crm/org60043078423/tab/CustomModule3/{record_id}` |
| Edit layout | `/crm/org60043078423/settings/modules/CustomModule3/layouts/955332000000425393` |
| Import Projects | `/crm/org60043078423/settings/import?module=CustomModule3&step=1` |
| Manage Tags | `/crm/org60043078423/settings/manage-tags?module=CustomModule3` |

---

## Integration with SellBot-360 Automation

The Projects Portfolio module is foundational to the **SellBot-360** automation blueprint (Step 1: Add Current Project). Before automation begins, every project must have:

| Asset | Stored In Project Record |
|---|---|
| Brochure (PDF) | Referenced in Description or Notes |
| Intro/Walkthrough Videos | Map Link or Description field |
| Google Map Location | Map Link field |
| Company Profile | Linked via Description |
| Nearby Project Comparison | Competitive Analysis subform |
| Marketing Posters | Referenced for WhatsApp campaigns |

When a lead expresses interest, the CRM executive can instantly share:
- Project brochure (PDF attachment)
- Walkthrough video (link)
- Google Maps location (directions)
- Competitive comparison (objection handling)

---

## Related Documentation

| File | Description |
|---|---|
| `ProjectsPortfolio.md` | Full DOM scan with 80+ field definitions, form structure, subform details |
| `projects_portfolio_overview.md` | This file — business context and usage |
| `Sellbot-plan/SellBot_Developer_Specific.yml` | SellBot-360 automation blueprint referencing this module |
