---
categories:
- monitoring
consumed_apis: []
description: Unified workflow for monitoring, incident response, and maintenance management across Oracle infrastructure using Enterprise Manager Cloud Control APIs. Designed for infrastructure administrators and operations teams.
layout: capability
name: Oracle Enterprise Manager Infrastructure Management
operations:
- description: List monitored targets
  method: GET
  name: list-targets
  path: /v1/targets
- description: Create a monitored target
  method: POST
  name: create-target
  path: /v1/targets
- description: Get target details
  method: GET
  name: get-target
  path: /v1/targets/{targetId}
- description: List incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Get incident details
  method: GET
  name: get-incident
  path: /v1/incidents/{incidentId}
- description: List blackouts
  method: GET
  name: list-blackouts
  path: /v1/blackouts
- description: Get metric time series data
  method: GET
  name: get-metric-time-series
  path: /v1/metrics
personas: []
provider_name: Oracle Enterprise Manager
provider_slug: oracle-enterprise-manager
search_terms:
- target details
- monitored targets
- get configuration properties of a target
- create blackout
- get event
- get target properties
- clear an incident marking it as resolved
- create a monitored target
- list blackouts
- list monitored targets
- get metric time series data
- monitoring
- get details of a specific monitored target
- list metric groups available for a target
- get details of a specific monitoring event
- database management
- list incidents in enterprise manager
- list metric groups
- oracle
- infrastructure management
- clear incident
- delete a scheduled blackout
- suppress incident
- create a new monitored target
- infrastructure incidents
- get details of a specific blackout
- performance metrics
- list monitored targets in enterprise manager
- list global target properties for classification
- suppress an incident from active views
- get incident details
- incident details
- enterprise management
- get metric time series
- create a new blackout (maintenance window)
- get target details
- enterprise manager
- cloud management
- list global target properties
- get metric time series data for performance analysis
- delete blackout
- maintenance windows
- get incident
- get details of a specific incident
- list blackouts (maintenance windows)
- get target
- list targets
- list incidents
- get blackout
- create target
slug: infrastructure-management
source_filename: infrastructure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Enterprise Manager Infrastructure Management\n  description: Unified workflow for monitoring, incident response, and maintenance management across Oracle infrastructure\n    using Enterprise Manager Cloud Control APIs. Designed for infrastructure administrators and operations teams.\n  tags:\n  - Oracle\n  - Enterprise Manager\n  - Infrastructure Management\n  - Monitoring\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OEM_USERNAME: OEM_USERNAME\n    OEM_PASSWORD: OEM_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-control\n    baseUri: https://{emHost}:{emPort}/em/api\n    description: Oracle Enterprise Manager Cloud Control REST API\n    authentication:\n      type: basic\n      username: '{{OEM_USERNAME}}'\n      password: '{{OEM_PASSWORD}}'\n    resources:\n    - name: targets\n      path: /targets\n      description: Manage monitored targets in Enterprise\
  \ Manager\n      operations:\n      - name: list-targets\n        method: GET\n        description: List monitored targets with optional filtering\n        inputParameters:\n        - name: targetName\n          in: query\n          type: string\n          required: false\n          description: Filter targets by name\n        - name: targetType\n          in: query\n          type: string\n          required: false\n          description: Filter targets by type\n        - name: lifecycleStatus\n          in: query\n          type: string\n          required: false\n          description: Filter targets by lifecycle status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of items to skip\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-target\n        method: POST\n        description: Create a new monitored target\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetName: '{{tools.targetName}}'\n            targetType: '{{tools.targetType}}'\n            hostName: '{{tools.hostName}}'\n    - name: target-details\n      path: /targets/{targetId}\n      description: Get, update, or delete a specific target\n      operations:\n      - name: get-target\n        method: GET\n        description: Get target details\n        inputParameters:\n        - name: targetId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n      - name: update-target\n        method: PATCH\n        description: Update target properties\n        inputParameters:\n        - name: targetId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: delete-target\n        method: DELETE\n        description: Remove a monitored target\n        inputParameters:\n        - name: targetId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: target-properties\n      path: /targets/{targetId}/properties\n\
  \      description: Get target configuration properties\n      operations:\n      - name: get-target-properties\n        method: GET\n        description: Get target properties\n        inputParameters:\n        - name: targetId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /targets/{targetId}/metricGroups\n      description: Manage metric groups for targets\n      operations:\n      - name: list-metric-groups\n        method: GET\n        description: List metric groups for a target\n        inputParameters:\n        - name: targetId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: metric-time-series\n      path: /metricTimeSeries\n      description: Query metric time series data\n      operations:\n      - name: get-metric-time-series\n        method: GET\n        description: Get metric time series data over a time range\n        inputParameters:\n        - name: targetNames\n          in: query\n          type: string\n          required: false\n          description: Comma-separated target names\n        - name: metricGroups\n          in: query\n          type: string\n          required: false\n          description: Comma-separated metric group names\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start time in ISO 8601 format\n        - name: endTime\n          in: query\n          type: string\n          required: false\n          description: End time in ISO 8601 format\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: incidents\n      path: /incidents\n      description: Search and manage incidents\n      operations:\n      - name: list-incidents\n        method: GET\n        description: List incidents with optional filtering\n        inputParameters:\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity level\n        - name: priority\n          in: query\n          type: string\n          required: false\n          description: Filter by priority\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: targetName\n          in: query\n          type: string\n          required: false\n          description: Filter by target name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Maximum number of items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-details\n      path: /incidents/{incidentId}\n      description: Get incident details\n      operations:\n      - name: get-incident\n        method: GET\n        description: Get incident details\n        inputParameters:\n        - name: incidentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-actions\n      path: /incidents/{incidentId}/actions\n      description: Perform actions on incidents\n      operations:\n      - name: clear-incident\n        method: POST\n        description: Clear an incident\n        inputParameters:\n        - name: incidentId\n          in: path\n        \
  \  type: string\n          required: true\n          description: Unique identifier of the incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suppress-incident\n        method: POST\n        description: Suppress an incident\n        inputParameters:\n        - name: incidentId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blackouts\n      path: /blackouts\n      description: Manage maintenance windows\n      operations:\n      - name: list-blackouts\n        method: GET\n        description: List blackouts\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by blackout\
  \ status\n        - name: targetName\n          in: query\n          type: string\n          required: false\n          description: Filter by target name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-blackout\n        method: POST\n        description: Create a new blackout\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            blackoutName: '{{tools.blackoutName}}'\n            reason: '{{tools.reason}}'\n    - name: blackout-details\n      path: /blackouts/{blackoutId}\n      description: Get, update, or delete a blackout\n      operations:\n      - name: get-blackout\n        method: GET\n        description: Get blackout details\n        inputParameters:\n        - name: blackoutId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Unique identifier of the blackout\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-blackout\n        method: DELETE\n        description: Delete a blackout\n        inputParameters:\n        - name: blackoutId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the blackout\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events/{eventId}\n      description: Get event details\n      operations:\n      - name: get-event\n        method: GET\n        description: Get event details\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the event\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: global-target-properties\n      path: /globalTargetProperties\n      description: Manage global target properties\n      operations:\n      - name: list-global-target-properties\n        method: GET\n        description: List global target properties\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oem-infra-api\n    description: Unified REST API for Oracle Enterprise Manager infrastructure management.\n    resources:\n    - path: /v1/targets\n      name: targets\n      description: Monitored targets\n      operations:\n      - method: GET\n        name: list-targets\n        description: List monitored targets\n        call: cloud-control.list-targets\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n      - method: POST\n        name: create-target\n        description: Create a monitored target\n        call: cloud-control.create-target\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/targets/{targetId}\n      name: target-details\n      description: Target details\n      operations:\n      - method: GET\n        name: get-target\n        description: Get target details\n        call: cloud-control.get-target\n        with:\n          targetId: rest.targetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents\n      name: incidents\n      description: Infrastructure incidents\n      operations:\n      - method: GET\n        name: list-incidents\n        description: List incidents\n        call: cloud-control.list-incidents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents/{incidentId}\n      name: incident-details\n\
  \      description: Incident details\n      operations:\n      - method: GET\n        name: get-incident\n        description: Get incident details\n        call: cloud-control.get-incident\n        with:\n          incidentId: rest.incidentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blackouts\n      name: blackouts\n      description: Maintenance windows\n      operations:\n      - method: GET\n        name: list-blackouts\n        description: List blackouts\n        call: cloud-control.list-blackouts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Performance metrics\n      operations:\n      - method: GET\n        name: get-metric-time-series\n        description: Get metric time series data\n        call: cloud-control.get-metric-time-series\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: oem-infra-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle Enterprise Manager infrastructure management.\n    tools:\n    - name: list-targets\n      description: List monitored targets in Enterprise Manager\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-control.list-targets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-target\n      description: Get details of a specific monitored target\n      hints:\n        readOnly: true\n      call: cloud-control.get-target\n      with:\n        targetId: tools.targetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-target\n      description: Create a new monitored target\n      hints:\n        readOnly: false\n      call: cloud-control.create-target\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-incidents\n      description: List incidents in Enterprise\
  \ Manager\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-control.list-incidents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-incident\n      description: Get details of a specific incident\n      hints:\n        readOnly: true\n      call: cloud-control.get-incident\n      with:\n        incidentId: tools.incidentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clear-incident\n      description: Clear an incident marking it as resolved\n      hints:\n        readOnly: false\n      call: cloud-control.clear-incident\n      with:\n        incidentId: tools.incidentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suppress-incident\n      description: Suppress an incident from active views\n      hints:\n        readOnly: false\n      call: cloud-control.suppress-incident\n      with:\n        incidentId: tools.incidentId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-blackouts\n      description: List blackouts (maintenance windows)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-control.list-blackouts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-blackout\n      description: Get details of a specific blackout\n      hints:\n        readOnly: true\n      call: cloud-control.get-blackout\n      with:\n        blackoutId: tools.blackoutId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-blackout\n      description: Create a new blackout (maintenance window)\n      hints:\n        readOnly: false\n      call: cloud-control.create-blackout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-blackout\n      description: Delete a scheduled blackout\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloud-control.delete-blackout\n\
  \      with:\n        blackoutId: tools.blackoutId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metric-time-series\n      description: Get metric time series data for performance analysis\n      hints:\n        readOnly: true\n      call: cloud-control.get-metric-time-series\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-metric-groups\n      description: List metric groups available for a target\n      hints:\n        readOnly: true\n      call: cloud-control.list-metric-groups\n      with:\n        targetId: tools.targetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event\n      description: Get details of a specific monitoring event\n      hints:\n        readOnly: true\n      call: cloud-control.get-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-target-properties\n      description:\
  \ Get configuration properties of a target\n      hints:\n        readOnly: true\n      call: cloud-control.get-target-properties\n      with:\n        targetId: tools.targetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-global-target-properties\n      description: List global target properties for classification\n      hints:\n        readOnly: true\n      call: cloud-control.list-global-target-properties\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-enterprise-manager/refs/heads/main/capabilities/infrastructure-management.yaml
