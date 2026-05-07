---
categories: []
consumed_apis: []
description: A collection capability that mirrors every Apigee API proxy as an MCP server, so anything published to Apigee is automatically reachable from MCP-aware agents.
layout: capability
name: Apigee Mcp Mirror Collection
operations:
- description: List mirrored Apigee proxies.
  method: GET
  name: list-mirrored-proxies
  path: /proxies
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- get proxy
- naftiko
- api integration
- mirror
- ai
- capabilities
- spec-driven integration
- list mirrored proxies
- mcp
- apigee
- list mirrored apigee proxies.
slug: apigee-mcp-mirror-collection
source_filename: apigee-mcp-mirror-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Apigee Mcp Mirror Collection\n  description: A collection capability that mirrors every Apigee API proxy as an MCP server, so anything published to Apigee is automatically reachable from MCP-aware agents.\n  tags: [Naftiko, Apigee, MCP, Mirror]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: apigee-env\n  keys: {APIGEE_TOKEN: APIGEE_TOKEN, APIGEE_ORG: APIGEE_ORG, APIGEE_ENV: APIGEE_ENV}\ncapability:\n  consumes:\n  - namespace: apigee\n    type: http\n    baseUri: https://apigee.googleapis.com\n    authentication: {type: bearer, token: '{{APIGEE_TOKEN}}'}\n    resources:\n    - name: api-proxies\n      path: /v1/organizations/{{APIGEE_ORG}}/apis\n      operations: [{name: list-api-proxies, method: GET}]\n    - name: api-proxy\n      path: /v1/organizations/{{APIGEE_ORG}}/apis/{{api_name}}\n      operations:\n      - {name: get-api-proxy, method: GET, inputParameters: [{name: api_name, in: path}]}\n    - name: deployments\n\
  \      path: /v1/organizations/{{APIGEE_ORG}}/environments/{{APIGEE_ENV}}/deployments\n      operations: [{name: list-deployments, method: GET}]\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: apigee-mcp-mirror-collection-rest\n    description: REST surface exposing Apigee proxies as a unified mirror.\n    resources:\n    - name: proxies\n      path: /proxies\n      operations: [{method: GET, name: list-mirrored-proxies, description: List mirrored Apigee proxies., call: apigee.list-api-proxies}]\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: apigee-mcp-mirror-collection-mcp\n    description: MCP server mirroring Apigee proxies as MCP tools.\n    tools:\n    - {name: list-mirrored-proxies, hints: {readOnly: true}, call: apigee.list-api-proxies}\n    - name: get-proxy\n      hints: {readOnly: true}\n      inputParameters: [{name: api_name, type: string, required: true}]\n      call: apigee.get-api-proxy\n  - type: skill\n    address:\
  \ 0.0.0.0\n    port: 3011\n    namespace: apigee-mcp-mirror-collection-skills\n    description: Skill bundle for the Apigee MCP mirror.\n    skills:\n    - name: apigee-mcp-mirror-collection\n      description: Mirror Apigee proxies as MCP tools.\n      location: file:///opt/naftiko/skills/apigee-mcp-mirror-collection\n      allowed-tools: list-mirrored-proxies,get-proxy\n      tools:\n      - {name: list-mirrored-proxies, from: {sourceNamespace: apigee-mcp-mirror-collection-mcp, action: list-mirrored-proxies}}\n      - {name: get-proxy, from: {sourceNamespace: apigee-mcp-mirror-collection-mcp, action: get-proxy}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/apigee-mcp-mirror-collection.yaml
tags:
- Naftiko
- Apigee
- MCP
- Mirror
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mirrored-proxies
- description: ''
  hints:
    readOnly: true
  name: get-proxy
---
