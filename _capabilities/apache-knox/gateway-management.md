---
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
- get apache knox gateway version information
- security engineering
- list all knox gateway topologies and their service urls
- Hadoop Administrator
- authentication
- open source
- create topology
- Security Engineer
- security
- get knox version
- gateway management
- admins who configure knox topologies for hadoop cluster access
- create or update a knox gateway topology
- delete topology
- engineers who configure authentication and authorization for knox
- apache knox
- sso
- get topology
- hadoop administration
- delete a knox gateway topology
- api gateway
- get the configuration details of a specific knox topology
- hadoop
- list topologies
slug: gateway-management
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
