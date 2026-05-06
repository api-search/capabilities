---
categories: []
consumed_apis: []
description: The Home Depot API provides access to product catalog data, inventory availability, store locations, and pricing information for partners and affiliates integrating with Home Depot's retail platform.
layout: capability
name: Home Depot API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: home-depot
provider_slug: home-depot
search_terms:
- get api status
- getstatus
- api
- home
- depot
slug: home-depot-capability
source_filename: home-depot-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Home Depot API\n  description: The Home Depot API provides access to product catalog data, inventory availability, store locations, and pricing\n    information for partners and affiliates integrating with Home Depot's retail platform.\n  tags:\n  - Home\n  - Depot\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: home-depot\n    baseUri: https://api.homedepot.com\n    description: Home Depot API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HOME_DEPOT_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: home-depot-rest\n    description: REST adapter\
  \ for Home Depot API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: home-depot.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: home-depot-mcp\n    transport: http\n    description: MCP adapter for Home Depot API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: home-depot.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HOME_DEPOT_TOKEN: HOME_DEPOT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/home-depot/refs/heads/main/capabilities/home-depot-capability.yaml
tags:
- Home
- Depot
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
