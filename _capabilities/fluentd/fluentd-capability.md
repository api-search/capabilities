---
categories: []
consumed_apis: []
description: The Fluentd HTTP Input plugin exposes an HTTP endpoint that accepts log records posted as JSON, MessagePack, or form-encoded data. It allows applications to send events to Fluentd over standard HTTP, making it accessible from any language or platform that can make HTTP requests. Events can be sent individually or in batches, and the tag routing system determines downstream processing pipelines.
layout: capability
name: Fluentd HTTP Input API
operations:
- description: Fluentd Post a log event
  method: POST
  name: postevent
  path: /{tag}
- description: Fluentd Post a log event with explicit format
  method: POST
  name: posteventwithformat
  path: /{tag}.{format}
personas: []
provider_name: Fluentd
provider_slug: fluentd
search_terms:
- posteventwithformat
- api
- data collection
- open source
- fluentd post a log event
- fluentd post a log event with explicit format
- postevent
- logging
- fluentd
slug: fluentd-capability
source_filename: fluentd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fluentd HTTP Input API\n  description: The Fluentd HTTP Input plugin exposes an HTTP endpoint that accepts log records posted as JSON, MessagePack,\n    or form-encoded data. It allows applications to send events to Fluentd over standard HTTP, making it accessible from any\n    language or platform that can make HTTP requests. Events can be sent individually or in batches, and the tag routing system\n    determines downstream processing pipelines.\n  tags:\n  - Fluentd\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fluentd\n    baseUri: http://localhost:8888\n    description: Fluentd HTTP Input API HTTP API.\n    resources:\n    - name: tag\n      path: /{tag}\n      operations:\n      - name: postevent\n        method: POST\n        description: Fluentd Post a log event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: tag-format\n      path: /{tag}.{format}\n      operations:\n      - name: posteventwithformat\n        method: POST\n        description: Fluentd Post a log event with explicit format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fluentd-rest\n    description: REST adapter for Fluentd HTTP Input API.\n    resources:\n    - path: /{tag}\n      name: postevent\n      operations:\n      - method: POST\n        name: postevent\n        description: Fluentd Post a log event\n        call: fluentd.postevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{tag}.{format}\n      name: posteventwithformat\n      operations:\n      - method: POST\n        name: posteventwithformat\n        description: Fluentd Post a log event with explicit format\n        call: fluentd.posteventwithformat\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fluentd-mcp\n    transport: http\n    description: MCP adapter for Fluentd HTTP Input API for AI agent use.\n    tools:\n    - name: postevent\n      description: Fluentd Post a log event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fluentd.postevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: posteventwithformat\n      description: Fluentd Post a log event with explicit format\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fluentd.posteventwithformat\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fluentd/refs/heads/main/capabilities/fluentd-capability.yaml
tags:
- Fluentd
- API
tools:
- description: Fluentd Post a log event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postevent
- description: Fluentd Post a log event with explicit format
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: posteventwithformat
---
