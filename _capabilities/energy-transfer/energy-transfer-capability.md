---
categories: []
consumed_apis: []
description: The Energy Transfer Messenger+ API provides programmatic access to Energy Transfer's pipeline messaging and gas scheduling platform. The API enables partners and shippers to manage gas nominations, scheduling, and pipeline capacity through automated integrations, reducing processing times from 90 minutes to approximately 12 minutes.
layout: capability
name: Energy Transfer Messenger+ API
operations:
- description: List nominations
  method: GET
  name: listnominations
  path: /nominations
- description: Create a nomination
  method: POST
  name: createnomination
  path: /nominations
- description: List schedules
  method: GET
  name: listschedules
  path: /schedules
- description: List pipelines
  method: GET
  name: listpipelines
  path: /pipelines
personas: []
provider_name: Energy Transfer
provider_slug: energy-transfer
search_terms:
- list nominations
- listpipelines
- list pipelines
- midstream
- list schedules
- createnomination
- energy
- create a nomination
- gas scheduling
- listnominations
- pipelines
- api
- listschedules
- transfer
slug: energy-transfer-capability
source_filename: energy-transfer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Energy Transfer Messenger+ API\n  description: The Energy Transfer Messenger+ API provides programmatic access to Energy Transfer's pipeline messaging and\n    gas scheduling platform. The API enables partners and shippers to manage gas nominations, scheduling, and pipeline capacity\n    through automated integrations, reducing processing times from 90 minutes to approximately 12 minutes.\n  tags:\n  - Energy\n  - Transfer\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: energy-transfer\n    baseUri: https://dev.messenger.energytransfer.com\n    description: Energy Transfer Messenger+ API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ENERGY_TRANSFER_TOKEN}}'\n    resources:\n    - name: nominations\n      path: /nominations\n      operations:\n      - name: listnominations\n        method: GET\n        description: List nominations\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnomination\n        method: POST\n        description: Create a nomination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      operations:\n      - name: listschedules\n        method: GET\n        description: List schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines\n      path: /pipelines\n      operations:\n      - name: listpipelines\n        method: GET\n        description: List pipelines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: energy-transfer-rest\n    description: REST adapter for\
  \ Energy Transfer Messenger+ API.\n    resources:\n    - path: /nominations\n      name: listnominations\n      operations:\n      - method: GET\n        name: listnominations\n        description: List nominations\n        call: energy-transfer.listnominations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nominations\n      name: createnomination\n      operations:\n      - method: POST\n        name: createnomination\n        description: Create a nomination\n        call: energy-transfer.createnomination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: listschedules\n      operations:\n      - method: GET\n        name: listschedules\n        description: List schedules\n        call: energy-transfer.listschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines\n      name: listpipelines\n      operations:\n      - method: GET\n  \
  \      name: listpipelines\n        description: List pipelines\n        call: energy-transfer.listpipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: energy-transfer-mcp\n    transport: http\n    description: MCP adapter for Energy Transfer Messenger+ API for AI agent use.\n    tools:\n    - name: listnominations\n      description: List nominations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-transfer.listnominations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnomination\n      description: Create a nomination\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: energy-transfer.createnomination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedules\n      description: List schedules\n      hints:\n       \
  \ readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-transfer.listschedules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelines\n      description: List pipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-transfer.listpipelines\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ENERGY_TRANSFER_TOKEN: ENERGY_TRANSFER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/energy-transfer/refs/heads/main/capabilities/energy-transfer-capability.yaml
tags:
- Energy
- Transfer
- API
tools:
- description: List nominations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnominations
- description: Create a nomination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnomination
- description: List schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedules
- description: List pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelines
---
