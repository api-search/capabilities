---
categories: []
consumed_apis: []
description: A Backstage software template that scaffolds a new Naftiko capability YAML and registers it in the catalog.
layout: capability
name: Backstage Naftiko Capability Template Capability
operations:
- description: ''
  method: POST
  name: scaffold-capability
  path: /new-capability
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list templates
- scaffold capability
- backstage
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
- software template
slug: backstage-naftiko-capability-template-capability
source_filename: backstage-naftiko-capability-template-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Naftiko Capability Template Capability\n  description: A Backstage software template that scaffolds a new Naftiko capability YAML and registers it in the catalog.\n  tags: [Naftiko, Backstage, Software Template]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: scaffolder-tasks, path: /api/scaffolder/v2/tasks, operations: [{name: run-scaffolder-task, method: POST}]}\n    - {name: templates, path: /api/scaffolder/v2/templates, operations: [{name: list-templates, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-naftiko-capability-template-capability-rest\n  \
  \  description: REST surface for scaffolding a Naftiko capability via Backstage.\n    resources:\n    - {name: new-capability, path: /new-capability, operations: [{method: POST, name: scaffold-capability, call: backstage.run-scaffolder-task}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-naftiko-capability-template-capability-mcp\n    description: MCP for Backstage capability scaffolding.\n    tools:\n    - {name: list-templates, hints: {readOnly: true}, call: backstage.list-templates}\n    - {name: scaffold-capability, call: backstage.run-scaffolder-task}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-naftiko-capability-template-capability-skills\n    description: Skill bundle for capability scaffolding.\n    skills:\n    - name: backstage-naftiko-capability-template-capability\n      description: Scaffold a new Naftiko capability via Backstage.\n      location: file:///opt/naftiko/skills/backstage-naftiko-capability-template-capability\n\
  \      allowed-tools: list-templates,scaffold-capability\n      tools:\n      - {name: list-templates, from: {sourceNamespace: backstage-naftiko-capability-template-capability-mcp, action: list-templates}}\n      - {name: scaffold-capability, from: {sourceNamespace: backstage-naftiko-capability-template-capability-mcp, action: scaffold-capability}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-naftiko-capability-template-capability.yaml
tags:
- Naftiko
- Backstage
- Software Template
tools:
- description: ''
  hints:
    readOnly: true
  name: list-templates
- description: ''
  hints: {}
  name: scaffold-capability
---
