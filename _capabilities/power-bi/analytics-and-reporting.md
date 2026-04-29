---
categories:
- analytics
consumed_apis:
- power-bi
description: Unified workflow for Power BI analytics operations including dataset management, report creation and distribution, dashboard monitoring, workspace administration, and gateway configuration. Used by BI analysts, report developers, and Power BI administrators.
layout: capability
name: Power BI Analytics and Reporting
operations:
- description: List all datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Create a dataset
  method: POST
  name: create-dataset
  path: /v1/datasets
- description: Get dataset details
  method: GET
  name: get-dataset
  path: /v1/datasets/{datasetId}
- description: Delete a dataset
  method: DELETE
  name: delete-dataset
  path: /v1/datasets/{datasetId}
- description: List all reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: List all dashboards
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a dashboard
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: List workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: List gateways
  method: GET
  name: list-gateways
  path: /v1/gateways
personas: []
provider_name: Power BI
provider_slug: power-bi
search_terms:
- list workspaces
- power bi
- trigger a dataset refresh
- list all workspaces
- get datasources for a dataset
- list reports
- export report
- get pages for a report
- get gateway datasources
- gateway management
- get dashboard details
- create a new workspace
- reporting
- create a new dashboard
- get workspace users
- dataset management
- delete a dataset
- export a report
- get tiles for a dashboard
- get dataset
- list all power bi datasets
- data analysis
- get report details by id
- get dataset details
- get dashboard tiles
- dashboard management
- create a dataset
- clone a report
- create dataset
- list all dashboards
- get report pages
- get gateway details
- list data gateways
- list all datasets
- create a new dataset
- delete dataset
- list datasets
- business intelligence
- workspace management
- get gateway
- individual dataset operations
- report management
- analytics
- refresh dataset
- get refresh history
- clone report
- get report
- create workspace
- list dashboards
- create dashboard
- list all power bi reports
- list workspace users
- get dataset details by id
- get dataset refresh history
- list all reports
- list gateways
- visualization
- get dashboard
- dashboards
- get datasources
- create a dashboard
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Power BI Analytics and Reporting\"\n  description: \"Unified workflow for Power BI analytics operations including dataset management, report creation and distribution, dashboard monitoring, workspace administration, and gateway configuration. Used by BI analysts, report developers, and Power BI administrators.\"\n  tags:\n    - Power BI\n    - Analytics\n    - Business Intelligence\n    - Reporting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      POWER_BI_ACCESS_TOKEN: POWER_BI_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: power-bi\n      location: ./shared/power-bi-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: power-bi-analytics-api\n      description: \"Unified REST API for Power BI analytics and reporting.\"\n      resources:\n        - path: /v1/datasets\n          name: datasets\n          description: \"Dataset management\"\n \
  \         operations:\n            - method: GET\n              name: list-datasets\n              description: \"List all datasets\"\n              call: \"power-bi.get-datasets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dataset\n              description: \"Create a dataset\"\n              call: \"power-bi.create-dataset\"\n              with:\n                name: \"rest.name\"\n                tables: \"rest.tables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets/{datasetId}\n          name: dataset\n          description: \"Individual dataset operations\"\n          operations:\n            - method: GET\n              name: get-dataset\n              description: \"Get dataset details\"\n              call: \"power-bi.get-dataset\"\n              with:\n                datasetId: \"\
  rest.datasetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-dataset\n              description: \"Delete a dataset\"\n              call: \"power-bi.delete-dataset\"\n              with:\n                datasetId: \"rest.datasetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Report management\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List all reports\"\n              call: \"power-bi.get-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"Dashboard management\"\n          operations:\n            - method: GET\n           \
  \   name: list-dashboards\n              description: \"List all dashboards\"\n              call: \"power-bi.get-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dashboard\n              description: \"Create a dashboard\"\n              call: \"power-bi.create-dashboard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Workspace management\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List workspaces\"\n              call: \"power-bi.get-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gateways\n          name: gateways\n          description: \"Gateway management\"\n          operations:\n\
  \            - method: GET\n              name: list-gateways\n              description: \"List gateways\"\n              call: \"power-bi.get-gateways\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: power-bi-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Power BI analytics and reporting.\"\n      tools:\n        - name: list-datasets\n          description: \"List all Power BI datasets\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"power-bi.get-datasets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset\n          description: \"Get dataset details by ID\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-dataset\"\n          with:\n            datasetId: \"tools.datasetId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-dataset\n          description: \"Create a new dataset\"\n          hints:\n            readOnly: false\n          call: \"power-bi.create-dataset\"\n          with:\n            name: \"tools.name\"\n            tables: \"tools.tables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-dataset\n          description: \"Delete a dataset\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"power-bi.delete-dataset\"\n          with:\n            datasetId: \"tools.datasetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refresh-dataset\n          description: \"Trigger a dataset refresh\"\n          hints:\n            readOnly: false\n          call: \"power-bi.refresh-dataset\"\n          with:\n            datasetId: \"tools.datasetId\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-refresh-history\n          description: \"Get dataset refresh history\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-refresh-history\"\n          with:\n            datasetId: \"tools.datasetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-datasources\n          description: \"Get datasources for a dataset\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-datasources\"\n          with:\n            datasetId: \"tools.datasetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List all Power BI reports\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"power-bi.get-reports\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n        - name: get-report\n          description: \"Get report details by ID\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: clone-report\n          description: \"Clone a report\"\n          hints:\n            readOnly: false\n          call: \"power-bi.clone-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-report\n          description: \"Export a report\"\n          hints:\n            readOnly: true\n          call: \"power-bi.export-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ get-report-pages\n          description: \"Get pages for a report\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-pages\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dashboards\n          description: \"List all dashboards\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"power-bi.get-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dashboard\n          description: \"Get dashboard details\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-dashboard\"\n          with:\n            dashboardId: \"tools.dashboardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-dashboard\n          description: \"Create a new dashboard\"\
  \n          hints:\n            readOnly: false\n          call: \"power-bi.create-dashboard\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dashboard-tiles\n          description: \"Get tiles for a dashboard\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-tiles\"\n          with:\n            dashboardId: \"tools.dashboardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List all workspaces\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"power-bi.get-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace\n          description: \"Create a new workspace\"\n          hints:\n            readOnly: false\n          call: \"power-bi.create-group\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-workspace-users\n          description: \"List workspace users\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-group-users\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-gateways\n          description: \"List data gateways\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-gateways\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gateway\n          description: \"Get gateway details\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-gateway\"\n          with:\n            gatewayId: \"tools.gatewayId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gateway-datasources\n      \
  \    description: \"Get gateway datasources\"\n          hints:\n            readOnly: true\n          call: \"power-bi.get-gateway-datasources\"\n          with:\n            gatewayId: \"tools.gatewayId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/power-bi/refs/heads/main/capabilities/analytics-and-reporting.yaml
