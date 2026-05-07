---
categories: []
consumed_apis: []
description: A capability over Datadog and Splunk that exposes a unified observability fabric — metrics, logs, traces queryable through a single surface.
layout: capability
name: Datadog Splunk Observability Fabric Capability
operations:
- description: ''
  method: POST
  name: cross-platform-search
  path: /observability/search
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- observability
- governance
- spec-driven integration
- datadog
- api integration
- query datadog metrics
- search datadog logs
- splunk
- ai
- capabilities
- cross platform search
- mcp
- naftiko
- search splunk
slug: datadog-splunk-observability-fabric-capability
source_filename: datadog-splunk-observability-fabric-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Datadog Splunk Observability Fabric Capability\n  description: A capability over Datadog and Splunk that exposes a unified observability fabric — metrics, logs, traces queryable through a single surface.\n  tags: [Naftiko, Datadog, Splunk, Observability]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: datadog-env\n  keys: {DD_API_KEY: DD_API_KEY, DD_APP_KEY: DD_APP_KEY}\n- namespace: splunk-env\n  keys: {SPLUNK_HOST: SPLUNK_HOST, SPLUNK_TOKEN: SPLUNK_TOKEN}\ncapability:\n  consumes:\n  - namespace: datadog\n    type: http\n    baseUri: https://api.datadoghq.com\n    authentication: {type: bearer, token: '{{DD_API_KEY}}'}\n    resources:\n    - {name: metrics-query, path: /api/v1/query, operations: [{name: query-metrics, method: GET}]}\n    - {name: logs-search, path: /api/v2/logs/events/search, operations: [{name: search-logs, method: POST}]}\n  - namespace: splunk\n    type: http\n    baseUri: https://{{SPLUNK_HOST}}\n\
  \    authentication: {type: bearer, token: '{{SPLUNK_TOKEN}}'}\n    resources:\n    - {name: search-jobs, path: /services/search/jobs, operations: [{name: create-search-job, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: datadog-splunk-observability-fabric-capability-rest\n    description: REST surface for unified observability.\n    resources:\n    - {name: search, path: /observability/search, operations: [{method: POST, name: cross-platform-search, call: datadog.search-logs}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: datadog-splunk-observability-fabric-capability-mcp\n    description: MCP for unified observability.\n    tools:\n    - {name: query-datadog-metrics, hints: {readOnly: true}, call: datadog.query-metrics}\n    - {name: search-datadog-logs, hints: {readOnly: true}, call: datadog.search-logs}\n    - {name: search-splunk, call: splunk.create-search-job}\n  - type: skill\n    address: 0.0.0.0\n    port:\
  \ 3011\n    namespace: datadog-splunk-observability-fabric-capability-skills\n    description: Skill for observability fabric.\n    skills:\n    - name: datadog-splunk-observability-fabric-capability\n      description: Datadog + Splunk observability fabric.\n      location: file:///opt/naftiko/skills/datadog-splunk-observability-fabric-capability\n      allowed-tools: query-datadog-metrics,search-datadog-logs,search-splunk\n      tools:\n      - {name: query-datadog-metrics, from: {sourceNamespace: datadog-splunk-observability-fabric-capability-mcp, action: query-datadog-metrics}}\n      - {name: search-datadog-logs, from: {sourceNamespace: datadog-splunk-observability-fabric-capability-mcp, action: search-datadog-logs}}\n      - {name: search-splunk, from: {sourceNamespace: datadog-splunk-observability-fabric-capability-mcp, action: search-splunk}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/datadog-splunk-observability-fabric-capability.yaml
tags:
- Naftiko
- Datadog
- Splunk
- Observability
tools:
- description: ''
  hints:
    readOnly: true
  name: query-datadog-metrics
- description: ''
  hints:
    readOnly: true
  name: search-datadog-logs
- description: ''
  hints: {}
  name: search-splunk
---
