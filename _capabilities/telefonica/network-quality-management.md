---
categories: []
consumed_apis: []
description: Network quality management capability combining Telefónica's Quality on Demand and Device Roaming Status APIs. Enables application developers, IoT platform providers, and telecom integrators to guarantee network quality for specific device sessions and verify roaming status for compliance and geo-restriction workflows.
layout: capability
name: Telefónica Network Quality Management
operations:
- description: Create a QoD session for guaranteed network quality.
  method: POST
  name: create-qod-session
  path: /v1/qod/sessions
- description: List active QoD sessions.
  method: GET
  name: list-qod-sessions
  path: /v1/qod/sessions
- description: Get QoD session details.
  method: GET
  name: get-qod-session
  path: /v1/qod/sessions/{sessionId}
- description: Terminate a QoD session.
  method: DELETE
  name: delete-qod-session
  path: /v1/qod/sessions/{sessionId}
personas: []
provider_name: Telefónica
provider_slug: telefonica
search_terms:
- roaming
- get qod session details.
- delete qod session
- list qod sessions
- mobile network
- network management
- terminate an active quality on demand session.
- quality on demand sessions.
- authentication
- location services
- list active qod sessions.
- telecommunications
- create a qod session for guaranteed network quality.
- camara
- get status and details for a specific quality on demand session.
- fraud prevention
- iot
- get qod session
- open gateway
- telefónica
- create qod session
- quality of service
- list all active quality on demand sessions.
- a specific qod session.
- terminate a qod session.
- create a quality on demand session to guarantee network bandwidth and latency for a device.
slug: network-quality-management
source_filename: network-quality-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telefónica Network Quality Management\n  description: Network quality management capability combining Telefónica's Quality on Demand and Device Roaming Status APIs.\n    Enables application developers, IoT platform providers, and telecom integrators to guarantee network quality for specific\n    device sessions and verify roaming status for compliance and geo-restriction workflows.\n  tags:\n  - Telefónica\n  - Quality of Service\n  - Network Management\n  - IoT\n  - Roaming\n  - Mobile Network\n  - CAMARA\n  - Open Gateway\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEFONICA_ACCESS_TOKEN: TELEFONICA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: telefonica-qod\n    baseUri: https://opengateway.telefonica.com/v1\n    description: Telefónica Quality on Demand API via Open Gateway.\n    authentication:\n      type: bearer\n      token: '{{TELEFONICA_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: qod-sessions\n      path: /qod/sessions\n      description: Quality on Demand sessions.\n      operations:\n      - name: create-qod-session\n        method: POST\n        description: Create a QoD session for a device.\n        body:\n          type: json\n          data:\n            device: '{{tools.device}}'\n            qosProfile: '{{tools.qosProfile}}'\n            duration: '{{tools.duration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-qod-sessions\n        method: GET\n        description: List active QoD sessions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-qod-session\n        method: GET\n        description: Get details for a specific QoD session.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n\
  \          required: true\n          description: Session UUID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-qod-session\n        method: DELETE\n        description: Terminate a QoD session.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session UUID to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: telefonica-network-api\n    description: Unified REST API for Telefónica network quality management.\n    resources:\n    - path: /v1/qod/sessions\n      name: qod-sessions\n      description: Quality on Demand sessions.\n      operations:\n      - method: POST\n        name: create-qod-session\n        description: Create a QoD session for guaranteed\
  \ network quality.\n        call: telefonica-qod.create-qod-session\n        with:\n          device: rest.device\n          qosProfile: rest.qosProfile\n          duration: rest.duration\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-qod-sessions\n        description: List active QoD sessions.\n        call: telefonica-qod.list-qod-sessions\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/qod/sessions/{sessionId}\n      name: qod-session\n      description: A specific QoD session.\n      operations:\n      - method: GET\n        name: get-qod-session\n        description: Get QoD session details.\n        call: telefonica-qod.get-qod-session\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-qod-session\n        description: Terminate a QoD session.\n       \
  \ call: telefonica-qod.delete-qod-session\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: telefonica-network-mcp\n    transport: http\n    description: MCP server for AI-assisted Telefónica network quality management.\n    tools:\n    - name: create-qod-session\n      description: Create a Quality on Demand session to guarantee network bandwidth and latency for a device.\n      hints:\n        readOnly: false\n      call: telefonica-qod.create-qod-session\n      with:\n        device: tools.device\n        qosProfile: tools.qosProfile\n        duration: tools.duration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-qod-sessions\n      description: List all active Quality on Demand sessions.\n      hints:\n        readOnly: true\n      call: telefonica-qod.list-qod-sessions\n      outputParameters:\n      - type: array\n     \
  \   mapping: $.\n    - name: get-qod-session\n      description: Get status and details for a specific Quality on Demand session.\n      hints:\n        readOnly: true\n      call: telefonica-qod.get-qod-session\n      with:\n        sessionId: tools.sessionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-qod-session\n      description: Terminate an active Quality on Demand session.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: telefonica-qod.delete-qod-session\n      with:\n        sessionId: tools.sessionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telefonica/refs/heads/main/capabilities/network-quality-management.yaml
tags:
- Telefónica
- Quality of Service
- Network Management
- IoT
- Roaming
- Mobile Network
- CAMARA
- Open Gateway
tools:
- description: Create a Quality on Demand session to guarantee network bandwidth and latency for a device.
  hints:
    readOnly: false
  name: create-qod-session
- description: List all active Quality on Demand sessions.
  hints:
    readOnly: true
  name: list-qod-sessions
- description: Get status and details for a specific Quality on Demand session.
  hints:
    readOnly: true
  name: get-qod-session
- description: Terminate an active Quality on Demand session.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-qod-session
---
