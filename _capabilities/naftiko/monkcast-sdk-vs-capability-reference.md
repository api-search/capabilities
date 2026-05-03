---
categories: []
consumed_apis: []
description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
layout: capability
name: Monkcast Sdk Vs Capability Reference
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
- a side-by-side reference capability that pairs a generated sdk with a naftiko-exposed capability over the same upstream api, illustrating "capabilities are the new abstraction layer."
- governance
- mcp
- capabilities
- ai
slug: monkcast-sdk-vs-capability-reference
source_filename: monkcast-sdk-vs-capability-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Monkcast Sdk Vs Capability Reference\n  description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating \"Capabilities Are the New Abstraction Layer.\"\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: monkcast-sdk-vs-capability-reference-rest\n    description: REST API for Monkcast Sdk Vs Capability Reference.\n    resources:\n  \
  \  - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: monkcast-sdk-vs-capability-reference-mcp\n    description: MCP server exposing Monkcast Sdk Vs Capability Reference for AI agents.\n    tools:\n    - name: example\n      description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating \"Capabilities Are the New Abstraction Layer.\"\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: monkcast-sdk-vs-capability-reference-skills\n    description: Agent Skill bundle for Monkcast Sdk Vs Capability Reference.\n    skills:\n    - name: monkcast-sdk-vs-capability-reference\n      description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed\
  \ capability over the same upstream API, illustrating \"Capabilities Are the New Abstraction Layer.\"\n      location: file:///opt/naftiko/skills/monkcast-sdk-vs-capability-reference\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating \"Capabilities Are the New Abstraction Layer.\"\n        from:\n          sourceNamespace: monkcast-sdk-vs-capability-reference-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/monkcast-sdk-vs-capability-reference.yaml
tags:
- Naftiko
tools:
- description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
  hints:
    readOnly: true
  name: example
---
