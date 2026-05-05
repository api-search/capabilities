---
categories: []
consumed_apis: []
description: A capability that publishes a Naftiko capability YAML as a Backstage software template, available in the developer portal.
layout: capability
name: Backstage Software Template Publisher
operations:
- description: ''
  method: POST
  name: publish-template
  path: /publish
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- publisher
- refresh catalog
- backstage
- spec-driven integration
- mcp
- ai
- capabilities
- naftiko
- api integration
- governance
- publish template
slug: backstage-software-template-publisher
source_filename: backstage-software-template-publisher.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Software Template Publisher\n  description: A capability that publishes a Naftiko capability YAML as a Backstage software template, available in the developer portal.\n  tags: [Naftiko, Backstage, Publisher]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: backstage-env\n  keys: {BACKSTAGE_HOST: BACKSTAGE_HOST, BACKSTAGE_TOKEN: BACKSTAGE_TOKEN}\ncapability:\n  consumes:\n  - namespace: backstage\n    type: http\n    baseUri: https://{{BACKSTAGE_HOST}}\n    authentication: {type: bearer, token: '{{BACKSTAGE_TOKEN}}'}\n    resources:\n    - {name: locations, path: /api/catalog/locations, operations: [{name: register-location, method: POST}]}\n    - {name: catalog-refresh, path: /api/catalog/refresh, operations: [{name: refresh-catalog, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-software-template-publisher-rest\n    description: REST surface\
  \ for publishing software templates to Backstage.\n    resources:\n    - {name: publish, path: /publish, operations: [{method: POST, name: publish-template, call: backstage.register-location}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-software-template-publisher-mcp\n    description: MCP for template publication.\n    tools:\n    - {name: publish-template, call: backstage.register-location}\n    - {name: refresh-catalog, call: backstage.refresh-catalog}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-software-template-publisher-skills\n    description: Skill for publishing templates.\n    skills:\n    - name: backstage-software-template-publisher\n      description: Publish capability YAML as Backstage template.\n      location: file:///opt/naftiko/skills/backstage-software-template-publisher\n      allowed-tools: publish-template,refresh-catalog\n      tools:\n      - {name: publish-template, from: {sourceNamespace:\
  \ backstage-software-template-publisher-mcp, action: publish-template}}\n      - {name: refresh-catalog, from: {sourceNamespace: backstage-software-template-publisher-mcp, action: refresh-catalog}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-software-template-publisher.yaml
tags:
- Naftiko
- Backstage
- Publisher
tools:
- description: ''
  hints: {}
  name: publish-template
- description: ''
  hints: {}
  name: refresh-catalog
---
