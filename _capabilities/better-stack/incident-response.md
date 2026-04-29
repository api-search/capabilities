---
categories:
- incident-management
consumed_apis:
- better-stack
description: Unified incident response workflow combining Better Stack uptime monitoring, heartbeat monitoring, and incident management. Used by SRE teams and on-call engineers to detect, acknowledge, and resolve infrastructure incidents.
layout: capability
name: Better Stack Incident Response
operations:
- description: List all uptime monitors
  method: GET
  name: list-monitors
  path: /v1/monitors
- description: Create a new uptime monitor
  method: POST
  name: create-monitor
  path: /v1/monitors
- description: Get monitor details
  method: GET
  name: get-monitor
  path: /v1/monitors/{id}
- description: Update a monitor
  method: PATCH
  name: update-monitor
  path: /v1/monitors/{id}
- description: Delete a monitor
  method: DELETE
  name: delete-monitor
  path: /v1/monitors/{id}
- description: Get monitor availability summary
  method: GET
  name: get-monitor-availability
  path: /v1/monitors/{id}/availability
- description: List all heartbeats
  method: GET
  name: list-heartbeats
  path: /v1/heartbeats
- description: Create a heartbeat monitor
  method: POST
  name: create-heartbeat
  path: /v1/heartbeats
- description: List all incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Create a manual incident
  method: POST
  name: create-incident
  path: /v1/incidents
- description: Get incident details
  method: GET
  name: get-incident
  path: /v1/incidents/{id}
- description: Delete an incident
  method: DELETE
  name: delete-incident
  path: /v1/incidents/{id}
- description: Acknowledge an active incident
  method: POST
  name: acknowledge-incident
  path: /v1/incidents/{id}/acknowledge
- description: Resolve an active incident
  method: POST
  name: resolve-incident
  path: /v1/incidents/{id}/resolve
personas:
- description: Site Reliability Engineer managing infrastructure uptime and incident response
  id: sre-engineer
  name: SRE Engineer
- description: Engineer on-call rotation responsible for responding to incidents
  id: on-call-engineer
  name: On-Call Engineer
