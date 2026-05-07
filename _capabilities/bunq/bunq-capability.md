---
categories: []
consumed_apis: []
description: Managing activity map for a user account.
layout: capability
name: Bunq Activity Map Place API
operations:
- description: Public endpoint for getting the place info.
  method: GET
  name: read-activitymapplacepublic
  path: /activity-map-place-public/{itemId}
personas: []
provider_name: Bunq
provider_slug: bunq
search_terms:
- banking
- read activitymapplacepublic
- bunq
- api
- public endpoint for getting the place info.
slug: bunq-capability
source_filename: bunq-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bunq Activity Map Place API\n  description: Managing activity map for a user account.\n  tags:\n  - Bunq\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bunq\n    baseUri: https://public-api.sandbox.bunq.com/v1\n    description: Bunq Activity Map Place API HTTP API.\n    resources:\n    - name: activity-map-place-public-itemid\n      path: /activity-map-place-public/{itemId}\n      operations:\n      - name: read-activitymapplacepublic\n        method: GET\n        description: Public endpoint for getting the place info.\n        inputParameters:\n        - name: itemId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bunq-rest\n    description: REST adapter for\
  \ Bunq Activity Map Place API.\n    resources:\n    - path: /activity-map-place-public/{itemId}\n      name: read-activitymapplacepublic\n      operations:\n      - method: GET\n        name: read-activitymapplacepublic\n        description: Public endpoint for getting the place info.\n        call: bunq.read-activitymapplacepublic\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bunq-mcp\n    transport: http\n    description: MCP adapter for Bunq Activity Map Place API for AI agent use.\n    tools:\n    - name: read-activitymapplacepublic\n      description: Public endpoint for getting the place info.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bunq.read-activitymapplacepublic\n      with:\n        itemId: tools.itemId\n      inputParameters:\n      - name: itemId\n        type: integer\n        description:\
  \ itemId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bunq/refs/heads/main/capabilities/bunq-capability.yaml
tags:
- Bunq
- API
tools:
- description: Public endpoint for getting the place info.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: read-activitymapplacepublic
---
