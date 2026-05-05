---
categories: []
consumed_apis: []
description: A scaffold capability that bootstraps a Backstage demo environment with example entities and TechDocs.
layout: capability
name: Backstage Demo Scaffold
operations:
- description: ''
  method: POST
  name: scaffold-demo
  path: /scaffold
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- backstage
- spec-driven integration
- scaffold demo
- mcp
- capabilities
- register location
- naftiko
- api integration
- scaffold
- governance
- ai
slug: backstage-demo-scaffold
source_filename: backstage-demo-scaffold.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Demo Scaffold\n  description: A scaffold capability that bootstraps a Backstage demo environment with example entities and TechDocs.\n  tags: [Naftiko, Backstage, Scaffold]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: locations, path: /api/catalog/locations, operations: [{name: register-location, method: POST}]}\n    - {name: scaffolder-tasks, path: /api/scaffolder/v2/tasks, operations: [{name: run-scaffolder-task, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-demo-scaffold-rest\n    description: REST surface for scaffolding a Backstage demo.\n   \
  \ resources:\n    - {name: scaffold, path: /scaffold, operations: [{method: POST, name: scaffold-demo, call: backstage.run-scaffolder-task}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-demo-scaffold-mcp\n    description: MCP for Backstage scaffolding.\n    tools:\n    - {name: scaffold-demo, call: backstage.run-scaffolder-task}\n    - {name: register-location, call: backstage.register-location}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-demo-scaffold-skills\n    description: Skill bundle for Backstage demo scaffolding.\n    skills:\n    - name: backstage-demo-scaffold\n      description: Bootstrap a Backstage demo.\n      location: file:///opt/naftiko/skills/backstage-demo-scaffold\n      allowed-tools: scaffold-demo,register-location\n      tools:\n      - {name: scaffold-demo, from: {sourceNamespace: backstage-demo-scaffold-mcp, action: scaffold-demo}}\n      - {name: register-location, from: {sourceNamespace:\
  \ backstage-demo-scaffold-mcp, action: register-location}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-demo-scaffold.yaml
tags:
- Naftiko
- Backstage
- Scaffold
tools:
- description: ''
  hints: {}
  name: scaffold-demo
- description: ''
  hints: {}
  name: register-location
---
