# Zoho CRM — Projects Portfolio Page: Full DOM Scan Report (Complete)
> Scan Date: 2026-02-26
> Source: Live DOM — read_page + screenshot + Create Project Portfolio form deep-scan
> Organisation: Kurinjee Promoters (org60043078423)
> No guesses. No summaries. Only what is visible in the UI.
---
## 1. Page Identity
```yaml
page_identity:
  page_name: "Projects Portfolio"
  module: "Projects Portfolio"
  internal_module_name: "CustomModule3"
  crm_platform: "Zoho CRM"
  organisation_id: "org60043078423"
  organisation_name: "Kurinjee Promoters"
  url_pattern: "https://crm.zoho.in/crm/org60043078423/tab/CustomModule3/custom-view/955332000000436287/list"
  custom_view_id: "955332000000436287"
  active_view_label: "All Projects Portfolio"
  current_page: 1
  total_records: 3
  records_shown: "1 to 3"
  layout_id: "955332000000425393"
  account_id: "955332000000406001"
  module_type: "Custom Module"
  create_button_label: "Create Project Portfolio"
  create_form_title: "Create Project Portfolio"
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
      - "Page title: Projects Portfolio"
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
      - "Custom View tab bar (All Projects Portfolio + ...)"
      - "Toolbar row (Filter, Sort, view toggles, Create Project Portfolio)"
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
      active: true
      has_more_actions: true
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
  page_title: "Projects Portfolio"
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
    active_view: "All Projects Portfolio"
    overflow_button: "... (More Custom Views)"
    actions:
      - "New Custom View → /tab/CustomModule3/custom-views/create"
      - "Manage Custom View → /tab/CustomModule3/custom-views/manage?category=all_custom_views"
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
    label: "Create Project Portfolio"
    style: "Blue primary button (truncated in viewport as 'Create Project P...')"
    secondary_arrow: "▼ dropdown"
    overflow_menu: "... (Actions)"
  actions_menu_items:
    - label: "Import Projects Portfolio"
      href: "/crm/org60043078423/settings/import?module=CustomModule3&step=1"
    - label: "Mass Delete"
      href: "/crm/org60043078423/tab/CustomModule3/actions/mass-tools?type=mass_delete"
    - label: "Mass Update"
      href: "/crm/org60043078423/tab/CustomModule3/actions/mass-tools?type=mass_update"
    - label: "Manage Tags"
      href: "/crm/org60043078423/settings/manage-tags?module=CustomModule3"
    - label: "Drafts"
      href: "/crm/org60043078423/tab/CustomModule3/actions/draft?module=CustomModule3"
    - label: "Mass Email"
      href: "/crm/org60043078423/settings/manage-mass-mail?module=CustomModule3"
    - label: "Autoresponders"
      href: "/crm/org60043078423/settings/auto-responders?module=CustomModule3"
    - label: "Approve Projects Portfolio"
      href: "/crm/org60043078423/tab/CustomModule3/actions/approvals"
    - label: "Deduplicate Projects Portfolio"
      type: "In-page action"
    - label: "Create Client Script"
      type: "In-page action"
    - label: "Export Projects Portfolio"
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
  title: "Filter Projects Portfolio by"
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
      fields:
        - "Airport Name"
        - "Annual Appreciation Rate"
        - "Approach Roads Condition"
        - "Banks"
        - "Base Price Per Unit"
        - "Budget"
        - "Bus Stop Name"
        - "Buyer Age Range Max"
        - "Buyer Age Range Min"
        - "Childrens Park"
        - "City"
        - "Colleges"
        - "Completion Stage"
        - "Compound Wall"
        - "Connected To"
        - "Created By"
        - "Created Time"
        - "Customization Available"
        - "Development Stage"
        - "Distance from Airport"
        - "Distance from Bus Stop"
        - "Distance from Railway Station"
        - "District"
        - "DTCP Approval Number"
        - "DTCP Approved"
        - "Electricity Connection"
        - "Estimated Completion Date"
        - "Expected Conversion Rate"
        - "Folder ID"
        - "Folder URL"
        - "Gated Community"
        - "Grocery"
        - "Highway Distance"
        - "Hospitals"
        - "Income Level Max"
        - "Income Level Min"
        - "Index"
        - "Job Creation Opportunities"
        - "Land Area"
        - "Land Ownership Verified"
        - "Landmarks"
        - "Last Activity Time"
        - "Litigation Risk"
        - "Local Population Growth"
        - "Major Infrastructure Projects"
        - "Map Link"
        - "Marketing Budget Digital"
        - "Marketing Budget Offline"
        - "Marketing Budget Partnerships"
        - "Modified By"
        - "Modified Time"
        - "Monthly Lead Target"
        - "Monthly Maintenance Fee"
        - "Nearest NH"
        - "No Of Units"
        - "Pincode"
        - "Project Portfolio Name"
        - "Project Portfolio Owner"
        - "Project Type"
        - "Railway Station Name"
        - "RERA Number"
        - "RERA Registered"
        - "Restaurants"
        - "Road Type"
        - "Sales Revenue Target"
        - "Solar Street Light"
        - "State"
        - "Storm Water Drainage"
        - "Street"
        - "Tag"
        - "Unsubscribed Mode"
        - "Unsubscribed Time"
        - "Water Supply"
        - "Website Project Link"
    filter_by_subforms:
      label: "Filter By Subforms"
      collapsible: true
      filter_type: "Checkbox"
      options:
        - "Competitive Analysis"
    filter_by_related_modules:
      label: "Filter By Related Modules"
      collapsible: true
      filter_type: "Checkbox"
      modules:
        - "Calls"
        - "Deals (Deals Site Visit Location)"
        - "Emails"
        - "Leads (Leads Site Visit Location)"
        - "Meetings"
        - "Notes"
        - "Tasks"
```
---
## 7. Records List View (Table)
```yaml
records_list_view:
  view_label: "All Projects Portfolio"
  total_records: 3
  current_page: 1
  records_shown: "1 to 3"
  view_settings_button: true
  note: "All records fit on one page — no pagination needed"
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
    - name: "Project Portfolio Name"
      type: "Text / Link to record detail"
      sortable: true
      filter_dropdown: "All"
      column_options: true
    - name: "Budget"
      type: "Currency (₹)"
      sortable: true
      column_options: true
    - name: "Project Type"
      type: "Text (project type label)"
      sortable: true
      column_options: true
    - name: "Created Time"
      type: "DateTime (DD/MM/YYYY HH:MM AM/PM)"
      sortable: true
      column_options: true
    - name: "(Column settings icon)"
      type: "Column configuration"
  projects:
    - row: 1
      project_name: "Mettupalayam"
      record_href: "/crm/org60043078423/tab/CustomModule3/955332000003796012"
      record_id: "955332000003796012"
      budget: "₹ 20,00,000.00"
      project_type: "Plots"
      created_time: "24/11/2025 01:36 PM"
      last_activity: "(none visible)"
    - row: 2
      project_name: "Mullai Nagar"
      record_href: "/crm/org60043078423/tab/CustomModule3/955332000000490001"
      record_id: "955332000000490001"
      budget: "₹ 67,00,000.00"
      project_type: "Mixed Use"
      created_time: "29/06/2025 09:29 PM"
      last_activity: "(none visible)"
    - row: 3
      project_name: "Eswara Nagar"
      record_href: "/crm/org60043078423/tab/CustomModule3/955332000000488002"
      record_id: "955332000000488002"
      budget: "₹ 25,00,000.00"
      project_type: "Mixed Use"
      created_time: "29/06/2025 09:25 PM"
      last_activity: "(none visible)"
  project_type_summary:
    Plots: 1
    Mixed_Use: 2
  budget_summary:
    - "₹ 20,00,000.00 — Mettupalayam (Plots)"
    - "₹ 67,00,000.00 — Mullai Nagar (Mixed Use)"
    - "₹ 25,00,000.00 — Eswara Nagar (Mixed Use)"
    total_visible: "₹ 1,12,00,000.00"
  per_row_actions:
    - "Checkbox (multi-select)"
    - "More options (hover ellipsis)"
    - "Click Project Portfolio Name → Project detail view"
  pagination:
    total_records: 3
    current_page: 1
    per_page: 3
    display: "1 to 3"
    previous_button: true
    next_button: true
    note: "All records on single page"
```
---
## 8. CREATE PROJECT PORTFOLIO — Full Form Scan
```yaml
create_project_portfolio_form:
  page_title: "Create Project Portfolio"
  url: "https://crm.zoho.in/crm/org60043078423/tab/CustomModule3/create?layoutId=955332000000425393&redirect=false"
  layout_id: "955332000000425393"
  edit_layout_link: "/crm/org60043078423/settings/modules/CustomModule3/layouts/955332000000425393"
  module_internal: "CustomModule3"
  form_action_buttons:
    - label: "Save"
      type: "Primary blue button"
      behavior: "Saves the new project portfolio record and returns to list"
    - label: "Save and New"
      type: "Secondary button"
      behavior: "Saves current record and opens a fresh Create Project Portfolio form"
    - label: "Cancel"
      type: "Secondary button"
      behavior: "Discards form and returns to Projects Portfolio list"
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
    project_overview:
      section_label: "Project Overview"
      note: "Core identity and financial overview of the project"
      fields:
        - label: "Project Portfolio Name"
          type: "Text input"
          required: true
          visual_indicator: "Red border / highlighted field"
        - label: "Budget"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
        - label: "Project Type"
          type: "Dropdown / combobox"
          default: "-None-"
          required: true
          visual_indicator: "Red border"
          note: "Visible types in existing records: Plots, Mixed Use"
        - label: "Land Area"
          type: "Text input"
          placeholder: "in Acres"
          required: false
        - label: "No Of Units"
          type: "Text input"
          required: false
        - label: "Development Stage"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Completion Stage"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Base Price Per Unit"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
        - label: "Estimated Completion Date"
          type: "Date picker"
          placeholder: "DD/MM/YYYY"
          required: false
        - label: "Price Advantages"
          type: "Text area (multi-line)"
          required: false
        - label: "Connected To"
          type: "Lookup (Leads)"
          sub_label: "Leads"
          has_search: true
          has_new_lead_option: true
          required: false
    location:
      section_label: "Location"
      note: "Physical address details of the project"
      fields:
        - label: "Street"
          type: "Text input"
          required: true
          visual_indicator: "Red border"
        - label: "City"
          type: "Text input"
          required: false
        - label: "District"
          type: "Text input"
          required: false
        - label: "State"
          type: "Dropdown / combobox"
          default_value: "Tamil Nadu"
          required: false
        - label: "Pincode"
          type: "Text input"
          required: false
        - label: "Nearest NH"
          type: "Text input"
          required: false
        - label: "Highway Distance"
          type: "Text input"
          required: false
        - label: "Landmarks"
          type: "Text input"
          required: false
    location_and_accessibility:
      section_label: "Location and Accessibility"
      note: "Proximity to transport, amenities, and infrastructure"
      fields:
        - label: "Railway Station Name"
          type: "Text input"
          required: false
        - label: "Bus Stop Name"
          type: "Text input"
          required: false
        - label: "Distance from Bus Stop"
          type: "Text input"
          required: false
        - label: "Airport Name"
          type: "Text input"
          required: false
        - label: "Distance from Airport"
          type: "Text input"
          required: false
        - label: "Distance from Railway Station"
          type: "Text input"
          required: false
        - label: "Restaurants"
          type: "Text input"
          required: false
        - label: "Colleges"
          type: "Text input"
          required: false
        - label: "Banks"
          type: "Text input"
          required: false
        - label: "Grocery"
          type: "Text input"
          required: false
        - label: "Hospitals"
          type: "Text input"
          required: false
        - label: "Major Infrastructure Projects"
          type: "Text input"
          required: false
        - label: "Approach Roads Condition"
          type: "Text input"
          required: false
        - label: "Annual Appreciation Rate"
          type: "Text input"
          required: false
        - label: "Local Population Growth"
          type: "Text input"
          required: false
        - label: "Property Value Trends"
          type: "Text input"
          required: false
        - label: "Job Creation Opportunities"
          type: "Text input"
          required: false
        - label: "Map Link"
          type: "Text input"
          required: false
    project_features:
      section_label: "Project Features"
      note: "Legal approvals, infrastructure, amenities, and customization"
      fields:
        - label: "DTCP Approved"
          type: "Text input"
          required: false
        - label: "DTCP Approval Number"
          type: "Text input"
          required: false
        - label: "RERA Registered"
          type: "Text input"
          required: false
        - label: "RERA Number"
          type: "Text input"
          required: false
        - label: "Land Ownership Verified"
          type: "Text input"
          required: false
        - label: "Litigation Risk"
          type: "Text input"
          required: false
        - label: "Gated Community"
          type: "Text input"
          required: false
        - label: "Road Type"
          type: "Text input"
          required: false
        - label: "Compound Wall"
          type: "Text input"
          required: false
        - label: "Road Widths"
          type: "Text input"
          required: false
        - label: "Water Supply"
          type: "Text input"
          required: false
        - label: "Storm Water Drainage"
          type: "Text input"
          required: false
        - label: "Electricity Connection"
          type: "Text input"
          required: false
        - label: "Solar Street Light"
          type: "Text input"
          required: false
        - label: "Childrens Park"
          type: "Text input"
          required: false
        - label: "Customization Available"
          type: "Text input"
          required: false
        - label: "Other Amenities"
          type: "Text input"
          required: false
        - label: "Customization Options"
          type: "Text input"
          required: false
        - label: "Monthly Maintenance Fee"
          type: "Text input"
          required: false
        - label: "Unique Selling Points"
          type: "Text input"
          required: false
        - label: "Maintenance Services"
          type: "Text input"
          required: false
    competitive_analysis:
      section_label: "Competitive Analysis"
      type: "Subform (repeatable rows)"
      note: "Tabular subform — each row represents one competitor"
      subform_columns:
        - "Competitor Name"
        - "Competitor Location"
        - "Distance From Highway"
        - "Price Range Per Cent"
        - "Key Strengths"
        - "Key Weaknesses"
      add_row_button:
        label: "Add row"
        behavior: "Adds a new competitor row to the subform"
      navigation:
        label: "Go to top of the list"
    target_audience:
      section_label: "Target Audience"
      note: "Demographic and lifestyle profile of ideal buyers"
      fields:
        - label: "Target Professions"
          type: "Text input"
          required: false
        - label: "Buyer Age Range Min"
          type: "Text input"
          required: false
        - label: "Buyer Age Range Max"
          type: "Text input"
          required: false
        - label: "Income Level Min"
          type: "Text input"
          required: false
        - label: "Income Level Max"
          type: "Text input"
          required: false
        - label: "Pain Points Addressed"
          type: "Text input"
          required: false
        - label: "Lifestyle Preferences"
          type: "Text input"
          required: false
    marketing_and_sales_strategy:
      section_label: "Marketing and Sales Strategy"
      note: "Budget allocation, channels, and sales targets"
      fields:
        - label: "Digital Marketing Channels"
          type: "Text area (multi-line)"
          required: false
        - label: "Offline Marketing Strategies"
          type: "Text area (multi-line)"
          required: false
        - label: "Monthly Lead Target"
          type: "Text input"
          required: false
        - label: "Expected Conversion Rate"
          type: "Text input"
          required: false
        - label: "Sales Revenue Target"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
        - label: "Marketing Budget Digital"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
        - label: "Marketing Budget Offline"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
        - label: "Marketing Budget Partnerships"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
    internal_use:
      section_label: "Internal Use"
      note: "CRM ownership, folder references, and project link"
      fields:
        - label: "Project Portfolio Owner"
          type: "Combobox / lookup with search"
          default_value: "Kurinjee Promoters"
          has_search: true
          search_placeholder: "Search Users"
          has_open_button: true
          required: false
          system_alert: "Maximum number of Projects Portfolio for this user is reached."
        - label: "Website Project Link"
          type: "Text input"
          required: false
        - label: "Folder ID"
          type: "Text input"
          required: false
        - label: "Folder URL"
          type: "Text input"
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
    - "Projects Portfolio → /tab/CustomModule3 (active)"
    - "Employee Portfolio → /tab/CustomModule5"
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
    - "Create Project Portfolio (primary CTA)"
    - "Create Project Portfolio dropdown (▼)"
    - "Actions overflow (...)"
  custom_view:
    - "All Projects Portfolio tab"
    - "More Custom Views (...)"
    - "New Custom View → /tab/CustomModule3/custom-views/create"
    - "Manage Custom View → /tab/CustomModule3/custom-views/manage?category=all_custom_views"
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
    - "Filter By Fields section toggle (70+ fields)"
    - "Filter By Subforms section toggle (Competitive Analysis)"
    - "Filter By Related Modules section toggle"
  table:
    - "Per-row checkbox (multi-select)"
    - "Per-row More options (hover)"
    - "Click Project Portfolio Name → detail view"
    - "Column header sort: Project Portfolio Name"
    - "Column header sort: Budget"
    - "Column header sort: Project Type"
    - "Column header sort: Created Time"
    - "Column config icon (⇌)"
    - "View Settings button"
  pagination:
    - "Previous page"
    - "Next page"
  actions_menu:
    - "Import Projects Portfolio → /settings/import?module=CustomModule3&step=1"
    - "Mass Delete → /tab/CustomModule3/actions/mass-tools?type=mass_delete"
    - "Mass Update → /tab/CustomModule3/actions/mass-tools?type=mass_update"
    - "Manage Tags → /settings/manage-tags?module=CustomModule3"
    - "Drafts → /tab/CustomModule3/actions/draft?module=CustomModule3"
    - "Mass Email → /settings/manage-mass-mail?module=CustomModule3"
    - "Autoresponders → /settings/auto-responders?module=CustomModule3"
    - "Approve Projects Portfolio → /tab/CustomModule3/actions/approvals"
    - "Deduplicate Projects Portfolio"
    - "Create Client Script"
    - "Export Projects Portfolio"
    - "Zoho Sheet View"
    - "Print View"
  create_project_portfolio_form:
    - "Save button"
    - "Save and New button"
    - "Cancel button"
    - "Edit Page Layout link"
    - "Project Portfolio Name text input"
    - "Project Type dropdown"
    - "Budget currency input"
    - "Land Area text input"
    - "No Of Units text input"
    - "Development Stage dropdown"
    - "Completion Stage dropdown"
    - "Base Price Per Unit currency input"
    - "Estimated Completion Date date picker"
    - "Price Advantages text area"
    - "Connected To (Leads) lookup"
    - "New Lead option in Connected To"
    - "Street text input"
    - "City text input"
    - "District text input"
    - "State dropdown (default: Tamil Nadu)"
    - "Pincode text input"
    - "Nearest NH text input"
    - "Highway Distance text input"
    - "Landmarks text input"
    - "All Location and Accessibility text inputs (18 fields)"
    - "All Project Features text inputs (22 fields)"
    - "Competitive Analysis subform — Add row button"
    - "Competitive Analysis subform — Go to top of list"
    - "All Target Audience text inputs (7 fields)"
    - "All Marketing and Sales Strategy inputs (8 fields)"
    - "Project Portfolio Owner combobox"
    - "Website Project Link text input"
    - "Folder ID text input"
    - "Folder URL text input"
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
## 11. Projects Portfolio Module — Purpose & Data Context
```yaml
projects_portfolio_module_context:
  purpose: >
    The Projects Portfolio module is a Custom Module in Zoho CRM used by
    Kurinjee Promoters to store and manage real estate project details.
    Each record represents a physical property development project (e.g. a
    plotted layout or mixed-use development). It captures project financials,
    location, legal approvals, amenities, competitive landscape, target buyer
    profile, and marketing strategy — providing a 360° project data store
    linked to Deals, Leads, and Site Visits.
  module_type: "Custom Module (CustomModule3)"
  data_creation_method: "Manual via 'Create Project Portfolio' button"
  key_data_stored:
    - "Project name, type (Plots / Mixed Use), budget"
    - "Land area, number of units, development & completion stage"
    - "Base price per unit, price advantages"
    - "Full location: Street, City, District, State, Pincode"
    - "Accessibility: railway, bus, airport distances"
    -