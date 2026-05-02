---
categories: []
consumed_apis: []
description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
layout: capability
name: Ml Output Shaping Capability
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
- capabilities
- naftiko
- mcp
- example op
- example
- a capability featuring capability composition + typed outputparameters + jsonpath as the ml pipeline context-shaping story.
- governance
slug: ml-output-shaping-capability
source_filename: ml-output-shaping-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Ml Output Shaping Capability\n  description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: ml-output-shaping-capability-rest\n    description: REST API for Ml Output Shaping Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n     \
  \   name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: ml-output-shaping-capability-mcp\n    description: MCP server exposing Ml Output Shaping Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: ml-output-shaping-capability-skills\n    description: Agent Skill bundle for Ml Output Shaping Capability.\n    skills:\n    - name: ml-output-shaping-capability\n      description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.\n      location: file:///opt/naftiko/skills/ml-output-shaping-capability\n      allowed-tools: example\n      tools:\n      - name: example\n\
  \        description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.\n        from:\n          sourceNamespace: ml-output-shaping-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/ml-output-shaping-capability.yaml
tags:
- Naftiko
tools:
- description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
  hints:
    readOnly: true
  name: example
---
