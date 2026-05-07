---
categories: []
consumed_apis: []
description: A capability that publishes MCP servers as installable bundle files (mcpb) to a registry.
layout: capability
name: Mcp Bundle Format Publish Capability
operations:
- description: ''
  method: GET
  name: list-mcp-bundles
  path: /bundles
- description: ''
  method: POST
  name: publish-mcp-bundle
  path: /bundles/publish
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- download mcp bundle
- publish mcp bundle
- bundle
- ai
- publish
- capabilities
- api integration
- mcp
- naftiko
- list mcp bundles
slug: mcp-bundle-format-publish-capability
source_filename: mcp-bundle-format-publish-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mcp Bundle Format Publish Capability\n  description: A capability that publishes MCP servers as installable bundle files (mcpb) to a registry.\n  tags: [Naftiko, MCP, Bundle, Publish]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: mcp-bundles, path: /v1/mcp-bundles, operations: [{name: list-mcp-bundles, method: GET}, {name: publish-mcp-bundle, method: POST}]}\n    - name: mcp-bundle\n      path: /v1/mcp-bundles/{{bundle_id}}\n      operations:\n      - {name: get-mcp-bundle, method: GET, inputParameters: [{name: bundle_id, in: path}]}\n    - name: mcp-bundle-download\n      path: /v1/mcp-bundles/{{bundle_id}}/download\n      operations:\n      - {name:\
  \ download-mcp-bundle, method: GET, inputParameters: [{name: bundle_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mcp-bundle-format-publish-capability-rest\n    description: REST surface for MCP bundle publish.\n    resources:\n    - {name: bundles, path: /bundles, operations: [{method: GET, name: list-mcp-bundles, call: naftiko-control.list-mcp-bundles}]}\n    - {name: publish, path: /bundles/publish, operations: [{method: POST, name: publish-mcp-bundle, call: naftiko-control.publish-mcp-bundle}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mcp-bundle-format-publish-capability-mcp\n    description: MCP for bundle publish.\n    tools:\n    - {name: list-mcp-bundles, hints: {readOnly: true}, call: naftiko-control.list-mcp-bundles}\n    - {name: publish-mcp-bundle, call: naftiko-control.publish-mcp-bundle}\n    - name: download-mcp-bundle\n      hints: {readOnly: true}\n      inputParameters: [{name: bundle_id,\
  \ type: string, required: true}]\n      call: naftiko-control.download-mcp-bundle\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mcp-bundle-format-publish-capability-skills\n    description: Skill for MCP bundles.\n    skills:\n    - name: mcp-bundle-format-publish-capability\n      description: MCP bundle format publish.\n      location: file:///opt/naftiko/skills/mcp-bundle-format-publish-capability\n      allowed-tools: list-mcp-bundles,publish-mcp-bundle,download-mcp-bundle\n      tools:\n      - {name: list-mcp-bundles, from: {sourceNamespace: mcp-bundle-format-publish-capability-mcp, action: list-mcp-bundles}}\n      - {name: publish-mcp-bundle, from: {sourceNamespace: mcp-bundle-format-publish-capability-mcp, action: publish-mcp-bundle}}\n      - {name: download-mcp-bundle, from: {sourceNamespace: mcp-bundle-format-publish-capability-mcp, action: download-mcp-bundle}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mcp-bundle-format-publish-capability.yaml
tags:
- Naftiko
- MCP
- Bundle
- Publish
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mcp-bundles
- description: ''
  hints: {}
  name: publish-mcp-bundle
- description: ''
  hints:
    readOnly: true
  name: download-mcp-bundle
---
