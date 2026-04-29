---
categories: []
consumed_apis:
- knox-admin
description: Workflow capability for Hadoop administrators and security engineers to manage Knox gateway topologies, service descriptors, and provider configurations.
layout: capability
name: Apache Knox Gateway Management
operations:
- description: ''
  method: GET
  name: list-topologies
  path: /v1/topologies
- description: ''
  method: POST
  name: create-topology
  path: /v1/topologies
- description: ''
  method: DELETE
  name: delete-topology
  path: /v1/topologies
personas: []
provider_name: Apache Knox
provider_slug: apache-knox
search_terms:
- get knox version
- gateway management
- hadoop administration
- hadoop
- delete a knox gateway topology
- get topology
- list all knox gateway topologies and their service urls
- apache knox
- create or update a knox gateway topology
- list topologies
- Security Engineer
- sso
- security engineering
- api gateway
- engineers who configure authentication and authorization for knox
- open source
- create topology
- delete topology
- security
- admins who configure knox topologies for hadoop cluster access
- get the configuration details of a specific knox topology
- get apache knox gateway version information
- Hadoop Administrator
- authentication
slug: gateway-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache Knox Gateway Management\"\n  description: \"Workflow capability for Hadoop administrators and security engineers to manage Knox gateway topologies, service descriptors, and provider configurations.\"\n  tags:\n    - Apache Knox\n    - Gateway Management\n    - Hadoop Administration\n    - Security Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      KNOX_ADMIN_PASSWORD: KNOX_ADMIN_PASSWORD\n\ncapability:\n  consumes:\n    - import: knox-admin\n      location: ./shared/knox-admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: knox-gateway-management-api\n      description: \"Unified REST API for Apache Knox gateway management.\"\n      resources:\n        - path: /v1/topologies\n          name: topologies\n          operations:\n            - method: GET\n              name: list-topologies\n              call: \"knox-admin.list-topologies\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-topology\n              call: \"knox-admin.create-topology\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-topology\n              call: \"knox-admin.delete-topology\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: knox-gateway-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Knox gateway management.\"\n      tools:\n        - name: list-topologies\n          description: List all Knox gateway topologies and their service URLs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"knox-admin.list-topologies\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-topology\n          description: Get the configuration details of a specific Knox topology\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"knox-admin.get-topology\"\n          with:\n            topologyName: \"tools.topology_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-topology\n          description: Create or update a Knox gateway topology\n          hints:\n            readOnly: false\n          call: \"knox-admin.create-topology\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-topology\n          description: Delete a Knox gateway topology\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"knox-admin.delete-topology\"\n          with:\n            topologyName: \"tools.topology_name\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-knox-version\n          description: Get Apache Knox gateway version information\n          hints:\n            readOnly: true\n          call: \"knox-admin.get-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-knox/refs/heads/main/capabilities/gateway-management.yaml
tags:
- Apache Knox
- Gateway Management
- Hadoop Administration
- Security Engineering
tools:
- description: List all Knox gateway topologies and their service URLs
  hints:
    openWorld: true
    readOnly: true
  name: list-topologies
- description: Get the configuration details of a specific Knox topology
  hints:
    openWorld: true
    readOnly: true
  name: get-topology
- description: Create or update a Knox gateway topology
  hints:
    readOnly: false
  name: create-topology
- description: Delete a Knox gateway topology
  hints:
    destructive: true
    readOnly: false
  name: delete-topology
- description: Get Apache Knox gateway version information
  hints:
    readOnly: true
  name: get-knox-version
---
