---
categories: []
consumed_apis: []
description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
layout: capability
name: Fortune50 Fleet Scale Demo
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- a capability authored to deploy via naftikocapability crd + capabilityclass, paired with a backstage template, used to demonstrate "thousands of capabilities under one fleet."
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: fortune50-fleet-scale-demo
source_filename: fortune50-fleet-scale-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Fortune50 Fleet Scale Demo\n  description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate \"thousands of capabilities under one fleet.\"\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: fortune50-fleet-scale-demo-rest\n    description: REST API for Fortune50 Fleet Scale Demo.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: fortune50-fleet-scale-demo-mcp\n    description: MCP server exposing Fortune50 Fleet Scale Demo for AI agents.\n    tools:\n    - name: example\n      description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate \"thousands of capabilities under one fleet.\"\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: fortune50-fleet-scale-demo-skills\n    description: Agent Skill bundle for Fortune50 Fleet Scale Demo.\n    skills:\n    - name: fortune50-fleet-scale-demo\n      description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate \"thousands of capabilities under one fleet.\"\
  \n      location: file:///opt/naftiko/skills/fortune50-fleet-scale-demo\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate \"thousands of capabilities under one fleet.\"\n        from:\n          sourceNamespace: fortune50-fleet-scale-demo-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/fortune50-fleet-scale-demo.yaml
tags:
- Naftiko
tools:
- description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
  hints:
    readOnly: true
  name: example
---
