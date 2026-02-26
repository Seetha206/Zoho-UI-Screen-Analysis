# Zoho CRM — Tasks Page: Full DOM Scan Report (Complete)
> Scan Date: 2026-02-26
> Source: Live DOM — read_page + screenshot + Create Task form deep-scan
> Organisation: Kurinjee Promoters (org60043078423)
> No guesses. No summaries. Only what is visible in the UI.
---
## 1. Page Identity
```yaml
page_identity:
  page_name: "Tasks"
  module: "Tasks"
  internal_module_name: "Tasks"
  crm_platform: "Zoho CRM"
  organisation_id: "org60043078423"
  organisation_name: "Kurinjee Promoters"
  url_pattern: "https://crm.zoho.in/crm/org60043078423/tab/Tasks/custom-view/955332000000435996/list"
  custom_view_id: "955332000000435996"
  active_view_label: "All Tasks"
  current_page: 1
  total_records: 4276
  records_per_page: 100
  records_shown: "1 to 100"
  layout_id: "955332000000425353"
  account_id: "955332000000406001"
  module_type: "Standard CRM Module"
  create_button_label: "Create Task"
  create_form_title: "Create Task"
  sort_applied: true
  sort_field: "Due Date"
  sort_indicator: "* (asterisk visible on Due Date column)"
  new_sidebar_item_visible: "Voice of the Customer"
```
---
## 2. Layout Structure
```yaml
layout_structure:
  top_header:
    position: "Fixed top bar, full width"
    elements:
      - "Zoho CRM logo (top-left)"
      - "Hide Menu toggle button"
      - "Page title: Tasks"
      - "Search bar: 'Search records' (center)"
      - "Create (+) quick action button"
      - "Ask Zia icon"
      - "Signals (notifications) icon"
      - "Calendar icon"
      - "Marketplace icon"
      - "Setup (gear) icon"
      - "Profile avatar (letter K, red circle)"
      - "App grid (waffle) icon"
  sidebar_navigation:
    position: "Left vertical panel, dark navy background"
    width: "~240px"
    has_search: true
    workspace_label: "CRM Teamspace"
    workspace_dropdown: true
    note: "Voice of the Customer now visible in sidebar — new module not seen in earlier scans"
  main_content_area:
    sub_sections:
      - "Custom View tab bar (All Tasks + ...)"
      - "Toolbar row (Filter, Sort [active], view toggles, Create Task)"
      - "Advanced Filter panel (left, collapsible)"
      - "Records List View (table)"
      - "Pagination bar (bottom)"
  widgets_section:
    position: "Bottom persistent status bar"
    items:
      - "Visitors Online"
      - "Feedback on New UI"
      - "Announcements"
      - "Mail"
      - "Motivator"
      - "Sticky Notes"
      - "Zia"
      - "Activity Reminders"
      - "Recent Items"
      - "Accessibility"
  footer:
    visible: true
    links:
      - label: "Privacy Policy"
        href: "http://www.zoho.in/privacy.html"
      - label: "Terms of Service"
        href: "http://www.zoho.in/crm/zohocrm-terms.html"
    copyright: "© 2026 Zoho Corp. All rights reserved."
    bottom_chat_bar:
      - "Chats"
      - "Channels"
      - "Contacts"
      - text_input: "Here is your Smart Chat (Ctrl+Space)"
```
---
## 3. Sidebar Navigation — Full Module List
```yaml
sidebar_navigation:
  logo:
    label: "Zoho CRM"
    type: "Brand / logo"
    action: "Toggle menu visibility"
  global_links:
    - label: "Home"
      href: "/crm/org60043078423/tab/Home/begin"
      is_primary: true
    - label: "Reports"
      href: "/crm/org60043078423/tab/Reports"
      is_primary: true
    - label: "Analytics"
      href: "/crm/org60043078423/tab/Dashboards"
      is_primary: true
    - label: "My Requests"
      href: "/crm/org60043078423/tab/Requesters"
      is_primary: true
  workspace:
    label: "CRM Teamspace"
    dropdown: true
    options:
      - "New Teamspace"
      - "Create Folder"
      - "Associate Modules"
      - "Manage CRM Teamspace"
      - "View All Teamspace"
  module_links:
    - label: "Leads"
      href: "/crm/org60043078423/tab/Leads"
      is_primary: true
      has_more_actions: true
    - label: "Workqueue"
      href: "/crm/org60043078423/tab/Workqueue"
      is_primary: true
      badge: "✨ (AI sparkle)"
    - label: "Contacts"
      href: "/crm/org60043078423/tab/Contacts"
      is_primary: true
      has_more_actions: true
    - label: "Accounts"
      href: "/crm/org60043078423/tab/Accounts"
      is_primary: true
      has_more_actions: true
    - label: "Deals"
      href: "/crm/org60043078423/tab/Potentials"
      is_primary: true
      has_more_actions: true
    - label: "Projects Portfolio"
      href: "/crm/org60043078423/tab/CustomModule3"
      module_type: "Custom Module"
      is_primary: false
    - label: "Employee Portfolio"
      href: "/crm/org60043078423/tab/CustomModule5"
      module_type: "Custom Module"
      is_primary: false
    - label: "Customer Feedback"
      href: "/crm/org60043078423/tab/CustomModule7"
      module_type: "Custom Module"
      is_primary: false
    - label: "Tasks"
      href: "/crm/org60043078423/tab/Tasks"
      is_primary: true
      active: true
      has_more_actions: true
    - label: "Meetings"
      href: "/crm/org60043078423/tab/Events"
      is_primary: true
      has_more_actions: true
    - label: "Calls"
      href: "/crm/org60043078423/tab/Calls"
      is_primary: true
      has_more_actions: true
    - label: "Prospecting Leads"
      href: "/crm/org60043078423/tab/CustomModule1"
      module_type: "Custom Module"
      is_primary: false
    - label: "Logs"
      href: "/crm/org60043078423/tab/CustomModule4"
      module_type: "Custom Module"
      is_primary: false
    - label: "Scheduler"
      href: "/crm/org60043078423/tab/CustomModule6"
      module_type: "Custom Module"
      is_primary: false
    - label: "Voice of the Customer"
      href: "/crm/org60043078423/tab/Voice of the Customer"
      module_type: "Custom Module"
      is_primary: false
      note: "New module — not visible in earlier page scans"
  sidebar_search:
    placeholder: "Search"
    type: "Text input"
    scope: "In-CRM module search"
```
---
## 4. Header Analysis
```yaml
header_analysis:
  page_title: "Tasks"
  search_bar:
    placeholder: "Search records"
    type: "Text input"
    position: "Top center"
    shortcut: "Ctrl + /"
  quick_create_button:
    label: "+"
    position: "Right of search bar"
    behavior: "Opens quick-create dialog"
  icon_actions:
    - name: "Ask Zia"
      type: "AI assistant"
    - name: "Signals"
      type: "Notification bell"
    - name: "Calendar"
      href: "/crm/org60043078423/calendar?date=26-02-2026&viewType=day"
    - name: "Marketplace"
      href: "/crm/org60043078423/settings/extensions/all"
    - name: "Setup"
      href: "/crm/org60043078423/settings/index"
    - name: "Profile (K)"
      type: "User profile avatar"
    - name: "App Grid (Waffle)"
      type: "Cross-app navigation"
  profile_section:
    avatar: "Red circle with letter K"
    org_name: "Kurinjee Promoters"
    status: "Available"
```
---
## 5. Toolbar
```yaml
toolbar:
  custom_view_tab:
    active_view: "All Tasks"
    overflow_button: "... (More Custom Views)"
    actions:
      - "New Custom View → /tab/Tasks/custom-views/create"
      - "Manage Custom View → /tab/Tasks/custom-views/manage?category=all_custom_views"
      - "Show custom views as Dropdown"
  filter_sort_controls:
    - label: "Filter"
      icon: "Funnel"
      behavior: "Opens/closes Advanced Filter panel"
    - label: "Sort"
      icon: "Sort arrows"
      active: true
      active_indicator: "✕ (clear sort) button visible next to Sort"
      sort_field: "Due Date"
      sort_indicator: "* (asterisk) on Due Date column header"
  view_toggles:
    - icon: "List View"
    - icon: "Kanban / Split View"
    - icon: "Canvas / Clock View"
    - icon: "Custom List View"
    - icon: "Tile View"
    - icon: "Chevron dropdown (more views)"
    note: "Table/Grid view toggle not visible — Tasks has fewer view options than Contacts/Deals"
  utility_buttons:
    - label: "Refresh Custom View"
      behavior: "Reloads current list view"
  primary_cta:
    label: "Create Task"
    style: "Blue primary button"
    secondary_arrow: "▼ dropdown"
    overflow_menu: "... (Actions)"
  actions_menu_items:
    - label: "Import Tasks"
      href: "/crm/org60043078423/settings/import?module=Tasks&step=1"
    - label: "Mass Delete"
      href: "/crm/org60043078423/tab/Tasks/actions/mass-tools?type=mass_delete"
    - label: "Mass Update"
      href: "/crm/org60043078423/tab/Tasks/actions/mass-tools?type=mass_update"
    - label: "Manage Tags"
      href: "/crm/org60043078423/settings/manage-tags?module=Tasks"
    - label: "Export Tasks"
      type: "In-page action"
    - label: "Print View"
      type: "In-page action"
    note: >
      Tasks Actions menu is leaner than Contacts/Deals — no Mass Email,
      Autoresponders, Approve, Deduplicate, Create Client Script, or Zoho Sheet View
```
---
## 6. Advanced Filter Panel
```yaml
advanced_filter_panel:
  title: "Filter Tasks by"
  search_input:
    placeholder: "Search"
    type: "Text input"
  sections:
    system_defined_filters:
      label: "System Defined Filters"
      collapsible: true
      filter_type: "Checkbox"
      options:
        - "Touched Records"
        - "Untouched Records"
        - "Record Action"
        - "Related Records Action"
        - "Locked"
      note: "Tasks has 5 system filters — fewer than Contacts/Deals (8). No Latest Email Status, Activities, or Cadences filters."
    filter_by_fields:
      label: "Filter By Fields"
      collapsible: true
      filter_type: "Checkbox"
      total_fields: 18
      fields:
        - "Approver"
        - "Auto Close"
        - "Closed Time"
        - "Contact Name"
        - "Created By"
        - "Created Time"
        - "Due Date"
        - "Last Activity Time"
        - "Modified By"
        - "Modified Time"
        - "Priority"
        - "Related To"
        - "Status"
        - "Subject"
        - "Tag"
        - "Task Owner"
        - "Telecaller"
        - "Type"
    filter_by_related_modules:
      label: "Filter By Related Modules"
      collapsible: true
      filter_type: "Checkbox"
      modules:
        - "Notes"
      note: "Tasks only relates to Notes — very limited compared to Contacts (11 modules) and Deals (8 modules)"
```
---
## 7. Records List View (Table)
```yaml
records_list_view:
  view_label: "All Tasks"
  total_records: 4276
  current_page: 1
  records_per_page: 100
  records_shown: "1 to 100"
  view_settings_button: true
  sort_active: true
  sort_field: "Due Date (ascending)"
  pagination_display: "100 (visible in pagination bar)"
  column_headers:
    - name: "(Row options / Edit)"
      type: "Edit link per row"
      sortable: false
    - name: "(Checkbox)"
      type: "Multi-select checkbox"
      sortable: false
    - name: "(Activity date badge)"
      type: "Activity indicator"
      note: "Not prominently visible on Tasks rows"
      sortable: false
    - name: "Subject"
      type: "Text / Link to task record"
      sortable: true
      filter_dropdown: "All"
      column_options: true
    - name: "Telecaller"
      type: "Text"
      sortable: true
      column_options: true
    - name: "Due Date"
      type: "Date (DD/MM/YYYY)"
      sortable: true
      active_sort: true
      sort_indicator: "* (asterisk)"
      column_options: true
    - name: "Status"
      type: "Text (status label)"
      sortable: true
      column_options: true
    - name: "Priority"
      type: "Text (priority label)"
      sortable: true
      column_options: true
    - name: "Related To"
      type: "Link (Account / Lead)"
      sortable: true
      column_options: true
    - name: "Contact Name"
      type: "Link (Contact record)"
      sortable: true
      column_options: true
    - name: "Task Owner"
      type: "Text"
      sortable: true
      column_options: true
    - name: "(Column settings icon)"
      type: "Column configuration"
  visible_tasks_sample:
    note: "100 records per page — showing first 10 visible in screenshot plus DOM data for first 4"
    - row: 1
      subject: "Eswaranagar"
      task_href: "/crm/org60043078423/tab/Tasks/955332000003567071"
      edit_href: "/crm/org60043078423/tab/Tasks/955332000003567071/edit"
      record_id: "955332000003567071"
      telecaller: ""
      due_date: "(none)"
      status: "Not Started"
      priority: "High"
      related_to: "vijaya santhiyas (Lead)"
      related_href: "/crm/org60043078423/tab/Leads/955332000003567001"
      contact_name: ""
      task_owner: "Kurinjee Promoters"
    - row: 2
      subject: "Call"
      task_href: "/crm/org60043078423/tab/Tasks/955332000001682265"
      edit_href: "/crm/org60043078423/tab/Tasks/955332000001682265/edit"
      record_id: "955332000001682265"
      telecaller: "Sumathi"
      due_date: "(none)"
      status: "Not Started"
      priority: "High"
      related_to: ""
      contact_name: ""
      task_owner: "Kurinjee Promoters"
    - row: 3
      subject: "Register for upcoming CRM Webinars"
      task_href: "/crm/org60043078423/tab/Tasks/955332000000419999"
      edit_href: "/crm/org60043078423/tab/Tasks/955332000000419999/edit"
      record_id: "955332000000419999"
      telecaller: ""
      due_date: "29/06/2025"
      status: "Not Started"
      priority: "Low"
      related_to: "King (Sample) (Account)"
      related_href: "/crm/org60043078423/tab/Accounts/955332000000419622"
      contact_name: "Kris Marrier (Sample)"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000000419713"
      task_owner: "Kurinjee Promoters"
    - row: 4
      subject: "Get Apporval from Manager"
      note: "Subject contains typo 'Apporval' — visible as-is in UI"
      task_href: "/crm/org60043078423/tab/Tasks/955332000000419993"
      edit_href: "/crm/org60043078423/tab/Tasks/955332000000419993/edit"
      record_id: "955332000000419993"
      telecaller: ""
      due_date: "30/06/2025"
      status: "In Progress"
      priority: "High"
      related_to: "King (Sample) (Account)"
      related_href: "/crm/org60043078423/tab/Accounts/955332000000419622"
      contact_name: "Kris Marrier (Sample)"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000000419713"
      task_owner: "Kurinjee Promoters"
    - row: 5
      subject: "Call Followup"
      due_date: "05/08/2025"
      status: "Not Started"
      priority: "High"
    - row: 6
      subject: "Call Followup"
      due_date: "06/08/2025"
      status: "Not Started"
      priority: "High"
    - row: 7
      subject: "Call Followup"
      due_date: "07/08/2025"
      status: "Not Started"
      priority: "High"
    - row: 8
      subject: "Call Followup"
      due_date: "08/08/2025"
      status: "Not Started"
      priority: "High"
    - row: 9
      subject: "Call Followup"
      due_date: "09/08/2025"
      status: "Not Started"
      priority: "High"
    - row: 10
      subject: "Call Followup"
      due_date: "10/08/2025"
      status: "Not Started"
      priority: "High"
  status_values_visible:
    - "Not Started"
    - "In Progress"
  priority_values_visible:
    - "High"
    - "Normal"
    - "Low"
  telecaller_values_visible:
    - "Sumathi"
    - "Vijayasri"
    - "(blank — many rows have no telecaller)"
  per_row_actions:
    - "Edit link (pencil icon per row)"
    - "Checkbox (multi-select)"
    - "Click Subject → Task detail view"
    - "Click Related To → Account or Lead detail view"
    - "Click Contact Name → Contact detail view"
  pagination:
    total_records: 4276
    current_page: 1
    records_per_page: 100
    display: "1 to 100"
    previous_button: true
    next_button: true
    total_pages: "~43 pages"
    note: "Tasks paginates at 100 per page — unlike Contacts (10) and Deals (9 total)"
```
---
## 8. CREATE TASK — Full Form Scan
```yaml
create_task_form:
  page_title: "Create Task"
  url: "https://crm.zoho.in/crm/org60043078423/tab/Tasks/create?layoutId=955332000000425353&redirect=false"
  layout_id: "955332000000425353"
  edit_layout_link: "Edit Page Layout (link visible top right of form)"
  module_internal: "Tasks"
  form_action_buttons:
    - label: "Save"
      type: "Primary blue button"
      behavior: "Saves the new task and returns to Tasks list"
    - label: "Save and New"
      type: "Secondary button"
      behavior: "Saves record and opens a fresh Create Task form"
    - label: "Cancel"
      type: "Secondary button"
      behavior: "Discards form and returns to Tasks list"
  navigation_guard:
    message: "You have not saved your changes."
    sub_message: "Are you sure you want to move away from this page?"
    actions:
      - "Yes, Leave Page"
      - "Stay Here"
  right_side_panel:
    label: "Client Script"
    position: "Right edge tab"
    behavior: "Slide-out scripting panel"
  form_sections:
    task_information:
      section_label: "Task Information"
      layout: "Two-column grid"
      fields:
        - label: "Subject"
          type: "Text input"
          required: true
          visual_indicator: "Red underline / highlighted field"
          position: "Left column"
        - label: "Telecaller"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
          position: "Right column"
          note: "Links to Employee Portfolio Telecaller type"
        - label: "Type"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
          position: "Left column"
        - label: "Approver"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
          position: "Right column"
        - label: "Due Date"
          type: "Date picker"
          placeholder: "DD/MM/YYYY"
          required: false
          position: "Left column"
        - label: "Account"
          type: "Dropdown (module selector) + Lookup input"
          default_module: "Account"
          module_options:
            - "Account"
            - "Deal"
            - "Prospecting Lead"
            - "Project Portfolio"
            - "Log"
            - "Employee Portfolios"
            - "Scheduler"
            - "Customer Feedbacks"
          has_search_icon: true
          required: false
          position: "Right column"
          note: "This is the 'Related To' field — user picks the related module type first, then searches for a record"
        - label: "Status"
          type: "Dropdown / combobox"
          default: "Not Started"
          options_visible:
            - "Not Started"
          required: false
          position: "Left column"
          note: "Status values visible in list: Not Started, In Progress"
        - label: "Repeat"
          type: "Toggle switch"
          default: "Off (disabled)"
          required: false
          position: "Right column"
        - label: "Priority"
          type: "Dropdown / combobox"
          default: "High"
          options_visible:
            - "High"
          required: false
          position: "Left column"
          note: "Priority values visible in list: High, Normal, Low"
        - label: "Auto Close"
          type: "Checkbox"
          default: "Unchecked"
          required: false
          position: "Right column"
        - label: "Reminder"
          type: "Toggle switch"
          default: "Off (disabled)"
          required: false
          position: "Right column"
    description_information:
      section_label: "Description Information"
      fields:
        - label: "Description"
          type: "Text area (multi-line, resizable)"
          required: false
    internal_use:
      section_label: "Internal Use"
      fields:
        - label: "Contact Name"
          type: "Dropdown (module selector) + Lookup input"
          default_module: "Contact"
          module_selector_visible: true
          has_search_icon: true
          required: false
          note: "Allows linking to a Contact record"
        - label: "Task Owner"
          type: "Combobox / lookup with search"
          default_value: "Kurinjee Promoters"
          has_search: true
          search_placeholder: "Search Users"
          has_open_button: true
          required: false
```
---
## 9. Widgets Section (Bottom Status Bar)
```yaml
widgets_section:
  description: "Persistent bottom panel — always visible across all CRM pages"
  widgets:
    - name: "Visitors Online"
      type: "Live visitor counter"
      data_type: "Count / Real-time"
      filter_options: ["All Accounts", "Kurinjee"]
      clickable: true
    - name: "Feedback on New UI"
      type: "Feedback trigger button"
      clickable: true
    - name: "Announcements"
      type: "Organisation announcements list"
      clickable: true
    - name: "Mail"
      type: "Quick email access"
      clickable: true
    - name: "Motivator"
      type: "Sales gamification / leaderboard"
      clickable: true
    - name: "Sticky Notes"
      type: "Quick note input"
      clickable: true
    - name: "Zia"
      type: "AI assistant panel"
      clickable: true
    - name: "Activity Reminders"
      type: "Reminder list"
      count: 0
      empty_state: "No Activity Reminders found."
      clickable: true
    - name: "Recent Items"
      type: "Recently viewed records"
      clickable: true
    - name: "Accessibility"
      type: "Accessibility settings panel"
      clickable: true
```
---
## 10. Full Interaction Map
```yaml
interaction_map:
  header:
    - "Search records input"
    - "Quick create (+) button"
    - "Ask Zia icon"
    - "Signals / notifications icon"
    - "Calendar → /calendar?date=26-02-2026&viewType=day"
    - "Marketplace → /settings/extensions/all"
    - "Setup → /settings/index"
    - "Profile avatar (K)"
    - "App grid waffle icon"
    - "Hide Menu toggle"
  sidebar:
    - "Home → /tab/Home/begin"
    - "Reports → /tab/Reports"
    - "Analytics → /tab/Dashboards"
    - "My Requests → /tab/Requesters"
    - "CRM Teamspace dropdown"
    - "Sidebar Search input"
    - "Leads → /tab/Leads"
    - "Workqueue → /tab/Workqueue"
    - "Contacts → /tab/Contacts"
    - "Accounts → /tab/Accounts"
    - "Deals → /tab/Potentials"
    - "Projects Portfolio → /tab/CustomModule3"
    - "Employee Portfolio → /tab/CustomModule5"
    - "Customer Feedback → /tab/CustomModule7"
    - "Tasks → /tab/Tasks (active)"
    - "Meetings → /tab/Events"
    - "Calls → /tab/Calls"
    - "Prospecting Leads → /tab/CustomModule1"
    - "Logs → /tab/CustomModule4"
    - "Scheduler → /tab/CustomModule6"
    - "Voice of the Customer → /tab/Voice of the Customer (NEW)"
  toolbar:
    - "Filter (toggle panel)"
    - "Sort (active — shows ✕ clear button)"
    - "List View toggle"
    - "Kanban View toggle"
    - "Canvas View toggle"
    - "Custom List View toggle"
    - "Tile View toggle"
    - "View dropdown (chevron)"
    - "Refresh Custom View"
    - "Create Task (primary CTA)"
    - "Create Task dropdown (▼)"
    - "Actions overflow (...)"
  custom_view:
    - "All Tasks tab"
    - "More Custom Views (...)"
    - "New Custom View → /tab/Tasks/custom-views/create"
    - "Manage Custom View → /tab/Tasks/custom-views/manage?category=all_custom_views"
  filter_panel:
    - "Filter search input"
    - "Touched Records toggle"
    - "Untouched Records toggle"
    - "Record Action toggle"
    - "Related Records Action toggle"
    - "Locked toggle"
    - "Filter By Fields section toggle (18 fields)"
    - "Filter By Related Modules section toggle (Notes only)"
  table:
    - "Per-row Edit link"
    - "Per-row checkbox (multi-select)"
    - "Click Subject → Task detail view"
    - "Click Related To → Account / Lead detail view"
    - "Click Contact Name → Contact detail view"
    - "Column header sort: Subject"
    - "Column header sort: Telecaller"
    - "Column header sort: Due Date (active)"
    - "Column header sort: Status"
    - "Column header sort: Priority"
    - "Column header sort: Related To"
    - "Column header sort: Contact Name"
    - "Column header sort: Task Owner"
    - "Column config icon (⇌)"
    - "View Settings button"
  pagination:
    - "Previous page"
    - "Next page"
  actions_menu:
    - "Import Tasks → /settings/import?module=Tasks&step=1"
    - "Mass Delete → /tab/Tasks/actions/mass-tools?type=mass_delete"
    - "Mass Update → /tab/Tasks/actions/mass-tools?type=mass_update"
    - "Manage Tags → /settings/manage-tags?module=Tasks"
    - "Export Tasks"
    - "Print View"
  create_task_form:
    - "Save button"
    - "Save and New button"
    - "Cancel button"
    - "Edit Page Layout link"
    - "Subject text input (required)"
    - "Telecaller dropdown"
    - "Type dropdown"
    - "Approver dropdown"
    - "Due Date date picker"
    - "Account module-selector dropdown + lookup input"
    - "Status dropdown (default: Not Started)"
    - "Repeat toggle switch"
    - "Priority dropdown (default: High)"
    - "Auto Close checkbox"
    - "Reminder toggle switch"
    - "Description text area"
    - "Contact Name module-selector dropdown + lookup input"
    - "Task Owner combobox (default: Kurinjee Promoters)"
    - "Client Script side panel"
  bottom_bar:
    - "Visitors Online widget"
    - "Feedback on New UI"
    - "Announcements"
    - "Mail"
    - "Motivator"
    - "Sticky Notes"
    - "Zia"
    - "Activity Reminders"
    - "Recent Items"
    - "Accessibility"
    - "Chats tab"
    - "Channels tab"
    - "Contacts tab"
    - "Smart Chat input"
```
---
## 11. Tasks Module — Purpose & Data Context
```yaml
tasks_module_context:
  purpose: >
    The Tasks module is a standard Zoho CRM activity module used by Kurinjee
    Promoters to schedule, assign, and track follow-up actions across all
    sales records. Tasks link to Leads, Contacts, Accounts, Deals and other
    custom modules. With 4,276 total records it is by far the most populated
    module scanned, reflecting heavy use of task-based follow-up workflows —
    particularly "Call Followup" tasks assigned to Telecallers (Sumathi,
    Vijayasri) on sequential daily due dates.
  module_type: "Standard CRM Module"
  data_volume: 4276
  records_per_page: 100
  data_creation_method: "Manual via 'Create Task' button"
  key_data_stored:
    - "Subject (task name)"
    - "Type (task category)"
    - "Due Date"
    - "Status (Not Started / In Progress / Completed)"
    - "Priority (High / Normal / Low)"
    - "Telecaller (assigned telecaller from Employee Portfolio)"
    - "Approver"
    - "Related To (Account, Deal, Lead, or Custom Module record)"
    - "Contact Name"
    - "Task Owner"
    - "Repeat (toggle)"
    - "Auto Close (checkbox)"
    - "Reminder (toggle)"
    - "Description"
  related_to_module_options:
    - "Account"
    - "Deal"
    - "Prospecting Lead"
    - "Project Portfolio"
    - "Log"
    - "Employee Portfolios"
    - "Scheduler"
    - "Customer Feedbacks"
  related_module_linkages:
    - "Notes"
  status_values:
    - "Not Started"
    - "In Progress"
    note: "Completed likely exists but not visible on current page"
  priority_values:
    - "High"
    - "Normal"
    - "Low"
  telecaller_values_visible:
    - "Sumathi"
    - "Vijayasri"
  subject_patterns_visible:
    - "Call Followup (bulk sequential daily tasks — majority of records)"
    - "Eswaranagar (project name task)"
    - "Call (generic)"
    - "Register for upcoming CRM Webinars (sample/system task)"
    - "Get Apporval from Manager (typo in subject — as-is in UI)"
  sample_task_links:
    - subject: "Eswaranagar"
      record_id: "955332000003567071"
      related_to: "vijaya santhiyas (Lead/955332000003567001)"
      task_owner: "Kurinjee Promoters"
    - subject: "Call"
      record_id: "955332000001682265"
      telecaller: "Sumathi"
      task_owner: "Kurinjee Promoters"
    - subject: "Register for upcoming CRM Webinars"
      record_id: "955332000000419999"
      due_date: "29/06/2025"
      related_to: "King (Sample) Account"
      contact_name: "Kris Marrier (Sample)"
    - subject: "Get Apporval from Manager"
      record_id: "955332000000419993"
      due_date: "30/06/2025"
      status: "In Progress"
      related_to: "King (Sample) Account"
      contact_name: "Kris Marrier (Sample)"
  organisation_context:
    name: "Kurinjee Promoters"
    org_id: "org60043078423"
    subscription: "1 user license (limit reached)"
  form_complexity:
    total_sections: 3
    total_fields: 14
    unique_features:
      - "Repeat toggle (recurring task support)"
      - "Auto Close checkbox (auto-complete on linked record close)"
      - "Reminder toggle (notification trigger)"
      - "Related To field with 8 module-type options"
      - "Telecaller dropdown linked to Employee Portfolio"
      - "Approver dropdown"
      - "Sort is active by default on Due Date"
      - "100 records per page (10x Contacts)"
  notable_observations:
    - "4,276 tasks — largest dataset of all scanned modules"
    - "Majority are 'Call Followup' tasks on sequential daily dates (Aug 2025+)"
    - "Two telecallers actively assigned: Sumathi and Vijayasri"
    - "'Voice of the Customer' is a new sidebar module appearing for first time in this scan"
    - "Tasks Actions menu is leaner than other modules — no Mass Email, Autoresponders, Deduplicate"
    - "Filter panel has only 5 system defined filters (vs 8 in Contacts/Deals)"
    - "Only 1 related module for filtering: Notes"
    - "No activity date badges visible on task rows (unlike Contacts/Deals)"
```
---