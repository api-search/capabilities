---
categories: []
consumed_apis: []
description: The Plausible Events API allows server-side and non-browser clients to send pageviews and custom events to Plausible.
layout: capability
name: Plausible Events API
operations:
- description: Record a pageview or custom event
  method: POST
  name: recordevent
  path: /api/event
personas: []
provider_name: Plausible
provider_slug: plausible
search_terms:
- analytics
- cookie-free
- privacy
- open source
- gdpr
- recordevent
- web analytics
- plausible
- api
- record a pageview or custom event
slug: plausible-capability
source_filename: plausible-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Plausible Events API\n  description: The Plausible Events API allows server-side and non-browser clients to send pageviews and custom events to\n    Plausible.\n  tags:\n  - Plausible\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: plausible\n    baseUri: https://plausible.io\n    description: Plausible Events API HTTP API.\n    resources:\n    - name: api-event\n      path: /api/event\n      operations:\n      - name: recordevent\n        method: POST\n        description: Record a pageview or custom event\n        inputParameters:\n        - name: User-Agent\n          in: header\n          type: string\n          required: true\n          description: Used to derive the visitor identifier.\n        - name: X-Forwarded-For\n          in: header\n          type: string\n          description: Client IP address; defaults to the sender's remote IP.\n        - name: X-Debug-Request\n\
  \          in: header\n          type: boolean\n          description: When true, returns the IP used for visitor counting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: plausible-rest\n    description: REST adapter for Plausible Events API.\n    resources:\n    - path: /api/event\n      name: recordevent\n      operations:\n      - method: POST\n        name: recordevent\n        description: Record a pageview or custom event\n        call: plausible.recordevent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: plausible-mcp\n    transport: http\n    description: MCP adapter for Plausible Events API for AI agent use.\n    tools:\n    - name: recordevent\n      description: Record a pageview or custom event\n      hints:\n        readOnly: false\n        destructive: false\n  \
  \      idempotent: false\n      call: plausible.recordevent\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/plausible/refs/heads/main/capabilities/plausible-capability.yaml
tags:
- Plausible
- API
tools:
- description: Record a pageview or custom event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recordevent
---