tags:
- Power BI
- Analytics
- Business Intelligence
- Reporting
tools:
- description: List all Power BI datasets
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Get dataset details by ID
  hints:
    readOnly: true
  name: get-dataset
- description: Create a new dataset
  hints:
    readOnly: false
  name: create-dataset
- description: Delete a dataset
  hints:
    destructive: true
    idempotent: true
  name: delete-dataset
- description: Trigger a dataset refresh
  hints:
    readOnly: false
  name: refresh-dataset
- description: Get dataset refresh history
  hints:
    readOnly: true
  name: get-refresh-history
- description: Get datasources for a dataset
  hints:
    readOnly: true
  name: get-datasources
- description: List all Power BI reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Get report details by ID
  hints:
    readOnly: true
  name: get-report
- description: Clone a report
  hints:
    readOnly: false
  name: clone-report
- description: Export a report
  hints:
    readOnly: true
  name: export-report
- description: Get pages for a report
  hints:
    readOnly: true
  name: get-report-pages
- description: List all dashboards
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: Get dashboard details
  hints:
    readOnly: true
  name: get-dashboard
- description: Create a new dashboard
  hints:
    readOnly: false
  name: create-dashboard
- description: Get tiles for a dashboard
  hints:
    readOnly: true
  name: get-dashboard-tiles
- description: List all workspaces
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Create a new workspace
  hints:
    readOnly: false
  name: create-workspace
- description: List workspace users
  hints:
    readOnly: true
  name: get-workspace-users
- description: List data gateways
  hints:
    readOnly: true
  name: list-gateways
- description: Get gateway details
  hints:
    readOnly: true
  name: get-gateway
- description: Get gateway datasources
  hints:
    readOnly: true
  name: get-gateway-datasources
---
