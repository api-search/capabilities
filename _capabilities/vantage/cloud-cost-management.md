---
categories: []
consumed_apis: []
description: Unified workflow for cloud cost management combining cost reporting, alerting, optimization recommendations, and cloud pricing comparison. Used by FinOps teams and cloud engineers to monitor, optimize, and control cloud spending.
layout: capability
name: Vantage Cloud Cost Management
operations:
- description: List all Cost Reports.
  method: GET
  name: list-cost-reports
  path: /v1/cost-reports
- description: Create a new Cost Report.
  method: POST
  name: create-cost-report
  path: /v1/cost-reports
- description: Get a specific Cost Report.
  method: GET
  name: get-cost-report
  path: /v1/cost-reports/{cost_report_token}
- description: Update a Cost Report.
  method: PUT
  name: update-cost-report
  path: /v1/cost-reports/{cost_report_token}
- description: Delete a Cost Report.
  method: DELETE
  name: delete-cost-report
  path: /v1/cost-reports/{cost_report_token}
- description: Get costs for a report or VQL filter.
  method: GET
  name: get-costs
  path: /v1/costs
- description: List all Dashboards.
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a new Dashboard.
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: List all Budget Alerts.
  method: GET
  name: list-budget-alerts
  path: /v1/budget-alerts
- description: Create a new Budget Alert.
  method: POST
  name: create-budget-alert
  path: /v1/budget-alerts
- description: List all Anomaly Alerts.
  method: GET
  name: list-anomaly-alerts
  path: /v1/anomaly-alerts
- description: Create a new Anomaly Alert.
  method: POST
  name: create-anomaly-alert
  path: /v1/anomaly-alerts
- description: List cost optimization recommendations.
  method: GET
  name: list-recommendations
  path: /v1/recommendations
- description: List all Segments.
  method: GET
  name: list-segments
  path: /v1/segments
- description: List all Integrations.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List all cloud pricing providers.
  method: GET
  name: list-providers
  path: /v1/providers
- description: Get a specific cloud provider.
  method: GET
  name: get-provider
  path: /v1/providers/{provider_id}
- description: List cloud services.
  method: GET
  name: list-services
  path: /v1/services
- description: List cloud products with pricing.
  method: GET
  name: list-products
  path: /v1/products
- description: Get pricing data for products.
  method: GET
  name: list-prices
  path: /v1/prices
