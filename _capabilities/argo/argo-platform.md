---
categories:
- container-orchestration
consumed_apis:
- argoworkflows
- argocd
description: Unified capability combining all Argo Project tools — Workflows, CD, Events, and Rollouts — for a complete Kubernetes-native DevOps and ML platform. Serves Platform Engineers and DevOps teams.
layout: capability
name: Argo Platform
operations:
- description: List all workflows
  method: GET
  name: list-workflows
  path: /v1/workflows/{namespace}
- description: Submit a new workflow
  method: POST
  name: create-workflow
  path: /v1/workflows/{namespace}
- description: List Argo CD applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Sync an application from Git
  method: POST
  name: sync-application
  path: /v1/applications
personas: []
provider_name: Argo
provider_slug: argo
search_terms:
- ci/cd
- list applications
- sync an application from git
- workflow management
- kubernetes
- list argo cd applications
- list all workflows
- git-driven deployment and infrastructure management
- workflow engine
- list all argo workflows in a namespace
- workflows list
- container-native workflow execution
- progressive delivery
- sync application
- list workflows
- container orchestration platform
- list all argo cd applications with sync and health status
- Platform Engineer
- gitops
- trigger an argo cd application sync from git
- manages kubernetes platform tools including argo workflows and argo cd
- platform engineering
- DevOps Engineer
- uses argo tools for ci/cd and gitops workflows
- complete argo project platform combining workflows and cd for devops teams
- submit a new argo workflow
- submit a new workflow
- gitops application management
- applications list
- applications sync
- create workflow
- workflows create
- open source
- cncf
- argo
slug: argo-platform
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Argo Platform\"\n  description: \"Unified capability combining all Argo Project tools — Workflows, CD, Events, and Rollouts — for a complete Kubernetes-native DevOps and ML platform. Serves Platform Engineers and DevOps teams.\"\n  tags:\n    - Argo\n    - GitOps\n    - Kubernetes\n    - Workflow Engine\n    - CNCF\n    - Platform Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ARGO_TOKEN: ARGO_TOKEN\n      ARGO_SERVER: ARGO_SERVER\n      ARGOCD_TOKEN: ARGOCD_TOKEN\n      ARGOCD_SERVER: ARGOCD_SERVER\n\ncapability:\n  consumes:\n    - import: argoworkflows\n      location: ./shared/argo-workflows-api.yaml\n    - import: argocd\n      location: ./shared/argo-cd-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: argo-platform-api\n      description: \"Unified REST API for the complete Argo Project platform.\"\n      resources:\n        -\
  \ path: /v1/workflows/{namespace}\n          name: workflows\n          description: \"Workflow management\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List all workflows\"\n              call: \"argoworkflows.list-workflows\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workflow\n              description: \"Submit a new workflow\"\n              call: \"argoworkflows.create-workflow\"\n              with:\n                namespace: \"rest.namespace\"\n                workflow: \"rest.workflow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"GitOps application management\"\n          operations:\n\
  \            - method: GET\n              name: list-applications\n              description: \"List Argo CD applications\"\n              call: \"argocd.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: sync-application\n              description: \"Sync an application from Git\"\n              call: \"argocd.sync-application\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: argo-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Argo platform operations.\"\n      tools:\n        - name: workflows-list\n          description: \"List all Argo Workflows in a namespace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"argoworkflows.list-workflows\"\
  \n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: workflows-create\n          description: \"Submit a new Argo Workflow\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"argoworkflows.create-workflow\"\n          with:\n            namespace: \"tools.namespace\"\n            workflow: \"tools.workflow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: applications-list\n          description: \"List all Argo CD applications with sync and health status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"argocd.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: applications-sync\n          description: \"Trigger an Argo CD application sync from Git\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n          call: \"argocd.sync-application\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/argo/refs/heads/main/capabilities/argo-platform.yaml
tags:
- Argo
- GitOps
- Kubernetes
- Workflow Engine
- CNCF
- Platform Engineering
tools:
- description: List all Argo Workflows in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: workflows-list
- description: Submit a new Argo Workflow
  hints:
    destructive: false
    readOnly: false
  name: workflows-create
- description: List all Argo CD applications with sync and health status
  hints:
    openWorld: true
    readOnly: true
  name: applications-list
- description: Trigger an Argo CD application sync from Git
  hints:
    destructive: false
    readOnly: false
  name: applications-sync
---
