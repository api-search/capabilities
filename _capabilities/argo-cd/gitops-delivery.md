---
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
- automated application deployment and lifecycle management
- get application
- list all kubernetes clusters registered with argo cd
- get detailed status of an argo cd application including resource tree
- list all argo cd projects and their rbac policies
- list clusters
- Platform Engineer
- deploy a new application from git
- gitops application lifecycle management
- list all argo cd user accounts
- gitops
- containers
- deployment
- deploys and manages applications using gitops workflows
- kubernetes
- list accounts
- list registered kubernetes clusters
- list all argo cd applications with their sync and health status
- list all deployed applications
- list applications
- list all git repositories configured in argo cd
- remove an application
- delete an argo cd application and optionally cascade delete resources
- continuous delivery
- DevOps Engineer
- git repository configuration
- kubernetes cluster registry
- application synchronization
- trigger an argo cd application sync to reconcile desired git state
- platform engineering
- container orchestration platform
- sync application
- list repositories
- list configured git repositories
- cncf
- list all argo cd projects
- delete application
- list projects
- trigger application sync from git
- manages the argo cd platform, clusters, and project rbac
- deploy a new application by creating an argo cd application resource
- end-to-end gitops continuous delivery combining application lifecycle, cluster management, and repository configuration
- single application management
- project and rbac management
- git as single source of truth for infrastructure and application state
- argo cd
- create application
- open source
- get application details and sync status
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