personas: []
provider_name: Vantage
provider_slug: vantage
search_terms:
- list cost reports
- delete a cost report.
- vantage
- list all resource reports.
- list all financial commitment reports.
- manage cloud provider integrations.
- list pricing providers
- get pricing data filtered by product, provider, service, or region.
- get a specific cloud product with pricing details.
- list all saved filters.
- list all business metrics.
- get a specific cost report by token.
- create dashboard
- list all cloud provider integrations.
- list all network flow reports.
- list prices
- cloud infrastructure products.
- list cloud services with pricing data.
- manage cost reports.
- list saved filters
- cloud costs
- list all cost providers.
- get costs for a report or vql filter.
- list financial commitment reports
- list all cost allocation segments.
- update an existing cost report.
- get a specific cost report.
- costs
- finops
- list all workspaces.
- list cost optimization recommendations.
- list providers
- retrieve cost data.
- list products
- create a new cost report with vql filter.
- cloud pricing
- list anomaly alerts
- manage anomaly detection alerts.
- manage cost dashboards.
- list cloud services.
- manage budget alerts.
- get a specific cloud provider.
- list cloud products with pricing.
- create a new anomaly alert.
- list all kubernetes efficiency reports.
- get a specific cloud service.
- update a cost report.
- cloud pricing services.
- cost optimization recommendations.
- list pricing services
- list resource reports
- get pricing service
- get pricing provider
- get pricing product
- list integrations
- list workspaces
- create anomaly alert
- list all integrations.
- list all cost reports.
- delete cost report
- create a new dashboard.
- list folders
- cloud pricing providers.
- list pricing products
- list managed accounts
- list all dashboards.
- update cost report
- list kubernetes efficiency reports
- list budget alerts
- get a specific cloud pricing provider.
- list all budget alerts.
- list segments
- create budget alert
- list all managed cloud accounts.
- list all teams.
- list services
- get cost report
- list all anomaly alerts.
- create a new budget alert.
- create a new cost report.
- list all cloud pricing providers.
- manage a specific cost report.
- get provider
- list cost providers
- list teams
- manage cost allocation segments.
- create cost report
- cloud infrastructure pricing.
- cost management
- list all folders.
- get pricing data for products.
- list all segments.
- list business metrics
- get costs
- list dashboards
- list network flow reports
- budgets
- list recommendations
slug: cloud-cost-management
source_filename: cloud-cost-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vantage Cloud Cost Management\n  description: Unified workflow for cloud cost management combining cost reporting, alerting, optimization recommendations,\n    and cloud pricing comparison. Used by FinOps teams and cloud engineers to monitor, optimize, and control cloud spending.\n  tags:\n  - Vantage\n  - FinOps\n  - Cloud Costs\n  - Cost Management\n  - Cloud Pricing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VANTAGE_API_TOKEN: VANTAGE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vantage-cost-mgmt\n    baseUri: https://api.vantage.sh/v2\n    description: Vantage Cost Management API v2 for managing cloud cost data and workflows.\n    authentication:\n      type: bearer\n      token: '{{VANTAGE_API_TOKEN}}'\n    resources:\n    - name: cost-reports\n      path: /cost_reports\n      description: Create, read, update, and delete Cost Reports.\n      operations:\n    \
  \  - name: get-cost-reports\n        method: GET\n        description: Returns all Cost Reports.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: The page of results to return.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cost-report\n        method: POST\n        description: Creates a new Cost Report.\n        inputParameters:\n        - name: title\n          in: body\n          type: string\n          required: true\n          description: Title of the cost report.\n        - name: filter\n          in: body\n          type: string\n          required: false\n          description: VQL filter expression.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            filter: '{{tools.filter}}'\n      - name: get-cost-report\n        method: GET\n        description: Returns a specific Cost Report by token.\n        inputParameters:\n        - name: cost_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Cost Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-cost-report\n        method: PUT\n        description: Updates an existing Cost Report.\n        inputParameters:\n        - name: cost_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Cost Report.\n        - name: title\n          in: body\n     \
  \     type: string\n          required: false\n          description: Updated title.\n        - name: filter\n          in: body\n          type: string\n          required: false\n          description: Updated VQL filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            filter: '{{tools.filter}}'\n      - name: delete-cost-report\n        method: DELETE\n        description: Deletes an existing Cost Report.\n        inputParameters:\n        - name: cost_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Cost Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: costs\n      path: /costs\n      description: Retrieve cost data.\n      operations:\n\
  \      - name: get-costs\n        method: GET\n        description: Returns all Costs for a CostReport or VQL filter.\n        inputParameters:\n        - name: cost_report_token\n          in: query\n          type: string\n          required: false\n          description: The token of the Cost Report.\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD).\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      description: Manage folders for organizing Cost Reports.\n      operations:\n      - name: get-folders\n        method: GET\n        description: Returns all Folders.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-folder\n        method: POST\n        description: Creates a new Folder.\n        inputParameters:\n        - name: title\n          in: body\n          type: string\n          required: true\n          description: Folder title.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: get-folder\n        method: GET\n        description: Returns a specific Folder.\n        inputParameters:\n        - name: folder_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-folder\n        method: PUT\n        description:\
  \ Updates an existing Folder.\n        inputParameters:\n        - name: folder_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Folder.\n        - name: title\n          in: body\n          type: string\n          required: false\n          description: Updated title.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: delete-folder\n        method: DELETE\n        description: Deletes a Folder.\n        inputParameters:\n        - name: folder_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /dashboards\n\
  \      description: Create and manage cost dashboards.\n      operations:\n      - name: get-dashboards\n        method: GET\n        description: Returns all Dashboards.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dashboard\n        method: POST\n        description: Creates a new Dashboard.\n        inputParameters:\n        - name: title\n          in: body\n          type: string\n          required: true\n          description: Dashboard title.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: get-dashboard\n        method: GET\n        description: Returns a specific Dashboard.\n        inputParameters:\n        - name: dashboard_token\n          in: path\n          type: string\n          required:\
  \ true\n          description: The token of the Dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dashboard\n        method: PUT\n        description: Updates a Dashboard.\n        inputParameters:\n        - name: dashboard_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dashboard\n        method: DELETE\n        description: Deletes a Dashboard.\n        inputParameters:\n        - name: dashboard_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: saved-filters\n      path: /saved_filters\n      description: Manage saved filters for cost data.\n      operations:\n      - name: get-saved-filters\n        method: GET\n        description: Returns all Saved Filters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-saved-filter\n        method: POST\n        description: Creates a new Saved Filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-saved-filter\n        method: GET\n        description: Returns a specific Saved Filter.\n        inputParameters:\n        - name: saved_filter_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Saved Filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: update-saved-filter\n        method: PUT\n        description: Updates a Saved Filter.\n        inputParameters:\n        - name: saved_filter_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Saved Filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-saved-filter\n        method: DELETE\n        description: Deletes a Saved Filter.\n        inputParameters:\n        - name: saved_filter_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Saved Filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      description: Create and manage teams.\n      operations:\n      - name: get-teams\n        method: GET\n\
  \        description: Returns all Teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n        method: POST\n        description: Creates a new Team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-team\n        method: GET\n        description: Returns a specific Team.\n        inputParameters:\n        - name: team_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-team\n        method: PUT\n        description: Updates a Team.\n        inputParameters:\n        - name: team_token\n          in: path\n          type: string\n          required: true\n          description:\
  \ The token of the Team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-team\n        method: DELETE\n        description: Deletes a Team.\n        inputParameters:\n        - name: team_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: access-grants\n      path: /access_grants\n      description: Manage resource access grants for teams.\n      operations:\n      - name: get-access-grants\n        method: GET\n        description: Returns all Access Grants.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-access-grant\n        method: POST\n        description: Creates a new Access\
  \ Grant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-access-grant\n        method: GET\n        description: Returns a specific Access Grant.\n        inputParameters:\n        - name: access_grant_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Access Grant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-access-grant\n        method: DELETE\n        description: Deletes an Access Grant.\n        inputParameters:\n        - name: access_grant_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Access Grant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: budget-alerts\n\
  \      path: /budget_alerts\n      description: Create and manage budget alerts.\n      operations:\n      - name: get-budget-alerts\n        method: GET\n        description: Returns all Budget Alerts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-budget-alert\n        method: POST\n        description: Creates a new Budget Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-budget-alert\n        method: GET\n        description: Returns a specific Budget Alert.\n        inputParameters:\n        - name: budget_alert_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Budget Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ update-budget-alert\n        method: PUT\n        description: Updates a Budget Alert.\n        inputParameters:\n        - name: budget_alert_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Budget Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-budget-alert\n        method: DELETE\n        description: Deletes a Budget Alert.\n        inputParameters:\n        - name: budget_alert_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Budget Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: anomaly-alerts\n      path: /anomaly_alerts\n      description: Create and manage cost anomaly alerts.\n      operations:\n      - name: get-anomaly-alerts\n       \
  \ method: GET\n        description: Returns all Anomaly Alerts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-anomaly-alert\n        method: POST\n        description: Creates a new Anomaly Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-anomaly-alert\n        method: GET\n        description: Returns a specific Anomaly Alert.\n        inputParameters:\n        - name: anomaly_alert_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Anomaly Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-anomaly-alert\n        method: PUT\n        description: Updates an Anomaly Alert.\n        inputParameters:\n        - name:\
  \ anomaly_alert_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Anomaly Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-anomaly-alert\n        method: DELETE\n        description: Deletes an Anomaly Alert.\n        inputParameters:\n        - name: anomaly_alert_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Anomaly Alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recommendations\n      path: /recommendations\n      description: Retrieve cost optimization recommendations.\n      operations:\n      - name: get-recommendations\n        method: GET\n        description: Returns all cost optimization Recommendations.\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments\n      path: /segments\n      description: Create, update, and delete cost allocation segments.\n      operations:\n      - name: get-segments\n        method: GET\n        description: Returns all Segments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-segment\n        method: POST\n        description: Creates a new Segment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-segment\n        method: GET\n        description: Returns a specific Segment.\n        inputParameters:\n        - name: segment_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Segment.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-segment\n        method: PUT\n        description: Updates a Segment.\n        inputParameters:\n        - name: segment_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Segment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-segment\n        method: DELETE\n        description: Deletes a Segment.\n        inputParameters:\n        - name: segment_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Segment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /integrations\n      description: Manage cloud provider integrations.\n      operations:\n      -\
  \ name: get-integrations\n        method: GET\n        description: Returns all Integrations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-integration\n        method: POST\n        description: Creates a new Integration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-integration\n        method: GET\n        description: Returns a specific Integration.\n        inputParameters:\n        - name: integration_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Integration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-integration\n        method: DELETE\n        description: Deletes an Integration.\n        inputParameters:\n\
  \        - name: integration_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Integration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Manage workspaces.\n      operations:\n      - name: get-workspaces\n        method: GET\n        description: Returns all Workspaces.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-workspace\n        method: GET\n        description: Returns a specific Workspace.\n        inputParameters:\n        - name: workspace_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: managed-accounts\n      path: /managed_accounts\n      description: Manage linked cloud provider accounts.\n      operations:\n      - name: get-managed-accounts\n        method: GET\n        description: Returns all Managed Accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-providers\n      path: /cost_providers\n      description: Retrieve available cost providers.\n      operations:\n      - name: get-cost-providers\n        method: GET\n        description: Returns all Cost Providers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-metrics\n      path: /business_metrics\n      description: Create, update, and delete business metrics.\n      operations:\n      - name: get-business-metrics\n        method: GET\n        description: Returns all Business\
  \ Metrics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-business-metric\n        method: POST\n        description: Creates a new Business Metric.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-business-metric\n        method: GET\n        description: Returns a specific Business Metric.\n        inputParameters:\n        - name: business_metric_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Business Metric.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-business-metric\n        method: PUT\n        description: Updates a Business Metric.\n        inputParameters:\n        - name: business_metric_token\n          in:\
  \ path\n          type: string\n          required: true\n          description: The token of the Business Metric.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-business-metric\n        method: DELETE\n        description: Deletes a Business Metric.\n        inputParameters:\n        - name: business_metric_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Business Metric.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource-reports\n      path: /resource_reports\n      description: Create and manage resource reports.\n      operations:\n      - name: get-resource-reports\n        method: GET\n        description: Returns all Resource Reports.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: create-resource-report\n        method: POST\n        description: Creates a new Resource Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-resource-report\n        method: GET\n        description: Returns a specific Resource Report.\n        inputParameters:\n        - name: resource_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Resource Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-resource-report\n        method: PUT\n        description: Updates a Resource Report.\n        inputParameters:\n        - name: resource_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the\
  \ Resource Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-resource-report\n        method: DELETE\n        description: Deletes a Resource Report.\n        inputParameters:\n        - name: resource_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Resource Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /resources\n      description: Retrieve resource data from reports.\n      operations:\n      - name: get-resources\n        method: GET\n        description: Returns Resources for a Resource Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-flow-reports\n      path: /network_flow_reports\n\
  \      description: Create and manage network flow reports.\n      operations:\n      - name: get-network-flow-reports\n        method: GET\n        description: Returns all Network Flow Reports.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-network-flow-report\n        method: POST\n        description: Creates a new Network Flow Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-network-flow-report\n        method: GET\n        description: Returns a specific Network Flow Report.\n        inputParameters:\n        - name: network_flow_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Network Flow Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: delete-network-flow-report\n        method: DELETE\n        description: Deletes a Network Flow Report.\n        inputParameters:\n        - name: network_flow_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Network Flow Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-commitment-reports\n      path: /financial_commitment_reports\n      description: Create and manage financial commitment reports.\n      operations:\n      - name: get-financial-commitment-reports\n        method: GET\n        description: Returns all Financial Commitment Reports.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-financial-commitment-report\n        method: POST\n        description: Creates\
  \ a new Financial Commitment Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-financial-commitment-report\n        method: GET\n        description: Returns a specific Financial Commitment Report.\n        inputParameters:\n        - name: financial_commitment_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Financial Commitment Report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-financial-commitment-report\n        method: DELETE\n        description: Deletes a Financial Commitment Report.\n        inputParameters:\n        - name: financial_commitment_report_token\n          in: path\n          type: string\n          required: true\n          description: The token of the Financial Commitment Report.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-efficiency-reports\n      path: /kubernetes_efficiency_reports\n      description: Manage Kubernetes cost data and efficiency reports.\n      operations:\n      - name: get-kubernetes-efficiency-reports\n        method: GET\n        description: Returns all Kubernetes Efficiency Reports.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: vantage-pricing\n    baseUri: https://api.vantage.sh/v1\n    description: Vantage Cloud Pricing API v1 for querying cloud infrastructure pricing data.\n    authentication:\n      type: bearer\n      token: '{{VANTAGE_API_TOKEN}}'\n    resources:\n    - name: providers\n      path: /providers\n      description: Retrieve available cloud providers.\n      operations:\n      - name: get-providers\n  \
  \      method: GET\n        description: Returns all supported cloud Providers.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: The page of results to return.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-provider\n        method: GET\n        description: Returns a specific cloud Provider by identifier.\n        inputParameters:\n        - name: provider_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the cloud provider.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path:\
  \ /services\n      description: Retrieve cloud services and their details.\n      operations:\n      - name: get-services\n        method: GET\n        description: Returns all Services across Providers.\n        inputParameters:\n        - name: provider_id\n          in: query\n          type: string\n          required: false\n          description: Filter by provider identifier.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: The page of results to return.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service\n        method: GET\n        description: Returns a specific Service by identifier.\n        inputParameters:\n        - name: service_id\n          in: path\n\
  \          type: string\n          required: true\n          description: The identifier of the service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Query cloud infrastructure products and pricing.\n      operations:\n      - name: get-products\n        method: GET\n        description: Returns all Products for a given Provider and Service.\n        inputParameters:\n        - name: provider_id\n          in: query\n          type: string\n          required: false\n          description: Filter by provider identifier.\n        - name: service_id\n          in: query\n          type: string\n          required: false\n          description: Filter by service identifier.\n        - name: name\n          in: que\n\n# --- truncated at 32 KB (49 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/vantage/refs/heads/main/capabilities/cloud-cost-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vantage/refs/heads/main/capabilities/cloud-cost-management.yaml
