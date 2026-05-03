---
categories: []
consumed_apis: []
description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so developers spin up a new governed capability from inside the developer portal without leaving Backstage.
layout: capability
name: Backstage Naftiko Capability Template Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability that ships a backstage software template bundling the naftikocapability crd scaffold, so developers spin up a new governed capability from inside the developer portal without leaving backstage.
- example op
- example
- api integration
- spec-driven integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: backstage-naftiko-capability-template-capability
source_filename: backstage-naftiko-capability-template-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Naftiko Capability Template Capability\n  description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so developers spin up a new governed capability from inside the developer portal without leaving Backstage.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-naftiko-capability-template-capability-rest\n    description: REST API for Backstage Naftiko\
  \ Capability Template Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-naftiko-capability-template-capability-mcp\n    description: MCP server exposing Backstage Naftiko Capability Template Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so developers spin up a new governed capability from inside the developer portal without leaving Backstage.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-naftiko-capability-template-capability-skills\n    description: Agent Skill bundle for Backstage Naftiko Capability Template Capability.\n    skills:\n    - name: backstage-naftiko-capability-template-capability\n\
  \      description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so developers spin up a new governed capability from inside the developer portal without leaving Backstage.\n      location: file:///opt/naftiko/skills/backstage-naftiko-capability-template-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so developers spin up a new governed capability from inside the developer portal without leaving Backstage.\n        from:\n          sourceNamespace: backstage-naftiko-capability-template-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-naftiko-capability-template-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so developers spin up a new governed capability from inside the developer portal without leaving Backstage.
  hints:
    readOnly: true
  name: example
---