tags:
- Oracle
- Enterprise Manager
- Infrastructure Management
- Monitoring
tools:
- description: List monitored targets in Enterprise Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-targets
- description: Get details of a specific monitored target
  hints:
    readOnly: true
  name: get-target
- description: Create a new monitored target
  hints:
    readOnly: false
  name: create-target
- description: List incidents in Enterprise Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-incidents
- description: Get details of a specific incident
  hints:
    readOnly: true
  name: get-incident
- description: Clear an incident marking it as resolved
  hints:
    readOnly: false
  name: clear-incident
- description: Suppress an incident from active views
  hints:
    readOnly: false
  name: suppress-incident
- description: List blackouts (maintenance windows)
  hints:
    openWorld: true
    readOnly: true
  name: list-blackouts
- description: Get details of a specific blackout
  hints:
    readOnly: true
  name: get-blackout
- description: Create a new blackout (maintenance window)
  hints:
    readOnly: false
  name: create-blackout
- description: Delete a scheduled blackout
  hints:
    destructive: true
    idempotent: true
  name: delete-blackout
- description: Get metric time series data for performance analysis
  hints:
    readOnly: true
  name: get-metric-time-series
- description: List metric groups available for a target
  hints:
    readOnly: true
  name: list-metric-groups
- description: Get details of a specific monitoring event
  hints:
    readOnly: true
  name: get-event
- description: Get configuration properties of a target
  hints:
    readOnly: true
  name: get-target-properties
- description: List global target properties for classification
  hints:
    readOnly: true
  name: list-global-target-properties
---