tags:
- Vantage
- FinOps
- Cloud Costs
- Cost Management
- Cloud Pricing
tools:
- description: List all Cost Reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-cost-reports
- description: Create a new Cost Report with VQL filter.
  hints:
    idempotent: false
    readOnly: false
  name: create-cost-report
- description: Get a specific Cost Report by token.
  hints:
    openWorld: true
    readOnly: true
  name: get-cost-report
- description: Update an existing Cost Report.
  hints:
    idempotent: true
    readOnly: false
  name: update-cost-report
- description: Delete a Cost Report.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cost-report
- description: Get costs for a report or VQL filter.
  hints:
    openWorld: true
    readOnly: true
  name: get-costs
- description: List all Folders.
  hints:
    openWorld: true
    readOnly: true
  name: list-folders
- description: List all Dashboards.
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: List all Saved Filters.
  hints:
    openWorld: true
    readOnly: true
  name: list-saved-filters
- description: List all Teams.
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: List all Budget Alerts.
  hints:
    openWorld: true
    readOnly: true
  name: list-budget-alerts
- description: List all Anomaly Alerts.
  hints:
    openWorld: true
    readOnly: true
  name: list-anomaly-alerts
- description: List cost optimization recommendations.
  hints:
    openWorld: true
    readOnly: true
  name: list-recommendations
