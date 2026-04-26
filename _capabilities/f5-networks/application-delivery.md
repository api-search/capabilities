---
consumed_apis:
- bigip-icontrol
description: Unified workflow for managing application delivery infrastructure including virtual servers, server pools, backend nodes, and traffic profiles on F5 BIG-IP. Used by network administrators and DevOps engineers for load balancing configuration and application traffic management.
layout: capability
name: F5 Application Delivery
operations:
- description: List all virtual servers
  method: GET
  name: list-virtual-servers
  path: /v1/virtual-servers
- description: Create a new virtual server
  method: POST
  name: create-virtual-server
  path: /v1/virtual-servers
- description: Get virtual server details
  method: GET
  name: get-virtual-server
  path: /v1/virtual-servers/{virtualName}
- description: Update a virtual server
  method: PUT
  name: update-virtual-server
  path: /v1/virtual-servers/{virtualName}
- description: Delete a virtual server
  method: DELETE
  name: delete-virtual-server
  path: /v1/virtual-servers/{virtualName}
- description: List all pools
  method: GET
  name: list-pools
  path: /v1/pools
- description: Create a new pool
  method: POST
  name: create-pool
  path: /v1/pools
- description: Get pool details
  method: GET
  name: get-pool
  path: /v1/pools/{poolName}
- description: Update a pool
  method: PUT
  name: update-pool
  path: /v1/pools/{poolName}
- description: Delete a pool
  method: DELETE
  name: delete-pool
  path: /v1/pools/{poolName}
- description: List pool members
  method: GET
  name: list-pool-members
  path: /v1/pools/{poolName}/members
- description: Add a pool member
  method: POST
  name: add-pool-member
  path: /v1/pools/{poolName}/members
- description: List all nodes
  method: GET
  name: list-nodes
  path: /v1/nodes
- description: Create a node
  method: POST
  name: create-node
  path: /v1/nodes
- description: Get node details
  method: GET
  name: get-node
  path: /v1/nodes/{nodeName}
- description: Update a node
  method: PUT
  name: update-node
  path: /v1/nodes/{nodeName}
- description: Delete a node
  method: DELETE
  name: delete-node
  path: /v1/nodes/{nodeName}
- description: List HTTP profiles
  method: GET
  name: list-http-profiles
  path: /v1/profiles
personas: []
provider_name: F5 Networks
provider_slug: f5-networks
search_terms:
- create pool
- add pool member
- get pool details
- automation
- list tcp profiles
- get details of a pool member
- delete a node
- update a virtual server
- list all backend nodes
- add a pool member
- create node
- get virtual server
- add a member to a pool
- list pools
- update pool member
- delete node
- manage a specific pool
- list http traffic profiles
- multi-cloud
- delete a virtual server
- get node details
- update a pool
- list all pools
- get node
- list nodes
- remove a pool member
- create a new backend node
- get pool member
- get details of a specific node
- edge computing
- list all virtual servers on the big-ip
- list members of a pool
- list tcp traffic profiles
- manage server pools
- update a pool member
- update pool
- get pool
- manage a specific virtual server
- list virtual servers
- update node
- application delivery
- create a node
- kubernetes
- manage backend nodes
- manage a specific node
- update a node
- delete virtual server
- get details of a specific pool
- create a new virtual server
- api gateway
- list all virtual servers
- list http profiles
- delete pool
- security
- create virtual server
- f5
- list pool members
- delete pool member
- view traffic profiles
- nginx
- list all server pools
- network management
- manage virtual servers that direct client traffic
- get virtual server details
- waf
- list client ssl profiles
- update virtual server
- delete a pool
- manage pool members
- create a new pool
- get details of a specific virtual server
- load balancing
- list all nodes
slug: application-delivery
tags:
- F5
- Application Delivery
- Load Balancing
- Network Management
tools:
- description: List all virtual servers on the BIG-IP
  hints:
    openWorld: true
    readOnly: true
  name: list-virtual-servers
- description: Get details of a specific virtual server
  hints:
    readOnly: true
  name: get-virtual-server
- description: Create a new virtual server
  hints:
    readOnly: false
  name: create-virtual-server
- description: Update a virtual server
  hints:
    idempotent: true
    readOnly: false
  name: update-virtual-server
- description: Delete a virtual server
  hints:
    destructive: true
    idempotent: true
  name: delete-virtual-server
- description: List all server pools
  hints:
    openWorld: true
    readOnly: true
  name: list-pools
- description: Get details of a specific pool
  hints:
    readOnly: true
  name: get-pool
- description: Create a new pool
  hints:
    readOnly: false
  name: create-pool
- description: Update a pool
  hints:
    idempotent: true
    readOnly: false
  name: update-pool
- description: Delete a pool
  hints:
    destructive: true
    idempotent: true
  name: delete-pool
- description: List members of a pool
  hints:
    readOnly: true
  name: list-pool-members
- description: Add a member to a pool
  hints:
    readOnly: false
  name: add-pool-member
- description: Get details of a pool member
  hints:
    readOnly: true
  name: get-pool-member
- description: Update a pool member
  hints:
    idempotent: true
    readOnly: false
  name: update-pool-member
- description: Remove a pool member
  hints:
    destructive: true
    idempotent: true
  name: delete-pool-member
- description: List all backend nodes
  hints:
    openWorld: true
    readOnly: true
  name: list-nodes
- description: Get details of a specific node
  hints:
    readOnly: true
  name: get-node
- description: Create a new backend node
  hints:
    readOnly: false
  name: create-node
- description: Update a node
  hints:
    idempotent: true
    readOnly: false
  name: update-node
- description: Delete a node
  hints:
    destructive: true
    idempotent: true
  name: delete-node
- description: List HTTP traffic profiles
  hints:
    readOnly: true
  name: list-http-profiles
- description: List TCP traffic profiles
  hints:
    readOnly: true
  name: list-tcp-profiles
- description: List client SSL profiles
  hints:
    readOnly: true
  name: list-client-ssl-profiles
---
