# Tasks Module — Overview & Context

## What Is This Module?

The **Tasks** module in Zoho CRM tracks actionable items that need to be completed by team members. A Task represents a specific activity with a due date, priority level, and status — such as making a phone call, sending an email, preparing documents, or following up with a lead. Tasks are essential for managing daily workflows and ensuring no follow-up falls through the cracks.

Each Task record includes a subject, due date, priority (High/Normal/Low), status (Not Started/In Progress/Completed), and optional links to related records (Leads, Contacts, Accounts, Deals).

---

## Why Does This Module Exist?

In real estate sales, consistent follow-up is the difference between closing a deal and losing a prospect. The Tasks module exists to:

1. **Track pending activities** — Every call, email, document preparation, and follow-up is recorded as a task.
2. **Prioritize daily work** — Priority and due date help team members focus on what's urgent and important.
3. **Ensure accountability** — Task Owner field makes it clear who is responsible for each activity.
4. **Support sales workflows** — Tasks are auto-created during lead qualification, site visit scheduling, and deal progression.
5. **Measure team productivity** — Completed vs. pending tasks provide insight into individual and team performance.
6. **Prevent dropped follow-ups** — Task reminders ensure no lead goes uncontacted.

Without a Tasks module, follow-ups would rely on memory or scattered notes — leading to missed opportunities and inconsistent customer experience.

---

## Who Uses This Module?

| Role | Usage |
|---|---|
| **Telecaller** | Creates and completes call tasks; follows up on lead assignments; logs call outcomes |
| **BDM (Business Development Manager)** | Schedules site visit tasks; creates deal follow-up tasks; tracks document preparation |
| **Manager / Admin** | Reviews team task completion; assigns tasks to team members; monitors overdue tasks |
| **All CRM Users** | Creates personal tasks; views task calendar; marks tasks as completed |

---

## How It Fits in the CRM Workflow

```
[Lead Created]
       ↓
[Auto-Create Tasks]
  ├── Call Attempt 1 (Day 1)
  ├── Call Attempt 2 (Day 2)
  ├── Call Attempt 3 (Day 3)
  ├── Call Attempt 4 (Day 4)
  └── Call Attempt 5 (Day 5)
       ↓
[Lead Qualified]
       ↓
[Site Visit Scheduled]
       ↓
[New Tasks Created]
  ├── Send Brochure (Today)
  ├── Confirm Visit (Day before)
  ├── Conduct Site Visit (Scheduled date)
  └── Follow-up Call (Day after visit)
       ↓
[Deal Progression]
       ↓
[More Tasks]
  ├── Send Agreement Draft
  ├── Collect Documents
  ├── Schedule Signing Meeting
  └── Follow-up for Payment
```

The Tasks module is **cross-functional** — it integrates with every other module. Tasks can be related to Leads, Contacts, Accounts, Deals, Meetings, and Calls. A single lead may have 10+ tasks created throughout its lifecycle.

---

## Key Sections in a Task Record

### Task Information
| Field | Type | Purpose |
|---|---|---|
| Subject | Text | Brief description of the task (e.g., "Call Followup", "Site Visit") |
| Task Owner | User Lookup | CRM user who owns the task |
| Due Date | Date | When the task should be completed |
| Start Date | Date | When work on the task begins |
| Send Notification | Checkbox | Email reminder before due date |
| Hours to Complete | Number | Estimated effort |
| Task Type | Dropdown | Call, Email, Meeting, Admin, etc. |

### Status & Priority
| Field | Values | Purpose |
|---|---|---|
| Status | Not Started, In Progress, Completed, Deferred, Waiting on Input | Current progress state |
| Priority | High, Normal, Low | Urgency level |

### Relationship Fields
| Field | Lookup | Purpose |
|---|---|---|
| Related To | Account/Lead | Links task to a sales record |
| Contact Name | Contact | Person associated with the task |
| Telecaller | Employee Portfolio | Telecaller assigned (custom field) |
| Approver | User | Manager who must approve task completion |

### Description
| Field | Type | Purpose |
|---|---|---|
| Description | Text Area | Detailed notes about what needs to be done |

---

## Kurinjee Promoters — Business Context

| Detail | Value |
|---|---|
| Organisation | Kurinjee Promoters |
| Org ID | 60043078423 |
| Industry | Real estate (property sales) |
| Total tasks observed | 4,276 |
| Layout ID | 955332000000425353 |
| Module Type | Standard CRM Module |
| Active view | All Tasks (custom_view_id: 955332000000435996) |
| Default sort | Due Date (ascending) |

### Task Distribution (Observed Sample)

| Status | Count (Sample) | Percentage |
|---|---|---|
| Not Started | Majority | ~80% |
| In Progress | Some | ~15% |
| Completed | — | ~5% |

