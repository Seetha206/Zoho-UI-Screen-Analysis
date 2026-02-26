# Employee Portfolio Module — Overview & Context

## What Is This Module?

The **Employee Portfolio** module is a **custom module** (CustomModule5) in Zoho CRM that stores employee records for Kurinjee Promoters. Unlike the standard Users module (which controls CRM login access), this module maintains a comprehensive employee directory with role-based information, contact details, and organizational hierarchy.

Each Employee Portfolio record represents a team member with details such as employee name, type (role), mobile number, email, manager, location, and employment metadata.

---

## Why Does This Module Exist?

Real estate organizations need to track employee information separately from CRM user licenses. The Employee Portfolio module exists to:

1. **Maintain employee directory** — Central repository of all team members, regardless of whether they have CRM access.
2. **Track role-based assignments** — Employees are classified by type (BDM, Telecaller, CEO, Manager) for task allocation and reporting.
3. **Enable lead/task assignment** — When leads are assigned or tasks created, the Employee Portfolio module provides the lookup list of available team members.
4. **Support organizational hierarchy** — Manager field establishes reporting relationships for approval workflows.
5. **Store contact information** — Mobile numbers and emails for internal communication and external caller ID.
6. **Track employment metadata** — Year of experience, verified broker status, broker type for specialized roles.

Without this module, employee information would be scattered across spreadsheets or only available in the Users module (which is limited to CRM license holders).

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **Admin / HR** | Creates and maintains employee records, updates role changes, manages contact information |
| **Management** | Reviews team structure, assigns leads to employees, monitors employee performance |
| **BDM (Business Development Manager)** | Referenced in lead assignment; may view team member contact details |
| **Telecaller** | Assigned to leads via this module; task ownership links to employee records |

---

## How It Fits in the CRM Workflow

```
[Employee Record Created]
       ↓
[Employee Linked to Other Modules]
  ├── Leads → BDM field (lookup to Employee Portfolio)
  ├── Leads → Telecaller field (lookup to Employee Portfolio)
  ├── Deals → BDM field (lookup to Employee Portfolio)
  ├── Tasks → Task Owner / Telecaller field
  └── Related Modules → Calls, Meetings, Emails, Notes
       ↓
[Ongoing Updates]
  ├── Role changes (Type field)
  ├── Contact information updates
  └── Manager reassignment
```

The Employee Portfolio module is a **reference/master module** — it doesn't have a lifecycle like Leads or Deals. Instead, it provides context and data that enriches records in other modules. Employee records are created once and updated as employment status changes.

---

## Key Sections in an Employee Portfolio Record

### Employee Information
| Field | Purpose |
|---|---|
| Employee Name | Full name of the employee |
| Type | Role classification (BDM, Telecaller, CEO, Manager) |
| Email | Primary email address |
| Secondary Email | Additional email address |
| Mobile | Primary mobile number |
| Location | Work location or office branch |
| Manager | Reports-to relationship (lookup to Employee Portfolio) |
| Employee Portfolios Owner | CRM record owner (user lookup) |

### Employment Metadata
| Field | Purpose |
|---|---|
| Verified Broker | Broker verification status (Yes/No) |
| Broker Type | Classification for broker roles |
| Year of Experience | Total years in real estate/industry |
| Tag | Categorization tags for filtering |

### System Fields
| Field | Purpose |
|---|---|
| Created By | User who created the record |
| Created Time | Record creation timestamp |
| Modified By | User who last modified the record |
| Modified Time | Last modification timestamp |
| Last Activity Time | Most recent activity timestamp |
| Unsubscribed Mode | Email opt-out status |
| Unsubscribed Time | Opt-out timestamp |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total employees observed | 8 |
| Layout ID | 955332000001288040 |
| Internal module name | CustomModule5 |
| Active view | All Employee Portfolio |

### Employee Distribution (Observed)

