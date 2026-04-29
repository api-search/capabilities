---
categories: []
consumed_apis:
- akamai-edgeworkers
- akamai-network-lists
description: Unified workflow for managing Akamai edge platform resources including EdgeWorkers serverless functions, network lists, and property configurations. For platform engineers and DevOps teams managing Akamai delivery configurations.
layout: capability
name: Akamai Edge Platform Management
operations:
- description: List EdgeWorker identifiers
  method: GET
  name: list-edgeworkers
  path: /v1/edgeworkers
- description: Create EdgeWorker
  method: POST
  name: create-edgeworker
  path: /v1/edgeworkers
- description: List network lists
  method: GET
  name: list-network-lists
  path: /v1/network-lists
personas: []
provider_name: Akamai
provider_slug: akamai
search_terms:
- list all akamai edgeworker serverless functions
- DevOps Engineer
- automates akamai configuration deployment via ci/cd pipelines
- list network lists
- manages akamai property configurations and edge deployments
- cdn
- manage akamai edge platform including edgeworkers and network lists
- create edgeworker
- network list management
- list edgeworker identifiers
- edge computing
- network lists and access control for ip and geographic filtering
- edgeworker serverless function management
- network security
- akamai
- content delivery property management and configuration
- platform management
- list edgeworkers
- Platform Engineer
- platform
- edgeworkers serverless execution and edgekv storage at the edge
- cloud
- list all akamai network lists for ip and geographic access control
- create a new akamai edgeworker serverless function
- security
- networks
slug: edge-platform-management
source_filename: edge-platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Akamai Edge Platform Management\"\n  description: \"Unified workflow for managing Akamai edge platform resources including EdgeWorkers serverless functions, network lists, and property configurations. For platform engineers and DevOps teams managing Akamai delivery configurations.\"\n  tags:\n    - Akamai\n    - CDN\n    - Edge Computing\n    - Platform Management\n    - Network Security\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AKAMAI_CLIENT_TOKEN: AKAMAI_CLIENT_TOKEN\n      AKAMAI_CLIENT_SECRET: AKAMAI_CLIENT_SECRET\n      AKAMAI_ACCESS_TOKEN: AKAMAI_ACCESS_TOKEN\n      AKAMAI_EDGEGRID_HOST: AKAMAI_EDGEGRID_HOST\ncapability:\n  consumes:\n    - import: akamai-edgeworkers\n      location: ./shared/edgeworkers.yaml\n    - import: akamai-network-lists\n      location: ./shared/network-lists.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: edge-platform-management-api\n\
  \      description: \"Unified REST API for Akamai edge platform management.\"\n      resources:\n        - path: /v1/edgeworkers\n          name: edgeworkers\n          description: \"EdgeWorker serverless function management\"\n          operations:\n            - method: GET\n              name: list-edgeworkers\n              description: \"List EdgeWorker identifiers\"\n              call: \"akamai-edgeworkers.list-edgeworkers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-edgeworker\n              description: \"Create EdgeWorker\"\n              call: \"akamai-edgeworkers.create-edgeworker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/network-lists\n          name: network-lists\n          description: \"Network list management\"\n          operations:\n            - method: GET\n              name:\
  \ list-network-lists\n              description: \"List network lists\"\n              call: \"akamai-network-lists.list-network-lists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: edge-platform-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Akamai edge platform management.\"\n      tools:\n        - name: list-edgeworkers\n          description: \"List all Akamai EdgeWorker serverless functions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"akamai-edgeworkers.list-edgeworkers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-edgeworker\n          description: \"Create a new Akamai EdgeWorker serverless function\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"akamai-edgeworkers.create-edgeworker\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-network-lists\n          description: \"List all Akamai network lists for IP and geographic access control\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"akamai-network-lists.list-network-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/akamai/refs/heads/main/capabilities/edge-platform-management.yaml
tags:
- Akamai
- CDN
- Edge Computing
- Platform Management
- Network Security
tools:
- description: List all Akamai EdgeWorker serverless functions
  hints:
    openWorld: true
    readOnly: true
  name: list-edgeworkers
- description: Create a new Akamai EdgeWorker serverless function
  hints:
    destructive: false
    readOnly: false
  name: create-edgeworker
- description: List all Akamai network lists for IP and geographic access control
  hints:
    openWorld: true
    readOnly: true
  name: list-network-lists
---