| Priority | Count (Sample) | Percentage |
|---|---|---|
| High | Majority | ~60% |
| Normal | Some | ~30% |
| Low | Few | ~10% |

### Task Types Observed

| Subject Pattern | Purpose |
|---|---|
| Call / Call Followup | Outbound call to lead/customer |
| Eswaranagar | Project-specific task (linked to property) |
| Register for upcoming CRM Webinars | Training/administrative task |
| Get Apporval from Manager | Approval workflow task (note: typo "Apporval" visible in UI) |

**Observation:** The high task count (4,276) relative to leads (2,077) suggests approximately **2 tasks per lead on average** — indicating a structured follow-up system where multiple call attempts and actions are tracked per prospect.

---

## Key Relationships with Other Modules

| Related Module | Relationship |
|---|---|
| **Leads** | "Related To" field links task to a lead; call tasks created for lead follow-up |
| **Contacts** | "Contact Name" field links task to a person |
| **Accounts** | "Related To" field links task to a company |
| **Deals** | Tasks created for deal follow-up, document collection, meetings |
| **Meetings** | Tasks can precede or follow scheduled meetings |
| **Calls** | Call tasks logged; completed calls may generate follow-up tasks |
| **Notes** | "Notes" is the only related module in filter panel |
| **Employee Portfolio** | "Telecaller" field assigns task to specific employee |

---

## Module URL Reference

| Screen | URL |
|---|---|
| Tasks list (default view) | `/crm/org60043078423/tab/Tasks` |
| All Tasks custom view | `/crm/org60043078423/tab/Tasks/custom-view/955332000000435996/list` |
| Create Task form | `/crm/org60043078423/tab/Tasks/create?layoutId=955332000000425353` |
| Task detail view | `/crm/org60043078423/tab/Tasks/{task_id}` |
| Edit Task | `/crm/org60043078423/tab/Tasks/{task_id}/edit` |
| Edit layout | `/crm/org60043078423/settings/modules/Tasks/layouts/955332000000425353` |
| Import Tasks | `/crm/org60043078423/settings/import?module=Tasks&step=1` |
| Manage Tags | `/crm/org60043078423/settings/manage-tags?module=Tasks` |

---

## Task Lifecycle

```
[Task Created]
       ↓
[Status: Not Started]
       ↓
[Work Begun]
       ↓
[Status: In Progress]
       ↓
[Work Completed]
       ↓
[Status: Completed]
       ↓
[Task Closed]
```

**Alternative Paths:**
- **Deferred:** Task postponed to later date
- **Waiting on Input:** Blocked until external input received
- **Cancelled:** Task no longer needed

---

## Actions Menu (Limited Compared to Other Modules)

The Tasks module has a **leaner actions menu** than Contacts, Deals, or Employee Portfolio:

| Available | Not Available |
|---|---|
| Import Tasks | Mass Email |
| Mass Delete | Autoresponders |
| Mass Update | Approve Tasks |
| Manage Tags | Deduplicate Tasks |
| Export Tasks | Create Client Script |
| Print View | Zoho Sheet View |

**Note:** Tasks don't support mass email or autoresponders (tasks are internal activities, not customer-facing records).

---

## Integration with SellBot-360 Automation

In the **SellBot-360** blueprint (Step 4: Lead Assignment & Call Attempts), tasks are auto-created:

| Automation Step | Task Created |
|---|---|
| Lead Assignment | 5 tasks: Call Attempt 1 → Call Attempt 5 (Day 1–5) |
| Site Visit Booked | Task: "Site Visit Booked" in lead timeline |
| Day 6 TL Review | Task for Team Leader to review unresponsive lead |
| Hot Lead Qualified | 8 follow-up tasks over 60 days |
| Warm Lead Qualified | 4 follow-up tasks over 30 days |

**Task Auto-Creation Rules:**
- Tasks cannot be skipped — sequential progress required
- If task not completed before due time → WhatsApp message sent to lead automatically
- Task completion triggers next task in sequence

---

## Related Documentation

| File | Description |
|---|---|
| `Tasks.md` | Full DOM scan with 18 field definitions, list view structure |
| `tasks_overview.md` | This file — business context and usage |

---

## Comparison with Other Activity Modules

| Module | Purpose | Direction | Customer-Facing |
|---|---|---|---|
| **Tasks** | Internal to-do items | Outbound (we do) | No |
| **Calls** | Phone call logs | Bidirectional | Yes (call records) |
| **Meetings** | Scheduled events | Bidirectional | Yes (invites sent) |
| **Emails** | Email correspondence | Bidirectional | Yes (emails sent) |

**Best Practice:** Use Tasks for internal planning; use Calls/Meetings/Emails for customer interaction tracking.
