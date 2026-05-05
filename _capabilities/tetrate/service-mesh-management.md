---
api_specs:
- filename: tetrate-service-bridge-openapi.yml
  format: yaml
  label: tsb
  slug: tsb
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tetrate/refs/heads/main/openapi/tetrate-service-bridge-openapi.yml
categories: []
consumed_apis:
- tsb
description: Unified service mesh management capability for platform engineers and DevOps teams. Composes Tetrate Service Bridge management APIs to enable multi-cluster mesh onboarding, tenant provisioning, workspace configuration, and application API lifecycle management from a single interface.
layout: capability
name: Tetrate Service Mesh Management
operations:
- description: List all TSB organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Create a new TSB organization
  method: POST
  name: create-organization
  path: /v1/organizations
- description: List all tenants in an organization
  method: GET
  name: list-tenants
  path: /v1/tenants
- description: Create a new tenant
  method: POST
  name: create-tenant
  path: /v1/tenants
- description: List all workspaces in a tenant
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create a new workspace with namespace assignments
  method: POST
  name: create-workspace
  path: /v1/workspaces
- description: List all onboarded clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Onboard a new Kubernetes cluster
  method: POST
  name: onboard-cluster
  path: /v1/clusters
- description: List all applications in a tenant
  method: GET
  name: list-applications
  path: /v1/applications
- description: Create a new application
  method: POST
  name: create-application
  path: /v1/applications
- description: List all APIs for an application
  method: GET
  name: list-apis
  path: /v1/apis
- description: Register an OpenAPI spec as an API
  method: POST
  name: register-api
  path: /v1/apis
