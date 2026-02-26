# Zoho CRM — Deals Page: Full DOM Scan Report (Complete)
> Scan Date: 2026-02-26
> Source: Live DOM — read_page + screenshot + Create Deal form deep-scan
> Organisation: Kurinjee Promoters (org60043078423)
> No guesses. No summaries. Only what is visible in the UI.
---
## 1. Page Identity
```yaml
page_identity:
  page_name: "Deals"
  module: "Deals"
  internal_module_name: "Potentials"
  crm_platform: "Zoho CRM"
  organisation_id: "org60043078423"
  organisation_name: "Kurinjee Promoters"
  url_pattern: "https://crm.zoho.in/crm/org60043078423/tab/Potentials/custom-view/955332000000441430/list?page=1"
  custom_view_id: "955332000000441430"
  active_view_label: "All Deals"
  current_page: 1
  total_records: 9
  records_shown: "1 to 9"
  layout_id: "955332000000425340"
  account_id: "955332000000406001"
  organisation_label: "Kurinjee Promoters"
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
      - "Page title: Deals"
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
      - "Custom View tab bar (All Deals + ...)"
      - "Toolbar row (Filter, Sort, view toggles, Create Deal)"
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
      active: true
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
  page_title: "Deals"
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
    active_view: "All Deals"
    overflow_button: "... (More Custom Views)"
    actions:
      - "New Custom View → /tab/Potentials/custom-views/create"
      - "Manage Custom View → /tab/Potentials/custom-views/manage?category=all_custom_views"
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
    label: "Create Deal"
    style: "Blue primary button"
    secondary_arrow: "▼ dropdown"
    overflow_menu: "... (Actions)"
  actions_menu_items:
    - label: "Import Deals"
      href: "/crm/org60043078423/settings/import?module=Potentials&step=1"
    - label: "Import Notes"
      href: "/crm/org60043078423/settings/import?module=Notes&step=1&parentModule=Potentials"
    - label: "Mass Delete"
      href: "/crm/org60043078423/tab/Potentials/actions/mass-tools?type=mass_delete"
    - label: "Mass Update"
      href: "/crm/org60043078423/tab/Potentials/actions/mass-tools?type=mass_update"
    - label: "Manage Tags"
      href: "/crm/org60043078423/settings/manage-tags?module=Potentials"
    - label: "Drafts"
      href: "/crm/org60043078423/tab/Potentials/actions/draft?module=Potentials"
    - label: "Mass Email"
      href: "/crm/org60043078423/settings/manage-mass-mail?module=Potentials"
    - label: "Deduplicate Deals"
      type: "In-page action"
    - label: "Create Client Script"
      type: "In-page action"
    - label: "Export Deals"
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
  title: "Filter Deals by"
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
      total_fields: 130
      fields:
        - "1. Preferred Location"
        - "2. Preferred Location"
        - "3. Preferred Location"
        - "Ads Form Name"
        - "Ads Forms ID"
        - "Ads Lead Created Time"
        - "Ads Lead ID"
        - "All Traffic Sources"
        - "Amount"
        - "Approval for Closure"
        - "Attempt"
        - "Authority"
        - "BANT Form URL"
        - "BDM"
        - "BDM Feedback"
        - "BDM Form URL"
        - "Browser"
        - "Budget"
        - "Budget Concern Description"
        - "Budget Range"
        - "Budget Range Max"
        - "Budget Range Min"
        - "City (from IP address)"
        - "Client Comments"
        - "Client Feedback after the Site Visit"
        - "Client Location"
        - "Client Major Concern on Purchase"
        - "Client Rating"
        - "Client's Overall Impression"
        - "Closing Date"
        - "Comfortable Price"
        - "Comments"
        - "Connected To"
        - "Contact Name"
        - "Country (from IP address)"
        - "Created By"
        - "Created Time"
        - "Deal Closed Time"
        - "Deal Name"
        - "Deal Owner"
        - "Decision Influencers"
        - "Does the lead have the financial capability to purchase?"
        - "Does the project match the lead's location preference?"
        - "Down Payment"
        - "Estimated Budget"
        - "Expected Revenue"
        - "Family Decision Involved?"
        - "Feedback URL"
        - "First Click Campaign"
        - "First Click Channel"
        - "First Click Content"
        - "First Click Landing Page"
        - "First Click Landing Page Url"
        - "First Click Medium"
        - "First Click Referrer"
        - "First Click Source"
        - "First Click Term"
        - "First Click Timestamp"
        - "Folder ID"
        - "Folder URL"
        - "Follow-up date"
        - "GA Client ID"
        - "GA Measurement ID"
        - "GA Session ID"
        - "GCLID (GA Connector)"
        - "Index"
        - "IP Address"
        - "Is There is Any Other Specific Concerns"
        - "Land Area in cents"
        - "Language Preference"
        - "Last Activity Time"
        - "Last Click Campaign"
        - "Last Click Channel"
        - "Last Click Content"
        - "Last Click Landing Page"
        - "Last Click Landing Page Url"
        - "Last Click Medium"
        - "Last Click Referrer"
        - "Last Click Source"
        - "Last Click Term"
        - "Last Click Timestamp"
        - "Latitude"
        - "Lead Conversion Time"
        - "Lead Source"
        - "Lead Type"
        - "Loan Delay / Bank Issue Description"
        - "Loan Requirement"
        - "Longitude"
        - "Meta Lead Created Time"
        - "Modified By"
        - "Modified Time"
        - "Need"
        - "Next Committed Step"
        - "Next Step"
        - "Objection Status"
        - "Old Created Date"
        - "Old Status"
        - "Operating System"
        - "Overall Sales Duration"
        - "Pages Visited"
        - "Payment Type"
        - "Preferred Communication Channel"
        - "Preferred Location"
        - "Preferred Project"
        - "Preferred Size (Sq.Ft or Cents)"
        - "Probability (%)"
        - "Purpose Of Purchase"
        - "Real Objections"
        - "Reason For Loss"
        - "Reason For Unattempted"
        - "Reason Qualified Out"
        - "Referral Form URL"
        - "Referred By"
        - "Referred Date"
        - "Referrer Relationship"
        - "Requirement Property Type"
        - "Rooms in BHK"
        - "Sales Cycle Duration"
        - "Site Visit Date"
        - "Site Visit Location"
        - "Site Visit URL"
        - "Site Visited"
        - "Social Lead ID"
        - "Stage"
        - "Tag"
        - "Telecaller"
        - "Time"
        - "Time Zone"
        - "Timeframe to Purchase"
        - "Travel mode / Notes"
        - "Type of Property"
        - "Up to Price"
        - "Urgency Level"
        - "Visit Date"
        - "Visit Status"
        - "Visit Verified"
        - "When Are You Planning to Start"
        - "When is the lead planning to buy?"
        - "Who is making the decision for this purchase?"
    filter_by_subforms:
      label: "Filter By Subforms"
      collapsible: true
      filter_type: "Checkbox"
      options:
        - "Relevant Property"
    filter_by_related_modules:
      label: "Filter By Related Modules"
      collapsible: true
      filter_type: "Checkbox"
      modules:
        - "Calls"
        - "Deal Contact Role (Contact Roles)"
        - "Deals (Referrals)"
        - "Emails"
        - "Leads (Converted Leads)"
        - "Meetings"
        - "Notes"
        - "Tasks"
```
---
## 7. Records List View (Table)
```yaml
records_list_view:
  view_label: "All Deals"
  total_records: 9
  current_page: 1
  records_shown: "1 to 9"
  view_settings_button: true
  column_headers:
    - name: "(Row options)"
      type: "Hover action menu (More options)"
      sortable: false
    - name: "(Checkbox)"
      type: "Multi-select checkbox"
      sortable: false
    - name: "(Activity date badge)"
      type: "Last activity date — red badge"
      sortable: false
    - name: "Contact Name"
      type: "Text / Link to Contact record"
      sortable: true
      column_options: true
    - name: "Deal Name"
      type: "Text / Link to Deal record"
      sortable: true
      filter_dropdown: "All"
      column_options: true
    - name: "Amount"
      type: "Currency (₹)"
      sortable: true
      column_options: true
    - name: "Stage"
      type: "Text (deal stage label)"
      sortable: true
      column_options: true
    - name: "Closing Date"
      type: "Date (DD/MM/YYYY)"
      sortable: true
      column_options: true
    - name: "Deal Owner"
      type: "Text"
      sortable: true
      column_options: true
    - name: "(Column settings icon)"
      type: "Column configuration"
  deals:
    - row: 1
      contact_name: "Prasanth"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000004403606"
      deal_name: "Prasanth"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000004403609"
      amount: "₹ 25,00,000.00"
      stage: "Closed Won"
      closing_date: "27/11/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "Dec 11, 2025"
    - row: 2
      contact_name: "Amsa"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000003267006"
      deal_name: "Amsa"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000003267009"
      amount: ""
      stage: "Visit Completed"
      closing_date: "04/11/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "Nov 4, 2025"
    - row: 3
      contact_name: "sakthi kumar"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000003013075"
      deal_name: "sakthi kumar"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000003013078"
      amount: ""
      stage: "Visit Pending"
      closing_date: "04/01/2026"
      deal_owner: "Kurinjee Promoters"
      last_activity: "Nov 6, 2025"
    - row: 4
      contact_name: "Baskar"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000002929038"
      deal_name: "Baskar"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000002929041"
      amount: "₹ 13,26,000.00"
      stage: "Closed Won"
      closing_date: "27/11/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "Sep 11, 2025"
    - row: 5
      contact_name: "wasil"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000002819016"
      deal_name: "wasil"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000002819019"
      amount: ""
      stage: "Visit Pending"
      closing_date: "26/12/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "Oct 26, 2025"
    - row: 6
      contact_name: "Hemamurugan"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000001978012"
      deal_name: "Hemamurugan"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000001978015"
      amount: ""
      stage: "Visit Pending"
      closing_date: "29/11/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "Sep 25, 2025"
    - row: 7
      contact_name: "Krishnan"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000001907012"
      deal_name: "Krishnan"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000001907015"
      amount: "₹ 75,00,000.00"
      stage: "Booking Completed"
      closing_date: "28/08/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "(none visible)"
    - row: 8
      contact_name: "Srinivashaperumal"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000001100136"
      deal_name: "Srinivashaperumal"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000001100139"
      amount: ""
      stage: "Visit Pending"
      closing_date: "24/10/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "(none visible)"
    - row: 9
      contact_name: "Senthilkumar Rangaraj"
      contact_href: "/crm/org60043078423/tab/Contacts/955332000000681506"
      deal_name: "Senthilkumar Rangaraj"
      deal_href: "/crm/org60043078423/tab/Potentials/955332000000681509"
      amount: "₹ 15,00,000.00"
      stage: "Visit Pending"
      closing_date: "06/08/2025"
      deal_owner: "Kurinjee Promoters"
      last_activity: "(none visible)"
  stage_summary:
    Closed_Won: 2
    Booking_Completed: 1
    Visit_Completed: 1
    Visit_Pending: 5
  amount_summary:
    visible_amounts:
      - "₹ 25,00,000.00 (Prasanth — Closed Won)"
      - "₹ 13,26,000.00 (Baskar — Closed Won)"
      - "₹ 75,00,000.00 (Krishnan — Booking Completed)"
      - "₹ 15,00,000.00 (Senthilkumar Rangaraj — Visit Pending)"
    blank_amount_rows: 5
  per_row_actions:
    - "Checkbox (multi-select)"
    - "More options (hover ellipsis)"
    - "Click Contact Name → Contact Detail View"
    - "Click Deal Name → Deal Detail View"
  pagination:
    total_records: 9
    current_page: 1
    per_page: 9
    display: "1 to 9"
    previous_button: true
    next_button: true
    note: "All records fit on one page"
```
---
## 8. CREATE DEAL — Full Form Scan
```yaml
create_deal_form:
  page_title: "Create Deal"
  url: "https://crm.zoho.in/crm/org60043078423/tab/Potentials/create?layoutId=955332000000425340&redirect=false"
  layout_id: "955332000000425340"
  edit_layout_link: "/crm/org60043078423/settings/modules/Potentials/layouts/955332000000425340"
  form_action_buttons:
    - label: "Save"
      type: "Primary blue button"
      behavior: "Saves the new deal and returns to Deals list"
    - label: "Save and New"
      type: "Secondary button"
      behavior: "Saves record and opens a fresh Create Deal form"
    - label: "Cancel"
      type: "Secondary button"
      behavior: "Discards form and returns to Deals list"
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
    lead_assessment:
      section_label: "Lead Assessment"
      fields:
        - label: "Budget"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Authority"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Need"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Time"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Budget Range Max"
          type: "Text input"
          has_info_icon: true
          required: false
        - label: "Budget Range Min"
          type: "Text input"
          has_info_icon: true
          required: false
    description_information:
      section_label: "Description Information"
      fields:
        - label: "Description"
          type: "Text area (multi-line, resizable)"
          required: false
        - label: "Client Feedback after the Site Visit"
          type: "Text area (multi-line, resizable)"
          required: false
        - label: "BDM Feedback"
          type: "Text area (multi-line, resizable)"
          required: false
    qualification_form:
      section_label: "Qualification Form"
      fields:
        - label: "Does the lead have the financial capability to purchase?"
          type: "Checkbox + text input"
          required: false
        - label: "Does the project match the lead's location preference?"
          type: "Text input"
          required: false
        - label: "Who is making the decision for this purchase?"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "When is the lead planning to buy?"
          type: "Text input"
          required: false
    client_feedback:
      section_label: "Client Feedback"
      fields:
        - label: "Client Feedback"
          type: "Text input"
          required: false
        - label: "Feedback URL"
          type: "Text input"
          required: false
        - label: "Client Rating"
          type: "Text input"
          required: false
        - label: "Comments"
          type: "Text input"
          required: false
    team_lead_section:
      section_label: "Team Lead Section"
      fields:
        - label: "Team Lead"
          type: "Text input"
          required: false
        - label: "Approval for Closure"
          type: "Text input / toggle"
          required: false
    site_visit_information:
      section_label: "Site Visit Information"
      note: "Section label shown as 'Site Visit Infomation' (typo in UI)"
      fields:
        - label: "Site Visit URL"
          type: "Text input"
          required: false
        - label: "Client Comments"
          type: "Text input"
          required: false
        - label: "BDM Form URL"
          type: "Text input"
          required: false
        - label: "When Are You Planning to Start"
          type: "Text input"
          required: false
        - label: "Visit Status"
          type: "Text input"
          required: false
        - label: "Site Visit Location"
          type: "Text input"
          required: false
        - label: "Site Visit Date"
          type: "Text input"
          required: false
        - label: "BDM"
          type: "Text input"
          required: false
        - label: "Is There is Any Other Specific Concerns"
          type: "Text input"
          required: false
    site_completion_form_submission:
      section_label: "Site Completion Form Submission"
      fields:
        - label: "Visit Date"
          type: "Text input"
          required: false
        - label: "Client's Overall Impression"
          type: "Text input"
          required: false
        - label: "Real Objections"
          type: "Text input"
          required: false
        - label: "Decision Influencers"
          type: "Text input"
          required: false
        - label: "Next Committed Step"
          type: "Text input"
          required: false
        - label: "Follow-up date"
          type: "Text input"
          required: false
        - label: "Visit Verified"
          type: "Text input"
          required: false
        - label: "Objection Status"
          type: "Text input"
          required: false
        - label: "Urgency Level"
          type: "Text input"
          required: false
        - label: "BDM Notes"
          type: "Text input"
          required: false
        - label: "Amenities / Facility Expectation Description"
          type: "Text area"
          required: false
        - label: "Other Description"
          type: "Text area"
          required: false
        - label: "Travel mode / Notes"
          type: "Text input"
          required: false
        - label: "Location Mismatch Description"
          type: "Text input"
          required: false
        - label: "Timing Description"
          type: "Text input"
          required: false
        - label: "Loan Delay / Bank Issue Description"
          type: "Text input"
          required: false
        - label: "Need to Discuss with Family Description"
          type: "Text input"
          required: false
        - label: "Competing Project Comparison Description"
          type: "Text input"
          required: false
        - label: "Budget Concern Description"
          type: "Text input"
          required: false
        - label: "Legal / Approvals Clarification Description"
          type: "Text input"
          required: false
    deal_information:
      section_label: "Deal Information"
      note: "Core deal fields — required fields have red border highlight"
      fields:
        - label: "Deal Name"
          type: "Text input"
          required: true
          visual_indicator: "Red border"
        - label: "Contact Name"
          type: "Lookup with icon button"
          required: false
        - label: "Closing Date"
          type: "Date picker"
          placeholder: "DD/MM/YYYY"
          required: true
          visual_indicator: "Red border"
        - label: "Lead Source"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Stage"
          type: "Dropdown / combobox"
          default: "Closed Won"
          color_indicator: "Green dot"
          required: true
          visual_indicator: "Red border"
        - label: "Next Step"
          type: "Text input"
          required: false
        - label: "Probability (%)"
          type: "Numeric input"
          default_value: "100"
          required: false
        - label: "Amount"
          type: "Currency input"
          currency_symbol: "₹"
          has_info_icon: true
          required: false
        - label: "Expected Revenue"
          type: "Currency input"
          currency_symbol: "₹"
          required: false
        - label: "Client Location"
          type: "Text input"
          required: false
        - label: "Social Lead ID"
          type: "Text input"
          required: false
        - label: "Connected To"
          type: "Lookup (Leads)"
          sub_label: "Leads"
          has_search: true
          has_new_lead_option: true
          required: false
        - label: "Telecaller"
          type: "Text input"
          required: false
        - label: "Preferred Location"
          type: "Text input"
          required: false
        - label: "Family Decision Involved?"
          type: "Text input"
          required: false
        - label: "Language Preference"
          type: "Text input"
          required: false
        - label: "Budget Range"
          type: "Text input"
          required: false
        - label: "Preferred Communication Channel"
          type: "Text input"
          required: false
        - label: "Lead Source"
          type: "Text input"
          required: false
        - label: "Next Step"
          type: "Text input"
          required: false
        - label: "Reason For Loss"
          type: "Dropdown / combobox"
          default: "-None-"
          required: false
        - label: "Client Location"
          type: "Text input"
          required: false
        - label: "Estimated Budget"
          type: "Text input"
          required: false
        - label: "Reason Qualified Out"
          type: "Text input"
          required: false
        - label: "Lead Type"
          type: "Text input"
          required: false
        - label: "Preferred Size (Sq.Ft or Cents)"
          type: "Text input"
          required: false
        - label: "Timeframe to Purchase"
          type: "Text input"
          required: false
        - label: "Loan Requirement"
          type: "Text input"
          required: false
        - label: "Type of Property"
          type: "Text input"
          required: false
        - label: "Deal Closed Time"
          type: "Text input"
          required: false
    centilio_tracking:
      section_label: "Centilio Tracking"
      note: "Marketing attribution and web tracking fields"
      fields:
        - label: "First Click Channel"
          type: "Text input"
        - label: "First Click Referrer"
          type: "Text input"
        - label: "First Click Campaign"
          type: "Text input"
        - label: "First Click Term"
          type: "Text input"
        - label: "First Click Medium"
          type: "Text input"
        - label: "First Click Source"
          type: "Text input"
        - label: "First Click Content"
          type: "Text input"
        - label: "First Click Landing Page"
          type: "Text input"
        - label: "First Click Timestamp"
          type: "Text input"
        - label: "First Click Landing Page Url"
          type: "Text input"
        - label: "IP Address"
          type: "Text input"
        - label: "City (from IP address)"
          type: "Text input"
        - label: "Country (from IP address)"
          type: "Text input"
        - label: "Browser"
          type: "Text input"
        - label: "Operating System"
          type: "Text input"
        - label: "Latitude"
          type: "Text input"
        - label: "Longitude"
          type: "Text input"
        - label: "Ads Lead ID"
          type: "Text input"
        - label: "Ads Forms ID"
          type: "Text input"
        - label: "Last Click Channel"
          type: "Text input"
        - label: "Last Click Campaign"
          type: "Text input"
        - label: "Last Click Term"
          type: "Text input"
        - label: "Last Click Medium"
          type: "Text input"
        - label: "Last Click Content"
          type: "Text input"
        - label: "Last Click Referrer"
          type: "Text input"
        - label: "Last Click Source"
          type: "Text input"
        - label: "Last Click Landing Page"
          type: "Text input"
        - label: "Last Click Landing Page Url"
          type: "Text input"
        - label: "Last Click Timestamp"
          type: "Text input"
        - label: "Time Zone"
          type: "Text input"
        - label: "GA Client ID"
          type: "Text input"
        - label: "GCLID (GA Connector)"
          type: "Text input"
        - label: "GA Session ID"
          type: "Text input"
        - label: "GA Measurement ID"
          type: "Text input"
        - label: "Pages Visited"
          type: "Text input"
        - label: "All Traffic Sources"
          type: "Text input"
        - label: "Ads Form Name"
          type: "Text input"
        - label: "Meta Lead Created Time"
          type: "Text input"
        - label: "Ads Lead Created Time"
          type: "Text input"
    internal_use:
      section_label: "Internal Use"
      fields:
        - label: "Deal Owner"
          type: "Combobox / lookup with