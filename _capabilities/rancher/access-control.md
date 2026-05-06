---
categories: []
consumed_apis: []
description: Workflow capability for managing users, roles, tokens, and access policies in Rancher. Enables platform administrators to provision users, assign role templates, manage API tokens, and enforce RBAC across multi-cluster environments.
layout: capability
name: Rancher Access Control
operations:
- description: List all users.
  method: GET
  name: list-users
  path: /v1/users
- description: List all API tokens.
  method: GET
  name: list-tokens
  path: /v1/tokens
- description: Create a new API token.
  method: POST
  name: create-token
  path: /v1/tokens
- description: List all role templates.
  method: GET
  name: list-role-templates
  path: /v1/role-templates
personas: []
provider_name: Rancher
provider_slug: rancher
search_terms:
- list all users.
- rancher user accounts.
- rancher
- users
- list all role templates.
- list all rbac role templates defining permissions across clusters and projects.
- platform engineering
- multi-cluster
- list tokens
- list role templates
- cluster management
- containers
- create a new api token.
- kubernetes
- open source
- rbac role templates.
- list all api tokens.
- tokens
- api tokens.
- create a new api token for programmatic access to the rancher api.
- access control
- rbac
- suse
- list users
- list all api tokens issued in rancher, including their expiry and description.
- list all rancher users with their enabled status and login information.
- create token
slug: access-control
source_filename: access-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rancher Access Control\n  description: Workflow capability for managing users, roles, tokens, and access policies in Rancher. Enables platform administrators\n    to provision users, assign role templates, manage API tokens, and enforce RBAC across multi-cluster environments.\n  tags:\n  - Access Control\n  - RBAC\n  - Users\n  - Tokens\n  - Kubernetes\n  - Rancher\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RANCHER_BEARER_TOKEN: RANCHER_BEARER_TOKEN\n    RANCHER_HOST: RANCHER_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: rancher\n    baseUri: https://{{RANCHER_HOST}}/v3\n    description: Rancher v3 Management API.\n    authentication:\n      type: bearer\n      token: '{{RANCHER_BEARER_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /clusters\n      description: Downstream Kubernetes clusters managed by Rancher.\n      operations:\n      - name: list-clusters\n\
  \        method: GET\n        description: List all clusters managed by Rancher.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Provision a new cluster.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            kubernetesVersion: '{{tools.kubernetesVersion}}'\n            provider: '{{tools.provider}}'\n    - name: cluster\n      path: /clusters/{id}\n      description: Single cluster resource.\n      operations:\n      - name: get-cluster\n        method: GET\n        description: Retrieve a single cluster by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Cluster identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cluster\n        method: DELETE\n        description: Remove a cluster from Rancher management.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Rancher projects grouping namespaces.\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create\
  \ a new project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /nodes\n      description: Cluster nodes.\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List all nodes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Rancher users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      description: API tokens.\n      operations:\n      - name: list-tokens\n        method: GET\n        description: List all API tokens.\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: create-token\n        method: POST\n        description: Create a new API token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalogs\n      path: /catalogs\n      description: Helm chart catalogs.\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List registered Helm catalogs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /apps\n      description: Deployed Helm applications.\n      operations:\n      - name: list-apps\n        method: GET\n        description: List deployed apps.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: role-templates\n      path: /roleTemplates\n\
  \      description: Role templates for RBAC.\n      operations:\n      - name: list-role-templates\n        method: GET\n        description: List all role templates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: rancher-access-control-api\n    description: Unified REST API for Rancher access control management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Rancher user accounts.\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users.\n        call: rancher.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: tokens\n      description: API tokens.\n      operations:\n      - method: GET\n        name: list-tokens\n        description: List all API tokens.\n        call: rancher.list-tokens\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-token\n        description: Create a new API token.\n        call: rancher.create-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/role-templates\n      name: role-templates\n      description: RBAC role templates.\n      operations:\n      - method: GET\n        name: list-role-templates\n        description: List all role templates.\n        call: rancher.list-role-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: rancher-access-control-mcp\n    transport: http\n    description: MCP server for AI-assisted access control management in Rancher.\n    tools:\n    - name: list-users\n      description: List all Rancher users with their enabled status and login information.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rancher.list-users\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tokens\n      description: List all API tokens issued in Rancher, including their expiry and description.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rancher.list-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-token\n      description: Create a new API token for programmatic access to the Rancher API.\n      hints:\n        readOnly: false\n        destructive: false\n      call: rancher.create-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-role-templates\n      description: List all RBAC role templates defining permissions across clusters and projects.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rancher.list-role-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rancher/refs/heads/main/capabilities/access-control.yaml
tags:
- Access Control
- RBAC
- Users
- Tokens
- Kubernetes
- Rancher
tools:
- description: List all Rancher users with their enabled status and login information.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: List all API tokens issued in Rancher, including their expiry and description.
  hints:
    openWorld: true
    readOnly: true
  name: list-tokens
- description: Create a new API token for programmatic access to the Rancher API.
  hints:
    destructive: false
    readOnly: false
  name: create-token
- description: List all RBAC role templates defining permissions across clusters and projects.
  hints:
    openWorld: true
    readOnly: true
  name: list-role-templates
---