provider_name: Better Stack
provider_slug: better-stack
search_terms:
- logs
- monitoring
- engineer on-call rotation responsible for responding to incidents
- list all heartbeats
- list all heartbeat monitors for scheduled jobs
- list incidents with optional date and filter parameters
- monitor management for uptime checks
- get monitor details
- list all incidents
- single incident operations
- single monitor operations
- delete a monitor
- incident response
- update a monitor
- delete incident
- create monitor
- resolve an incident
- get availability metrics for a monitor
- sre
- get incident
- create a heartbeat monitor
- list heartbeats
- delete an incident
- create heartbeat
- get monitor availability summary
- incident management
- acknowledge an active incident to indicate someone is working on it
- site reliability engineer managing infrastructure uptime and incident response
- uptime and availability monitoring for services and scheduled jobs
- sre engineer
- acknowledge incident
- acknowledge an incident
- resolve incident
- get details for a specific incident
- uptime
- create a manual incident
- incidents
- update monitor
- observability
- monitor detection, incident acknowledgement, and resolution workflow for sre teams
- heartbeat monitor management
- create incident
- acknowledge an active incident
- heartbeats
- on-call
- managing team access and membership
- monitor availability metrics
- resolve an active incident once the issue is fixed
- list all uptime monitors
- on call engineer
- create a new uptime monitor for a url or api
- better stack
- list monitors
- list incidents
- status
- get monitor availability
- create a new uptime monitor
- get monitor
- detection, acknowledgement, and resolution of service incidents
- platform
- get details for a specific uptime monitor
- get heartbeat availability
- delete monitor
- get availability for a heartbeat monitor
- get incident details
- communicating service health to customers and stakeholders
- resolve an active incident
- list all uptime monitors to check what is being monitored
slug: incident-response
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Better Stack Incident Response\n  description: >-\n    Unified incident response workflow combining Better Stack uptime monitoring,\n    heartbeat monitoring, and incident management. Used by SRE teams and on-call\n    engineers to detect, acknowledge, and resolve infrastructure incidents.\n  tags:\n    - Better Stack\n    - Incident Response\n    - Monitoring\n    - On-Call\n    - Sre\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BETTER_STACK_API_TOKEN: BETTER_STACK_API_TOKEN\n\ncapability:\n  consumes:\n    - import: better-stack\n      location: ./shared/better-stack.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: better-stack-incident-response-api\n      description: Unified REST API for Better Stack incident response workflows.\n      resources:\n        - path: /v1/monitors\n          name: monitors\n          description: Monitor management for\
  \ uptime checks\n          operations:\n            - method: GET\n              name: list-monitors\n              description: List all uptime monitors\n              call: \"better-stack.list-monitors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-monitor\n              description: Create a new uptime monitor\n              call: \"better-stack.create-monitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors/{id}\n          name: monitor\n          description: Single monitor operations\n          operations:\n            - method: GET\n              name: get-monitor\n              description: Get monitor details\n              call: \"better-stack.get-monitor\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n            - method: PATCH\n              name: update-monitor\n              description: Update a monitor\n              call: \"better-stack.update-monitor\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-monitor\n              description: Delete a monitor\n              call: \"better-stack.delete-monitor\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors/{id}/availability\n          name: monitor-availability\n          description: Monitor availability metrics\n          operations:\n            - method: GET\n              name: get-monitor-availability\n              description: Get monitor availability summary\n              call: \"better-stack.get-monitor-availability\"\
  \n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/heartbeats\n          name: heartbeats\n          description: Heartbeat monitor management\n          operations:\n            - method: GET\n              name: list-heartbeats\n              description: List all heartbeats\n              call: \"better-stack.list-heartbeats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-heartbeat\n              description: Create a heartbeat monitor\n              call: \"better-stack.create-heartbeat\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents\n          name: incidents\n          description: Incident management\n          operations:\n            - method: GET\n             \
  \ name: list-incidents\n              description: List all incidents\n              call: \"better-stack.list-incidents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-incident\n              description: Create a manual incident\n              call: \"better-stack.create-incident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents/{id}\n          name: incident\n          description: Single incident operations\n          operations:\n            - method: GET\n              name: get-incident\n              description: Get incident details\n              call: \"better-stack.get-incident\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-incident\n\
  \              description: Delete an incident\n              call: \"better-stack.delete-incident\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents/{id}/acknowledge\n          name: incident-acknowledge\n          description: Acknowledge an incident\n          operations:\n            - method: POST\n              name: acknowledge-incident\n              description: Acknowledge an active incident\n              call: \"better-stack.acknowledge-incident\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents/{id}/resolve\n          name: incident-resolve\n          description: Resolve an incident\n          operations:\n            - method: POST\n              name: resolve-incident\n              description: Resolve\
  \ an active incident\n              call: \"better-stack.resolve-incident\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: better-stack-incident-response-mcp\n      transport: http\n      description: MCP server for AI-assisted Better Stack incident response.\n      tools:\n        - name: list-monitors\n          description: List all uptime monitors to check what is being monitored\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"better-stack.list-monitors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-monitor\n          description: Create a new uptime monitor for a URL or API\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"better-stack.create-monitor\"\
  \n          with:\n            url: \"tools.url\"\n            pronounceable_name: \"tools.pronounceable_name\"\n            check_frequency: \"tools.check_frequency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-monitor\n          description: Get details for a specific uptime monitor\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"better-stack.get-monitor\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-monitor-availability\n          description: Get availability metrics for a monitor\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"better-stack.get-monitor-availability\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-heartbeats\n          description: List all heartbeat monitors for scheduled jobs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"better-stack.list-heartbeats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-heartbeat-availability\n          description: Get availability for a heartbeat monitor\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"better-stack.get-heartbeat-availability\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-incidents\n          description: List incidents with optional date and filter parameters\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"better-stack.list-incidents\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n\
  \            resolved: \"tools.resolved\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-incident\n          description: Get details for a specific incident\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"better-stack.get-incident\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-incident\n          description: Create a manual incident\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"better-stack.create-incident\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acknowledge-incident\n          description: Acknowledge an active incident to indicate someone is working on it\n         \
  \ hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"better-stack.acknowledge-incident\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resolve-incident\n          description: Resolve an active incident once the issue is fixed\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"better-stack.resolve-incident\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/better-stack/refs/heads/main/capabilities/incident-response.yaml
tags:
- Better Stack
- Incident Response
- Monitoring
- On-Call
- Sre
tools:
- description: List all uptime monitors to check what is being monitored
  hints:
    openWorld: true
    readOnly: true
  name: list-monitors
- description: Create a new uptime monitor for a URL or API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-monitor
- description: Get details for a specific uptime monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-monitor
- description: Get availability metrics for a monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-monitor-availability
- description: List all heartbeat monitors for scheduled jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-heartbeats
- description: Get availability for a heartbeat monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-heartbeat-availability
- description: List incidents with optional date and filter parameters
  hints:
    openWorld: true
    readOnly: true
  name: list-incidents
- description: Get details for a specific incident
  hints:
    openWorld: false
    readOnly: true
  name: get-incident
- description: Create a manual incident
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-incident
- description: Acknowledge an active incident to indicate someone is working on it
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acknowledge-incident
- description: Resolve an active incident once the issue is fixed
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resolve-incident
---
