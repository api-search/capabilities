---
categories: []
consumed_apis: []
description: A standard capability documenting the Naftiko Backstage scaffolding contract — required template inputs, naming, registry path.
layout: capability
name: Backstage Scaffolding Standard
operations:
- description: ''
  method: GET
  name: list-templates
  path: /templates
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- backstage
- governance
- standard
- spec-driven integration
- get template
- ai
- list templates
- capabilities
- api integration
- mcp
- naftiko
slug: backstage-scaffolding-standard
source_filename: backstage-scaffolding-standard.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Scaffolding Standard\n  description: A standard capability documenting the Naftiko Backstage scaffolding contract — required template inputs, naming, registry path.\n  tags: [Naftiko, Backstage, Standard]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: templates, path: /api/scaffolder/v2/templates, operations: [{name: list-templates, method: GET}]}\n    - name: template\n      path: /api/scaffolder/v2/templates/{{namespace}}/{{name}}\n      operations:\n      - {name: get-template, method: GET, inputParameters: [{name: namespace, in: path}, {name: name, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n\
  \    port: 8080\n    namespace: backstage-scaffolding-standard-rest\n    description: REST surface exposing the scaffolding standard's templates.\n    resources:\n    - {name: templates, path: /templates, operations: [{method: GET, name: list-templates, call: backstage.list-templates}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-scaffolding-standard-mcp\n    description: MCP exposing the scaffolding standard.\n    tools:\n    - {name: list-templates, hints: {readOnly: true}, call: backstage.list-templates}\n    - name: get-template\n      hints: {readOnly: true}\n      inputParameters: [{name: namespace, type: string, required: true}, {name: name, type: string, required: true}]\n      call: backstage.get-template\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-scaffolding-standard-skills\n    description: Skill for the scaffolding standard.\n    skills:\n    - name: backstage-scaffolding-standard\n      description: Naftiko\
  \ Backstage scaffolding standard.\n      location: file:///opt/naftiko/skills/backstage-scaffolding-standard\n      allowed-tools: list-templates,get-template\n      tools:\n      - {name: list-templates, from: {sourceNamespace: backstage-scaffolding-standard-mcp, action: list-templates}}\n      - {name: get-template, from: {sourceNamespace: backstage-scaffolding-standard-mcp, action: get-template}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-scaffolding-standard.yaml
tags:
- Naftiko
- Backstage
- Standard
tools:
- description: ''
  hints:
    readOnly: true
  name: list-templates
- description: ''
  hints:
    readOnly: true
  name: get-template
---
