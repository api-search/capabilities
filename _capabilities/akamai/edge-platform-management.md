---
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
- akamai
- content delivery property management and configuration
- platform management
- manage akamai edge platform including edgeworkers and network lists
- Platform Engineer
- edge computing
- create a new akamai edgeworker serverless function
- network lists and access control for ip and geographic filtering
- list edgeworkers
- list edgeworker identifiers
- platform
- DevOps Engineer
- manages akamai property configurations and edge deployments
- list all akamai edgeworker serverless functions
- security
- create edgeworker
- cdn
- list all akamai network lists for ip and geographic access control
- edgeworker serverless function management
- networks
- list network lists
- cloud
- edgeworkers serverless execution and edgekv storage at the edge
- network list management
- network security
- automates akamai configuration deployment via ci/cd pipelines
slug: edge-platform-management
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
