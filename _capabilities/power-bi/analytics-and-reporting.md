---
categories:
- analytics
consumed_apis: []
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
- gateway management
- create workspace
- data analysis
- delete dataset
- get datasources
- get pages for a report
- create a new dashboard
- visualization
- reporting
- delete a dataset
- analytics
- get report
- export a report
- list datasets
- get workspace users
- list all dashboards
- dataset management
- get tiles for a dashboard
- report management
- refresh dataset
- list all power bi reports
- dashboards
- create a new workspace
- list all reports
- create dashboard
- list workspace users
- clone a report
- get dataset details
- list all datasets
- get report details by id
- get datasources for a dataset
- get dashboard details
- list reports
- list gateways
- workspace management
- individual dataset operations
- create a dashboard
- create dataset
- get refresh history
- list workspaces
- export report
- get dashboard
- power bi
- get dashboard tiles
- business intelligence
- get dataset details by id
- list data gateways
- list dashboards
- get report pages
- create a new dataset
- get gateway
- list all power bi datasets
- get gateway details
- get gateway datasources
- create a dataset
- get dataset
- trigger a dataset refresh
- clone report
- list all workspaces
- get dataset refresh history
- dashboard management
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Power BI Analytics and Reporting\n  description: Unified workflow for Power BI analytics operations including dataset management, report creation and distribution,\n    dashboard monitoring, workspace administration, and gateway configuration. Used by BI analysts, report developers, and\n    Power BI administrators.\n  tags:\n  - Power BI\n  - Analytics\n  - Business Intelligence\n  - Reporting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    POWER_BI_ACCESS_TOKEN: POWER_BI_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: power-bi\n    baseUri: https://api.powerbi.com/v1.0/myorg\n    description: Power BI REST API\n    authentication:\n      type: bearer\n      token: '{{POWER_BI_ACCESS_TOKEN}}'\n    resources:\n    - name: datasets\n      path: /datasets\n      description: Manage Power BI datasets\n      operations:\n      - name: get-datasets\n        method: GET\n    \
  \    description: List datasets in My Workspace\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dataset\n        method: POST\n        description: Create a new dataset\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            tables: '{{tools.tables}}'\n      - name: get-dataset\n        method: GET\n        description: Get a dataset by ID\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dataset\n        method:\
  \ DELETE\n        description: Delete a dataset\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-dataset\n        method: POST\n        description: Trigger a dataset refresh\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-refresh-history\n        method: GET\n        description: Get dataset refresh history\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-datasources\n        method: GET\n        description: Get datasources for a dataset\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-parameters\n        method: GET\n        description: Get dataset parameters\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-parameters\n        method: POST\n        description: Update dataset parameters\n        inputParameters:\n\
  \        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Manage Power BI reports\n      operations:\n      - name: get-reports\n        method: GET\n        description: List reports in My Workspace\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report\n        method: GET\n        description: Get a report by ID\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: delete-report\n        method: DELETE\n        description: Delete a report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clone-report\n        method: POST\n        description: Clone a report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-report\n        method: GET\n        description: Export a report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pages\n        method: GET\n        description: Get report pages\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /dashboards\n      description: Manage Power BI dashboards\n      operations:\n      - name: get-dashboards\n        method: GET\n        description: List dashboards\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dashboard\n        method: POST\n        description: Create a dashboard\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-dashboard\n        method: GET\n        description: Get a dashboard by ID\n        inputParameters:\n        - name: dashboardId\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tiles\n        method: GET\n        description: Get dashboard tiles\n        inputParameters:\n        - name: dashboardId\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Manage workspaces (groups)\n      operations:\n      - name: get-groups\n        method: GET\n        description:\
  \ List workspaces\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a workspace\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Delete a workspace\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-group-users\n        method: GET\n        description: List workspace users\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-group-user\n        method: POST\n        description: Add a user to a workspace\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateways\n      path: /gateways\n      description: Manage data gateways\n      operations:\n      - name: get-gateways\n        method: GET\n        description: List gateways\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gateway\n        method: GET\n        description: Get a gateway by ID\n        inputParameters:\n\
  \        - name: gatewayId\n          in: path\n          type: string\n          required: true\n          description: Gateway ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gateway-datasources\n        method: GET\n        description: Get gateway datasources\n        inputParameters:\n        - name: gatewayId\n          in: path\n          type: string\n          required: true\n          description: Gateway ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: power-bi-analytics-api\n    description: Unified REST API for Power BI analytics and reporting.\n    resources:\n    - path: /v1/datasets\n      name: datasets\n      description: Dataset management\n      operations:\n      - method: GET\n        name: list-datasets\n        description:\
  \ List all datasets\n        call: power-bi.get-datasets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dataset\n        description: Create a dataset\n        call: power-bi.create-dataset\n        with:\n          name: rest.name\n          tables: rest.tables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets/{datasetId}\n      name: dataset\n      description: Individual dataset operations\n      operations:\n      - method: GET\n        name: get-dataset\n        description: Get dataset details\n        call: power-bi.get-dataset\n        with:\n          datasetId: rest.datasetId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-dataset\n        description: Delete a dataset\n        call: power-bi.delete-dataset\n        with:\n          datasetId: rest.datasetId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Report management\n      operations:\n      - method: GET\n        name: list-reports\n        description: List all reports\n        call: power-bi.get-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards\n      name: dashboards\n      description: Dashboard management\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List all dashboards\n        call: power-bi.get-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dashboard\n        description: Create a dashboard\n        call: power-bi.create-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Workspace management\n      operations:\n      - method:\
  \ GET\n        name: list-workspaces\n        description: List workspaces\n        call: power-bi.get-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      name: gateways\n      description: Gateway management\n      operations:\n      - method: GET\n        name: list-gateways\n        description: List gateways\n        call: power-bi.get-gateways\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: power-bi-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Power BI analytics and reporting.\n    tools:\n    - name: list-datasets\n      description: List all Power BI datasets\n      hints:\n        readOnly: true\n        openWorld: true\n      call: power-bi.get-datasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset\n      description: Get dataset details by ID\n      hints:\n    \
  \    readOnly: true\n      call: power-bi.get-dataset\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dataset\n      description: Create a new dataset\n      hints:\n        readOnly: false\n      call: power-bi.create-dataset\n      with:\n        name: tools.name\n        tables: tools.tables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-dataset\n      description: Delete a dataset\n      hints:\n        destructive: true\n        idempotent: true\n      call: power-bi.delete-dataset\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refresh-dataset\n      description: Trigger a dataset refresh\n      hints:\n        readOnly: false\n      call: power-bi.refresh-dataset\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-refresh-history\n      description: Get dataset refresh history\n      hints:\n        readOnly: true\n      call: power-bi.get-refresh-history\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-datasources\n      description: Get datasources for a dataset\n      hints:\n        readOnly: true\n      call: power-bi.get-datasources\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List all Power BI reports\n      hints:\n        readOnly: true\n        openWorld: true\n      call: power-bi.get-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report\n      description: Get report details by ID\n      hints:\n        readOnly: true\n      call: power-bi.get-report\n      with:\n        reportId: tools.reportId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: clone-report\n      description: Clone a report\n      hints:\n        readOnly: false\n      call: power-bi.clone-report\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-report\n      description: Export a report\n      hints:\n        readOnly: true\n      call: power-bi.export-report\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-pages\n      description: Get pages for a report\n      hints:\n        readOnly: true\n      call: power-bi.get-pages\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dashboards\n      description: List all dashboards\n      hints:\n        readOnly: true\n        openWorld: true\n      call: power-bi.get-dashboards\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: get-dashboard\n      description: Get dashboard details\n      hints:\n        readOnly: true\n      call: power-bi.get-dashboard\n      with:\n        dashboardId: tools.dashboardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dashboard\n      description: Create a new dashboard\n      hints:\n        readOnly: false\n      call: power-bi.create-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dashboard-tiles\n      description: Get tiles for a dashboard\n      hints:\n        readOnly: true\n      call: power-bi.get-tiles\n      with:\n        dashboardId: tools.dashboardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all workspaces\n      hints:\n        readOnly: true\n        openWorld: true\n      call: power-bi.get-groups\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: create-workspace\n      description: Create a new workspace\n      hints:\n        readOnly: false\n      call: power-bi.create-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workspace-users\n      description: List workspace users\n      hints:\n        readOnly: true\n      call: power-bi.get-group-users\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-gateways\n      description: List data gateways\n      hints:\n        readOnly: true\n      call: power-bi.get-gateways\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gateway\n      description: Get gateway details\n      hints:\n        readOnly: true\n      call: power-bi.get-gateway\n      with:\n        gatewayId: tools.gatewayId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gateway-datasources\n\
  \      description: Get gateway datasources\n      hints:\n        readOnly: true\n      call: power-bi.get-gateway-datasources\n      with:\n        gatewayId: tools.gatewayId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
