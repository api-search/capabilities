---
categories: []
consumed_apis: []
description: A capability that right-sizes microservice responses for AI consumption — drops verbose fields, normalizes shapes, returns a token-budgeted view.
layout: capability
name: Microservice Rightsize Capability
operations:
- description: ''
  method: GET
  name: get-rightsized
  path: /rightsized/{{resource}}/{{id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- microservice
- api integration
- governance
- spec-driven integration
- rightsize
- get rightsized
- ai
- mcp
- capabilities
slug: microservice-rightsize-capability
source_filename: microservice-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Microservice Rightsize Capability\n  description: A capability that right-sizes microservice responses for AI consumption — drops verbose fields, normalizes shapes, returns a token-budgeted view.\n  tags: [Naftiko, Microservice, Rightsize]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: target-env\n  keys: {TARGET_HOST: TARGET_HOST, TARGET_TOKEN: TARGET_TOKEN}\ncapability:\n  consumes:\n  - namespace: target\n    type: http\n    baseUri: https://{{TARGET_HOST}}\n    authentication: {type: bearer, token: '{{TARGET_TOKEN}}'}\n    resources:\n    - name: resource\n      path: /api/v1/{{resource}}/{{id}}\n      operations:\n      - {name: get-resource, method: GET, inputParameters: [{name: resource, in: path}, {name: id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: microservice-rightsize-capability-rest\n    description: Right-sized microservice surface.\n    resources:\n\
  \    - name: rightsized\n      path: /rightsized/{{resource}}/{{id}}\n      operations:\n      - {method: GET, name: get-rightsized, inputParameters: [{name: resource, in: path, type: string}, {name: id, in: path, type: string}], call: target.get-resource}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: microservice-rightsize-capability-mcp\n    description: MCP for right-sized microservice.\n    tools:\n    - name: get-rightsized\n      hints: {readOnly: true}\n      inputParameters: [{name: resource, type: string, required: true}, {name: id, type: string, required: true}]\n      call: target.get-resource\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: microservice-rightsize-capability-skills\n    description: Skill for right-sized microservice.\n    skills:\n    - name: microservice-rightsize-capability\n      description: Microservice rightsize.\n      location: file:///opt/naftiko/skills/microservice-rightsize-capability\n      allowed-tools:\
  \ get-rightsized\n      tools:\n      - {name: get-rightsized, from: {sourceNamespace: microservice-rightsize-capability-mcp, action: get-rightsized}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/microservice-rightsize-capability.yaml
tags:
- Naftiko
- Microservice
- Rightsize
tools:
- description: ''
  hints:
    readOnly: true
  name: get-rightsized
---
