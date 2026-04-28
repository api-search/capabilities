---
categories:
- container-orchestration
consumed_apis:
- argocd
description: Unified capability for GitOps-driven continuous delivery using Argo CD. Combines application management, cluster registration, repository configuration, and project governance for Platform Engineers and DevOps teams.
layout: capability
name: Argo CD GitOps Delivery
operations:
- description: List all deployed applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Deploy a new application from Git
  method: POST
  name: create-application
  path: /v1/applications
- description: Get application details and sync status
  method: GET
  name: get-application
  path: /v1/applications/{name}
- description: Remove an application
  method: DELETE
  name: delete-application
  path: /v1/applications/{name}
- description: Trigger application sync from Git
  method: POST
  name: sync-application
  path: /v1/applications/{name}/sync
- description: List registered Kubernetes clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: List configured Git repositories
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: List all Argo CD projects
  method: GET
  name: list-projects
  path: /v1/projects
personas: []
provider_name: Argo CD
provider_slug: argo-cd
search_terms:
- continuous delivery
- gitops application lifecycle management
- get application details and sync status
- platform engineering
- list all kubernetes clusters registered with argo cd
- trigger application sync from git
- gitops
- list repositories
- list accounts
- deployment
- list all argo cd projects
- list all argo cd applications with their sync and health status
- kubernetes
- list all deployed applications
- delete application
- automated application deployment and lifecycle management
- kubernetes cluster registry
- list registered kubernetes clusters
- list configured git repositories
- list all git repositories configured in argo cd
- end-to-end gitops continuous delivery combining application lifecycle, cluster management, and repository configuration
- manages the argo cd platform, clusters, and project rbac
- argo cd
- get detailed status of an argo cd application including resource tree
- deploy a new application from git
- delete an argo cd application and optionally cascade delete resources
- application synchronization
- list applications
- project and rbac management
- DevOps Engineer
- Platform Engineer
- container orchestration platform
- containers
- deploy a new application by creating an argo cd application resource
- list projects
- sync application
- trigger an argo cd application sync to reconcile desired git state
- cncf
- open source
- list all argo cd user accounts
- deploys and manages applications using gitops workflows
- single application management
- list clusters
- remove an application
- list all argo cd projects and their rbac policies
- git repository configuration
- git as single source of truth for infrastructure and application state
- create application
- get application
slug: gitops-delivery
tags:
- Argo CD
- GitOps
- Kubernetes
- Continuous Delivery
- Platform Engineering
tools:
- description: List all Argo CD applications with their sync and health status
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get detailed status of an Argo CD application including resource tree
  hints:
    openWorld: false
    readOnly: true
  name: get-application
- description: Deploy a new application by creating an Argo CD Application resource
  hints:
    destructive: false
    readOnly: false
  name: create-application
- description: Trigger an Argo CD application sync to reconcile desired Git state
  hints:
    destructive: false
    readOnly: false
  name: sync-application
- description: Delete an Argo CD application and optionally cascade delete resources
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-application
- description: List all Kubernetes clusters registered with Argo CD
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: List all Git repositories configured in Argo CD
  hints:
    openWorld: true
    readOnly: true
  name: list-repositories
- description: List all Argo CD projects and their RBAC policies
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: List all Argo CD user accounts
  hints:
    readOnly: true
  name: list-accounts
---
