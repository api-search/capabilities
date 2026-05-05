---
categories: []
consumed_apis:
- tanium-platform
- tanium-threat-response
- tanium-connect
description: Workflow capability for unified endpoint management and security operations using Tanium. Combines the Platform REST API, Threat Response API, and Connect API to enable endpoint visibility, action deployment, threat investigation, and data delivery automation. Designed for security operations teams, IT administrators, and incident responders who need real-time control across all managed endpoints.
layout: capability
name: Tanium Endpoint Management
operations:
- description: Ask a question to all managed endpoints
  method: POST
  name: ask-question
  path: /v1/questions
- description: Get results collected from endpoints for a question
  method: GET
  name: get-question-results
  path: /v1/questions/{id}/results
- description: List all saved questions
  method: GET
  name: list-saved-questions
  path: /v1/saved-questions
- description: Get latest results for a saved question
  method: GET
  name: get-saved-question-results
  path: /v1/saved-questions/{id}/results
- description: Deploy a package action to targeted endpoints
  method: POST
  name: deploy-action
  path: /v1/actions
- description: List all available deployment packages
  method: GET
  name: list-packages
  path: /v1/packages
- description: List all endpoint sensors
  method: GET
  name: list-sensors
  path: /v1/sensors
- description: List all computer groups for endpoint targeting
  method: GET
  name: list-computer-groups
  path: /v1/computer-groups
- description: List threat alerts from Threat Response
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: List active endpoint investigation connections
  method: GET
  name: list-investigations
  path: /v1/investigations
- description: Start a live endpoint investigation connection
  method: POST
  name: start-investigation
  path: /v1/investigations
- description: List data delivery connections
  method: GET
  name: list-data-connections
  path: /v1/data-connections
- description: Create a data delivery connection
  method: POST
  name: create-data-connection
  path: /v1/data-connections
