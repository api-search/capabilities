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
- platform management
- create edgeworker
- list network lists
- network list management
- networks
- cdn
- manage akamai edge platform including edgeworkers and network lists
- platform
- manages akamai property configurations and edge deployments
- security
- list edgeworker identifiers
- DevOps Engineer
- network security
- list all akamai edgeworker serverless functions
- automates akamai configuration deployment via ci/cd pipelines
- network lists and access control for ip and geographic filtering
- content delivery property management and configuration
- akamai
- edge computing
- edgeworker serverless function management
- list edgeworkers
- edgeworkers serverless execution and edgekv storage at the edge
- cloud
- create a new akamai edgeworker serverless function
- list all akamai network lists for ip and geographic access control
- Platform Engineer
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
