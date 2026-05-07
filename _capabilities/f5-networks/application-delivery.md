---
categories: []
consumed_apis: []
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
- list all pools
- get node details
- view traffic profiles
- update a pool member
- update a pool
- list tcp traffic profiles
- automation
- get pool
- create node
- add a member to a pool
- add a pool member
- application delivery
- remove a pool member
- network management
- get virtual server details
- create pool
- get details of a pool member
- get node
- waf
- delete a pool
- delete pool
- list client ssl profiles
- edge computing
- get pool details
- delete pool member
- list http profiles
- list all server pools
- manage virtual servers that direct client traffic
- list all virtual servers
- create a new pool
- get details of a specific pool
- multi-cloud
- get details of a specific virtual server
- delete a virtual server
- list pools
- list all nodes
- list members of a pool
- get details of a specific node
- manage a specific node
- kubernetes
- list http traffic profiles
- manage a specific virtual server
- create a new backend node
- manage server pools
- create a node
- update a node
- api gateway
- delete node
- update a virtual server
- load balancing
- create a new virtual server
- delete a node
- update virtual server
- get pool member
- add pool member
- nginx
- manage backend nodes
- list pool members
- update pool member
- f5
- list tcp profiles
- update pool
- create virtual server
- delete virtual server
- list nodes
- manage a specific pool
- get virtual server
- list all virtual servers on the big-ip
- update node
- security
- list all backend nodes
- list virtual servers
- manage pool members
slug: application-delivery
source_filename: application-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: F5 Application Delivery\n  description: Unified workflow for managing application delivery infrastructure including virtual servers, server pools,\n    backend nodes, and traffic profiles on F5 BIG-IP. Used by network administrators and DevOps engineers for load balancing\n    configuration and application traffic management.\n  tags:\n  - F5\n  - Application Delivery\n  - Load Balancing\n  - Network Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BIGIP_USERNAME: BIGIP_USERNAME\n    BIGIP_PASSWORD: BIGIP_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: bigip-icontrol\n    baseUri: https://{bigip_host}/mgmt/tm\n    description: F5 BIG-IP iControl REST API for managing LTM resources\n    authentication:\n      type: basic\n      username: '{{BIGIP_USERNAME}}'\n      password: '{{BIGIP_PASSWORD}}'\n    resources:\n    - name: virtual-servers\n      path: /ltm/virtual\n\
  \      description: Manage virtual servers for traffic direction\n      operations:\n      - name: list-virtual-servers\n        method: GET\n        description: List all virtual servers configured on the BIG-IP system\n        inputParameters:\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Select specific properties to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: Filter results by property values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-virtual-server\n        method: POST\n        description: Create a new virtual server resource\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n \
  \         data:\n            name: '{{tools.name}}'\n            destination: '{{tools.destination}}'\n            pool: '{{tools.pool}}'\n    - name: virtual-server\n      path: /ltm/virtual/{virtualName}\n      description: Manage a specific virtual server\n      operations:\n      - name: get-virtual-server\n        method: GET\n        description: Get a specific virtual server by name\n        inputParameters:\n        - name: virtualName\n          in: path\n          type: string\n          required: true\n          description: Name of the virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-virtual-server\n        method: PUT\n        description: Update a virtual server configuration\n        inputParameters:\n        - name: virtualName\n          in: path\n          type: string\n          required: true\n          description: Name of the virtual server\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pool: '{{tools.pool}}'\n            description: '{{tools.description}}'\n      - name: delete-virtual-server\n        method: DELETE\n        description: Delete a virtual server\n        inputParameters:\n        - name: virtualName\n          in: path\n          type: string\n          required: true\n          description: Name of the virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pools\n      path: /ltm/pool\n      description: Manage pools of backend servers\n      operations:\n      - name: list-pools\n        method: GET\n        description: List all pools configured on the BIG-IP\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-pool\n        method: POST\n        description: Create a new pool\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            monitor: '{{tools.monitor}}'\n    - name: pool\n      path: /ltm/pool/{poolName}\n      description: Manage a specific pool\n      operations:\n      - name: get-pool\n        method: GET\n        description: Get a specific pool by name\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-pool\n        method: PUT\n        description: Update a pool configuration\n\
  \        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            monitor: '{{tools.monitor}}'\n            loadBalancingMode: '{{tools.loadBalancingMode}}'\n      - name: delete-pool\n        method: DELETE\n        description: Delete a pool\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pool-members\n      path: /ltm/pool/{poolName}/members\n      description: Manage pool members within a pool\n      operations:\n      - name: list-pool-members\n\
  \        method: GET\n        description: List all members of a pool\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-pool-member\n        method: POST\n        description: Add a member to a pool\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: pool-member\n      path: /ltm/pool/{poolName}/members/{memberName}\n      description: Manage a specific pool member\n      operations:\n      - name:\
  \ get-pool-member\n        method: GET\n        description: Get a specific pool member\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        - name: memberName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-pool-member\n        method: PUT\n        description: Update a pool member\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        - name: memberName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool member\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            session: '{{tools.session}}'\n      - name: delete-pool-member\n        method: DELETE\n        description: Remove a pool member\n        inputParameters:\n        - name: poolName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool\n        - name: memberName\n          in: path\n          type: string\n          required: true\n          description: Name of the pool member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /ltm/node\n      description: Manage backend server nodes\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List all nodes\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: create-node\n        method: POST\n        description: Create a new node\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            address: '{{tools.address}}'\n    - name: node\n      path: /ltm/node/{nodeName}\n      description: Manage a specific node\n      operations:\n      - name: get-node\n        method: GET\n        description: Get a specific node\n        inputParameters:\n        - name: nodeName\n          in: path\n          type: string\n          required: true\n          description: Name of the node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-node\n        method: PUT\n        description: Update a node\n  \
  \      inputParameters:\n        - name: nodeName\n          in: path\n          type: string\n          required: true\n          description: Name of the node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            session: '{{tools.session}}'\n            description: '{{tools.description}}'\n      - name: delete-node\n        method: DELETE\n        description: Delete a node\n        inputParameters:\n        - name: nodeName\n          in: path\n          type: string\n          required: true\n          description: Name of the node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles\n      path: /ltm/profile\n      description: Manage traffic handling profiles\n      operations:\n      - name: list-http-profiles\n        method: GET\n        description:\
  \ List HTTP profiles\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-tcp-profiles\n        method: GET\n        description: List TCP profiles\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-client-ssl-profiles\n        method: GET\n        description: List client SSL profiles\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: f5-application-delivery-api\n    description: Unified REST API for F5 BIG-IP application delivery management.\n    resources:\n    - path: /v1/virtual-servers\n      name: virtual-servers\n      description: Manage virtual servers that direct client\
  \ traffic\n      operations:\n      - method: GET\n        name: list-virtual-servers\n        description: List all virtual servers\n        call: bigip-icontrol.list-virtual-servers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-virtual-server\n        description: Create a new virtual server\n        call: bigip-icontrol.create-virtual-server\n        with:\n          name: rest.name\n          destination: rest.destination\n          pool: rest.pool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/virtual-servers/{virtualName}\n      name: virtual-server\n      description: Manage a specific virtual server\n      operations:\n      - method: GET\n        name: get-virtual-server\n        description: Get virtual server details\n        call: bigip-icontrol.get-virtual-server\n        with:\n          virtualName: rest.virtualName\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: PUT\n        name: update-virtual-server\n        description: Update a virtual server\n        call: bigip-icontrol.update-virtual-server\n        with:\n          virtualName: rest.virtualName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-virtual-server\n        description: Delete a virtual server\n        call: bigip-icontrol.delete-virtual-server\n        with:\n          virtualName: rest.virtualName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pools\n      name: pools\n      description: Manage server pools\n      operations:\n      - method: GET\n        name: list-pools\n        description: List all pools\n        call: bigip-icontrol.list-pools\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-pool\n        description: Create a new pool\n  \
  \      call: bigip-icontrol.create-pool\n        with:\n          name: rest.name\n          monitor: rest.monitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pools/{poolName}\n      name: pool\n      description: Manage a specific pool\n      operations:\n      - method: GET\n        name: get-pool\n        description: Get pool details\n        call: bigip-icontrol.get-pool\n        with:\n          poolName: rest.poolName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-pool\n        description: Update a pool\n        call: bigip-icontrol.update-pool\n        with:\n          poolName: rest.poolName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-pool\n        description: Delete a pool\n        call: bigip-icontrol.delete-pool\n        with:\n          poolName: rest.poolName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/pools/{poolName}/members\n      name: pool-members\n      description: Manage pool members\n      operations:\n      - method: GET\n        name: list-pool-members\n        description: List pool members\n        call: bigip-icontrol.list-pool-members\n        with:\n          poolName: rest.poolName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-pool-member\n        description: Add a pool member\n        call: bigip-icontrol.add-pool-member\n        with:\n          poolName: rest.poolName\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes\n      name: nodes\n      description: Manage backend nodes\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List all nodes\n        call: bigip-icontrol.list-nodes\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: POST\n        name: create-node\n        description: Create a node\n        call: bigip-icontrol.create-node\n        with:\n          name: rest.name\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes/{nodeName}\n      name: node\n      description: Manage a specific node\n      operations:\n      - method: GET\n        name: get-node\n        description: Get node details\n        call: bigip-icontrol.get-node\n        with:\n          nodeName: rest.nodeName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-node\n        description: Update a node\n        call: bigip-icontrol.update-node\n        with:\n          nodeName: rest.nodeName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-node\n        description: Delete a\
  \ node\n        call: bigip-icontrol.delete-node\n        with:\n          nodeName: rest.nodeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles\n      name: profiles\n      description: View traffic profiles\n      operations:\n      - method: GET\n        name: list-http-profiles\n        description: List HTTP profiles\n        call: bigip-icontrol.list-http-profiles\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: f5-application-delivery-mcp\n    transport: http\n    description: MCP server for AI-assisted F5 BIG-IP application delivery management.\n    tools:\n    - name: list-virtual-servers\n      description: List all virtual servers on the BIG-IP\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bigip-icontrol.list-virtual-servers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-virtual-server\n\
  \      description: Get details of a specific virtual server\n      hints:\n        readOnly: true\n      call: bigip-icontrol.get-virtual-server\n      with:\n        virtualName: tools.virtualName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-virtual-server\n      description: Create a new virtual server\n      hints:\n        readOnly: false\n      call: bigip-icontrol.create-virtual-server\n      with:\n        name: tools.name\n        destination: tools.destination\n        pool: tools.pool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-virtual-server\n      description: Update a virtual server\n      hints:\n        readOnly: false\n        idempotent: true\n      call: bigip-icontrol.update-virtual-server\n      with:\n        virtualName: tools.virtualName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-virtual-server\n      description: Delete a virtual server\n\
  \      hints:\n        destructive: true\n        idempotent: true\n      call: bigip-icontrol.delete-virtual-server\n      with:\n        virtualName: tools.virtualName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pools\n      description: List all server pools\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bigip-icontrol.list-pools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pool\n      description: Get details of a specific pool\n      hints:\n        readOnly: true\n      call: bigip-icontrol.get-pool\n      with:\n        poolName: tools.poolName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pool\n      description: Create a new pool\n      hints:\n        readOnly: false\n      call: bigip-icontrol.create-pool\n      with:\n        name: tools.name\n        monitor: tools.monitor\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: update-pool\n      description: Update a pool\n      hints:\n        readOnly: false\n        idempotent: true\n      call: bigip-icontrol.update-pool\n      with:\n        poolName: tools.poolName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-pool\n      description: Delete a pool\n      hints:\n        destructive: true\n        idempotent: true\n      call: bigip-icontrol.delete-pool\n      with:\n        poolName: tools.poolName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pool-members\n      description: List members of a pool\n      hints:\n        readOnly: true\n      call: bigip-icontrol.list-pool-members\n      with:\n        poolName: tools.poolName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-pool-member\n      description: Add a member to a pool\n      hints:\n        readOnly: false\n      call: bigip-icontrol.add-pool-member\n\
  \      with:\n        poolName: tools.poolName\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pool-member\n      description: Get details of a pool member\n      hints:\n        readOnly: true\n      call: bigip-icontrol.get-pool-member\n      with:\n        poolName: tools.poolName\n        memberName: tools.memberName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-pool-member\n      description: Update a pool member\n      hints:\n        readOnly: false\n        idempotent: true\n      call: bigip-icontrol.update-pool-member\n      with:\n        poolName: tools.poolName\n        memberName: tools.memberName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-pool-member\n      description: Remove a pool member\n      hints:\n        destructive: true\n        idempotent: true\n      call: bigip-icontrol.delete-pool-member\n      with:\n      \
  \  poolName: tools.poolName\n        memberName: tools.memberName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List all backend nodes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bigip-icontrol.list-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-node\n      description: Get details of a specific node\n      hints:\n        readOnly: true\n      call: bigip-icontrol.get-node\n      with:\n        nodeName: tools.nodeName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-node\n      description: Create a new backend node\n      hints:\n        readOnly: false\n      call: bigip-icontrol.create-node\n      with:\n        name: tools.name\n        address: tools.address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-node\n      description: Update a node\n      hints:\n  \
  \      readOnly: false\n        idempotent: true\n      call: bigip-icontrol.update-node\n      with:\n        nodeName: tools.nodeName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-node\n      description: Delete a node\n      hints:\n        destructive: true\n        idempotent: true\n      call: bigip-icontrol.delete-node\n      with:\n        nodeName: tools.nodeName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-http-profiles\n      description: List HTTP traffic profiles\n      hints:\n        readOnly: true\n      call: bigip-icontrol.list-http-profiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tcp-profiles\n      description: List TCP traffic profiles\n      hints:\n        readOnly: true\n      call: bigip-icontrol.list-tcp-profiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-client-ssl-profiles\n      description:\
  \ List client SSL profiles\n      hints:\n        readOnly: true\n      call: bigip-icontrol.list-client-ssl-profiles\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