personas: []
provider_name: Tanium
provider_slug: tanium
search_terms:
- list data connections
- list threat alerts
- get results collected from endpoints for a question
- incident response
- results from saved questions
- deploy actions and packages to endpoints
- list all computer groups for endpoint targeting
- get endpoint data results for a question by id
- patch management
- endpoint deployment packages
- security
- list active endpoint investigation connections
- live endpoint investigation connections
- start a live endpoint investigation connection
- ask a natural language question to all tanium-managed endpoints (e.g., 'get running processes from all machines')
- list all endpoint sensors
- list all saved questions
- list all available deployment packages on the tanium server
- get the full process ancestry tree for a suspicious process on an endpoint
- create a data delivery connection to export tanium endpoint data to a downstream system
- query endpoint state using natural language questions
- start endpoint investigation
- list all endpoint sensors available for data collection in questions
- ask question
- threat detection
- threat response security alerts
- endpoint targeting groups
- deploy package to endpoints
- list packages
- endpoint management
- list investigations
- saved endpoint questions for recurring data collection
- list saved questions
- list alerts
- start a live investigation connection to an endpoint for incident response
- get question results
- list all available deployment packages
- ask a question to all managed endpoints
- list computer groups
- deploy a package action to targeted endpoints
- list threat alerts from threat response
- get recorder events from an endpoint connection (process, network, file events)
- deploy a package action to a targeted group of endpoints
- endpoint data collection sensors
- unified endpoint management
- get saved question results
- list data delivery connections
- list sensors
- retrieve endpoint question results
- list all computer groups for endpoint targeting in actions and questions
- start investigation
- list threat alerts detected by tanium threat response
- get process tree
- compliance
- data export connections to downstream systems
- deploy action
- get latest results for a saved question
- create a data delivery connection
- get endpoint events
- list all data delivery connections for exporting endpoint data to siem and other systems
- create data connection
- list all saved questions configured for recurring endpoint data collection
- get the latest collected results from a saved recurring question
- ask endpoint question
slug: endpoint-management
source_filename: endpoint-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tanium Endpoint Management\"\n  description: >-\n    Workflow capability for unified endpoint management and security operations using Tanium.\n    Combines the Platform REST API, Threat Response API, and Connect API to enable\n    endpoint visibility, action deployment, threat investigation, and data delivery\n    automation. Designed for security operations teams, IT administrators, and\n    incident responders who need real-time control across all managed endpoints.\n  tags:\n    - Compliance\n    - Endpoint Management\n    - Incident Response\n    - Patch Management\n    - Security\n    - Threat Detection\n    - Unified Endpoint Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TANIUM_API_TOKEN: TANIUM_API_TOKEN\n      TANIUM_SERVER: TANIUM_SERVER\n\ncapability:\n  consumes:\n    - import: tanium-platform\n      location: ./shared/platform-rest-api.yaml\n    -\
  \ import: tanium-threat-response\n      location: ./shared/threat-response-api.yaml\n    - import: tanium-connect\n      location: ./shared/connect-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tanium-endpoint-management-api\n      description: \"Unified REST API for Tanium endpoint management, threat response, and data integration.\"\n      resources:\n        - path: /v1/questions\n          name: questions\n          description: \"Query endpoint state using natural language questions\"\n          operations:\n            - method: POST\n              name: ask-question\n              description: \"Ask a question to all managed endpoints\"\n              call: \"tanium-platform.create-question\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/questions/{id}/results\n          name: question-results\n          description: \"Retrieve endpoint question results\"\n          operations:\n\
  \            - method: GET\n              name: get-question-results\n              description: \"Get results collected from endpoints for a question\"\n              call: \"tanium-platform.get-question-results\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/saved-questions\n          name: saved-questions\n          description: \"Saved endpoint questions for recurring data collection\"\n          operations:\n            - method: GET\n              name: list-saved-questions\n              description: \"List all saved questions\"\n              call: \"tanium-platform.list-saved-questions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/saved-questions/{id}/results\n          name: saved-question-results\n          description: \"Results from saved questions\"\n          operations:\n\
  \            - method: GET\n              name: get-saved-question-results\n              description: \"Get latest results for a saved question\"\n              call: \"tanium-platform.get-saved-question-results\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/actions\n          name: actions\n          description: \"Deploy actions and packages to endpoints\"\n          operations:\n            - method: POST\n              name: deploy-action\n              description: \"Deploy a package action to targeted endpoints\"\n              call: \"tanium-platform.create-action\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/packages\n          name: packages\n          description: \"Endpoint deployment packages\"\n          operations:\n            - method: GET\n              name: list-packages\n\
  \              description: \"List all available deployment packages\"\n              call: \"tanium-platform.list-packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sensors\n          name: sensors\n          description: \"Endpoint data collection sensors\"\n          operations:\n            - method: GET\n              name: list-sensors\n              description: \"List all endpoint sensors\"\n              call: \"tanium-platform.list-sensors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/computer-groups\n          name: computer-groups\n          description: \"Endpoint targeting groups\"\n          operations:\n            - method: GET\n              name: list-computer-groups\n              description: \"List all computer groups for endpoint targeting\"\n              call: \"tanium-platform.list-groups\"\n            \
  \  outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Threat Response security alerts\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List threat alerts from Threat Response\"\n              call: \"tanium-threat-response.list-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/investigations\n          name: investigations\n          description: \"Live endpoint investigation connections\"\n          operations:\n            - method: GET\n              name: list-investigations\n              description: \"List active endpoint investigation connections\"\n              call: \"tanium-threat-response.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            -\
  \ method: POST\n              name: start-investigation\n              description: \"Start a live endpoint investigation connection\"\n              call: \"tanium-threat-response.create-connection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-connections\n          name: data-connections\n          description: \"Data export connections to downstream systems\"\n          operations:\n            - method: GET\n              name: list-data-connections\n              description: \"List data delivery connections\"\n              call: \"tanium-connect.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-data-connection\n              description: \"Create a data delivery connection\"\n              call: \"tanium-connect.create-connection\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tanium-endpoint-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted endpoint management, threat investigation, and security operations.\"\n      tools:\n        - name: ask-endpoint-question\n          description: \"Ask a natural language question to all Tanium-managed endpoints (e.g., 'Get Running Processes from all machines')\"\n          hints:\n            readOnly: true\n            idempotent: false\n            openWorld: true\n          call: \"tanium-platform.create-question\"\n          with:\n            query_text: \"tools.query_text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-question-results\n          description: \"Get endpoint data results for a question by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld:\
  \ true\n          call: \"tanium-platform.get-question-results\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-saved-questions\n          description: \"List all saved questions configured for recurring endpoint data collection\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-platform.list-saved-questions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-saved-question-results\n          description: \"Get the latest collected results from a saved recurring question\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-platform.get-saved-question-results\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: deploy-package-to-endpoints\n          description: \"Deploy a package action to a targeted group of endpoints\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tanium-platform.create-action\"\n          with:\n            name: \"tools.name\"\n            package_spec: \"tools.package_spec\"\n            action_group: \"tools.action_group\"\n            target_group: \"tools.target_group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-packages\n          description: \"List all available deployment packages on the Tanium server\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-platform.list-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sensors\n\
  \          description: \"List all endpoint sensors available for data collection in questions\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-platform.list-sensors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-computer-groups\n          description: \"List all computer groups for endpoint targeting in actions and questions\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-platform.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-threat-alerts\n          description: \"List threat alerts detected by Tanium Threat Response\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-threat-response.list-alerts\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-endpoint-investigation\n          description: \"Start a live investigation connection to an endpoint for incident response\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tanium-threat-response.create-connection\"\n          with:\n            target: \"tools.target\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-endpoint-events\n          description: \"Get Recorder events from an endpoint connection (process, network, file events)\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-threat-response.list-events\"\n          with:\n            cid: \"tools.cid\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-process-tree\n          description: \"Get the full process ancestry tree for a suspicious process on an endpoint\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-threat-response.get-process-tree\"\n          with:\n            cid: \"tools.cid\"\n            pid: \"tools.pid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-connections\n          description: \"List all data delivery connections for exporting endpoint data to SIEM and other systems\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tanium-connect.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-connection\n          description: \"Create a data delivery connection\
  \ to export Tanium endpoint data to a downstream system\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tanium-connect.create-connection\"\n          with:\n            name: \"tools.name\"\n            source: \"tools.source\"\n            destination: \"tools.destination\"\n            schedule: \"tools.schedule\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tanium/refs/heads/main/capabilities/endpoint-management.yaml
