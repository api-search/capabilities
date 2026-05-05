---
categories: []
consumed_apis: []
description: A demo capability treating MCP servers as first-class Kubernetes resources via a Naftiko CRD.
layout: capability
name: Mcp As K8S Resource Demo
operations:
- description: ''
  method: GET
  name: list-mcp-server-crs
  path: /mcp-servers
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list mcp server crs
- demo
- spec-driven integration
- get mcp server cr
- mcp
- ai
- capabilities
- naftiko
- kubernetes
- api integration
- governance
- create mcp server cr
slug: mcp-as-k8s-resource-demo
source_filename: mcp-as-k8s-resource-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mcp As K8s Resource Demo\n  description: A demo capability treating MCP servers as first-class Kubernetes resources via a Naftiko CRD.\n  tags: [Naftiko, MCP, Kubernetes, Demo]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: k8s-env\n  keys: {K8S_HOST: K8S_HOST, K8S_TOKEN: K8S_TOKEN, K8S_NAMESPACE: K8S_NAMESPACE}\ncapability:\n  consumes:\n  - namespace: k8s\n    type: http\n    baseUri: 'https://{{K8S_HOST}}'\n    authentication: {type: bearer, token: '{{K8S_TOKEN}}'}\n    resources:\n    - {name: mcp-servers, path: '/apis/naftiko.io/v1alpha1/namespaces/{{K8S_NAMESPACE}}/mcpservers', operations: [{name: list-mcp-server-crs, method: GET}, {name: create-mcp-server-cr, method: POST}]}\n    - name: mcp-server\n      path: '/apis/naftiko.io/v1alpha1/namespaces/{{K8S_NAMESPACE}}/mcpservers/{{name}}'\n      operations:\n      - {name: get-mcp-server-cr, method: GET, inputParameters: [{name: name, in: path}]}\n  exposes:\n\
  \  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mcp-as-k8s-resource-demo-rest\n    description: REST surface for MCP-as-K8s-resource demo.\n    resources:\n    - {name: mcp-servers, path: /mcp-servers, operations: [{method: GET, name: list-mcp-server-crs, call: k8s.list-mcp-server-crs}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mcp-as-k8s-resource-demo-mcp\n    description: MCP for the demo.\n    tools:\n    - {name: list-mcp-server-crs, hints: {readOnly: true}, call: k8s.list-mcp-server-crs}\n    - name: get-mcp-server-cr\n      hints: {readOnly: true}\n      inputParameters: [{name: name, type: string, required: true}]\n      call: k8s.get-mcp-server-cr\n    - {name: create-mcp-server-cr, call: k8s.create-mcp-server-cr}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mcp-as-k8s-resource-demo-skills\n    description: Skill for MCP-as-K8s.\n    skills:\n    - name: mcp-as-k8s-resource-demo\n      description: MCP\
  \ servers as K8s resources.\n      location: file:///opt/naftiko/skills/mcp-as-k8s-resource-demo\n      allowed-tools: list-mcp-server-crs,get-mcp-server-cr,create-mcp-server-cr\n      tools:\n      - {name: list-mcp-server-crs, from: {sourceNamespace: mcp-as-k8s-resource-demo-mcp, action: list-mcp-server-crs}}\n      - {name: get-mcp-server-cr, from: {sourceNamespace: mcp-as-k8s-resource-demo-mcp, action: get-mcp-server-cr}}\n      - {name: create-mcp-server-cr, from: {sourceNamespace: mcp-as-k8s-resource-demo-mcp, action: create-mcp-server-cr}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mcp-as-k8s-resource-demo.yaml
tags:
- Naftiko
- MCP
- Kubernetes
- Demo
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mcp-server-crs
- description: ''
  hints:
    readOnly: true
  name: get-mcp-server-cr
- description: ''
  hints: {}
  name: create-mcp-server-cr
---
