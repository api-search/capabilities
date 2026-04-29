---
categories: []
consumed_apis:
- call-control
- reporting
- administration
- vxml-services
description: Unified workflow for contact center operations combining call control, reporting, administration, and VXML services. Used by contact center administrators and operations teams for monitoring, managing, and optimizing voice self-service applications.
layout: capability
name: Cisco Voice Portal Contact Center Operations
operations:
- description: List active calls
  method: GET
  name: list-active-calls
  path: /v1/calls
- description: Get call details
  method: GET
  name: get-call
  path: /v1/calls/{callGuid}
- description: List call detail records
  method: GET
  name: list-cdrs
  path: /v1/cdrs
- description: Get real-time call statistics
  method: GET
  name: get-statistics
  path: /v1/statistics
- description: List managed devices
  method: GET
  name: list-devices
  path: /v1/devices
- description: List deployed applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List active VXML sessions
  method: GET
  name: list-sessions
  path: /v1/sessions
- description: Get call server health
  method: GET
  name: get-health
  path: /v1/health
personas: []
provider_name: Cisco Voice Portal
provider_slug: cisco-voice-portal
search_terms:
- ivr
- application management
- real-time statistics
- call detail records
- get health
- list deployed applications
- voice portal
- list active calls
- system health
- list deployed cvp applications
- list applications
- telephony
- list managed cvp devices
- list all active calls on the cvp call server
- list devices
- active call management
- get statistics
- vxml session monitoring
- list deployed vxml applications
- list managed devices
- list vxml applications
- list cdrs
- list dialed number patterns
- list call detail records
- list active sessions
- get call
- voice
- get call server health
- list configured dialed number patterns
- vxml
- get details of a specific active call
- get real-time call statistics
- list sessions
- list active vxml sessions
- check cvp call server health status
- list call detail records from the reporting server
- individual call details
- cisco
- device management
- contact center
- get call details
slug: contact-center-operations
source_filename: contact-center-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cisco Voice Portal Contact Center Operations\"\n  description: \"Unified workflow for contact center operations combining call control, reporting, administration, and VXML services. Used by contact center administrators and operations teams for monitoring, managing, and optimizing voice self-service applications.\"\n  tags:\n    - Cisco\n    - Contact Center\n    - Voice Portal\n    - IVR\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      CVP_USERNAME: CVP_USERNAME\n      CVP_PASSWORD: CVP_PASSWORD\n      CVP_ADMIN_USERNAME: CVP_ADMIN_USERNAME\n      CVP_ADMIN_PASSWORD: CVP_ADMIN_PASSWORD\n\ncapability:\n  consumes:\n    - import: call-control\n      location: ./shared/call-control.yaml\n    - import: reporting\n      location: ./shared/reporting.yaml\n    - import: administration\n      location: ./shared/administration.yaml\n    - import: vxml-services\n      location: ./shared/vxml-services.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: contact-center-api\n      description: \"Unified REST API for Cisco Voice Portal contact center operations.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n          description: \"Active call management\"\n          operations:\n            - method: GET\n              name: list-active-calls\n              description: \"List active calls\"\n              call: \"call-control.list-active-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calls/{callGuid}\n          name: call\n          description: \"Individual call details\"\n          operations:\n            - method: GET\n              name: get-call\n              description: \"Get call details\"\n              call: \"call-control.get-call\"\n              with:\n                callGuid: \"rest.callGuid\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/cdrs\n          name: cdrs\n          description: \"Call detail records\"\n          operations:\n            - method: GET\n              name: list-cdrs\n              description: \"List call detail records\"\n              call: \"reporting.list-cdrs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/statistics\n          name: statistics\n          description: \"Real-time statistics\"\n          operations:\n            - method: GET\n              name: get-statistics\n              description: \"Get real-time call statistics\"\n              call: \"reporting.get-statistics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices\n          name: devices\n          description: \"Device management\"\n          operations:\n            - method: GET\n              name:\
  \ list-devices\n              description: \"List managed devices\"\n              call: \"administration.list-devices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"Application management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List deployed applications\"\n              call: \"administration.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sessions\n          name: sessions\n          description: \"VXML session monitoring\"\n          operations:\n            - method: GET\n              name: list-sessions\n              description: \"List active VXML sessions\"\n              call: \"vxml-services.list-active-sessions\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"System health\"\n          operations:\n            - method: GET\n              name: get-health\n              description: \"Get call server health\"\n              call: \"call-control.get-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: contact-center-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cisco Voice Portal contact center operations.\"\n      tools:\n        - name: list-active-calls\n          description: \"List all active calls on the CVP Call Server\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"call-control.list-active-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-call\n     \
  \     description: \"Get details of a specific active call\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"call-control.get-call\"\n          with:\n            callGuid: \"tools.callGuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-call-server-health\n          description: \"Check CVP Call Server health status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"call-control.get-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cdrs\n          description: \"List call detail records from the Reporting Server\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"reporting.list-cdrs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-statistics\n          description:\
  \ \"Get real-time call statistics\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"reporting.get-statistics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-devices\n          description: \"List managed CVP devices\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"administration.list-devices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applications\n          description: \"List deployed CVP applications\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"administration.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dialed-number-patterns\n          description: \"List configured dialed number patterns\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"administration.list-dialed-number-patterns\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vxml-applications\n          description: \"List deployed VXML applications\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vxml-services.list-vxml-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-active-sessions\n          description: \"List active VXML sessions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vxml-services.list-active-sessions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cisco-voice-portal/refs/heads/main/capabilities/contact-center-operations.yaml
tags:
- Cisco
- Contact Center
- Voice Portal
- IVR
tools:
- description: List all active calls on the CVP Call Server
  hints:
    idempotent: true
    readOnly: true
  name: list-active-calls
- description: Get details of a specific active call
  hints:
    idempotent: true
    readOnly: true
  name: get-call
- description: Check CVP Call Server health status
  hints:
    idempotent: true
    readOnly: true
  name: get-call-server-health
- description: List call detail records from the Reporting Server
  hints:
    idempotent: true
    readOnly: true
  name: list-cdrs
- description: Get real-time call statistics
  hints:
    idempotent: true
    readOnly: true
  name: get-statistics
- description: List managed CVP devices
  hints:
    idempotent: true
    readOnly: true
  name: list-devices
- description: List deployed CVP applications
  hints:
    idempotent: true
    readOnly: true
  name: list-applications
- description: List configured dialed number patterns
  hints:
    idempotent: true
    readOnly: true
  name: list-dialed-number-patterns
- description: List deployed VXML applications
  hints:
    idempotent: true
    readOnly: true
  name: list-vxml-applications
- description: List active VXML sessions
  hints:
    idempotent: true
    readOnly: true
  name: list-active-sessions
---