tags:
- Compliance
- Endpoint Management
- Incident Response
- Patch Management
- Security
- Threat Detection
- Unified Endpoint Management
tools:
- description: Ask a natural language question to all Tanium-managed endpoints (e.g., 'Get Running Processes from all machines')
  hints:
    idempotent: false
    openWorld: true
    readOnly: true
  name: ask-endpoint-question
- description: Get endpoint data results for a question by ID
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-question-results
- description: List all saved questions configured for recurring endpoint data collection
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-saved-questions
- description: Get the latest collected results from a saved recurring question
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-saved-question-results
- description: Deploy a package action to a targeted group of endpoints
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-package-to-endpoints
- description: List all available deployment packages on the Tanium server
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-packages
- description: List all endpoint sensors available for data collection in questions
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-sensors
- description: List all computer groups for endpoint targeting in actions and questions
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-computer-groups
- description: List threat alerts detected by Tanium Threat Response
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-threat-alerts
- description: Start a live investigation connection to an endpoint for incident response
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-endpoint-investigation
- description: Get Recorder events from an endpoint connection (process, network, file events)
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-endpoint-events
- description: Get the full process ancestry tree for a suspicious process on an endpoint
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-process-tree
- description: List all data delivery connections for exporting endpoint data to SIEM and other systems
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-data-connections
- description: Create a data delivery connection to export Tanium endpoint data to a downstream system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-data-connection
---
