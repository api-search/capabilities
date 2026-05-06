---
categories: []
consumed_apis: []
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
- gateway management
- get knox version
- delete a knox gateway topology
- list all knox gateway topologies and their service urls
- create topology
- security
- apache knox
- hadoop administration
- get topology
- Hadoop Administrator
- delete topology
- open source
- sso
- get apache knox gateway version information
- hadoop
- get the configuration details of a specific knox topology
- create or update a knox gateway topology
- authentication
- api gateway
- security engineering
- engineers who configure authentication and authorization for knox
- admins who configure knox topologies for hadoop cluster access
- list topologies
- Security Engineer
slug: gateway-management
source_filename: gateway-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Knox Gateway Management\n  description: Workflow capability for Hadoop administrators and security engineers to manage Knox gateway topologies, service\n    descriptors, and provider configurations.\n  tags:\n  - Apache Knox\n  - Gateway Management\n  - Hadoop Administration\n  - Security Engineering\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KNOX_ADMIN_PASSWORD: KNOX_ADMIN_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: knox-admin\n    baseUri: https://localhost:8443/gateway/admin\n    description: Apache Knox Admin REST API\n    authentication:\n      type: basic\n      username: admin\n      password: '{{KNOX_ADMIN_PASSWORD}}'\n    resources:\n    - name: topologies\n      path: /api/v1/topologies\n      description: Topology management\n      operations:\n      - name: list-topologies\n        method: GET\n        description: List all topologies\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-topology\n        method: POST\n        description: Create a topology\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-topology\n        method: GET\n        description: Get a topology\n        inputParameters:\n        - name: topologyName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-topology\n        method: DELETE\n        description: Delete a topology\n        inputParameters:\n        - name: topologyName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: knox-gateway-management-api\n    description: Unified REST API for Apache Knox gateway management.\n    resources:\n    - path: /v1/topologies\n      name: topologies\n      operations:\n      - method: GET\n        name: list-topologies\n        call: knox-admin.list-topologies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-topology\n        call: knox-admin.create-topology\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-topology\n        call: knox-admin.delete-topology\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: knox-gateway-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Knox gateway management.\n    tools:\n    - name: list-topologies\n      description:\
  \ List all Knox gateway topologies and their service URLs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: knox-admin.list-topologies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-topology\n      description: Get the configuration details of a specific Knox topology\n      hints:\n        readOnly: true\n        openWorld: true\n      call: knox-admin.get-topology\n      with:\n        topologyName: tools.topology_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-topology\n      description: Create or update a Knox gateway topology\n      hints:\n        readOnly: false\n      call: knox-admin.create-topology\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-topology\n      description: Delete a Knox gateway topology\n      hints:\n        readOnly: false\n        destructive: true\n      call: knox-admin.delete-topology\n      with:\n     \
  \   topologyName: tools.topology_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-knox-version\n      description: Get Apache Knox gateway version information\n      hints:\n        readOnly: true\n      call: knox-admin.get-version\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
