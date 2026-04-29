---
api_specs:
- filename: bigip-icontrol-rest.yml
  format: yaml
  label: bigip-icontrol
  slug: bigip-icontrol
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/f5-networks/refs/heads/main/openapi/bigip-icontrol-rest.yml
categories: []
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
- manage virtual servers that direct client traffic
- get node details
- list all server pools
- edge computing
- list all backend nodes
- get details of a specific node
- waf
- get virtual server
- delete pool member
- list nodes
- f5
- list pool members
- list members of a pool
- list all virtual servers
- manage pool members
- delete node
- update a node
- get pool
- automation
- add a pool member
- list tcp profiles
- manage server pools
- manage a specific pool
- add pool member
- get pool member
- get node
- view traffic profiles
- list http traffic profiles
- api gateway
- create a new backend node
- get pool details
- create node
- create virtual server
- update virtual server
- update pool
- list tcp traffic profiles
- list http profiles
- get details of a specific pool
- update node
- delete a virtual server
- list all pools
- list virtual servers
- manage a specific virtual server
- get virtual server details
- update a virtual server
- add a member to a pool
- manage backend nodes
- security
- application delivery
- network management
- list pools
- load balancing
- list client ssl profiles
- create a new pool
- create a node
- get details of a pool member
- create a new virtual server
- multi-cloud
- create pool
- delete pool
- kubernetes
- delete a node
- get details of a specific virtual server
- list all nodes
- update a pool member
- update pool member
- list all virtual servers on the big-ip
- manage a specific node
- nginx
- delete virtual server
- update a pool
- delete a pool
- remove a pool member
slug: application-delivery
source_filename: application-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"F5 Application Delivery\"\n  description: \"Unified workflow for managing application delivery infrastructure including virtual servers, server pools, backend nodes, and traffic profiles on F5 BIG-IP. Used by network administrators and DevOps engineers for load balancing configuration and application traffic management.\"\n  tags:\n    - F5\n    - Application Delivery\n    - Load Balancing\n    - Network Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      BIGIP_USERNAME: BIGIP_USERNAME\n      BIGIP_PASSWORD: BIGIP_PASSWORD\n\ncapability:\n  consumes:\n    - import: bigip-icontrol\n      location: ./shared/bigip-icontrol-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: f5-application-delivery-api\n      description: \"Unified REST API for F5 BIG-IP application delivery management.\"\n      resources:\n        - path: /v1/virtual-servers\n\
  \          name: virtual-servers\n          description: \"Manage virtual servers that direct client traffic\"\n          operations:\n            - method: GET\n              name: list-virtual-servers\n              description: \"List all virtual servers\"\n              call: \"bigip-icontrol.list-virtual-servers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-virtual-server\n              description: \"Create a new virtual server\"\n              call: \"bigip-icontrol.create-virtual-server\"\n              with:\n                name: \"rest.name\"\n                destination: \"rest.destination\"\n                pool: \"rest.pool\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/virtual-servers/{virtualName}\n          name: virtual-server\n          description: \"Manage a specific virtual server\"\
  \n          operations:\n            - method: GET\n              name: get-virtual-server\n              description: \"Get virtual server details\"\n              call: \"bigip-icontrol.get-virtual-server\"\n              with:\n                virtualName: \"rest.virtualName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-virtual-server\n              description: \"Update a virtual server\"\n              call: \"bigip-icontrol.update-virtual-server\"\n              with:\n                virtualName: \"rest.virtualName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-virtual-server\n              description: \"Delete a virtual server\"\n              call: \"bigip-icontrol.delete-virtual-server\"\n              with:\n                virtualName: \"rest.virtualName\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pools\n          name: pools\n          description: \"Manage server pools\"\n          operations:\n            - method: GET\n              name: list-pools\n              description: \"List all pools\"\n              call: \"bigip-icontrol.list-pools\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-pool\n              description: \"Create a new pool\"\n              call: \"bigip-icontrol.create-pool\"\n              with:\n                name: \"rest.name\"\n                monitor: \"rest.monitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pools/{poolName}\n          name: pool\n          description: \"Manage a specific pool\"\n          operations:\n            - method:\
  \ GET\n              name: get-pool\n              description: \"Get pool details\"\n              call: \"bigip-icontrol.get-pool\"\n              with:\n                poolName: \"rest.poolName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-pool\n              description: \"Update a pool\"\n              call: \"bigip-icontrol.update-pool\"\n              with:\n                poolName: \"rest.poolName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-pool\n              description: \"Delete a pool\"\n              call: \"bigip-icontrol.delete-pool\"\n              with:\n                poolName: \"rest.poolName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pools/{poolName}/members\n \
  \         name: pool-members\n          description: \"Manage pool members\"\n          operations:\n            - method: GET\n              name: list-pool-members\n              description: \"List pool members\"\n              call: \"bigip-icontrol.list-pool-members\"\n              with:\n                poolName: \"rest.poolName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-pool-member\n              description: \"Add a pool member\"\n              call: \"bigip-icontrol.add-pool-member\"\n              with:\n                poolName: \"rest.poolName\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nodes\n          name: nodes\n          description: \"Manage backend nodes\"\n          operations:\n            - method: GET\n              name: list-nodes\n   \
  \           description: \"List all nodes\"\n              call: \"bigip-icontrol.list-nodes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-node\n              description: \"Create a node\"\n              call: \"bigip-icontrol.create-node\"\n              with:\n                name: \"rest.name\"\n                address: \"rest.address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nodes/{nodeName}\n          name: node\n          description: \"Manage a specific node\"\n          operations:\n            - method: GET\n              name: get-node\n              description: \"Get node details\"\n              call: \"bigip-icontrol.get-node\"\n              with:\n                nodeName: \"rest.nodeName\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: PUT\n              name: update-node\n              description: \"Update a node\"\n              call: \"bigip-icontrol.update-node\"\n              with:\n                nodeName: \"rest.nodeName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-node\n              description: \"Delete a node\"\n              call: \"bigip-icontrol.delete-node\"\n              with:\n                nodeName: \"rest.nodeName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/profiles\n          name: profiles\n          description: \"View traffic profiles\"\n          operations:\n            - method: GET\n              name: list-http-profiles\n              description: \"List HTTP profiles\"\n              call: \"bigip-icontrol.list-http-profiles\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: f5-application-delivery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted F5 BIG-IP application delivery management.\"\n      tools:\n        - name: list-virtual-servers\n          description: \"List all virtual servers on the BIG-IP\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bigip-icontrol.list-virtual-servers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-virtual-server\n          description: \"Get details of a specific virtual server\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.get-virtual-server\"\n          with:\n            virtualName: \"tools.virtualName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-virtual-server\n\
  \          description: \"Create a new virtual server\"\n          hints:\n            readOnly: false\n          call: \"bigip-icontrol.create-virtual-server\"\n          with:\n            name: \"tools.name\"\n            destination: \"tools.destination\"\n            pool: \"tools.pool\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-virtual-server\n          description: \"Update a virtual server\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"bigip-icontrol.update-virtual-server\"\n          with:\n            virtualName: \"tools.virtualName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-virtual-server\n          description: \"Delete a virtual server\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"bigip-icontrol.delete-virtual-server\"\n         \
  \ with:\n            virtualName: \"tools.virtualName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pools\n          description: \"List all server pools\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bigip-icontrol.list-pools\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pool\n          description: \"Get details of a specific pool\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.get-pool\"\n          with:\n            poolName: \"tools.poolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-pool\n          description: \"Create a new pool\"\n          hints:\n            readOnly: false\n          call: \"bigip-icontrol.create-pool\"\n          with:\n            name: \"tools.name\"\n            monitor: \"\
  tools.monitor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-pool\n          description: \"Update a pool\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"bigip-icontrol.update-pool\"\n          with:\n            poolName: \"tools.poolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-pool\n          description: \"Delete a pool\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"bigip-icontrol.delete-pool\"\n          with:\n            poolName: \"tools.poolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pool-members\n          description: \"List members of a pool\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.list-pool-members\"\n          with:\n   \
  \         poolName: \"tools.poolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-pool-member\n          description: \"Add a member to a pool\"\n          hints:\n            readOnly: false\n          call: \"bigip-icontrol.add-pool-member\"\n          with:\n            poolName: \"tools.poolName\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pool-member\n          description: \"Get details of a pool member\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.get-pool-member\"\n          with:\n            poolName: \"tools.poolName\"\n            memberName: \"tools.memberName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-pool-member\n          description: \"Update a pool member\"\n          hints:\n            readOnly: false\n\
  \            idempotent: true\n          call: \"bigip-icontrol.update-pool-member\"\n          with:\n            poolName: \"tools.poolName\"\n            memberName: \"tools.memberName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-pool-member\n          description: \"Remove a pool member\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"bigip-icontrol.delete-pool-member\"\n          with:\n            poolName: \"tools.poolName\"\n            memberName: \"tools.memberName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-nodes\n          description: \"List all backend nodes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bigip-icontrol.list-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-node\n\
  \          description: \"Get details of a specific node\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.get-node\"\n          with:\n            nodeName: \"tools.nodeName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-node\n          description: \"Create a new backend node\"\n          hints:\n            readOnly: false\n          call: \"bigip-icontrol.create-node\"\n          with:\n            name: \"tools.name\"\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-node\n          description: \"Update a node\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"bigip-icontrol.update-node\"\n          with:\n            nodeName: \"tools.nodeName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: delete-node\n          description: \"Delete a node\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"bigip-icontrol.delete-node\"\n          with:\n            nodeName: \"tools.nodeName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-http-profiles\n          description: \"List HTTP traffic profiles\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.list-http-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tcp-profiles\n          description: \"List TCP traffic profiles\"\n          hints:\n            readOnly: true\n          call: \"bigip-icontrol.list-tcp-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-client-ssl-profiles\n          description: \"List client SSL profiles\"\n  \
  \        hints:\n            readOnly: true\n          call: \"bigip-icontrol.list-client-ssl-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/f5-networks/refs/heads/main/capabilities/application-delivery.yaml
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
