---
categories: []
consumed_apis: []
description: A capability that uses Backstage as source-of-record and auto-catalogs Naftiko capabilities discovered from a registry into the Backstage catalog.
layout: capability
name: Backstage Source Of Record Auto Catalog
operations:
- description: ''
  method: POST
  name: auto-catalog
  path: /auto-catalog
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- backstage
- spec-driven integration
- mcp
- capabilities
- list cataloged entities
- auto-catalog
- naftiko
- api integration
- governance
- ai
- auto catalog
slug: backstage-source-of-record-auto-catalog
source_filename: backstage-source-of-record-auto-catalog.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Source Of Record Auto Catalog\n  description: A capability that uses Backstage as source-of-record and auto-catalogs Naftiko capabilities discovered from a registry into the Backstage catalog.\n  tags: [Naftiko, Backstage, Auto-Catalog]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: locations, path: /api/catalog/locations, operations: [{name: register-location, method: POST}, {name: list-locations, method: GET}]}\n    - {name: entities, path: /api/catalog/entities, operations: [{name: list-entities, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-source-of-record-auto-catalog-rest\n\
  \    description: REST surface for auto-cataloging Naftiko capabilities into Backstage.\n    resources:\n    - {name: auto-catalog, path: /auto-catalog, operations: [{method: POST, name: auto-catalog, call: backstage.register-location}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-source-of-record-auto-catalog-mcp\n    description: MCP for auto-catalog ops.\n    tools:\n    - {name: list-cataloged-entities, hints: {readOnly: true}, call: backstage.list-entities}\n    - {name: auto-catalog, call: backstage.register-location}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-source-of-record-auto-catalog-skills\n    description: Skill bundle for auto-catalog.\n    skills:\n    - name: backstage-source-of-record-auto-catalog\n      description: Backstage as source-of-record auto-catalog.\n      location: file:///opt/naftiko/skills/backstage-source-of-record-auto-catalog\n      allowed-tools: list-cataloged-entities,auto-catalog\n\
  \      tools:\n      - {name: list-cataloged-entities, from: {sourceNamespace: backstage-source-of-record-auto-catalog-mcp, action: list-cataloged-entities}}\n      - {name: auto-catalog, from: {sourceNamespace: backstage-source-of-record-auto-catalog-mcp, action: auto-catalog}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-source-of-record-auto-catalog.yaml
tags:
- Naftiko
- Backstage
- Auto-Catalog
tools:
- description: ''
  hints:
    readOnly: true
  name: list-cataloged-entities
- description: ''
  hints: {}
  name: auto-catalog
---
