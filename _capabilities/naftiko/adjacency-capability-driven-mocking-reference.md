---
categories: []
consumed_apis: []
description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
layout: capability
name: Adjacency Capability Driven Mocking Reference
operations:
- description: Pull an Adjacency capability spec and stand up a Naftiko mock for it.
  method: POST
  name: mock-from-spec
  path: /mocks/from-spec/{{capability_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- mock from spec
- spec-driven integration
- return the runtime url and metadata of a naftiko mock.
- get mock
- mocking
- pull an adjacency capability spec and stand up a naftiko mock for it.
- stand up a naftiko mock from an adjacency capability spec.
- mcp
- capabilities
- naftiko
- adjacency
- api integration
- governance
- ai
slug: adjacency-capability-driven-mocking-reference
source_filename: adjacency-capability-driven-mocking-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Adjacency Capability Driven Mocking Reference\n  description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.\n  tags:\n  - Naftiko\n  - Adjacency\n  - Mocking\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: adjacency-env\n  description: Adjacency capability-spec source (e.g. spec registry URL).\n  keys:\n    ADJACENCY_SPEC_URL: ADJACENCY_SPEC_URL\n- namespace: naftiko-env\n  description: Naftiko mocking-runtime token.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: adjacency\n    type: http\n    baseUri: '{{ADJACENCY_SPEC_URL}}'\n    resources:\n    - name: capability-spec\n      path: /capabilities/{{capability_id}}\n      operations:\n      - name: get-capability-spec\n        method: GET\n        inputParameters:\n        - name: capability_id\n        \
  \  in: path\n  - namespace: naftiko-mock\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: mocks\n      path: /v1/mocks\n      operations:\n      - name: create-mock\n        method: POST\n        description: Create a runtime mock from an Adjacency capability spec.\n    - name: mock\n      path: /v1/mocks/{{mock_id}}\n      operations:\n      - name: get-mock\n        method: GET\n        inputParameters:\n        - name: mock_id\n          in: path\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: adjacency-capability-driven-mocking-reference-rest\n    description: REST surface that renders an Adjacency capability spec as a live Naftiko mock.\n    resources:\n    - name: mock-from-spec\n      path: /mocks/from-spec/{{capability_id}}\n      operations:\n      - method: POST\n        name: mock-from-spec\n        description: Pull an Adjacency capability\
  \ spec and stand up a Naftiko mock for it.\n        inputParameters:\n        - name: capability_id\n          in: path\n          type: string\n        call: naftiko-mock.create-mock\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: adjacency-capability-driven-mocking-reference-mcp\n    description: MCP server letting agents stand up capability-driven mocks on demand.\n    tools:\n    - name: mock-from-spec\n      description: Stand up a Naftiko mock from an Adjacency capability spec.\n      inputParameters:\n      - name: capability_id\n        type: string\n        required: true\n      call: naftiko-mock.create-mock\n    - name: get-mock\n      description: Return the runtime URL and metadata of a Naftiko mock.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: mock_id\n        type: string\n        required: true\n      call: naftiko-mock.get-mock\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: adjacency-capability-driven-mocking-reference-skills\n\
  \    description: Agent Skill bundle for capability-driven mocking.\n    skills:\n    - name: adjacency-capability-driven-mocking-reference\n      description: Spin up runtime mocks from Adjacency capability specs.\n      location: file:///opt/naftiko/skills/adjacency-capability-driven-mocking-reference\n      allowed-tools: mock-from-spec,get-mock\n      tools:\n      - name: mock-from-spec\n        from:\n          sourceNamespace: adjacency-capability-driven-mocking-reference-mcp\n          action: mock-from-spec\n      - name: get-mock\n        from:\n          sourceNamespace: adjacency-capability-driven-mocking-reference-mcp\n          action: get-mock\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/adjacency-capability-driven-mocking-reference.yaml
tags:
- Naftiko
- Adjacency
- Mocking
tools:
- description: Stand up a Naftiko mock from an Adjacency capability spec.
  hints: {}
  name: mock-from-spec
- description: Return the runtime URL and metadata of a Naftiko mock.
  hints:
    readOnly: true
  name: get-mock
---
