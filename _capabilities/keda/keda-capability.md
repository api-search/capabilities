---
categories: []
consumed_apis: []
description: KEDA's Metrics API scaler connects to an HTTP endpoint that exposes a numeric metric value, which KEDA uses to drive scaling decisions. The endpoint must return a JSON, Prometheus, XML, or YAML response containing a metric value at a configured path. KEDA polls the endpoint on a configurable interval and compares the extracted value against a threshold to determine the desired replica count for the target workload. This specification describes the interface that an external HTTP metrics endpoint must implement to be compatible with the KEDA Metrics API scaler.
layout: capability
name: KEDA Metrics API
operations:
- description: KEDA Get metric value
  method: GET
  name: getmetricvalue
  path: /{metricPath}
personas: []
provider_name: KEDA
provider_slug: keda
search_terms:
- keda
- event-driven
- api
- keda get metric value
- getmetricvalue
- graduated
- cncf
- autoscaling
- kubernetes
slug: keda-capability
source_filename: keda-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: KEDA Metrics API\n  description: KEDA's Metrics API scaler connects to an HTTP endpoint that exposes a numeric metric value, which KEDA uses\n    to drive scaling decisions. The endpoint must return a JSON, Prometheus, XML, or YAML response containing a metric value\n    at a configured path. KEDA polls the endpoint on a configurable interval and compares the extracted value against a threshold\n    to determine the desired replica count for the target workload. This specification describes the interface that an external\n    HTTP metrics endpoint must implement to be compatible with the KEDA Metrics API scaler.\n  tags:\n  - Keda\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: keda\n    baseUri: http://metrics-api:8080\n    description: KEDA Metrics API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KEDA_TOKEN}}'\n    resources:\n    - name: metricpath\n\
  \      path: /{metricPath}\n      operations:\n      - name: getmetricvalue\n        method: GET\n        description: KEDA Get metric value\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: keda-rest\n    description: REST adapter for KEDA Metrics API.\n    resources:\n    - path: /{metricPath}\n      name: getmetricvalue\n      operations:\n      - method: GET\n        name: getmetricvalue\n        description: KEDA Get metric value\n        call: keda.getmetricvalue\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: keda-mcp\n    transport: http\n    description: MCP adapter for KEDA Metrics API for AI agent use.\n    tools:\n    - name: getmetricvalue\n      description: KEDA Get metric value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: keda.getmetricvalue\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KEDA_TOKEN: KEDA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/keda/refs/heads/main/capabilities/keda-capability.yaml
tags:
- Keda
- API
tools:
- description: KEDA Get metric value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetricvalue
---
