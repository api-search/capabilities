---
categories: []
consumed_apis: []
description: A capability over a Kubernetes cluster's API server for GitOps-driven capability deployments — read-only deployments + scaling exposed as governed actions.
layout: capability
name: K8S Gitops Capability
operations:
- description: ''
  method: GET
  name: list-deployments
  path: /deployments
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list deployments
- spec-driven integration
- get deployment
- gitops
- scale deployment
- mcp
- capabilities
- naftiko
- kubernetes
- api integration
- governance
- ai
slug: k8s-gitops-capability
source_filename: k8s-gitops-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: K8s Gitops Capability\n  description: A capability over a Kubernetes cluster's API server for GitOps-driven capability deployments — read-only deployments + scaling exposed as governed actions.\n  tags: [Naftiko, Kubernetes, GitOps]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: k8s-env\n  keys: {K8S_HOST: K8S_HOST, K8S_TOKEN: K8S_TOKEN, K8S_NAMESPACE: K8S_NAMESPACE}\ncapability:\n  consumes:\n  - namespace: k8s\n    type: http\n    baseUri: 'https://{{K8S_HOST}}'\n    authentication: {type: bearer, token: '{{K8S_TOKEN}}'}\n    resources:\n    - {name: deployments, path: '/apis/apps/v1/namespaces/{{K8S_NAMESPACE}}/deployments', operations: [{name: list-deployments, method: GET}]}\n    - name: deployment\n      path: '/apis/apps/v1/namespaces/{{K8S_NAMESPACE}}/deployments/{{name}}'\n      operations:\n      - {name: get-deployment, method: GET, inputParameters: [{name: name, in: path}]}\n      - {name: patch-deployment,\
  \ method: PATCH, inputParameters: [{name: name, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: k8s-gitops-capability-rest\n    description: REST surface for K8s deploys.\n    resources:\n    - {name: deployments, path: /deployments, operations: [{method: GET, name: list-deployments, call: k8s.list-deployments}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: k8s-gitops-capability-mcp\n    description: MCP for K8s deploys.\n    tools:\n    - {name: list-deployments, hints: {readOnly: true}, call: k8s.list-deployments}\n    - name: get-deployment\n      hints: {readOnly: true}\n      inputParameters: [{name: name, type: string, required: true}]\n      call: k8s.get-deployment\n    - name: scale-deployment\n      inputParameters: [{name: name, type: string, required: true}]\n      call: k8s.patch-deployment\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: k8s-gitops-capability-skills\n    description:\
  \ Skill for K8s GitOps.\n    skills:\n    - name: k8s-gitops-capability\n      description: Kubernetes GitOps deploys.\n      location: file:///opt/naftiko/skills/k8s-gitops-capability\n      allowed-tools: list-deployments,get-deployment,scale-deployment\n      tools:\n      - {name: list-deployments, from: {sourceNamespace: k8s-gitops-capability-mcp, action: list-deployments}}\n      - {name: get-deployment, from: {sourceNamespace: k8s-gitops-capability-mcp, action: get-deployment}}\n      - {name: scale-deployment, from: {sourceNamespace: k8s-gitops-capability-mcp, action: scale-deployment}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/k8s-gitops-capability.yaml
tags:
- Naftiko
- Kubernetes
- GitOps
tools:
- description: ''
  hints:
    readOnly: true
  name: list-deployments
- description: ''
  hints:
    readOnly: true
  name: get-deployment
- description: ''
  hints: {}
  name: scale-deployment
---
