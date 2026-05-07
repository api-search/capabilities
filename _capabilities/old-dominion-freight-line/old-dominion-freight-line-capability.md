---
categories: []
consumed_apis: []
description: The Old Dominion Freight Line Bill of Lading API submits electronic bills of lading to the ODFL billing system. The service generates shipping labels and BOL documents that can be printed and applied to freight, enabling shippers to programmatically create freight documentation as part of their shipping workflow.
layout: capability
name: ODFL Bill of Lading API
operations:
- description: Create an electronic bill of lading
  method: POST
  name: createbilloflading
  path: /createBOL
personas: []
provider_name: Old Dominion Freight Line
provider_slug: old-dominion-freight-line
search_terms:
- logistics
- freight
- transportation
- create an electronic bill of lading
- old
- createbilloflading
- shipping
- api
- line
- less-than-truckload
- dominion
slug: old-dominion-freight-line-capability
source_filename: old-dominion-freight-line-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ODFL Bill of Lading API\n  description: The Old Dominion Freight Line Bill of Lading API submits electronic bills of lading to the ODFL billing system.\n    The service generates shipping labels and BOL documents that can be printed and applied to freight, enabling shippers\n    to programmatically create freight documentation as part of their shipping workflow.\n  tags:\n  - Old\n  - Dominion\n  - Freight\n  - Line\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: old-dominion-freight-line\n    baseUri: https://www.odfl.com/wsBOL/v3\n    description: ODFL Bill of Lading API HTTP API.\n    authentication:\n      type: basic\n      username: '{{OLD_DOMINION_FREIGHT_LINE_USERNAME}}'\n      password: '{{OLD_DOMINION_FREIGHT_LINE_PASSWORD}}'\n    resources:\n    - name: createbol\n      path: /createBOL\n      operations:\n      - name: createbilloflading\n        method:\
  \ POST\n        description: Create an electronic bill of lading\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: old-dominion-freight-line-rest\n    description: REST adapter for ODFL Bill of Lading API.\n    resources:\n    - path: /createBOL\n      name: createbilloflading\n      operations:\n      - method: POST\n        name: createbilloflading\n        description: Create an electronic bill of lading\n        call: old-dominion-freight-line.createbilloflading\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: old-dominion-freight-line-mcp\n    transport: http\n    description: MCP adapter for ODFL Bill of Lading API for AI agent use.\n    tools:\n    - name: createbilloflading\n      description: Create an electronic bill of lading\n      hints:\n        readOnly: false\n   \
  \     destructive: false\n        idempotent: false\n      call: old-dominion-freight-line.createbilloflading\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OLD_DOMINION_FREIGHT_LINE_USERNAME: OLD_DOMINION_FREIGHT_LINE_USERNAME\n    OLD_DOMINION_FREIGHT_LINE_PASSWORD: OLD_DOMINION_FREIGHT_LINE_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/old-dominion-freight-line/refs/heads/main/capabilities/old-dominion-freight-line-capability.yaml
tags:
- Old
- Dominion
- Freight
- Line
- API
tools:
- description: Create an electronic bill of lading
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbilloflading
---
