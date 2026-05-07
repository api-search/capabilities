---
categories: []
consumed_apis: []
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
- manage tsb applications
- istio
- list all tenants in an organization
- list workspaces
- devops
- list all workspaces within a tenant
- create organization
- manage tsb organizations
- manage tsb tenants
- list all workspaces in a tenant
- create a new application
- multi-cluster
- manage onboarded kubernetes clusters
- get tenant
- tetrate
- create application
- list all applications in a tsb tenant
- service mesh
- list all applications in a tenant
- list all apis for an application
- list all kubernetes clusters onboarded to tsb
- create workspace
- register api
- onboard a new kubernetes cluster
- list clusters
- list all onboarded clusters
- kubernetes
- get details of a specific tsb organization
- onboard cluster
- list all tenants within a tsb organization
- list all tsb organizations
- list organizations
- manage application apis
- enterprise
- register an openapi v3 spec as a managed api in tsb
- list apis
- list tenants
- manage tsb workspaces
- envoy
- list applications
- create a new tenant within a tsb organization
- create a new workspace with namespace selector
- get details of a specific tsb tenant
- onboard a new kubernetes cluster to tsb management
- create a new tsb organization
- register an openapi spec as an api
- list all apis registered to a tsb application
- create a new tsb application linked to a workspace
- create tenant
- create a new tenant
- get organization
- create a new workspace with namespace assignments
- platform engineering
slug: service-mesh-management
source_filename: service-mesh-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tetrate Service Mesh Management\n  description: Unified service mesh management capability for platform engineers and DevOps teams. Composes Tetrate Service\n    Bridge management APIs to enable multi-cluster mesh onboarding, tenant provisioning, workspace configuration, and application\n    API lifecycle management from a single interface.\n  tags:\n  - Tetrate\n  - Service Mesh\n  - Istio\n  - Multi-Cluster\n  - Platform Engineering\n  - DevOps\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TSB_TOKEN: TSB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tsb\n    baseUri: https://tsbhost:8443/v2\n    description: Tetrate Service Bridge management plane REST API\n    authentication:\n      type: apikey\n      key: x-tetrate-token\n      value: '{{TSB_TOKEN}}'\n      placement: header\n    resources:\n    - name: organizations\n      path: /organizations\n      description: Manage\
  \ TSB organizations\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-organization\n        method: POST\n        description: Create a new organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            spec:\n              displayName: '{{tools.displayName}}'\n              description: '{{tools.description}}'\n    - name: organization\n      path: /organizations/{organization}\n      description: Manage a specific organization\n      operations:\n      - name: get-organization\n        method: GET\n        description: Get organization details\n        inputParameters:\n        - name: organization\n\
  \          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organization\n        method: DELETE\n        description: Delete an organization\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tenants\n      path: /organizations/{organization}/tenants\n      description: Manage tenants within an organization\n      operations:\n      - name: list-tenants\n        method: GET\n        description: List all tenants in an organization\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n    \
  \      required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tenant\n        method: POST\n        description: Create a new tenant\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            spec:\n              displayName: '{{tools.displayName}}'\n              description: '{{tools.description}}'\n    - name: tenant\n      path: /organizations/{organization}/tenants/{tenant}\n      description: Manage a specific tenant\n      operations:\n      - name: get-tenant\n        method: GET\n        description:\
  \ Get tenant details\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: tenant\n          in: path\n          type: string\n          required: true\n          description: Tenant name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-tenant\n        method: DELETE\n        description: Delete a tenant\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /organizations/{organization}/tenants/{tenant}/workspaces\n      description: Manage\
  \ workspaces within a tenant\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all workspaces in a tenant\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace\n        method: POST\n        description: Create a new workspace\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            name: '{{tools.name}}'\n            spec:\n              displayName: '{{tools.displayName}}'\n              namespaceSelector:\n                names: '{{tools.namespaces}}'\n    - name: clusters\n      path: /organizations/{organization}/clusters\n      description: Manage onboarded Kubernetes clusters\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all onboarded clusters\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Onboard a new Kubernetes cluster\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            spec:\n              network: '{{tools.network}}'\n              tier1Cluster: '{{tools.tier1Cluster}}'\n    - name: applications\n      path: /organizations/{organization}/tenants/{tenant}/applications\n      description: Manage applications within a tenant\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all applications in a tenant\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Create a new application\n        inputParameters:\n\
  \        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            spec:\n              workspace: '{{tools.workspace}}'\n    - name: apis\n      path: /organizations/{organization}/tenants/{tenant}/applications/{application}/apis\n      description: Manage APIs registered to an application\n      operations:\n      - name: list-apis\n        method: GET\n        description: List all APIs in an application\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        - name:\
  \ application\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api\n        method: POST\n        description: Register a new API using an OpenAPI v3 spec\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: tenant\n          in: path\n          type: string\n          required: true\n        - name: application\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            spec:\n              openapi: '{{tools.openapi}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tetrate-mesh-api\n\
  \    description: Unified REST API for Tetrate service mesh management.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: Manage TSB organizations\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all TSB organizations\n        call: tsb.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-organization\n        description: Create a new TSB organization\n        call: tsb.create-organization\n        with:\n          name: rest.name\n          displayName: rest.displayName\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tenants\n      name: tenants\n      description: Manage TSB tenants\n      operations:\n      - method: GET\n        name: list-tenants\n        description: List all tenants in an organization\n        call: tsb.list-tenants\n\
  \        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-tenant\n        description: Create a new tenant\n        call: tsb.create-tenant\n        with:\n          organization: rest.organization\n          name: rest.name\n          displayName: rest.displayName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Manage TSB workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces in a tenant\n        call: tsb.list-workspaces\n        with:\n          organization: rest.organization\n          tenant: rest.tenant\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workspace\n        description: Create a new workspace with namespace assignments\n\
  \        call: tsb.create-workspace\n        with:\n          organization: rest.organization\n          tenant: rest.tenant\n          name: rest.name\n          namespaces: rest.namespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters\n      name: clusters\n      description: Manage onboarded Kubernetes clusters\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all onboarded clusters\n        call: tsb.list-clusters\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: onboard-cluster\n        description: Onboard a new Kubernetes cluster\n        call: tsb.create-cluster\n        with:\n          organization: rest.organization\n          name: rest.name\n          network: rest.network\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/applications\n      name: applications\n      description: Manage TSB applications\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all applications in a tenant\n        call: tsb.list-applications\n        with:\n          organization: rest.organization\n          tenant: rest.tenant\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-application\n        description: Create a new application\n        call: tsb.create-application\n        with:\n          organization: rest.organization\n          tenant: rest.tenant\n          name: rest.name\n          workspace: rest.workspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis\n      name: apis\n      description: Manage application APIs\n      operations:\n      - method: GET\n        name: list-apis\n        description: List all APIs for an application\n        call:\
  \ tsb.list-apis\n        with:\n          organization: rest.organization\n          tenant: rest.tenant\n          application: rest.application\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-api\n        description: Register an OpenAPI spec as an API\n        call: tsb.create-api\n        with:\n          organization: rest.organization\n          tenant: rest.tenant\n          application: rest.application\n          name: rest.name\n          openapi: rest.openapi\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tetrate-mesh-mcp\n    transport: http\n    description: MCP server for AI-assisted Tetrate service mesh management.\n    tools:\n    - name: list-organizations\n      description: List all TSB organizations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsb.list-organizations\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-tenants\n      description: List all tenants within a TSB organization\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsb.list-tenants\n      with:\n        organization: tools.organization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-tenant\n      description: Create a new tenant within a TSB organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tsb.create-tenant\n      with:\n        organization: tools.organization\n        name: tools.name\n        displayName: tools.displayName\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all workspaces within a tenant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsb.list-workspaces\n      with:\n        organization:\
  \ tools.organization\n        tenant: tools.tenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace\n      description: Create a new workspace with namespace selector\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tsb.create-workspace\n      with:\n        organization: tools.organization\n        tenant: tools.tenant\n        name: tools.name\n        namespaces: tools.namespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clusters\n      description: List all Kubernetes clusters onboarded to TSB\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsb.list-clusters\n      with:\n        organization: tools.organization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: onboard-cluster\n      description: Onboard a new Kubernetes cluster to TSB management\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: tsb.create-cluster\n      with:\n        organization: tools.organization\n        name: tools.name\n        network: tools.network\n        tier1Cluster: tools.tier1Cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List all applications in a TSB tenant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsb.list-applications\n      with:\n        organization: tools.organization\n        tenant: tools.tenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Create a new TSB application linked to a workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tsb.create-application\n      with:\n        organization: tools.organization\n        tenant: tools.tenant\n        name: tools.name\n\
  \        workspace: tools.workspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-apis\n      description: List all APIs registered to a TSB application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsb.list-apis\n      with:\n        organization: tools.organization\n        tenant: tools.tenant\n        application: tools.application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-api\n      description: Register an OpenAPI v3 spec as a managed API in TSB\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tsb.create-api\n      with:\n        organization: tools.organization\n        tenant: tools.tenant\n        application: tools.application\n        name: tools.name\n        openapi: tools.openapi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization\n      description: Get\
  \ details of a specific TSB organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tsb.get-organization\n      with:\n        organization: tools.organization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tenant\n      description: Get details of a specific TSB tenant\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tsb.get-tenant\n      with:\n        organization: tools.organization\n        tenant: tools.tenant\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