| Type | Count | Percentage |
|---|---|---|
| BDM (Business Development Manager) | 5 | 62.5% |
| Telecaller | 2 | 25.0% |
| CEO | 1 | 12.5% |

### Employee List (Observed)

| Employee Name | Type | Mobile | Email |
|---|---|---|---|
| Vijayasri | Telecaller | — | — |
| Sumathi | Telecaller | — | — |
| Arun pandian | BDM | (915) 002-4013 | — |
| Dinesh kumar | BDM | (915) 002-4014 | — |
| Vinoth kumar | BDM | (915) 002-4021 | — |
| Elangovan | CEO | (978) 927-7775 | — |
| Moorthy | BDM | (915) 002-4015 | — |
| Radhakrishnan | BDM | (915) 002-4018 | kurinjeepromoters.cbe@gmail.com |

**Observations:**
- **BDM-heavy team:** 5 out of 8 employees are BDMs, indicating a strong field sales focus.
- **Limited contact data:** Only 1 email visible (Radhakrishnan); 2 telecallers have no mobile/email recorded.
- **Phone number pattern:** BDM mobile numbers follow a consistent pattern `(915) 002-XXXX`, suggesting a Coimbatore landline series with extensions.

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Leads** | "BDM" field assigns lead to a BDM; "Telecaller" field assigns to telecaller; "Manager" field for approval |
| **Deals** | "BDM" field links deal owner to employee record |
| **Tasks** | "Task Owner" and "Telecaller" fields reference employees |
| **Meetings** | Meeting invitees and organizers link to employees |
| **Calls** | Call logs reference employee who made/received the call |
| **Emails** | Email sender/recipient links to employee records |
| **Notes** | Notes created by employees link to their record |

---

## Module URL Reference

| Screen | URL |
|---|---|
| Employee Portfolio list | `/crm/org60043078423/tab/CustomModule5` |
| All Employee Portfolio view | `/crm/org60043078423/tab/CustomModule5/custom-view/955332000001288053/list` |
| Create Employee Portfolio | `/crm/org60043078423/tab/CustomModule5/create?layoutId=955332000001288040` |
| Employee detail view | `/crm/org60043078423/tab/CustomModule5/{record_id}` |
| Edit layout | `/crm/org60043078423/settings/modules/CustomModule5/layouts/955332000001288040` |
| Import Employees | `/crm/org60043078423/settings/import?module=CustomModule5&step=1` |
| Manage Tags | `/crm/org60043078423/settings/manage-tags?module=CustomModule5` |

---

## Integration with Sales Workflow

The Employee Portfolio module is critical for **lead assignment and task ownership**:

| Workflow Step | Employee Portfolio Link |
|---|---|
| Lead Capture | Auto-assign to Telecaller or BDM based on round-robin or source |
| Lead Qualification | Telecaller field tracks who made call attempts |
| Site Visit | BDM field assigns who will conduct the visit |
| Deal Closure | BDM field tracks deal owner for commission tracking |
| Task Creation | Task Owner field links to employee responsible |
| Performance Reports | Filter by BDM/Telecaller to measure individual performance |

---

## Related Documentation

| File | Description |
|---|---|
| `EmployeePortfolio.md` | Full DOM scan with 19 field definitions, list view structure |
| `employee_portfolio_overview.md` | This file — business context and usage |

---

## Comparison with Standard CRM Users Module

| Feature | Users Module | Employee Portfolio Module |
|---|---|---|
| Purpose | CRM login access control | Employee directory |
| License Required | Yes (counts toward subscription) | No (unlimited records) |
| Contact Fields | Limited (email, phone) | Extended (mobile, location, manager) |
| Role Types | Fixed (Admin, Standard, Custom) | Custom (BDM, Telecaller, CEO, etc.) |
| Organizational Hierarchy | Profile-based | Manager field (flexible) |
| Employment Metadata | None | Year of Experience, Broker Type, Verified |

**Best Practice:** Use Users module for CRM access control; use Employee Portfolio for operational team management and lead assignment.
