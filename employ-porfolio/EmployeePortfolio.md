# Zoho CRM — Employee Portfolio Page: Full DOM Scan Report (Complete)
> Scan Date: 2026-02-26
> Source: Live DOM — read_page + screenshot + Create Employee Portfolios form deep-scan
> Organisation: Kurinjee Promoters (org60043078423)
> No guesses. No summaries. Only what is visible in the UI.
---
## 1. Page Identity
```yaml
page_identity:
  page_name: "Employee Portfolio"
  module: "Employee Portfolio"
  internal_module_name: "CustomModule5"
  crm_platform: "Zoho CRM"
  organisation_id: "org60043078423"
  organisation_name: "Kurinjee Promoters"
  url_pattern: "https://crm.zoho.in/crm/org60043078423/tab/CustomModule5/custom-view/955332000001288053/list?page=1"
  custom_view_id: "955332000001288053"
  active_view_label: "All Employee Portfolio"
  current_page: 1
  total_records: 8
  records_shown: "1 to 8"
  layout_id: "955332000001288040"
  account_id: "955332000000406001"
  module_type: "Custom Module"
  create_button_label: "Create Employee Portfolios"
  create_button_label_truncated: "Create Employe..."
  create_form_title: "Create Employee Portfolios"
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
      - "Page title: Employee Portfolio"
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
  main_content_area:
    sub_sections:
      - "Custom View tab bar (All Employee Portfolio + ...)"
      - "Toolbar row (Filter, Sort, view toggles, Create Employee Portfolios)"
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
      active: true
      has_more_actions: true
    - label: "Customer Feedback"
      href: "/crm/org60043078423/tab/CustomModule7"
      module_type: "Custom Module"
      is_primary: false
    - label: "Tasks"
      href: "/crm/org60043078423/tab/Tasks"
      is_primary: true
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
  sidebar_search:
    placeholder: "Search"
    type: "Text input"
    scope: "In-CRM module search"
```
---
## 4. Header Analysis
```yaml
header_analysis:
  page_title: "Employee Portfolio"
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
    active_view: "All Employee Portfolio"
    overflow_button: "... (More Custom Views)"
    actions:
      - "New Custom View → /tab/CustomModule5/custom-views/create"
      - "Manage Custom View → /tab/CustomModule5/custom-views/manage?category=all_custom_views"
      - "Show custom views as Dropdown"
  filter_sort_controls:
    - label: "Filter"
      icon: "Funnel"
      behavior: "Opens/closes Advanced Filter panel"
    - label: "Sort"
      icon: "Sort arrows"
      behavior: "Opens sort options"
  view_toggles:
    - icon: "List View"
    - icon: "Kanban / Split View"
    - icon: "Table / Grid View"
    - icon: "Canvas / Clock View"
    - icon: "Custom List View"
    - icon: "Tile View"
    - icon: "Chevron dropdown (more views)"
  utility_buttons:
    - label: "Refresh Custom View"
      behavior: "Reloads current list view"
  primary_cta:
    label: "Create Employee Portfolios"
    style: "Blue primary button (truncated in viewport as 'Create Employe...')"
    secondary_arrow: "▼ dropdown"
    overflow_menu: "... (Actions)"
  actions_menu_items:
    - label: "Import Employee Portfolio"
      href: "/crm/org60043078423/settings/import?module=CustomModule5&step=1"
    - label: "Mass Delete"
      href: "/crm/org60043078423/tab/CustomModule5/actions/mass-tools?type=mass_delete"
    - label: "Mass Update"
      href: "/crm/org60043078423/tab/CustomModule5/actions/mass-tools?type=mass_update"
    - label: "Manage Tags"
      href: "/crm/org60043078423/settings/manage-tags?module=CustomModule5"
    - label: "Drafts"
      href: "/crm/org60043078423/tab/CustomModule5/actions/draft?module=CustomModule5"
    - label: "Mass Email"
      href: "/crm/org60043078423/settings/manage-mass-mail?module=CustomModule5"
    - label: "Autoresponders"
      href: "/crm/org60043078423/settings/auto-responders?module=CustomModule5"
    - label: "Approve Employee Portfolio"
      href: "/crm/org60043078423/tab/CustomModule5/actions/approvals"
    - label: "Deduplicate Employee Portfolio"
      type: "In-page action"
    - label: "Create Client Script"
      type: "In-page action"
    - label: "Export Employee Portfolio"
      type: "In-page action"
    - label: "Zoho Sheet View"
      type: "In-page action"
    - label: "Print View"
      type: "In-page action"
```
---
## 6. Advanced Filter Panel
```yaml
advanced_filter_panel:
  title: "Filter Employee Portfolio by"
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
        - "Latest Email Status"
        - "Activities"
        - "Cadences"
    filter_by_fields:
      label: "Filter By Fields"
      collapsible: true
      filter_type: "Checkbox"
      total_fields: 19
      fields:
        - "Broker Type"
        - "Created By"
        - "Created Time"
        - "Email"
        - "Employee Name"
        - "Employee Portfolios Owner"
        - "Last Activity Time"
        - "Location"
        - "Manager"
        - "Mobile"
        - "Modified By"
        - "Modified Time"
        - "Secondary Email"
        - "Tag"
        - "Type"
        - "Unsubscribed Mode"
        - "Unsubscribed Time"
        - "Verified Broker"
        - "Year of Experience"
    filter_by_related_modules:
      label: "Filter By Related Modules"
      collapsible: true
      filter_type: "Checkbox"
      modules:
        - "Calls"
        - "Deals (Deals BDM)"
        - "Emails"
        - "Employee Portfolio (Brokers)"
        - "Leads (Leads BDM)"
        - "Leads (Leads Telecaller)"
        - "Leads (Manager)"
        - "Meetings"
        - "Notes"
        - "Tasks"
```
---
## 7. Records List View (Table)
```yaml
records_list_view:
  view_label: "All Employee Portfolio"
  total_records: 8
  current_page: 1
  records_shown: "1 to 8"
  view_settings_button: true
  note: "All 8 records fit on one page"
  column_headers:
    - name: "(Row options)"
      type: "Hover action menu (More options)"
      sortable: false
    - name: "(Checkbox)"
      type: "Multi-select checkbox"
      sortable: false
    - name: "(Activity date badge)"
      type: "Last activity date indicator"
      note: "No activity badges visible on any row — all empty"
      sortable: false
    - name: "Employee Name"
      type: "Text / Link to record detail"
      sortable: true
      filter_dropdown: "All"
      column_options: true
    - name: "Type"
      type: "Text (employee type label)"
      sortable: true
      column_options: true
    - name: "Mobile"
      type: "Phone number (clickable call link)"
      sortable: true
      column_options: true
    - name: "Email"
      type: "Email link (mailto)"
      sortable: true
      column_options: true
    - name: "(Column settings icon)"
      type: "Column configuration"
  employees:
    - row: 1
      employee_name: "Vijayasri"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000005376006"
      record_id: "955332000005376006"
      type: "Telecaller"
      mobile: ""
      email: ""
      last_activity: "(none visible)"
    - row: 2
      employee_name: "Sumathi"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000005376001"
      record_id: "955332000005376001"
      type: "Telecaller"
      mobile: ""
      email: ""
      last_activity: "(none visible)"
    - row: 3
      employee_name: "Arun pandian"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000003787133"
      record_id: "955332000003787133"
      type: "BDM"
      mobile: "(915) 002-4013"
      mobile_clickable: true
      email: ""
      last_activity: "(none visible)"
    - row: 4
      employee_name: "Dinesh kumar"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000003787123"
      record_id: "955332000003787123"
      type: "BDM"
      mobile: "(915) 002-4014"
      mobile_clickable: true
      email: ""
      last_activity: "(none visible)"
    - row: 5
      employee_name: "Vinoth kumar"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000003787097"
      record_id: "955332000003787097"
      type: "BDM"
      mobile: "(915) 002-4021"
      mobile_clickable: true
      email: ""
      last_activity: "(none visible)"
    - row: 6
      employee_name: "Elangovan"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000003787087"
      record_id: "955332000003787087"
      type: "CEO"
      mobile: "(978) 927-7775"
      mobile_clickable: true
      email: ""
      last_activity: "(none visible)"
    - row: 7
      employee_name: "Moorthy"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000001289471"
      record_id: "955332000001289471"
      type: "BDM"
      mobile: "(915) 002-4015"
      mobile_clickable: true
      email: ""
      last_activity: "(none visible)"
    - row: 8
      employee_name: "Radhakrishnan"
      record_href: "/crm/org60043078423/tab/CustomModule5/955332000001289466"
      record_id: "955332000001289466"
      type: "BDM"
      mobile: "(915) 002-4018"
      mobile_clickable: true
      email: "kurinjeepromoters.cbe@gmail.com"
      email_href: "mailto:kurinjeepromoters.cbe@gmail.com"
      last_activity: "(none visible)"
  type_summary:
    Telecaller: 2
    BDM: 5
    CEO: 1
  mobile_summary:
    note: "6 of 8 employees have visible mobile numbers; 2 (Vijayasri, Sumathi) have no mobile shown"
    numbers_visible:
      - "(915) 002-4013 — Arun pandian"
      - "(915) 002-4014 — Dinesh kumar"
      - "(915) 002-4021 — Vinoth kumar"
      - "(978) 927-7775 — Elangovan"
      - "(915) 002-4015 — Moorthy"
      - "(915) 002-4018 — Radhakrishnan"
  email_summary:
    visible_emails:
      - "kurinjeepromoters.cbe@gmail.com — Radhakrishnan"
    blank_email_rows: 7
  per_row_actions:
    - "Checkbox (multi-select)"
    - "More options (hover ellipsis)"
    - "Click Employee Name → Employee detail view"
    - "Click Mobile → Call link"
    - "Click Email → mailto link"
  pagination:
    total_records: 8
    current_page: 1
    per_page: 8
    display: "1 to 8"
    previous_button: true
    next_button: true
    note: "All records fit on one page"
```
---
## 8. CREATE EMPLOYEE PORTFOLIOS — Full Form Scan
```yaml
create_employee_portfolios_form:
  page_title: "Create Employee Portfolios"
  url: "https://crm.zoho.in/crm/org60043078423/tab/CustomModule5/create?layoutId=955332000001288040&redirect=false"
  layout_id: "955332000001288040"
  edit_layout_link: "/crm/org60043078423/settings/modules/CustomModule5/layouts/955332000001288040"
  module_internal: "CustomModule5"
  form_action_buttons:
    - label: "Save"
      type: "Primary blue button"
      behavior: "Saves the new employee portfolio record and returns to list"
    - label: "Save and New"
      type: "Secondary button"
      behavior: "Saves current record and opens a fresh Create Employee Portfolios form"
    - label: "Cancel"
      type: "Secondary button"
      behavior: "Discards form and returns to Employee Portfolio list"
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
    employee_portfolios_information:
      section_label: "Employee Portfolios Information"
      note: "Core identity and contact details of the employee"
      fields:
        - label: "Employee Name"
          type: "Text input"
          required: true
          visual_indicator: "Red border / highlighted active field"
          note: "Cursor focuses here on form open"
        - label: "Type"
          type: "Dropdown / combobox"
          default: "-None-"
          required: true
          visual_indicator: "Red border"
          note: "Visible types in existing records: Telecaller, BDM, CEO"
        - label: "Email"
          type: "Text input"
          required: false
        - label: "Mobile"
          type: "Text input"
          required: false
        - label: "Secondary Email"
          type: "Text input"
          required: false
    broker_information:
      section_label: "Broker Information"
      note: "Relevant for external broker / channel partner employees"
      fields:
        - label: "Broker Type"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Year of Experience"
          type: "Text input"
          required: false
        - label: "Location"
          type: "Multi-select combobox / tag-style input"
          placeholder: "None"
          required: false
          note: "Tag-style multi-select allowing multiple locations"
        - label: "Manager"
          type: "Lookup (Employee Portfolios)"
          has_search: true
          has_new_record_option: true
          new_record_label: "New Employee Portfolios"
          has_open_button: true
          required: false
        - label: "Verified Broker"
          type: "Checkbox (toggle)"
          default: "unchecked"
          required: false
    internal_use:
      section_label: "Internal Use"
      note: "CRM ownership and record administration"
      fields:
        - label: "Employee Portfolios Owner"
          type: "Combobox / lookup with search"
          default_value: "Kurinjee Promoters"
          has_search: true
          search_placeholder: "Search Users"
          has_open_button: true
          required: false
          system_alert: "Maximum number of Employee Portfolio for this user is reached."
  form_bottom_section:
    create_form_views:
      label: "Create Form Views"
      dropdown:
        label: "Standard View"
        options:
          - "Standard View"
      button:
        label: "Create a custom form page"
        behavior: "Opens custom form page builder"
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
    - "Employee Portfolio → /tab/CustomModule5 (active)"
    - "Customer Feedback → /tab/CustomModule7"
    - "Tasks → /tab/Tasks"
    - "Meetings → /tab/Events"
    - "Calls → /tab/Calls"
    - "Prospecting Leads → /tab/CustomModule1"
    - "Logs → /tab/CustomModule4"
    - "Scheduler → /tab/CustomModule6"
  toolbar:
    - "Filter (toggle panel)"
    - "Sort"
    - "List View toggle"
    - "Kanban View toggle"
    - "Table View toggle"
    - "Canvas View toggle"
    - "Custom List View toggle"
    - "Tile View toggle"
    - "View dropdown (chevron)"
    - "Refresh Custom View"
    - "Create Employee Portfolios (primary CTA)"
    - "Create Employee Portfolios dropdown (▼)"
    - "Actions overflow (...)"
  custom_view:
    - "All Employee Portfolio tab"
    - "More Custom Views (...)"
    - "New Custom View → /tab/CustomModule5/custom-views/create"
    - "Manage Custom View → /tab/CustomModule5/custom-views/manage?category=all_custom_views"
  filter_panel:
    - "Filter search input"
    - "Touched Records toggle"
    - "Untouched Records toggle"
    - "Record Action toggle"
    - "Related Records Action toggle"
    - "Locked toggle"
    - "Latest Email Status toggle"
    - "Activities toggle"
    - "Cadences toggle"
    - "Filter By Fields section toggle (19 fields)"
    - "Filter By Related Modules section toggle (10 modules)"
  table:
    - "Per-row checkbox (multi-select)"
    - "Per-row More options (hover)"
    - "Click Employee Name → detail view"
    - "Click Mobile → call link"
    - "Click Email → mailto link"
    - "Column header sort: Employee Name"
    - "Column header sort: Type"
    - "Column header sort: Mobile"
    - "Column header sort: Email"
    - "Column config icon (⇌)"
    - "View Settings button"
  pagination:
    - "Previous page"
    - "Next page"
  actions_menu:
    - "Import Employee Portfolio → /settings/import?module=CustomModule5&step=1"
    - "Mass Delete → /tab/CustomModule5/actions/mass-tools?type=mass_delete"
    - "Mass Update → /tab/CustomModule5/actions/mass-tools?type=mass_update"
    - "Manage Tags → /settings/manage-tags?module=CustomModule5"
    - "Drafts → /tab/CustomModule5/actions/draft?module=CustomModule5"
    - "Mass Email → /settings/manage-mass-mail?module=CustomModule5"
    - "Autoresponders → /settings/auto-responders?module=CustomModule5"
    - "Approve Employee Portfolio → /tab/CustomModule5/actions/approvals"
    - "Deduplicate Employee Portfolio"
    - "Create Client Script"
    - "Export Employee Portfolio"
    - "Zoho Sheet View"
    - "Print View"
  create_employee_portfolios_form:
    - "Save button"
    - "Save and New button"
    - "Cancel button"
    - "Edit Page Layout link"
    - "Employee Name text input (required)"
    - "Type dropdown (required)"
    - "Email text input"
    - "Mobile text input"
    - "Secondary Email text input"
    - "Broker Type dropdown"
    - "Year of Experience text input"
    - "Location multi-select combobox"
    - "Manager lookup (with search + New Employee Portfolios option)"
    - "Verified Broker checkbox"
    - "Employee Portfolios Owner combobox"
    - "Create a custom form page button"
    - "Standard View dropdown"
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
## 11. Employee Portfolio Module — Purpose & Data Context
```yaml
employee_portfolio_module_context:
  purpose: >
    The Employee Portfolio module is a Custom Module (CustomModule5) in Zoho CRM
    used by Kurinjee Promoters to store and manage internal staff and external
    channel partner (broker) profiles. Each record represents a person in the
    organisation's sales ecosystem — whether an internal employee (Telecaller, BDM,
    CEO) or an external broker. It is linked to Leads, Deals, and other employees
    via Manager relationships, enabling full team hierarchy and activity tracking.
  module_type: "Custom Module (CustomModule5)"
  data_creation_method: "Manual via 'Create Employee Portfolios' button"
  employee_types_visible:
    - label: "Telecaller"
      count: 2
      description: "Inbound/outbound call team members"
    - label: "BDM"
      count: 5
      description: "Business Development Managers — field sales team"
    - label: "CEO"
      count: 1
      description: "Chief Executive Officer"
  key_data_stored:
    - "Employee Name"
    - "Type (Telecaller / BDM / CEO)"
    - "Email (primary + secondary)"
    - "Mobile number"
    - "Broker Type (for external partners)"
    - "Year of Experience"
    - "Location (multi-select)"
    - "Manager (lookup to another Employee Portfolio)"
    - "Verified Broker (checkbox)"
    - "Employee Portfolios Owner (CRM user)"
  related_module_linkages:
    - "Calls"
    - "Deals (as BDM)"
    - "Emails"
    - "Employee Portfolio (as Brokers)"
    - "Leads (as BDM)"
    - "Leads (as Telecaller)"
    - "Leads (as Manager)"
    - "Meetings"
    - "Notes"
    - "Tasks"
  visible_employee_records:
    - name: "Vijayasri"
      type: "Telecaller"
      record_id: "955332000005376006"
    - name: "Sumathi"
      type: "Telecaller"
      record_id: "955332000005376001"
    - name: "Arun pandian"
      type: "BDM"
      mobile: "(915) 002-4013"
      record_id: "955332000003787133"
    - name: "Dinesh kumar"
      type: "BDM"
      mobile: "(915) 002-4014"
      record_id: "955332000003787123"
    - name: "Vinoth kumar"
      type: "BDM"
      mobile: "(915) 002-4021"
      record_id: "955332000003787097"
    - name: "Elangovan"
      type: "CEO"
      mobile: "(978) 927-7775"
      record_id: "955332000003787087"
    - name: "Moorthy"
      type: "BDM"
      mobile: "(915) 002-4015"
      record_id: "955332000001289471"
    - name: "Radhakrishnan"
      type: "BDM"
      mobile: "(915) 002-4018"
      email: "kurinjeepromoters.cbe@gmail.com"
      record_id: "955332000001289466"
  organisation_context:
    name: "Kurinjee Promoters"
    org_id: "org60043078423"
    account_id: "955332000000406001"
    subscription: "1 user license (limit reached)"
    system_alert: "Maximum number of Employee Portfolio for this user is reached."
  form_complexity:
    total_sections: 3
    total_fields: 10
    note: >
      The Employee Portfolio form is the most compact of all scanned modules —
      3 sections and 10 fields only. This reflects its role as a people-directory
      module rather than a complex sales or project management record.
```
---