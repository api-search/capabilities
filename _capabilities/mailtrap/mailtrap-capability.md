---
categories: []
consumed_apis: []
description: The Mailtrap Email Sending API allows sending transactional and bulk emails with high deliverability. It follows REST principles and supports authentication via API tokens, with all requests sent over HTTPS. The API exposes a JSON-based send endpoint and a batch endpoint capable of delivering up to 500 emails in a single request.
layout: capability
name: Mailtrap Email Sending API
operations:
- description: Send a transactional email
  method: POST
  name: sendemail
  path: /api/send
- description: Send batch emails
  method: POST
  name: sendbatchemails
  path: /api/batch
personas: []
provider_name: Mailtrap
provider_slug: mailtrap
search_terms:
- mailtrap
- email
- send a transactional email
- api
- email sandbox
- sendbatchemails
- email testing
- transactional email
- email delivery
- sendemail
- send batch emails
slug: mailtrap-capability
source_filename: mailtrap-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mailtrap Email Sending API\n  description: The Mailtrap Email Sending API allows sending transactional and bulk emails with high deliverability. It follows\n    REST principles and supports authentication via API tokens, with all requests sent over HTTPS. The API exposes a JSON-based\n    send endpoint and a batch endpoint capable of delivering up to 500 emails in a single request.\n  tags:\n  - Mailtrap\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mailtrap\n    baseUri: https://send.api.mailtrap.io\n    description: Mailtrap Email Sending API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MAILTRAP_TOKEN}}'\n    resources:\n    - name: api-send\n      path: /api/send\n      operations:\n      - name: sendemail\n        method: POST\n        description: Send a transactional email\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: api-batch\n      path: /api/batch\n      operations:\n      - name: sendbatchemails\n        method: POST\n        description: Send batch emails\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mailtrap-rest\n    description: REST adapter for Mailtrap Email Sending API.\n    resources:\n    - path: /api/send\n      name: sendemail\n      operations:\n      - method: POST\n        name: sendemail\n        description: Send a transactional email\n        call: mailtrap.sendemail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/batch\n      name: sendbatchemails\n      operations:\n      - method: POST\n        name: sendbatchemails\n        description: Send batch emails\n        call: mailtrap.sendbatchemails\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mailtrap-mcp\n    transport: http\n    description: MCP adapter for Mailtrap Email Sending API for AI agent use.\n    tools:\n    - name: sendemail\n      description: Send a transactional email\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailtrap.sendemail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendbatchemails\n      description: Send batch emails\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailtrap.sendbatchemails\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MAILTRAP_TOKEN: MAILTRAP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mailtrap/refs/heads/main/capabilities/mailtrap-capability.yaml
tags:
- Mailtrap
- API
tools:
- description: Send a transactional email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendemail
- description: Send batch emails
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbatchemails
---