- description: List all cost allocation Segments.
  hints:
    openWorld: true
    readOnly: true
  name: list-segments
- description: List all cloud provider Integrations.
  hints:
    openWorld: true
    readOnly: true
  name: list-integrations
- description: List all Workspaces.
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: List all managed cloud accounts.
  hints:
    openWorld: true
    readOnly: true
  name: list-managed-accounts
- description: List all cost providers.
  hints:
    openWorld: true
    readOnly: true
  name: list-cost-providers
- description: List all Business Metrics.
  hints:
    openWorld: true
    readOnly: true
  name: list-business-metrics
- description: List all Resource Reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-resource-reports
- description: List all Network Flow Reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-network-flow-reports
- description: List all Financial Commitment Reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-financial-commitment-reports
- description: List all Kubernetes Efficiency Reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-kubernetes-efficiency-reports
- description: List all cloud pricing providers.
  hints:
    openWorld: true
    readOnly: true
  name: list-pricing-providers
- description: Get a specific cloud pricing provider.
  hints:
    openWorld: true
    readOnly: true
  name: get-pricing-provider
- description: List cloud services with pricing data.
  hints:
    openWorld: true
    readOnly: true
  name: list-pricing-services
- description: Get a specific cloud service.
  hints:
    openWorld: true
    readOnly: true
  name: get-pricing-service
- description: List cloud products with pricing.
  hints:
    openWorld: true
    readOnly: true
  name: list-pricing-products
- description: Get a specific cloud product with pricing details.
  hints:
    openWorld: true
    readOnly: true
  name: get-pricing-product
- description: Get pricing data filtered by product, provider, service, or region.
  hints:
    openWorld: true
    readOnly: true
  name: list-prices
---
