---
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
- gitops
- submit a new argo workflow
- DevOps Engineer
- applications list
- git-driven deployment and infrastructure management
- create workflow
- kubernetes
- platform engineering
- manages kubernetes platform tools including argo workflows and argo cd
- Platform Engineer
- workflows list
- list all argo workflows in a namespace
- list all argo cd applications with sync and health status
- list workflows
- list applications
- list argo cd applications
- cncf
- open source
- sync application
- applications sync
- workflow engine
- gitops application management
- progressive delivery
- submit a new workflow
- container orchestration platform
- ci/cd
- list all workflows
- complete argo project platform combining workflows and cd for devops teams
- argo
- sync an application from git
- workflows create
- uses argo tools for ci/cd and gitops workflows
- trigger an argo cd application sync from git
- container-native workflow execution
- workflow management
slug: argo-platform
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
