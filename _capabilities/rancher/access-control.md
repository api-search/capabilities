---
api_specs:
- filename: rancher-management-api-openapi.yml
  format: yaml
  label: rancher
  slug: rancher
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/rancher/refs/heads/main/openapi/rancher-management-api-openapi.yml
categories: []
consumed_apis:
- rancher
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
- containers
- list users
- create token
- rbac role templates.
- multi-cluster
- rancher user accounts.
- open source
- cluster management
- list all api tokens issued in rancher, including their expiry and description.
- rancher
- rbac
- list all role templates.
- platform engineering
- users
- api tokens.
- list tokens
- access control
- create a new api token.
- create a new api token for programmatic access to the rancher api.
- suse
- list role templates
- tokens
- list all users.
- list all rbac role templates defining permissions across clusters and projects.
- kubernetes
- list all rancher users with their enabled status and login information.
- list all api tokens.
slug: access-control
source_filename: access-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Rancher Access Control\"\n  description: >-\n    Workflow capability for managing users, roles, tokens, and access policies in\n    Rancher. Enables platform administrators to provision users, assign role templates,\n    manage API tokens, and enforce RBAC across multi-cluster environments.\n  tags:\n    - Access Control\n    - RBAC\n    - Users\n    - Tokens\n    - Kubernetes\n    - Rancher\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RANCHER_BEARER_TOKEN: RANCHER_BEARER_TOKEN\n      RANCHER_HOST: RANCHER_HOST\n\ncapability:\n  consumes:\n    - import: rancher\n      location: ./shared/rancher-management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: rancher-access-control-api\n      description: \"Unified REST API for Rancher access control management.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description:\
  \ \"Rancher user accounts.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users.\"\n              call: \"rancher.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tokens\n          name: tokens\n          description: \"API tokens.\"\n          operations:\n            - method: GET\n              name: list-tokens\n              description: \"List all API tokens.\"\n              call: \"rancher.list-tokens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-token\n              description: \"Create a new API token.\"\n              call: \"rancher.create-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/role-templates\n          name: role-templates\n\
  \          description: \"RBAC role templates.\"\n          operations:\n            - method: GET\n              name: list-role-templates\n              description: \"List all role templates.\"\n              call: \"rancher.list-role-templates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: rancher-access-control-mcp\n      transport: http\n      description: \"MCP server for AI-assisted access control management in Rancher.\"\n      tools:\n        - name: list-users\n          description: \"List all Rancher users with their enabled status and login information.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rancher.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tokens\n          description: \"List all API tokens issued in Rancher, including their\
  \ expiry and description.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rancher.list-tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-token\n          description: \"Create a new API token for programmatic access to the Rancher API.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rancher.create-token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-role-templates\n          description: \"List all RBAC role templates defining permissions across clusters and projects.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rancher.list-role-templates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
