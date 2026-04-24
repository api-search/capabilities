---
consumed_apis:
- vantage-cost-mgmt
- vantage-pricing
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
- list saved filters
- list all business metrics.
- get pricing service
- list pricing services
- create anomaly alert
- cloud pricing services.
- list all cost providers.
- finops
- list kubernetes efficiency reports
- list recommendations
- update an existing cost report.
- list products
- get costs for a report or vql filter.
- list segments
- cloud pricing providers.
- list all network flow reports.
- list all integrations.
- manage budget alerts.
- list managed accounts
- list services
- cost management
- list all dashboards.
- list integrations
- manage cost allocation segments.
- create a new anomaly alert.
- update a cost report.
- cloud infrastructure products.
- create budget alert
- list cloud services.
- get pricing provider
- list all managed cloud accounts.
- get a specific cloud service.
- list all cloud pricing providers.
- create a new dashboard.
- list cost providers
- manage anomaly detection alerts.
- list folders
- get pricing product
- list all workspaces.
- list anomaly alerts
- delete cost report
- manage cost reports.
- get pricing data filtered by product, provider, service, or region.
- list cloud services with pricing data.
- cloud infrastructure pricing.
- get pricing data for products.
- list all resource reports.
- list resource reports
- get a specific cloud product with pricing details.
- manage a specific cost report.
- create dashboard
- get cost report
- get a specific cloud provider.
- vantage
- costs
- delete a cost report.
- list pricing products
- list business metrics
- retrieve cost data.
- create a new budget alert.
- get a specific cloud pricing provider.
- list teams
- list all segments.
- list all cost allocation segments.
- manage cost dashboards.
- list workspaces
- get a specific cost report.
- get provider
- create a new cost report.
- list cost optimization recommendations.
- budgets
- list all saved filters.
- list all teams.
- list prices
- list financial commitment reports
- list budget alerts
- list dashboards
- list all cost reports.
- list providers
- update cost report
- cloud costs
- create cost report
- get costs
- list cost reports
- cloud pricing
- list network flow reports
- list all kubernetes efficiency reports.
- create a new cost report with vql filter.
- manage cloud provider integrations.
- list cloud products with pricing.
- list all folders.
- list all budget alerts.
- cost optimization recommendations.
- list pricing providers
- list all cloud provider integrations.
- list all financial commitment reports.
- get a specific cost report by token.
- list all anomaly alerts.
slug: cloud-cost-management
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