personas: []
provider_name: Tetrate
provider_slug: tetrate
search_terms:
- list organizations
- create a new application
- create tenant
- multi-cluster
- create a new workspace with namespace selector
- get details of a specific tsb organization
- manage tsb applications
- list all tenants within a tsb organization
- tetrate
- manage onboarded kubernetes clusters
- register api
- create application
- enterprise
- create a new tsb organization
- list all workspaces in a tenant
- list all applications in a tsb tenant
- service mesh
- create a new tsb application linked to a workspace
- manage application apis
- onboard a new kubernetes cluster to tsb management
- onboard a new kubernetes cluster
- list all apis for an application
- platform engineering
- list all applications in a tenant
- create a new tenant within a tsb organization
- devops
- list all tsb organizations
- list tenants
- list all kubernetes clusters onboarded to tsb
- envoy
- onboard cluster
- list applications
- create organization
- list apis
- get tenant
- get details of a specific tsb tenant
- list all workspaces within a tenant
- list workspaces
- list clusters
- list all onboarded clusters
- istio
- create a new tenant
- manage tsb organizations
- manage tsb tenants
- list all apis registered to a tsb application
- register an openapi v3 spec as a managed api in tsb
- register an openapi spec as an api
- list all tenants in an organization
- get organization
- kubernetes
- create workspace
- create a new workspace with namespace assignments
- manage tsb workspaces
slug: service-mesh-management
source_filename: service-mesh-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tetrate Service Mesh Management\"\n  description: >-\n    Unified service mesh management capability for platform engineers and\n    DevOps teams. Composes Tetrate Service Bridge management APIs to enable\n    multi-cluster mesh onboarding, tenant provisioning, workspace configuration,\n    and application API lifecycle management from a single interface.\n  tags:\n    - Tetrate\n    - Service Mesh\n    - Istio\n    - Multi-Cluster\n    - Platform Engineering\n    - DevOps\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TSB_TOKEN: TSB_TOKEN\n\ncapability:\n  consumes:\n    - import: tsb\n      location: ./shared/tetrate-service-bridge.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tetrate-mesh-api\n      description: \"Unified REST API for Tetrate service mesh management.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n\
  \          description: \"Manage TSB organizations\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all TSB organizations\"\n              call: \"tsb.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-organization\n              description: \"Create a new TSB organization\"\n              call: \"tsb.create-organization\"\n              with:\n                name: \"rest.name\"\n                displayName: \"rest.displayName\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tenants\n          name: tenants\n          description: \"Manage TSB tenants\"\n          operations:\n            - method: GET\n              name: list-tenants\n              description:\
  \ \"List all tenants in an organization\"\n              call: \"tsb.list-tenants\"\n              with:\n                organization: \"rest.organization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tenant\n              description: \"Create a new tenant\"\n              call: \"tsb.create-tenant\"\n              with:\n                organization: \"rest.organization\"\n                name: \"rest.name\"\n                displayName: \"rest.displayName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Manage TSB workspaces\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List all workspaces in a tenant\"\n              call: \"tsb.list-workspaces\"\n            \
  \  with:\n                organization: \"rest.organization\"\n                tenant: \"rest.tenant\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace\n              description: \"Create a new workspace with namespace assignments\"\n              call: \"tsb.create-workspace\"\n              with:\n                organization: \"rest.organization\"\n                tenant: \"rest.tenant\"\n                name: \"rest.name\"\n                namespaces: \"rest.namespaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters\n          name: clusters\n          description: \"Manage onboarded Kubernetes clusters\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all onboarded clusters\"\n              call: \"tsb.list-clusters\"\
  \n              with:\n                organization: \"rest.organization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: onboard-cluster\n              description: \"Onboard a new Kubernetes cluster\"\n              call: \"tsb.create-cluster\"\n              with:\n                organization: \"rest.organization\"\n                name: \"rest.name\"\n                network: \"rest.network\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications\n          name: applications\n          description: \"Manage TSB applications\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications in a tenant\"\n              call: \"tsb.list-applications\"\n              with:\n                organization: \"rest.organization\"\n \
  \               tenant: \"rest.tenant\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application\n              description: \"Create a new application\"\n              call: \"tsb.create-application\"\n              with:\n                organization: \"rest.organization\"\n                tenant: \"rest.tenant\"\n                name: \"rest.name\"\n                workspace: \"rest.workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apis\n          name: apis\n          description: \"Manage application APIs\"\n          operations:\n            - method: GET\n              name: list-apis\n              description: \"List all APIs for an application\"\n              call: \"tsb.list-apis\"\n              with:\n                organization: \"rest.organization\"\n                tenant: \"\
  rest.tenant\"\n                application: \"rest.application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-api\n              description: \"Register an OpenAPI spec as an API\"\n              call: \"tsb.create-api\"\n              with:\n                organization: \"rest.organization\"\n                tenant: \"rest.tenant\"\n                application: \"rest.application\"\n                name: \"rest.name\"\n                openapi: \"rest.openapi\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tetrate-mesh-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tetrate service mesh management.\"\n      tools:\n        - name: list-organizations\n          description: \"List all TSB organizations\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"tsb.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tenants\n          description: \"List all tenants within a TSB organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsb.list-tenants\"\n          with:\n            organization: \"tools.organization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-tenant\n          description: \"Create a new tenant within a TSB organization\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tsb.create-tenant\"\n          with:\n            organization: \"tools.organization\"\n            name: \"tools.name\"\n            displayName: \"tools.displayName\"\n            description: \"tools.description\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-workspaces\n          description: \"List all workspaces within a tenant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsb.list-workspaces\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-workspace\n          description: \"Create a new workspace with namespace selector\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tsb.create-workspace\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n            name: \"tools.name\"\n            namespaces: \"tools.namespaces\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n\n        - name: list-clusters\n          description: \"List all Kubernetes clusters onboarded to TSB\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsb.list-clusters\"\n          with:\n            organization: \"tools.organization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: onboard-cluster\n          description: \"Onboard a new Kubernetes cluster to TSB management\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tsb.create-cluster\"\n          with:\n            organization: \"tools.organization\"\n            name: \"tools.name\"\n            network: \"tools.network\"\n            tier1Cluster: \"tools.tier1Cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-applications\n          description:\
  \ \"List all applications in a TSB tenant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsb.list-applications\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-application\n          description: \"Create a new TSB application linked to a workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tsb.create-application\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n            name: \"tools.name\"\n            workspace: \"tools.workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-apis\n          description: \"List all APIs registered to a TSB application\"\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsb.list-apis\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n            application: \"tools.application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: register-api\n          description: \"Register an OpenAPI v3 spec as a managed API in TSB\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tsb.create-api\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n            application: \"tools.application\"\n            name: \"tools.name\"\n            openapi: \"tools.openapi\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-organization\n          description: \"Get details of\
  \ a specific TSB organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tsb.get-organization\"\n          with:\n            organization: \"tools.organization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-tenant\n          description: \"Get details of a specific TSB tenant\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tsb.get-tenant\"\n          with:\n            organization: \"tools.organization\"\n            tenant: \"tools.tenant\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tetrate/refs/heads/main/capabilities/service-mesh-management.yaml
tags:
- Tetrate
- Service Mesh
- Istio
- Multi-Cluster
- Platform Engineering
- DevOps
tools:
- description: List all TSB organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List all tenants within a TSB organization
  hints:
    openWorld: true
    readOnly: true
  name: list-tenants
- description: Create a new tenant within a TSB organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-tenant
- description: List all workspaces within a tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Create a new workspace with namespace selector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workspace
- description: List all Kubernetes clusters onboarded to TSB
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Onboard a new Kubernetes cluster to TSB management
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: onboard-cluster
- description: List all applications in a TSB tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Create a new TSB application linked to a workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-application
- description: List all APIs registered to a TSB application
  hints:
    openWorld: true
    readOnly: true
  name: list-apis
- description: Register an OpenAPI v3 spec as a managed API in TSB
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: register-api
- description: Get details of a specific TSB organization
  hints:
    openWorld: false
    readOnly: true
  name: get-organization
- description: Get details of a specific TSB tenant
  hints:
    openWorld: false
    readOnly: true
  name: get-tenant
---
