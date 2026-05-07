---
categories: []
consumed_apis: []
description: A capability that drives BNP Paribas capability deployments through Argo CD GitOps with sync/rollback exposed as governance-tracked actions.
layout: capability
name: Bnp Gitops Argocd Capability
operations:
- description: ''
  method: POST
  name: sync-app
  path: /apps/{{name}}/sync
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- sync app
- gitops
- governance
- naftiko
- list apps
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- argo cd
- bnp paribas
slug: bnp-gitops-argocd-capability
source_filename: bnp-gitops-argocd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Gitops Argocd Capability\n  description: A capability that drives BNP Paribas capability deployments through Argo CD GitOps with sync/rollback exposed as governance-tracked actions.\n  tags: [Naftiko, BNP Paribas, GitOps, Argo CD]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: argocd-env\n  keys: {ARGOCD_HOST: ARGOCD_HOST, ARGOCD_TOKEN: ARGOCD_TOKEN}\ncapability:\n  consumes:\n  - namespace: argocd\n    type: http\n    baseUri: https://{{ARGOCD_HOST}}\n    authentication: {type: bearer, token: '{{ARGOCD_TOKEN}}'}\n    resources:\n    - {name: applications, path: /api/v1/applications, operations: [{name: list-applications, method: GET}]}\n    - name: app-sync\n      path: /api/v1/applications/{{name}}/sync\n      operations:\n      - {name: sync-application, method: POST, inputParameters: [{name: name, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-gitops-argocd-capability-rest\n\
  \    description: REST surface for BNP GitOps deploys.\n    resources:\n    - name: sync\n      path: /apps/{{name}}/sync\n      operations:\n      - {method: POST, name: sync-app, inputParameters: [{name: name, in: path, type: string}], call: argocd.sync-application}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-gitops-argocd-capability-mcp\n    description: MCP for BNP GitOps.\n    tools:\n    - {name: list-apps, hints: {readOnly: true}, call: argocd.list-applications}\n    - name: sync-app\n      inputParameters: [{name: name, type: string, required: true}]\n      call: argocd.sync-application\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-gitops-argocd-capability-skills\n    description: Skill for BNP GitOps.\n    skills:\n    - name: bnp-gitops-argocd-capability\n      description: BNP Argo CD GitOps deploys.\n      location: file:///opt/naftiko/skills/bnp-gitops-argocd-capability\n      allowed-tools: list-apps,sync-app\n   \
  \   tools:\n      - {name: list-apps, from: {sourceNamespace: bnp-gitops-argocd-capability-mcp, action: list-apps}}\n      - {name: sync-app, from: {sourceNamespace: bnp-gitops-argocd-capability-mcp, action: sync-app}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-gitops-argocd-capability.yaml
tags:
- Naftiko
- BNP Paribas
- GitOps
- Argo CD
tools:
- description: ''
  hints:
    readOnly: true
  name: list-apps
- description: ''
  hints: {}
  name: sync-app
---
