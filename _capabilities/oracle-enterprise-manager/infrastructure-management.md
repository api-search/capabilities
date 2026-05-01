---
categories:
- monitoring
consumed_apis:
- cloud-control
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
- get details of a specific monitored target
- database management
- get metric time series data
- get details of a specific blackout
- get incident details
- performance metrics
- delete a scheduled blackout
- monitoring
- get metric time series
- create a new monitored target
- get target properties
- enterprise management
- create target
- suppress an incident from active views
- infrastructure incidents
- get incident
- get metric time series data for performance analysis
- cloud management
- get target
- clear incident
- delete blackout
- get blackout
- monitored targets
- create a new blackout (maintenance window)
- get target details
- target details
- list blackouts (maintenance windows)
- oracle
- get event
- list blackouts
- list global target properties for classification
- list incidents
- list metric groups available for a target
- incident details
- create blackout
- get details of a specific incident
- get details of a specific monitoring event
- list targets
- list incidents in enterprise manager
- create a monitored target
- list global target properties
- maintenance windows
- enterprise manager
- list monitored targets in enterprise manager
- get configuration properties of a target
- suppress incident
- list monitored targets
- infrastructure management
- list metric groups
- clear an incident marking it as resolved
slug: infrastructure-management
source_filename: infrastructure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle Enterprise Manager Infrastructure Management\"\n  description: \"Unified workflow for monitoring, incident response, and maintenance management across Oracle infrastructure using Enterprise Manager Cloud Control APIs. Designed for infrastructure administrators and operations teams.\"\n  tags:\n    - Oracle\n    - Enterprise Manager\n    - Infrastructure Management\n    - Monitoring\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      OEM_USERNAME: OEM_USERNAME\n      OEM_PASSWORD: OEM_PASSWORD\n\ncapability:\n  consumes:\n    - import: cloud-control\n      location: ./shared/cloud-control.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: oem-infra-api\n      description: \"Unified REST API for Oracle Enterprise Manager infrastructure management.\"\n      resources:\n        - path: /v1/targets\n          name: targets\n          description: \"Monitored\
  \ targets\"\n          operations:\n            - method: GET\n              name: list-targets\n              description: \"List monitored targets\"\n              call: \"cloud-control.list-targets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-target\n              description: \"Create a monitored target\"\n              call: \"cloud-control.create-target\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/targets/{targetId}\n          name: target-details\n          description: \"Target details\"\n          operations:\n            - method: GET\n              name: get-target\n              description: \"Get target details\"\n              call: \"cloud-control.get-target\"\n              with:\n                targetId: \"rest.targetId\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/incidents\n          name: incidents\n          description: \"Infrastructure incidents\"\n          operations:\n            - method: GET\n              name: list-incidents\n              description: \"List incidents\"\n              call: \"cloud-control.list-incidents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents/{incidentId}\n          name: incident-details\n          description: \"Incident details\"\n          operations:\n            - method: GET\n              name: get-incident\n              description: \"Get incident details\"\n              call: \"cloud-control.get-incident\"\n              with:\n                incidentId: \"rest.incidentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blackouts\n          name: blackouts\n          description: \"\
  Maintenance windows\"\n          operations:\n            - method: GET\n              name: list-blackouts\n              description: \"List blackouts\"\n              call: \"cloud-control.list-blackouts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Performance metrics\"\n          operations:\n            - method: GET\n              name: get-metric-time-series\n              description: \"Get metric time series data\"\n              call: \"cloud-control.get-metric-time-series\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: oem-infra-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle Enterprise Manager infrastructure management.\"\n      tools:\n        - name: list-targets\n          description: \"List monitored\
  \ targets in Enterprise Manager\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-control.list-targets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-target\n          description: \"Get details of a specific monitored target\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.get-target\"\n          with:\n            targetId: \"tools.targetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-target\n          description: \"Create a new monitored target\"\n          hints:\n            readOnly: false\n          call: \"cloud-control.create-target\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-incidents\n          description: \"List incidents in Enterprise Manager\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"cloud-control.list-incidents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-incident\n          description: \"Get details of a specific incident\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.get-incident\"\n          with:\n            incidentId: \"tools.incidentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: clear-incident\n          description: \"Clear an incident marking it as resolved\"\n          hints:\n            readOnly: false\n          call: \"cloud-control.clear-incident\"\n          with:\n            incidentId: \"tools.incidentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: suppress-incident\n          description: \"Suppress an incident from active views\"\n          hints:\n            readOnly: false\n\
  \          call: \"cloud-control.suppress-incident\"\n          with:\n            incidentId: \"tools.incidentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-blackouts\n          description: \"List blackouts (maintenance windows)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-control.list-blackouts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-blackout\n          description: \"Get details of a specific blackout\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.get-blackout\"\n          with:\n            blackoutId: \"tools.blackoutId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-blackout\n          description: \"Create a new blackout (maintenance window)\"\n          hints:\n            readOnly: false\n\
  \          call: \"cloud-control.create-blackout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-blackout\n          description: \"Delete a scheduled blackout\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloud-control.delete-blackout\"\n          with:\n            blackoutId: \"tools.blackoutId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metric-time-series\n          description: \"Get metric time series data for performance analysis\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.get-metric-time-series\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-metric-groups\n          description: \"List metric groups available for a target\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.list-metric-groups\"\
  \n          with:\n            targetId: \"tools.targetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-event\n          description: \"Get details of a specific monitoring event\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.get-event\"\n          with:\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-target-properties\n          description: \"Get configuration properties of a target\"\n          hints:\n            readOnly: true\n          call: \"cloud-control.get-target-properties\"\n          with:\n            targetId: \"tools.targetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-global-target-properties\n          description: \"List global target properties for classification\"\n          hints:\n            readOnly:\
  \ true\n          call: \"cloud-control.list-global-target-properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
