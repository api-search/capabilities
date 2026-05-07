---
categories: []
consumed_apis: []
description: Public API providing information about mining pools listed on Minerstat, including supported coins, fees, payout thresholds, and pool metadata.
layout: capability
name: Minerstat Mining Pools API
operations:
- description: List mining pools
  method: GET
  name: listpools
  path: /pools
personas: []
provider_name: Minerstat
provider_slug: minerstat
search_terms:
- listpools
- mining
- cryptocurrency
- list mining pools
- minerstat
- mining pools
- api
slug: minerstat-capability
source_filename: minerstat-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Minerstat Mining Pools API\n  description: Public API providing information about mining pools listed on Minerstat, including supported coins, fees, payout\n    thresholds, and pool metadata.\n  tags:\n  - Minerstat\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: minerstat\n    baseUri: https://api.minerstat.com/v2\n    description: Minerstat Mining Pools API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{MINERSTAT_TOKEN}}'\n    resources:\n    - name: pools\n      path: /pools\n      operations:\n      - name: listpools\n        method: GET\n        description: List mining pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: minerstat-rest\n    description: REST adapter\
  \ for Minerstat Mining Pools API.\n    resources:\n    - path: /pools\n      name: listpools\n      operations:\n      - method: GET\n        name: listpools\n        description: List mining pools\n        call: minerstat.listpools\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: minerstat-mcp\n    transport: http\n    description: MCP adapter for Minerstat Mining Pools API for AI agent use.\n    tools:\n    - name: listpools\n      description: List mining pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: minerstat.listpools\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MINERSTAT_TOKEN: MINERSTAT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/minerstat/refs/heads/main/capabilities/minerstat-capability.yaml
tags:
- Minerstat
- API
tools:
- description: List mining pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpools
---
