---
categories: []
consumed_apis: []
description: Qualcomm provides developer APIs and SDKs for mobile computing, 5G connectivity, AI inference, and IoT. The platform supports developers building applications for Snapdragon-powered devices.
layout: capability
name: Qualcomm Developer API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: qualcomm
provider_slug: qualcomm
search_terms:
- get api status
- qualcomm
- getstatus
- api
slug: qualcomm-capability
source_filename: qualcomm-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Qualcomm Developer API\n  description: Qualcomm provides developer APIs and SDKs for mobile computing, 5G connectivity, AI inference, and IoT. The\n    platform supports developers building applications for Snapdragon-powered devices.\n  tags:\n  - Qualcomm\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: qualcomm\n    baseUri: https://developer.qualcomm.com/api\n    description: Qualcomm Developer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{QUALCOMM_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: qualcomm-rest\n    description: REST adapter\
  \ for Qualcomm Developer API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: qualcomm.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: qualcomm-mcp\n    transport: http\n    description: MCP adapter for Qualcomm Developer API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qualcomm.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QUALCOMM_TOKEN: QUALCOMM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/qualcomm/refs/heads/main/capabilities/qualcomm-capability.yaml
tags:
- Qualcomm
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
