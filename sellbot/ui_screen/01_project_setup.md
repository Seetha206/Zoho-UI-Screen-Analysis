# Step 1 — Project Setup (Digital Asset Management)
# SellBot UI Implementation Plan

> SellBot Step: 1 of 14
> Zoho CRM Source: /projects-porfolio/ProjectsPortfolio.md + projects_portfolio_full_structure.yaml
> Internal Zoho Name: CustomModule3

---

## 1. SellBot Objective

Before any lead is captured, the CRM Admin sets up each real estate project with all
marketing assets — brochure, videos, Google Map link, company profile, social media,
and 40–50 marketing posters. These assets are then attachable to automated WhatsApp
messages sent during Steps 4–9 via a multi-select field on each lead record.

---

## 2. Source Zoho CRM Analysis (CustomModule3 — Projects Portfolio)

From `projects_portfolio_full_structure.yaml`:
- 3 existing records: Mettupalayam (₹20L), Mullai Nagar (₹67L), Eswara Nagar (₹25L)
- Current fields captured: Project Name, Location, Price, Unit Price, Land Area, BHK, etc.
- Create form has 7 sections: Project Overview, Location, Location & Accessibility,
  Project Features, Competitive Analysis (subform), Target Audience, Marketing & Sales Strategy
- Module URL: /crm/org60043078423/tab/CustomModule3

---

## 3. SellBot Project Setup Screen Design

### 3.1 Module: Project Assets Library
```
URL Pattern: /sellbot/projects/{project_id}/assets
Access: Admin / Team Leader only
```

### 3.2 Create / Edit Project Form

#### Section 1 — Project Identity
| Field | Type | Required | Notes |
|---|---|---|---|
| Project Name | Text | Yes | Maps to existing Zoho field |
| Location | Text | Yes | Maps to existing field |
| Property Type | Picklist | Yes | Plot / Villa / Apartment / Commercial |
| Unit Price (₹) | Currency | Yes | Maps to existing field |
| Land Area (cents) | Number | No | Maps to existing field |
| Room in BHK | Text | No | e.g. "2BHK", "3BHK" |
| Available Plots | Number | No | Current inventory count |
| Promotor | Text | No | Promoter/builder name |

#### Section 2 — Digital Assets (NEW in SellBot)
| Field | Type | Required | Notes |
|---|---|---|---|
| Brochure PDF | File upload | Yes | 4–6 pages; max 5MB; PDF only |
| Intro Video Link | URL | Yes | 1–2 min; YouTube/Drive link |
| Walkthrough Video Link | URL | No | 2–4 min; site tour |
| Google Map Link | URL | Yes | Direct Maps embed/share link |
| Company Profile PDF | File upload | No | Company overview document |
| Website URL | URL | No | Project or company website |
| Social Media Link 1 | URL | No | Facebook Page |
| Social Media Link 2 | URL | No | Instagram Profile |
| Site Visit Invitation Template | Long Text | No | Default WA message text for invitations |
| Nearby Project Comparison Chart | File upload | No | PDF/PNG; max 2MB |

#### Section 3 — Marketing Posters (NEW in SellBot)
| Field | Type | Required | Notes |
|---|---|---|---|
| Marketing Posters (gallery) | Multi-file upload | No | Target: 40–50 posters; 1080×1080 px |
| Poster Tags | Multi-select | No | Festival / Offer / Feature / Update |

#### Section 4 — Competitive Analysis (Subform — from Zoho analysis)
Mirrors existing Competitive Analysis subform in CustomModule3:
| Field | Type |
|---|---|
| Competitor Project Name | Text |
| Competitor Price | Currency |
| Key Advantage | Text |
| Key Disadvantage | Text |

---

## 4. List View — Project Assets Library

```
Columns: Project Name | Location | Property Type | Unit Price | Brochure | Status | Actions
Toolbar: Filter | Sort | Create Project (blue split button) | Actions (overflow)
Per-page: [10, 20, 25, 50, 100, 200]  [reuse Zoho pattern]
```

### Toolbar — Actions overflow
- Import Projects (CSV/XLS/XLSX, max 30,000 records, 5MB)
- Export Projects
- Mass Delete
- Mass Update
- Manage Tags

---

## 5. Asset Attachment on Lead Records

A new multi-select field `Attach_from_Project_Assets` on the Lead module allows
CRM Executives to select which assets to include in outgoing WhatsApp messages.

```
Field: Attach_from_Project_Assets
Type: Multi-select picklist (dynamic — populated from Project Assets Library)
Options: Brochure PDF | Intro Video | Walkthrough Video | Google Map | Company Profile | Website
Shown in: Lead Edit form > Related Records section
Used by: Steps 4, 5, 6, 7 automation for WhatsApp attachment selection
```

---

## 6. UI Interaction States (from Zoho pattern)

| State | Behavior |
|---|---|
| File upload in progress | Progress bar inline |
| File size exceeded | Inline error: "File exceeds [X]MB limit" |
| Required field empty on Save | Inline red border + error message |
| Save success | Toast: "Project saved successfully" |
| Delete | Confirmation modal → toast: "Project deleted successfully" |
| Recycle bin | Record retained 60 days (mirrors Zoho pattern) |

---

## 7. Access Control

| Role | Permissions |
|---|---|
| Admin / Owner | Full CRUD |
| Team Leader | Read + Edit (no delete) |
| CRM Executive | Read only (view asset links when composing messages) |
| BDM | Read only |

---

## 8. Implementation Delta vs Zoho CustomModule3

| Element | Zoho (existing) | SellBot (new/changed) |
|---|---|---|
| Digital asset fields | Not present | Add: Brochure, Videos, Map, Company Profile, Social Media, Posters |
| Marketing poster gallery | Not present | Multi-file upload (40–50 images, 1080×1080) |
| Asset attachment on leads | Not present | Attach_from_Project_Assets multi-select on Lead form |
| Competitive Analysis subform | Present (already reverse-engineered) | Retain as-is |
| Remaining form structure | 7 sections confirmed | Add Section 2 (Digital Assets) + Section 3 (Posters) |
