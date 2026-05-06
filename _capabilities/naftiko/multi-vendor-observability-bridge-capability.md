---
categories: []
consumed_apis: []
description: A bridge across Datadog, New Relic, and Splunk that exposes a unified observability query surface.
layout: capability
name: Multi Vendor Observability Bridge Capability
operations:
- description: ''
  method: POST
  name: query-unified
  path: /query
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- query newrelic
- new relic
- splunk
- mcp
- api integration
- query unified
- query splunk
- governance
- ai
- spec-driven integration
- datadog
- capabilities
- query datadog
slug: multi-vendor-observability-bridge-capability
source_filename: multi-vendor-observability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Multi Vendor Observability Bridge Capability\n  description: A bridge across Datadog, New Relic, and Splunk that exposes a unified observability query surface.\n  tags: [Naftiko, Datadog, New Relic, Splunk]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: datadog-env\n  keys: {DD_API_KEY: DD_API_KEY}\n- namespace: newrelic-env\n  keys: {NR_API_KEY: NR_API_KEY, NR_ACCOUNT_ID: NR_ACCOUNT_ID}\n- namespace: splunk-env\n  keys: {SPLUNK_HOST: SPLUNK_HOST, SPLUNK_TOKEN: SPLUNK_TOKEN}\ncapability:\n  consumes:\n  - namespace: datadog\n    type: http\n    baseUri: https://api.datadoghq.com\n    authentication: {type: bearer, token: '{{DD_API_KEY}}'}\n    resources:\n    - {name: query, path: /api/v1/query, operations: [{name: query-dd, method: GET}]}\n  - namespace: newrelic\n    type: http\n    baseUri: https://api.newrelic.com\n    authentication: {type: bearer, token: '{{NR_API_KEY}}'}\n    resources:\n    - {name: nrql,\
  \ path: /graphql, operations: [{name: query-nrql, method: POST}]}\n  - namespace: splunk\n    type: http\n    baseUri: https://{{SPLUNK_HOST}}\n    authentication: {type: bearer, token: '{{SPLUNK_TOKEN}}'}\n    resources:\n    - {name: search-jobs, path: /services/search/jobs, operations: [{name: query-splunk, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: multi-vendor-observability-bridge-capability-rest\n    description: REST surface for unified observability query.\n    resources:\n    - {name: query, path: /query, operations: [{method: POST, name: query-unified, call: datadog.query-dd}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: multi-vendor-observability-bridge-capability-mcp\n    description: MCP for unified observability.\n    tools:\n    - {name: query-datadog, hints: {readOnly: true}, call: datadog.query-dd}\n    - {name: query-newrelic, hints: {readOnly: true}, call: newrelic.query-nrql}\n    - {name:\
  \ query-splunk, call: splunk.query-splunk}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: multi-vendor-observability-bridge-capability-skills\n    description: Skill for multi-vendor observability.\n    skills:\n    - name: multi-vendor-observability-bridge-capability\n      description: Multi-vendor observability bridge.\n      location: file:///opt/naftiko/skills/multi-vendor-observability-bridge-capability\n      allowed-tools: query-datadog,query-newrelic,query-splunk\n      tools:\n      - {name: query-datadog, from: {sourceNamespace: multi-vendor-observability-bridge-capability-mcp, action: query-datadog}}\n      - {name: query-newrelic, from: {sourceNamespace: multi-vendor-observability-bridge-capability-mcp, action: query-newrelic}}\n      - {name: query-splunk, from: {sourceNamespace: multi-vendor-observability-bridge-capability-mcp, action: query-splunk}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/multi-vendor-observability-bridge-capability.yaml
tags:
- Naftiko
- Datadog
- New Relic
- Splunk
tools:
- description: ''
  hints:
    readOnly: true
  name: query-datadog
- description: ''
  hints:
    readOnly: true
  name: query-newrelic
- description: ''
  hints: {}
  name: query-splunk
---
