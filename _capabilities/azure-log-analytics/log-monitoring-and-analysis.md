---
categories:
- monitoring
consumed_apis: []
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
- analytics
- list workspaces
- send custom log data.
- DevOps Engineer
- execute a kql query.
- administrators managing workspaces, tables, and data collection configurations.
- get a workspace.
- create saved search
- kql
- list workspace tables.
- execute a kql query against a log analytics workspace.
- execute kql queries against workspaces.
- monitoring
- delete workspace
- create or update a log analytics workspace.
- unified workflow combining query, management, and ingestion apis for complete log monitoring and analysis.
- create workspace
- manage log analytics workspaces.
- list tables
- send custom log data to a workspace via data collection rule.
- security event analysis and custom security log ingestion.
- engineers monitoring infrastructure and application health through log queries.
- upload custom log entries.
- create or update a saved search in a workspace.
- execute query
- list saved searches
- cloud
- get workspace details.
- Platform Administrator
- list all tables.
- list saved searches.
- upload logs
- manage saved kql queries.
- list saved searches in a workspace.
- infrastructure and application monitoring through log analysis.
- list all tables in a log analytics workspace.
- azure
- list all log analytics workspaces in a subscription.
- get details of a specific log analytics workspace.
- kql-based data exploration and saved query management.
- log analytics
- security analysts investigating incidents and threats through log data.
- SOC Analyst
- delete a log analytics workspace.
- logging
- get workspace
- list all workspaces.
slug: log-monitoring-and-analysis
source_filename: log-monitoring-and-analysis.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Log Analytics Log Monitoring and Analysis\n  description: Unified workflow for log monitoring and analysis combining the Query API for KQL-based data exploration, the\n    Management API for workspace and saved search administration, and the Ingestion API for custom log data collection. Used\n    by DevOps engineers, SOC analysts, and platform administrators.\n  tags:\n  - Azure\n  - Log Analytics\n  - Monitoring\n  - Analytics\n  - KQL\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_LOG_ANALYTICS_BEARER_TOKEN: AZURE_LOG_ANALYTICS_BEARER_TOKEN\n    AZURE_MANAGEMENT_BEARER_TOKEN: AZURE_MANAGEMENT_BEARER_TOKEN\n    AZURE_INGESTION_BEARER_TOKEN: AZURE_INGESTION_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: log-analytics-query\n    baseUri: https://api.loganalytics.azure.com/v1\n    description: Azure Log Analytics Query API for executing KQL queries.\n    authentication:\n\
  \      type: bearer\n      token: '{{AZURE_LOG_ANALYTICS_BEARER_TOKEN}}'\n    resources:\n    - name: queries\n      path: /workspaces\n      description: Execute KQL queries against Log Analytics workspaces.\n      operations:\n      - name: get-query\n        method: GET\n        description: Execute a KQL query using GET method.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The ID of the Log Analytics workspace.\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: The KQL query to execute.\n        - name: timespan\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration for the query timespan.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.tables\n      - name: post-query\n        method:\
  \ POST\n        description: Execute a KQL query using POST method.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The ID of the Log Analytics workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.tables\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            timespan: '{{tools.timespan}}'\n  - type: http\n    namespace: log-analytics-management\n    baseUri: https://management.azure.com\n    description: Azure Log Analytics Management API for workspace and resource management.\n    authentication:\n      type: bearer\n      token: '{{AZURE_MANAGEMENT_BEARER_TOKEN}}'\n    resources:\n    - name: workspaces\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.OperationalInsights/workspaces\n      description: Manage\
  \ Log Analytics workspaces.\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all workspaces in a subscription.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.value\n      - name: get-workspace\n        method: GET\n        description: Get a specific workspace instance.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n\
  \          description: The resource group name.\n        - name: workspaceName\n          in: path\n          type: string\n          required: true\n          description: The workspace name.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-or-update-workspace\n        method: PUT\n        description: Create or update a workspace.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: The resource group name.\n        - name: workspaceName\n          in: path\n          type: string\n          required:\
  \ true\n          description: The workspace name.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            location: '{{tools.location}}'\n            properties: '{{tools.properties}}'\n      - name: delete-workspace\n        method: DELETE\n        description: Delete a workspace.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: The resource group name.\n        - name: workspaceName\n          in: path\n          type: string\n          required: true\n    \
  \      description: The workspace name.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: saved-searches\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.OperationalInsights/workspaces/{workspaceName}/savedSearches\n      description: Manage saved KQL queries.\n      operations:\n      - name: list-saved-searches\n        method: GET\n        description: List saved searches for a workspace.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: The resource group\
  \ name.\n        - name: workspaceName\n          in: path\n          type: string\n          required: true\n          description: The workspace name.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.value\n      - name: create-or-update-saved-search\n        method: PUT\n        description: Create or update a saved search.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: The resource group name.\n        - name: workspaceName\n          in: path\n          type: string\n          required: true\n          description:\
  \ The workspace name.\n        - name: savedSearchId\n          in: path\n          type: string\n          required: true\n          description: The saved search ID.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: delete-saved-search\n        method: DELETE\n        description: Delete a saved search.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: The resource group name.\n        - name: workspaceName\n\
  \          in: path\n          type: string\n          required: true\n          description: The workspace name.\n        - name: savedSearchId\n          in: path\n          type: string\n          required: true\n          description: The saved search ID.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tables\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.OperationalInsights/workspaces/{workspaceName}/tables\n      description: Manage workspace tables.\n      operations:\n      - name: list-tables\n        method: GET\n        description: List all tables in a workspace.\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n      \
  \    description: The target subscription ID.\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: The resource group name.\n        - name: workspaceName\n          in: path\n          type: string\n          required: true\n          description: The workspace name.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.value\n  - type: http\n    namespace: log-analytics-ingestion\n    baseUri: https://{endpoint}\n    description: Azure Log Analytics Ingestion API for sending log data.\n    authentication:\n      type: bearer\n      token: '{{AZURE_INGESTION_BEARER_TOKEN}}'\n    resources:\n    - name: logs\n      path: /dataCollectionRules\n      description: Send log data via data collection rules.\n  \
  \    operations:\n      - name: upload-logs\n        method: POST\n        description: Send custom log data to a Log Analytics workspace.\n        inputParameters:\n        - name: dcrImmutableId\n          in: path\n          type: string\n          required: true\n          description: The immutable ID of the data collection rule.\n        - name: streamName\n          in: path\n          type: string\n          required: true\n          description: The stream name in the DCR.\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.logEntries}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: log-monitoring-api\n    description: Unified REST API for Azure Log Analytics monitoring and analysis.\n    resources:\n\
  \    - path: /v1/queries\n      name: queries\n      description: Execute KQL queries against workspaces.\n      operations:\n      - method: POST\n        name: execute-query\n        description: Execute a KQL query.\n        call: log-analytics-query.post-query\n        with:\n          workspaceId: rest.workspaceId\n          query: rest.query\n          timespan: rest.timespan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Manage Log Analytics workspaces.\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces.\n        call: log-analytics-management.list-workspaces\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces/{workspaceName}\n      name: workspace-detail\n      description: Get workspace details.\n      operations:\n\
  \      - method: GET\n        name: get-workspace\n        description: Get a workspace.\n        call: log-analytics-management.get-workspace\n        with:\n          subscriptionId: rest.subscriptionId\n          resourceGroupName: rest.resourceGroupName\n          workspaceName: rest.workspaceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/saved-searches\n      name: saved-searches\n      description: Manage saved KQL queries.\n      operations:\n      - method: GET\n        name: list-saved-searches\n        description: List saved searches.\n        call: log-analytics-management.list-saved-searches\n        with:\n          subscriptionId: rest.subscriptionId\n          resourceGroupName: rest.resourceGroupName\n          workspaceName: rest.workspaceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tables\n      name: tables\n      description: List workspace tables.\n      operations:\n\
  \      - method: GET\n        name: list-tables\n        description: List all tables.\n        call: log-analytics-management.list-tables\n        with:\n          subscriptionId: rest.subscriptionId\n          resourceGroupName: rest.resourceGroupName\n          workspaceName: rest.workspaceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ingest\n      name: ingest\n      description: Send custom log data.\n      operations:\n      - method: POST\n        name: upload-logs\n        description: Upload custom log entries.\n        call: log-analytics-ingestion.upload-logs\n        with:\n          dcrImmutableId: rest.dcrImmutableId\n          streamName: rest.streamName\n          logEntries: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: log-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Log Analytics monitoring and\
  \ analysis.\n    tools:\n    - name: execute-query\n      description: Execute a KQL query against a Log Analytics workspace.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-analytics-query.post-query\n      with:\n        workspaceId: tools.workspaceId\n        query: tools.query\n        timespan: tools.timespan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all Log Analytics workspaces in a subscription.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-analytics-management.list-workspaces\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workspace\n      description: Get details of a specific Log Analytics workspace.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-analytics-management.get-workspace\n      with:\n        subscriptionId:\
  \ tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        workspaceName: tools.workspaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace\n      description: Create or update a Log Analytics workspace.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: log-analytics-management.create-or-update-workspace\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        workspaceName: tools.workspaceName\n        location: tools.location\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-workspace\n      description: Delete a Log Analytics workspace.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: log-analytics-management.delete-workspace\n      with:\n        subscriptionId: tools.subscriptionId\n  \
  \      resourceGroupName: tools.resourceGroupName\n        workspaceName: tools.workspaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-saved-searches\n      description: List saved searches in a workspace.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-analytics-management.list-saved-searches\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        workspaceName: tools.workspaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-saved-search\n      description: Create or update a saved search in a workspace.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: log-analytics-management.create-or-update-saved-search\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        workspaceName: tools.workspaceName\n        savedSearchId:\
  \ tools.savedSearchId\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tables\n      description: List all tables in a Log Analytics workspace.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: log-analytics-management.list-tables\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        workspaceName: tools.workspaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-logs\n      description: Send custom log data to a workspace via data collection rule.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: log-analytics-ingestion.upload-logs\n      with:\n        dcrImmutableId: tools.dcrImmutableId\n        streamName: tools.streamName\n        logEntries: tools.logEntries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
