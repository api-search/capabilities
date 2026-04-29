---
categories:
- monitoring
consumed_apis:
- log-analytics-query
- log-analytics-management
- log-analytics-ingestion
description: Unified workflow for log monitoring and analysis combining the Query API for KQL-based data exploration, the Management API for workspace and saved search administration, and the Ingestion API for custom log data collection. Used by DevOps engineers, SOC analysts, and platform administrators.
layout: capability
name: Azure Log Analytics Log Monitoring and Analysis
operations:
- description: Execute a KQL query.
  method: POST
  name: execute-query
  path: /v1/queries
- description: List all workspaces.
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Get a workspace.
  method: GET
  name: get-workspace
  path: /v1/workspaces/{workspaceName}
- description: List saved searches.
  method: GET
  name: list-saved-searches
  path: /v1/saved-searches
- description: List all tables.
  method: GET
  name: list-tables
  path: /v1/tables
- description: Upload custom log entries.
  method: POST
  name: upload-logs
  path: /v1/ingest
personas: []
provider_name: Azure Log Analytics
provider_slug: azure-log-analytics
search_terms:
- monitoring
- list all tables.
- DevOps Engineer
- execute query
- analytics
- execute a kql query against a log analytics workspace.
- list saved searches in a workspace.
- get details of a specific log analytics workspace.
- unified workflow combining query, management, and ingestion apis for complete log monitoring and analysis.
- infrastructure and application monitoring through log analysis.
- list all workspaces.
- azure
- create workspace
- log analytics
- send custom log data to a workspace via data collection rule.
- kql-based data exploration and saved query management.
- logging
- get workspace
- get workspace details.
- list all tables in a log analytics workspace.
- administrators managing workspaces, tables, and data collection configurations.
- security event analysis and custom security log ingestion.
- delete workspace
- engineers monitoring infrastructure and application health through log queries.
- manage log analytics workspaces.
- manage saved kql queries.
- create or update a log analytics workspace.
- list saved searches
- upload logs
- execute kql queries against workspaces.
- cloud
- security analysts investigating incidents and threats through log data.
- kql
- Platform Administrator
- list tables
- list all log analytics workspaces in a subscription.
- upload custom log entries.
- SOC Analyst
- create or update a saved search in a workspace.
- list workspace tables.
- execute a kql query.
- list workspaces
- create saved search
- list saved searches.
- send custom log data.
- get a workspace.
- delete a log analytics workspace.
slug: log-monitoring-and-analysis
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Log Analytics Log Monitoring and Analysis\"\n  description: >-\n    Unified workflow for log monitoring and analysis combining the Query API for\n    KQL-based data exploration, the Management API for workspace and saved search\n    administration, and the Ingestion API for custom log data collection. Used by\n    DevOps engineers, SOC analysts, and platform administrators.\n  tags:\n    - Azure\n    - Log Analytics\n    - Monitoring\n    - Analytics\n    - KQL\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_LOG_ANALYTICS_BEARER_TOKEN: AZURE_LOG_ANALYTICS_BEARER_TOKEN\n      AZURE_MANAGEMENT_BEARER_TOKEN: AZURE_MANAGEMENT_BEARER_TOKEN\n      AZURE_INGESTION_BEARER_TOKEN: AZURE_INGESTION_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: log-analytics-query\n      location: ./shared/query-api.yaml\n    - import: log-analytics-management\n      location: ./shared/management-api.yaml\n\
  \    - import: log-analytics-ingestion\n      location: ./shared/ingestion-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: log-monitoring-api\n      description: \"Unified REST API for Azure Log Analytics monitoring and analysis.\"\n      resources:\n        - path: /v1/queries\n          name: queries\n          description: \"Execute KQL queries against workspaces.\"\n          operations:\n            - method: POST\n              name: execute-query\n              description: \"Execute a KQL query.\"\n              call: \"log-analytics-query.post-query\"\n              with:\n                workspaceId: \"rest.workspaceId\"\n                query: \"rest.query\"\n                timespan: \"rest.timespan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Manage Log Analytics workspaces.\"\n          operations:\n  \
  \          - method: GET\n              name: list-workspaces\n              description: \"List all workspaces.\"\n              call: \"log-analytics-management.list-workspaces\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{workspaceName}\n          name: workspace-detail\n          description: \"Get workspace details.\"\n          operations:\n            - method: GET\n              name: get-workspace\n              description: \"Get a workspace.\"\n              call: \"log-analytics-management.get-workspace\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n                resourceGroupName: \"rest.resourceGroupName\"\n                workspaceName: \"rest.workspaceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/saved-searches\n          name: saved-searches\n          description: \"Manage saved KQL queries.\"\n          operations:\n            - method: GET\n              name: list-saved-searches\n              description: \"List saved searches.\"\n              call: \"log-analytics-management.list-saved-searches\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n                resourceGroupName: \"rest.resourceGroupName\"\n                workspaceName: \"rest.workspaceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tables\n          name: tables\n          description: \"List workspace tables.\"\n          operations:\n            - method: GET\n              name: list-tables\n              description: \"List all tables.\"\n              call: \"log-analytics-management.list-tables\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n      \
  \          resourceGroupName: \"rest.resourceGroupName\"\n                workspaceName: \"rest.workspaceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ingest\n          name: ingest\n          description: \"Send custom log data.\"\n          operations:\n            - method: POST\n              name: upload-logs\n              description: \"Upload custom log entries.\"\n              call: \"log-analytics-ingestion.upload-logs\"\n              with:\n                dcrImmutableId: \"rest.dcrImmutableId\"\n                streamName: \"rest.streamName\"\n                logEntries: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: log-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Log Analytics monitoring and analysis.\"\n      tools:\n   \
  \     - name: execute-query\n          description: \"Execute a KQL query against a Log Analytics workspace.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-analytics-query.post-query\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n            query: \"tools.query\"\n            timespan: \"tools.timespan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List all Log Analytics workspaces in a subscription.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-analytics-management.list-workspaces\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workspace\n          description: \"Get details of a specific Log Analytics workspace.\"\n         \
  \ hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-analytics-management.get-workspace\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            workspaceName: \"tools.workspaceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace\n          description: \"Create or update a Log Analytics workspace.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"log-analytics-management.create-or-update-workspace\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            workspaceName: \"tools.workspaceName\"\n            location: \"tools.location\"\n            properties: \"tools.properties\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: delete-workspace\n          description: \"Delete a Log Analytics workspace.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"log-analytics-management.delete-workspace\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            workspaceName: \"tools.workspaceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-saved-searches\n          description: \"List saved searches in a workspace.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-analytics-management.list-saved-searches\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            workspaceName: \"tools.workspaceName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-saved-search\n          description: \"Create or update a saved search in a workspace.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"log-analytics-management.create-or-update-saved-search\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            workspaceName: \"tools.workspaceName\"\n            savedSearchId: \"tools.savedSearchId\"\n            properties: \"tools.properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tables\n          description: \"List all tables in a Log Analytics workspace.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"log-analytics-management.list-tables\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\
  \n            resourceGroupName: \"tools.resourceGroupName\"\n            workspaceName: \"tools.workspaceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-logs\n          description: \"Send custom log data to a workspace via data collection rule.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"log-analytics-ingestion.upload-logs\"\n          with:\n            dcrImmutableId: \"tools.dcrImmutableId\"\n            streamName: \"tools.streamName\"\n            logEntries: \"tools.logEntries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-log-analytics/refs/heads/main/capabilities/log-monitoring-and-analysis.yaml
tags:
- Azure
- Log Analytics
- Monitoring
- Analytics
- KQL
tools:
- description: Execute a KQL query against a Log Analytics workspace.
  hints:
    openWorld: true
    readOnly: true
  name: execute-query
- description: List all Log Analytics workspaces in a subscription.
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Get details of a specific Log Analytics workspace.
  hints:
    openWorld: true
    readOnly: true
  name: get-workspace
- description: Create or update a Log Analytics workspace.
  hints:
    idempotent: true
    readOnly: false
  name: create-workspace
- description: Delete a Log Analytics workspace.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-workspace
- description: List saved searches in a workspace.
  hints:
    openWorld: true
    readOnly: true
  name: list-saved-searches
- description: Create or update a saved search in a workspace.
  hints:
    idempotent: true
    readOnly: false
  name: create-saved-search
- description: List all tables in a Log Analytics workspace.
  hints:
    openWorld: true
    readOnly: true
  name: list-tables
- description: Send custom log data to a workspace via data collection rule.
  hints:
    idempotent: false
    readOnly: false
  name: upload-logs
---
