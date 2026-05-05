---
categories: []
consumed_apis: []
description: A capability over Backstage that pulls catalog entities and their TechDocs and exposes them as composed documentation context for AI agents.
layout: capability
name: Backstage Catalog Documentation Capability
operations:
- description: ''
  method: GET
  name: list-entities
  path: /entities
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- techdocs
- list entities
- backstage
- spec-driven integration
- mcp
- capabilities
- get entity
- naftiko
- api integration
- get techdocs
- governance
- ai
slug: backstage-catalog-documentation-capability
source_filename: backstage-catalog-documentation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Catalog Documentation Capability\n  description: A capability over Backstage that pulls catalog entities and their TechDocs and exposes them as composed documentation context for AI agents.\n  tags: [Naftiko, Backstage, TechDocs]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: entities, path: /api/catalog/entities, operations: [{name: list-entities, method: GET}]}\n    - name: entity\n      path: /api/catalog/entities/by-name/{{kind}}/{{namespace}}/{{name}}\n      operations:\n      - {name: get-entity, method: GET, inputParameters: [{name: kind, in: path}, {name: namespace, in: path}, {name: name, in: path}]}\n\
  \    - name: techdocs\n      path: /api/techdocs/static/docs/{{namespace}}/{{kind}}/{{name}}/index.html\n      operations:\n      - {name: get-techdocs, method: GET, inputParameters: [{name: kind, in: path}, {name: namespace, in: path}, {name: name, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-catalog-documentation-capability-rest\n    description: REST surface for Backstage catalog + TechDocs.\n    resources:\n    - {name: entities, path: /entities, operations: [{method: GET, name: list-entities, call: backstage.list-entities}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-catalog-documentation-capability-mcp\n    description: MCP for Backstage catalog/TechDocs.\n    tools:\n    - {name: list-entities, hints: {readOnly: true}, call: backstage.list-entities}\n    - name: get-entity\n      hints: {readOnly: true}\n      inputParameters: [{name: kind, type: string, required: true}, {name: namespace,\
  \ type: string, required: true}, {name: name, type: string, required: true}]\n      call: backstage.get-entity\n    - name: get-techdocs\n      hints: {readOnly: true}\n      inputParameters: [{name: kind, type: string, required: true}, {name: namespace, type: string, required: true}, {name: name, type: string, required: true}]\n      call: backstage.get-techdocs\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-catalog-documentation-capability-skills\n    description: Skill for Backstage catalog+docs context.\n    skills:\n    - name: backstage-catalog-documentation-capability\n      description: Backstage catalog + TechDocs context for agents.\n      location: file:///opt/naftiko/skills/backstage-catalog-documentation-capability\n      allowed-tools: list-entities,get-entity,get-techdocs\n      tools:\n      - {name: list-entities, from: {sourceNamespace: backstage-catalog-documentation-capability-mcp, action: list-entities}}\n      - {name: get-entity,\
  \ from: {sourceNamespace: backstage-catalog-documentation-capability-mcp, action: get-entity}}\n      - {name: get-techdocs, from: {sourceNamespace: backstage-catalog-documentation-capability-mcp, action: get-techdocs}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-catalog-documentation-capability.yaml
tags:
- Naftiko
- Backstage
- TechDocs
tools:
- description: ''
  hints:
    readOnly: true
  name: list-entities
- description: ''
  hints:
    readOnly: true
  name: get-entity
- description: ''
  hints:
    readOnly: true
  name: get-techdocs
---
