---
categories:
- container-orchestration
consumed_apis: []
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
- trigger application sync from git
- list all argo cd projects
- list all deployed applications
- deploys and manages applications using gitops workflows
- trigger an argo cd application sync to reconcile desired git state
- delete an argo cd application and optionally cascade delete resources
- DevOps Engineer
- list all argo cd user accounts
- automated application deployment and lifecycle management
- list all git repositories configured in argo cd
- platform engineering
- list all argo cd projects and their rbac policies
- list repositories
- deployment
- list registered kubernetes clusters
- end-to-end gitops continuous delivery combining application lifecycle, cluster management, and repository configuration
- containers
- kubernetes
- kubernetes cluster registry
- list all kubernetes clusters registered with argo cd
- open source
- gitops
- argo cd
- git as single source of truth for infrastructure and application state
- sync application
- container orchestration platform
- delete application
- deploy a new application by creating an argo cd application resource
- single application management
- get application details and sync status
- cncf
- gitops application lifecycle management
- list projects
- list all argo cd applications with their sync and health status
- Platform Engineer
- list configured git repositories
- project and rbac management
- list accounts
- create application
- manages the argo cd platform, clusters, and project rbac
- continuous delivery
- get application
- application synchronization
- deploy a new application from git
- list applications
- git repository configuration
- get detailed status of an argo cd application including resource tree
- remove an application
- list clusters
slug: gitops-delivery
source_filename: gitops-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Argo CD GitOps Delivery\n  description: Unified capability for GitOps-driven continuous delivery using Argo CD. Combines application management, cluster\n    registration, repository configuration, and project governance for Platform Engineers and DevOps teams.\n  tags:\n  - Argo CD\n  - GitOps\n  - Kubernetes\n  - Continuous Delivery\n  - Platform Engineering\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ARGOCD_TOKEN: ARGOCD_TOKEN\n    ARGOCD_SERVER: ARGOCD_SERVER\ncapability:\n  consumes:\n  - type: http\n    namespace: argocd\n    baseUri: '{{env.ARGOCD_SERVER}}/api/v1'\n    description: Argo CD REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Bearer {{env.ARGOCD_TOKEN}}\n      placement: header\n    resources:\n    - name: applications\n      path: /application\n      description: Manage Argo CD applications\n      operations:\n      - name: list-applications\n\
  \        method: GET\n        description: List all applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Create a new application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            metadata: '{{tools.metadata}}'\n            spec: '{{tools.spec}}'\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sync-application\n        method: POST\n    \
  \    description: Sync an application\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-application\n        method: DELETE\n        description: Delete an application\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /cluster\n      description: Manage Kubernetes clusters\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List registered clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Register a new cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            server: '{{tools.server}}'\n            name: '{{tools.name}}'\n    - name: repositories\n      path: /repositories\n      description: Manage Git repositories\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List configured repositories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repository\n        method: POST\n        description: Add a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            repo: '{{tools.repo}}'\n    - name: projects\n      path: /projects\n      description: Manage Argo CD projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            metadata: '{{tools.metadata}}'\n            spec: '{{tools.spec}}'\n    - name: accounts\n      path: /account\n      description: Manage user accounts and tokens\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all accounts\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gitops-delivery-api\n    description: Unified REST API for GitOps continuous delivery with Argo CD.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: GitOps application lifecycle management\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all deployed applications\n        call: argocd.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-application\n        description: Deploy a new application from Git\n        call: argocd.create-application\n        with:\n          metadata: rest.metadata\n          spec: rest.spec\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{name}\n      name: application\n      description: Single application\
  \ management\n      operations:\n      - method: GET\n        name: get-application\n        description: Get application details and sync status\n        call: argocd.get-application\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-application\n        description: Remove an application\n        call: argocd.delete-application\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{name}/sync\n      name: application-sync\n      description: Application synchronization\n      operations:\n      - method: POST\n        name: sync-application\n        description: Trigger application sync from Git\n        call: argocd.sync-application\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters\n      name:\
  \ clusters\n      description: Kubernetes cluster registry\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List registered Kubernetes clusters\n        call: argocd.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories\n      name: repositories\n      description: Git repository configuration\n      operations:\n      - method: GET\n        name: list-repositories\n        description: List configured Git repositories\n        call: argocd.list-repositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Project and RBAC management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all Argo CD projects\n        call: argocd.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n \
  \   namespace: gitops-delivery-mcp\n    transport: http\n    description: MCP server for AI-assisted GitOps delivery with Argo CD.\n    tools:\n    - name: list-applications\n      description: List all Argo CD applications with their sync and health status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argocd.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get detailed status of an Argo CD application including resource tree\n      hints:\n        readOnly: true\n        openWorld: false\n      call: argocd.get-application\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Deploy a new application by creating an Argo CD Application resource\n      hints:\n        readOnly: false\n        destructive: false\n      call: argocd.create-application\n      with:\n     \
  \   metadata: tools.metadata\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-application\n      description: Trigger an Argo CD application sync to reconcile desired Git state\n      hints:\n        readOnly: false\n        destructive: false\n      call: argocd.sync-application\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-application\n      description: Delete an Argo CD application and optionally cascade delete resources\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: argocd.delete-application\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clusters\n      description: List all Kubernetes clusters registered with Argo CD\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argocd.list-clusters\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-repositories\n      description: List all Git repositories configured in Argo CD\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argocd.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all Argo CD projects and their RBAC policies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argocd.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List all Argo CD user accounts\n      hints:\n        readOnly: true\n      call: argocd.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/argo-cd/refs/heads/main/capabilities/gitops-delivery.yaml
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
