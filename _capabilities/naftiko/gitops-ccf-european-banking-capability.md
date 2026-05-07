---
categories: []
consumed_apis: []
description: A capability combining GitOps deploys (Argo CD) with Continuous Compliance Framework (CCF) checks tailored for European banking regulators.
layout: capability
name: Gitops Ccf European Banking Capability
operations:
- description: ''
  method: POST
  name: deploy-with-compliance
  path: /deploy-with-compliance/{{name}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- gitops
- governance
- deploy with compliance
- list apps
- ccf
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- naftiko
- european banking
slug: gitops-ccf-european-banking-capability
source_filename: gitops-ccf-european-banking-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Gitops Ccf European Banking Capability\n  description: A capability combining GitOps deploys (Argo CD) with Continuous Compliance Framework (CCF) checks tailored for European banking regulators.\n  tags: [Naftiko, GitOps, CCF, European Banking]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: argocd-env\n  keys: {ARGOCD_HOST: ARGOCD_HOST, ARGOCD_TOKEN: ARGOCD_TOKEN}\n- namespace: ccf-env\n  keys: {CCF_HOST: CCF_HOST, CCF_TOKEN: CCF_TOKEN}\ncapability:\n  consumes:\n  - namespace: argocd\n    type: http\n    baseUri: https://{{ARGOCD_HOST}}\n    authentication: {type: bearer, token: '{{ARGOCD_TOKEN}}'}\n    resources:\n    - {name: applications, path: /api/v1/applications, operations: [{name: list-applications, method: GET}]}\n    - name: app-sync\n      path: '/api/v1/applications/{{name}}/sync'\n      operations:\n      - {name: sync-application, method: POST, inputParameters: [{name: name, in: path}]}\n  - namespace:\
  \ ccf\n    type: http\n    baseUri: https://{{CCF_HOST}}\n    authentication: {type: bearer, token: '{{CCF_TOKEN}}'}\n    resources:\n    - {name: assessments, path: /api/v1/assessments, operations: [{name: run-assessment, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: gitops-ccf-european-banking-capability-rest\n    description: REST surface for GitOps + CCF for European banking.\n    resources:\n    - {name: deploy-with-compliance, path: '/deploy-with-compliance/{{name}}', operations: [{method: POST, name: deploy-with-compliance, inputParameters: [{name: name, in: path, type: string}], call: ccf.run-assessment}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: gitops-ccf-european-banking-capability-mcp\n    description: MCP for GitOps + CCF.\n    tools:\n    - {name: list-apps, hints: {readOnly: true}, call: argocd.list-applications}\n    - name: deploy-with-compliance\n      inputParameters: [{name: name, type:\
  \ string, required: true}]\n      call: ccf.run-assessment\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: gitops-ccf-european-banking-capability-skills\n    description: Skill for GitOps + CCF.\n    skills:\n    - name: gitops-ccf-european-banking-capability\n      description: GitOps + CCF for European banking.\n      location: file:///opt/naftiko/skills/gitops-ccf-european-banking-capability\n      allowed-tools: list-apps,deploy-with-compliance\n      tools:\n      - {name: list-apps, from: {sourceNamespace: gitops-ccf-european-banking-capability-mcp, action: list-apps}}\n      - {name: deploy-with-compliance, from: {sourceNamespace: gitops-ccf-european-banking-capability-mcp, action: deploy-with-compliance}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/gitops-ccf-european-banking-capability.yaml
tags:
- Naftiko
- GitOps
- CCF
- European Banking
tools:
- description: ''
  hints:
    readOnly: true
  name: list-apps
- description: ''
  hints: {}
  name: deploy-with-compliance
---
