---
categories: []
consumed_apis: []
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
- check cvp call server health status
- real-time statistics
- contact center
- get real-time call statistics
- individual call details
- vxml session monitoring
- list active vxml sessions
- list active calls
- voice portal
- list configured dialed number patterns
- list deployed vxml applications
- device management
- system health
- list deployed applications
- list devices
- cisco
- voice
- get call details
- list cdrs
- list managed devices
- list sessions
- list active sessions
- telephony
- ivr
- list dialed number patterns
- get call server health
- list deployed cvp applications
- get details of a specific active call
- list call detail records
- vxml
- list vxml applications
- list call detail records from the reporting server
- active call management
- list managed cvp devices
- get call
- get statistics
- list applications
- call detail records
- list all active calls on the cvp call server
- get health
- application management
slug: contact-center-operations
source_filename: contact-center-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cisco Voice Portal Contact Center Operations\n  description: Unified workflow for contact center operations combining call control, reporting, administration, and VXML\n    services. Used by contact center administrators and operations teams for monitoring, managing, and optimizing voice self-service\n    applications.\n  tags:\n  - Cisco\n  - Contact Center\n  - Voice Portal\n  - IVR\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CVP_USERNAME: CVP_USERNAME\n    CVP_PASSWORD: CVP_PASSWORD\n    CVP_ADMIN_USERNAME: CVP_ADMIN_USERNAME\n    CVP_ADMIN_PASSWORD: CVP_ADMIN_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: call-control\n    baseUri: https://cvp-callserver.example.com:8000/cvp/rest\n    description: CVP Call Server REST API\n    authentication:\n      type: basic\n      username: '{{CVP_USERNAME}}'\n      password: '{{CVP_PASSWORD}}'\n    resources:\n    - name: calls\n\
  \      path: /call\n      description: Active call management\n      operations:\n      - name: list-active-calls\n        method: GET\n        description: List all active calls\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by call state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: call\n      path: /call/{callGuid}\n      description: Individual call operations\n      operations:\n      - name: get-call\n        method: GET\n        description: Get call details\n        inputParameters:\n        - name: callGuid\n          in: path\n          type: string\n          required: true\n          description: Call GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n    \
  \  description: Call server health\n      operations:\n      - name: get-health\n        method: GET\n        description: Get call server health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: reporting\n    baseUri: https://cvp-reporting.example.com:8111/cvp-reporting/rest\n    description: CVP Reporting Server REST API\n    authentication:\n      type: basic\n      username: '{{CVP_USERNAME}}'\n      password: '{{CVP_PASSWORD}}'\n    resources:\n    - name: cdrs\n      path: /cdr\n      description: Call detail records\n      operations:\n      - name: list-cdrs\n        method: GET\n        description: List call detail records\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start time filter\n        - name: endTime\n          in: query\n          type: string\n   \
  \       required: false\n          description: End time filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: statistics\n      path: /statistics\n      description: Real-time call statistics\n      operations:\n      - name: get-statistics\n        method: GET\n        description: Get real-time call statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: administration\n    baseUri: https://cvp-oamp.example.com:9443/oamp/rest\n    description: CVP OAMP REST API\n    authentication:\n      type: basic\n      username: '{{CVP_ADMIN_USERNAME}}'\n      password: '{{CVP_ADMIN_PASSWORD}}'\n    resources:\n    - name: devices\n      path: /device\n      description: Device management\n      operations:\n      - name: list-devices\n        method: GET\n        description: List managed devices\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /application\n      description: Application management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List deployed applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dialed-number-patterns\n      path: /dialedNumberPattern\n      description: Dialed number pattern management\n      operations:\n      - name: list-dialed-number-patterns\n        method: GET\n        description: List dialed number patterns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: vxml-services\n    baseUri: https://cvp-vxmlserver.example.com:7443/CVP/rest\n    description: CVP VXML Server REST\
  \ API\n    authentication:\n      type: basic\n      username: '{{CVP_USERNAME}}'\n      password: '{{CVP_PASSWORD}}'\n    resources:\n    - name: applications\n      path: /application\n      description: VXML application management\n      operations:\n      - name: list-vxml-applications\n        method: GET\n        description: List VXML applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /session\n      description: Active session monitoring\n      operations:\n      - name: list-active-sessions\n        method: GET\n        description: List active VXML sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: contact-center-api\n    description: Unified REST API for Cisco Voice Portal contact center operations.\n    resources:\n\
  \    - path: /v1/calls\n      name: calls\n      description: Active call management\n      operations:\n      - method: GET\n        name: list-active-calls\n        description: List active calls\n        call: call-control.list-active-calls\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calls/{callGuid}\n      name: call\n      description: Individual call details\n      operations:\n      - method: GET\n        name: get-call\n        description: Get call details\n        call: call-control.get-call\n        with:\n          callGuid: rest.callGuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cdrs\n      name: cdrs\n      description: Call detail records\n      operations:\n      - method: GET\n        name: list-cdrs\n        description: List call detail records\n        call: reporting.list-cdrs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/statistics\n\
  \      name: statistics\n      description: Real-time statistics\n      operations:\n      - method: GET\n        name: get-statistics\n        description: Get real-time call statistics\n        call: reporting.get-statistics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices\n      name: devices\n      description: Device management\n      operations:\n      - method: GET\n        name: list-devices\n        description: List managed devices\n        call: administration.list-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Application management\n      operations:\n      - method: GET\n        name: list-applications\n        description: List deployed applications\n        call: administration.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sessions\n      name: sessions\n\
  \      description: VXML session monitoring\n      operations:\n      - method: GET\n        name: list-sessions\n        description: List active VXML sessions\n        call: vxml-services.list-active-sessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: System health\n      operations:\n      - method: GET\n        name: get-health\n        description: Get call server health\n        call: call-control.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: contact-center-mcp\n    transport: http\n    description: MCP server for AI-assisted Cisco Voice Portal contact center operations.\n    tools:\n    - name: list-active-calls\n      description: List all active calls on the CVP Call Server\n      hints:\n        readOnly: true\n        idempotent: true\n      call: call-control.list-active-calls\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-call\n      description: Get details of a specific active call\n      hints:\n        readOnly: true\n        idempotent: true\n      call: call-control.get-call\n      with:\n        callGuid: tools.callGuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-call-server-health\n      description: Check CVP Call Server health status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: call-control.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cdrs\n      description: List call detail records from the Reporting Server\n      hints:\n        readOnly: true\n        idempotent: true\n      call: reporting.list-cdrs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-statistics\n      description: Get real-time call statistics\n      hints:\n        readOnly: true\n        idempotent: true\n\
  \      call: reporting.get-statistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-devices\n      description: List managed CVP devices\n      hints:\n        readOnly: true\n        idempotent: true\n      call: administration.list-devices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List deployed CVP applications\n      hints:\n        readOnly: true\n        idempotent: true\n      call: administration.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dialed-number-patterns\n      description: List configured dialed number patterns\n      hints:\n        readOnly: true\n        idempotent: true\n      call: administration.list-dialed-number-patterns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vxml-applications\n      description: List deployed VXML applications\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: vxml-services.list-vxml-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-active-sessions\n      description: List active VXML sessions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vxml-services.list-active-sessions\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
