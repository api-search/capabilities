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
- Platform Engineer
- deploy a new application by creating an argo cd application resource
- automated application deployment and lifecycle management
- DevOps Engineer
- delete application
- list all git repositories configured in argo cd
- list applications
- list clusters
- delete an argo cd application and optionally cascade delete resources
- deploys and manages applications using gitops workflows
- cncf
- sync application
- git as single source of truth for infrastructure and application state
- argo cd
- list accounts
- list all argo cd projects
- project and rbac management
- list all deployed applications
- gitops application lifecycle management
- git repository configuration
- list projects
- list all kubernetes clusters registered with argo cd
- get detailed status of an argo cd application including resource tree
- gitops
- manages the argo cd platform, clusters, and project rbac
- list configured git repositories
- kubernetes cluster registry
- single application management
- list all argo cd projects and their rbac policies
- trigger an argo cd application sync to reconcile desired git state
- platform engineering
- open source
- deployment
- application synchronization
- kubernetes
- get application details and sync status
- containers
- list registered kubernetes clusters
- continuous delivery
- create application
- deploy a new application from git
- trigger application sync from git
- remove an application
- get application
- end-to-end gitops continuous delivery combining application lifecycle, cluster management, and repository configuration
- container orchestration platform
- list all argo cd applications with their sync and health status
- list all argo cd user accounts
- list repositories
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
