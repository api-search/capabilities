---
categories: []
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
- delete a cost report.
- get a specific cost report by token.
- list all saved filters.
- list all network flow reports.
- cloud infrastructure pricing.
- get costs
- get a specific cloud product with pricing details.
- get costs for a report or vql filter.
- manage cost dashboards.
- get a specific cloud pricing provider.
- list dashboards
- list network flow reports
- create budget alert
- list all cost reports.
- list all integrations.
- list all dashboards.
- list teams
- list services
- list business metrics
- list saved filters
- get pricing service
- create dashboard
- list providers
- list all kubernetes efficiency reports.
- list all cloud pricing providers.
- list cloud products with pricing.
- manage budget alerts.
- list financial commitment reports
- list workspaces
- list cloud services with pricing data.
- list all segments.
- cloud costs
- get pricing provider
- cloud pricing
- list cost providers
- retrieve cost data.
- list all teams.
- list all workspaces.
- get a specific cost report.
- manage cloud provider integrations.
- list all folders.
- list all managed cloud accounts.
- list managed accounts
- list all resource reports.
- list segments
- create anomaly alert
- list cost optimization recommendations.
- manage cost allocation segments.
- list all financial commitment reports.
- list all cost allocation segments.
- costs
- get pricing product
- manage anomaly detection alerts.
- list all budget alerts.
- cloud infrastructure products.
- budgets
- cost optimization recommendations.
- list resource reports
- manage cost reports.
- create a new cost report with vql filter.
- get a specific cloud service.
- get a specific cloud provider.
- list pricing products
- list integrations
- list folders
- list all cloud provider integrations.
- manage a specific cost report.
- list kubernetes efficiency reports
- get pricing data for products.
- list recommendations
- list budget alerts
- cost management
- update a cost report.
- list prices
- list cloud services.
- get pricing data filtered by product, provider, service, or region.
- list cost reports
- cloud pricing providers.
- list pricing services
- delete cost report
- vantage
- list all business metrics.
- update an existing cost report.
- get cost report
- create a new dashboard.
- list anomaly alerts
- create a new anomaly alert.
- list all anomaly alerts.
- get provider
- list pricing providers
- cloud pricing services.
- finops
- list all cost providers.
- create cost report
- create a new cost report.
- update cost report
- create a new budget alert.
- list products
slug: cloud-cost-management
source_filename: cloud-cost-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vantage Cloud Cost Management\"\n  description: \"Unified workflow for cloud cost management combining cost reporting, alerting, optimization recommendations, and cloud pricing comparison. Used by FinOps teams and cloud engineers to monitor, optimize, and control cloud spending.\"\n  tags:\n    - Vantage\n    - FinOps\n    - Cloud Costs\n    - Cost Management\n    - Cloud Pricing\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      VANTAGE_API_TOKEN: VANTAGE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: vantage-cost-mgmt\n      location: ./shared/cost-management.yaml\n    - import: vantage-pricing\n      location: ./shared/cloud-pricing.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vantage-finops-api\n      description: \"Unified REST API for cloud cost management, optimization, and pricing comparison.\"\n      resources:\n        - path: /v1/cost-reports\n\
  \          name: cost-reports\n          description: \"Manage Cost Reports.\"\n          operations:\n            - method: GET\n              name: list-cost-reports\n              description: \"List all Cost Reports.\"\n              call: \"vantage-cost-mgmt.get-cost-reports\"\n              with:\n                page: \"rest.page\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cost-report\n              description: \"Create a new Cost Report.\"\n              call: \"vantage-cost-mgmt.create-cost-report\"\n              with:\n                title: \"rest.title\"\n                filter: \"rest.filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cost-reports/{cost_report_token}\n          name: cost-report\n          description: \"Manage a specific Cost\
  \ Report.\"\n          operations:\n            - method: GET\n              name: get-cost-report\n              description: \"Get a specific Cost Report.\"\n              call: \"vantage-cost-mgmt.get-cost-report\"\n              with:\n                cost_report_token: \"rest.cost_report_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-cost-report\n              description: \"Update a Cost Report.\"\n              call: \"vantage-cost-mgmt.update-cost-report\"\n              with:\n                cost_report_token: \"rest.cost_report_token\"\n                title: \"rest.title\"\n                filter: \"rest.filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cost-report\n              description: \"Delete a Cost Report.\"\n              call: \"vantage-cost-mgmt.delete-cost-report\"\
  \n              with:\n                cost_report_token: \"rest.cost_report_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/costs\n          name: costs\n          description: \"Retrieve cost data.\"\n          operations:\n            - method: GET\n              name: get-costs\n              description: \"Get costs for a report or VQL filter.\"\n              call: \"vantage-cost-mgmt.get-costs\"\n              with:\n                cost_report_token: \"rest.cost_report_token\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"Manage cost dashboards.\"\n          operations:\n            - method: GET\n              name: list-dashboards\n              description: \"List\
  \ all Dashboards.\"\n              call: \"vantage-cost-mgmt.get-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dashboard\n              description: \"Create a new Dashboard.\"\n              call: \"vantage-cost-mgmt.create-dashboard\"\n              with:\n                title: \"rest.title\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/budget-alerts\n          name: budget-alerts\n          description: \"Manage budget alerts.\"\n          operations:\n            - method: GET\n              name: list-budget-alerts\n              description: \"List all Budget Alerts.\"\n              call: \"vantage-cost-mgmt.get-budget-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-budget-alert\n\
  \              description: \"Create a new Budget Alert.\"\n              call: \"vantage-cost-mgmt.create-budget-alert\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/anomaly-alerts\n          name: anomaly-alerts\n          description: \"Manage anomaly detection alerts.\"\n          operations:\n            - method: GET\n              name: list-anomaly-alerts\n              description: \"List all Anomaly Alerts.\"\n              call: \"vantage-cost-mgmt.get-anomaly-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-anomaly-alert\n              description: \"Create a new Anomaly Alert.\"\n              call: \"vantage-cost-mgmt.create-anomaly-alert\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations\n  \
  \        name: recommendations\n          description: \"Cost optimization recommendations.\"\n          operations:\n            - method: GET\n              name: list-recommendations\n              description: \"List cost optimization recommendations.\"\n              call: \"vantage-cost-mgmt.get-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/segments\n          name: segments\n          description: \"Manage cost allocation segments.\"\n          operations:\n            - method: GET\n              name: list-segments\n              description: \"List all Segments.\"\n              call: \"vantage-cost-mgmt.get-segments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integrations\n          name: integrations\n          description: \"Manage cloud provider integrations.\"\n          operations:\n            -\
  \ method: GET\n              name: list-integrations\n              description: \"List all Integrations.\"\n              call: \"vantage-cost-mgmt.get-integrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/providers\n          name: providers\n          description: \"Cloud pricing providers.\"\n          operations:\n            - method: GET\n              name: list-providers\n              description: \"List all cloud pricing providers.\"\n              call: \"vantage-pricing.get-providers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/providers/{provider_id}\n          name: provider\n          description: \"Get a specific cloud provider.\"\n          operations:\n            - method: GET\n              name: get-provider\n              description: \"Get a specific cloud provider.\"\n              call: \"vantage-pricing.get-provider\"\
  \n              with:\n                provider_id: \"rest.provider_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services\n          name: services\n          description: \"Cloud pricing services.\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List cloud services.\"\n              call: \"vantage-pricing.get-services\"\n              with:\n                provider_id: \"rest.provider_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: products\n          description: \"Cloud infrastructure products.\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List cloud products with pricing.\"\n              call: \"vantage-pricing.get-products\"\n              with:\n        \
  \        provider_id: \"rest.provider_id\"\n                service_id: \"rest.service_id\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/prices\n          name: prices\n          description: \"Cloud infrastructure pricing.\"\n          operations:\n            - method: GET\n              name: list-prices\n              description: \"Get pricing data for products.\"\n              call: \"vantage-pricing.get-prices\"\n              with:\n                product_id: \"rest.product_id\"\n                provider_id: \"rest.provider_id\"\n                service_id: \"rest.service_id\"\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vantage-finops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud\
  \ cost management and pricing comparison.\"\n      tools:\n        - name: list-cost-reports\n          description: \"List all Cost Reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-cost-reports\"\n          with:\n            page: \"tools.page\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-cost-report\n          description: \"Create a new Cost Report with VQL filter.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"vantage-cost-mgmt.create-cost-report\"\n          with:\n            title: \"tools.title\"\n            filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cost-report\n          description: \"Get a specific Cost Report by token.\"\n          hints:\n       \
  \     readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-cost-report\"\n          with:\n            cost_report_token: \"tools.cost_report_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-cost-report\n          description: \"Update an existing Cost Report.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"vantage-cost-mgmt.update-cost-report\"\n          with:\n            cost_report_token: \"tools.cost_report_token\"\n            title: \"tools.title\"\n            filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-cost-report\n          description: \"Delete a Cost Report.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vantage-cost-mgmt.delete-cost-report\"\n  \
  \        with:\n            cost_report_token: \"tools.cost_report_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-costs\n          description: \"Get costs for a report or VQL filter.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-costs\"\n          with:\n            cost_report_token: \"tools.cost_report_token\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-folders\n          description: \"List all Folders.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-folders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-dashboards\n          description: \"List all Dashboards.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-saved-filters\n          description: \"List all Saved Filters.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-saved-filters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams\n          description: \"List all Teams.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-budget-alerts\n          description: \"List all Budget Alerts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-budget-alerts\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-anomaly-alerts\n          description: \"List all Anomaly Alerts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-anomaly-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-recommendations\n          description: \"List cost optimization recommendations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-recommendations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-segments\n          description: \"List all cost allocation Segments.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-segments\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: list-integrations\n          description: \"List all cloud provider Integrations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-integrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-workspaces\n          description: \"List all Workspaces.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-managed-accounts\n          description: \"List all managed cloud accounts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-managed-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        -\
  \ name: list-cost-providers\n          description: \"List all cost providers.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-cost-providers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-business-metrics\n          description: \"List all Business Metrics.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-business-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resource-reports\n          description: \"List all Resource Reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-resource-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-network-flow-reports\n          description:\
  \ \"List all Network Flow Reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-network-flow-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-financial-commitment-reports\n          description: \"List all Financial Commitment Reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-financial-commitment-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-kubernetes-efficiency-reports\n          description: \"List all Kubernetes Efficiency Reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-cost-mgmt.get-kubernetes-efficiency-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pricing-providers\n\
  \          description: \"List all cloud pricing providers.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-providers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pricing-provider\n          description: \"Get a specific cloud pricing provider.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-provider\"\n          with:\n            provider_id: \"tools.provider_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pricing-services\n          description: \"List cloud services with pricing data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-services\"\n          with:\n            provider_id: \"tools.provider_id\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n\n        - name: get-pricing-service\n          description: \"Get a specific cloud service.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-service\"\n          with:\n            service_id: \"tools.service_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pricing-products\n          description: \"List cloud products with pricing.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-products\"\n          with:\n            provider_id: \"tools.provider_id\"\n            service_id: \"tools.service_id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pricing-product\n          description: \"Get a specific cloud product with pricing details.\"\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-product\"\n          with:\n            product_id: \"tools.product_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-prices\n          description: \"Get pricing data filtered by product, provider, service, or region.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vantage-pricing.get-prices\"\n          with:\n            product_id: \"tools.product_id\"\n            provider_id: \"tools.provider_id\"\n            service_id: \"tools.service_id\"\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
