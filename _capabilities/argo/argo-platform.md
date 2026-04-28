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
- platform engineering
- trigger an argo cd application sync from git
- workflow engine
- gitops
- uses argo tools for ci/cd and gitops workflows
- progressive delivery
- ci/cd
- list all argo cd applications with sync and health status
- manages kubernetes platform tools including argo workflows and argo cd
- applications list
- kubernetes
- workflow management
- list all argo workflows in a namespace
- argo
- applications sync
- workflows create
- create workflow
- list argo cd applications
- gitops application management
- list applications
- DevOps Engineer
- list all workflows
- Platform Engineer
- container orchestration platform
- list workflows
- sync application
- cncf
- sync an application from git
- open source
- submit a new workflow
- container-native workflow execution
- complete argo project platform combining workflows and cd for devops teams
- workflows list
- git-driven deployment and infrastructure management
- submit a new argo workflow
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
