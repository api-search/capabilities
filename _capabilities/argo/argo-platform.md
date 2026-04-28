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
- workflow management
- list workflows
- list all argo workflows in a namespace
- sync an application from git
- list all argo cd applications with sync and health status
- kubernetes
- workflows list
- DevOps Engineer
- applications list
- progressive delivery
- create workflow
- manages kubernetes platform tools including argo workflows and argo cd
- list all workflows
- submit a new argo workflow
- complete argo project platform combining workflows and cd for devops teams
- applications sync
- submit a new workflow
- trigger an argo cd application sync from git
- uses argo tools for ci/cd and gitops workflows
- git-driven deployment and infrastructure management
- argo
- platform engineering
- ci/cd
- sync application
- Platform Engineer
- cncf
- gitops
- gitops application management
- list argo cd applications
- workflows create
- open source
- workflow engine
- list applications
- container-native workflow execution
- container orchestration platform
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
