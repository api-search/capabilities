---
categories: []
consumed_apis: []
description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
layout: capability
name: Multi Vendor Observability Bridge Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- api integration
- naftiko
- a capability that fans out to existing observability stack (new relic + datadog + dynatrace + google cloud logging) plus opentelemetry traces and returns a unified agent-driven-api-call view, sized for the gartner-hasn't-caught-up gap john flagged.
- governance
- mcp
- capabilities
- ai
slug: multi-vendor-observability-bridge-capability
source_filename: multi-vendor-observability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Multi Vendor Observability Bridge Capability\n  description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: multi-vendor-observability-bridge-capability-rest\n    description:\
  \ REST API for Multi Vendor Observability Bridge Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: multi-vendor-observability-bridge-capability-mcp\n    description: MCP server exposing Multi Vendor Observability Bridge Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: multi-vendor-observability-bridge-capability-skills\n    description: Agent Skill bundle for Multi Vendor Observability Bridge\
  \ Capability.\n    skills:\n    - name: multi-vendor-observability-bridge-capability\n      description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.\n      location: file:///opt/naftiko/skills/multi-vendor-observability-bridge-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.\n        from:\n          sourceNamespace: multi-vendor-observability-bridge-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/multi-vendor-observability-bridge-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
  hints:
    readOnly: true
  name: example
---
