---
categories: []
consumed_apis: []
description: The Neighbor API allows trusted hosts to retrieve account-related reports including reservations and payout transfers.
layout: capability
name: Neighbor API
operations:
- description: Get reservation report
  method: GET
  name: getreservationreport
  path: /public/reports/reservation
- description: Get transfer/payout report
  method: GET
  name: gettransferreport
  path: /public/reports/transfer
personas: []
provider_name: Neighbor
provider_slug: neighbor
search_terms:
- getreservationreport
- marketplace
- reporting
- get reservation report
- api
- neighbor
- storage
- gettransferreport
- get transfer/payout report
slug: neighbor-capability
source_filename: neighbor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Neighbor API\n  description: The Neighbor API allows trusted hosts to retrieve account-related reports including reservations and payout\n    transfers.\n  tags:\n  - Neighbor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: neighbor\n    baseUri: https://api.neighbor.com\n    description: Neighbor API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{NEIGHBOR_TOKEN}}'\n    resources:\n    - name: public-reports-reservation\n      path: /public/reports/reservation\n      operations:\n      - name: getreservationreport\n        method: GET\n        description: Get reservation report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-reports-transfer\n      path: /public/reports/transfer\n      operations:\n    \
  \  - name: gettransferreport\n        method: GET\n        description: Get transfer/payout report\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n        - name: month\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: neighbor-rest\n    description: REST adapter for Neighbor API.\n    resources:\n    - path: /public/reports/reservation\n      name: getreservationreport\n      operations:\n      - method: GET\n        name: getreservationreport\n        description: Get reservation report\n        call: neighbor.getreservationreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/reports/transfer\n      name: gettransferreport\n      operations:\n      - method: GET\n        name: gettransferreport\n        description:\
  \ Get transfer/payout report\n        call: neighbor.gettransferreport\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: neighbor-mcp\n    transport: http\n    description: MCP adapter for Neighbor API for AI agent use.\n    tools:\n    - name: getreservationreport\n      description: Get reservation report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbor.getreservationreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransferreport\n      description: Get transfer/payout report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbor.gettransferreport\n      with:\n        year: tools.year\n        month: tools.month\n      inputParameters:\n      - name: year\n        type: integer\n        description: year\n      - name: month\n        type: integer\n\
  \        description: month\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NEIGHBOR_TOKEN: NEIGHBOR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/neighbor/refs/heads/main/capabilities/neighbor-capability.yaml
tags:
- Neighbor
- API
tools:
- description: Get reservation report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreservationreport
- description: Get transfer/payout report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransferreport
---
