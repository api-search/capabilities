---
categories: []
consumed_apis: []
description: A runbook capability over Argo CD that exposes capability deployment as a GitOps-driven Naftiko flow with sync/rollback as MCP tools.
layout: capability
name: Argocd Gitops Naftikocapability Runbook
operations:
- description: ''
  method: POST
  name: sync-app
  path: /apps/{{name}}/sync
- description: ''
  method: POST
  name: rollback-app
  path: /apps/{{name}}/rollback
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- sync app
- gitops
- governance
- naftiko
- rollback app
- list apps
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- argo cd
slug: argocd-gitops-naftikocapability-runbook
source_filename: argocd-gitops-naftikocapability-runbook.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Argocd Gitops Naftikocapability Runbook\n  description: A runbook capability over Argo CD that exposes capability deployment as a GitOps-driven Naftiko flow with sync/rollback as MCP tools.\n  tags: [Naftiko, Argo CD, GitOps]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: argocd-env\n  keys: {ARGOCD_HOST: ARGOCD_HOST, ARGOCD_TOKEN: ARGOCD_TOKEN}\ncapability:\n  consumes:\n  - namespace: argocd\n    type: http\n    baseUri: https://{{ARGOCD_HOST}}\n    authentication: {type: bearer, token: '{{ARGOCD_TOKEN}}'}\n    resources:\n    - {name: applications, path: /api/v1/applications, operations: [{name: list-applications, method: GET}]}\n    - name: application\n      path: /api/v1/applications/{{name}}\n      operations:\n      - {name: get-application, method: GET, inputParameters: [{name: name, in: path}]}\n    - name: app-sync\n      path: /api/v1/applications/{{name}}/sync\n      operations:\n      - {name: sync-application,\
  \ method: POST, inputParameters: [{name: name, in: path}]}\n    - name: app-rollback\n      path: /api/v1/applications/{{name}}/rollback\n      operations:\n      - {name: rollback-application, method: POST, inputParameters: [{name: name, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: argocd-gitops-naftikocapability-runbook-rest\n    description: REST surface exposing Argo CD sync and rollback for capability runbooks.\n    resources:\n    - name: sync\n      path: /apps/{{name}}/sync\n      operations:\n      - {method: POST, name: sync-app, inputParameters: [{name: name, in: path, type: string}], call: argocd.sync-application}\n    - name: rollback\n      path: /apps/{{name}}/rollback\n      operations:\n      - {method: POST, name: rollback-app, inputParameters: [{name: name, in: path, type: string}], call: argocd.rollback-application}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: argocd-gitops-naftikocapability-runbook-mcp\n\
  \    description: MCP for Argo CD GitOps operations on Naftiko capabilities.\n    tools:\n    - {name: list-apps, hints: {readOnly: true}, call: argocd.list-applications}\n    - name: sync-app\n      inputParameters: [{name: name, type: string, required: true}]\n      call: argocd.sync-application\n    - name: rollback-app\n      inputParameters: [{name: name, type: string, required: true}]\n      call: argocd.rollback-application\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: argocd-gitops-naftikocapability-runbook-skills\n    description: Skill for Argo CD runbook ops.\n    skills:\n    - name: argocd-gitops-naftikocapability-runbook\n      description: GitOps-driven sync/rollback for Naftiko capabilities.\n      location: file:///opt/naftiko/skills/argocd-gitops-naftikocapability-runbook\n      allowed-tools: list-apps,sync-app,rollback-app\n      tools:\n      - {name: list-apps, from: {sourceNamespace: argocd-gitops-naftikocapability-runbook-mcp, action: list-apps}}\n\
  \      - {name: sync-app, from: {sourceNamespace: argocd-gitops-naftikocapability-runbook-mcp, action: sync-app}}\n      - {name: rollback-app, from: {sourceNamespace: argocd-gitops-naftikocapability-runbook-mcp, action: rollback-app}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/argocd-gitops-naftikocapability-runbook.yaml
tags:
- Naftiko
- Argo CD
- GitOps
tools:
- description: ''
  hints:
    readOnly: true
  name: list-apps
- description: ''
  hints: {}
  name: sync-app
- description: ''
  hints: {}
  name: rollback-app
---
