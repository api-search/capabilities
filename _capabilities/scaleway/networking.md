---
categories: []
consumed_apis: []
description: Unified workflow capability for managing Scaleway networking infrastructure including Virtual Private Clouds, private networks, subnets, and load balancers. Used by network engineers and cloud architects to design and manage private connectivity and traffic distribution for Scaleway resources.
layout: capability
name: Scaleway Networking
operations:
- description: List VPCs
  method: GET
  name: list-vpcs
  path: /v1/vpcs
- description: Create a VPC
  method: POST
  name: create-vpc
  path: /v1/vpcs
- description: Get VPC details
  method: GET
  name: get-vpc
  path: /v1/vpcs/{id}
- description: Delete a VPC
  method: DELETE
  name: delete-vpc
  path: /v1/vpcs/{id}
- description: List private networks
  method: GET
  name: list-private-networks
  path: /v1/private-networks
- description: Create a private network
  method: POST
  name: create-private-network
  path: /v1/private-networks
- description: List subnets
  method: GET
  name: list-subnets
  path: /v1/subnets
- description: List load balancers
  method: GET
  name: list-load-balancers
  path: /v1/load-balancers
- description: Create a load balancer
  method: POST
  name: create-load-balancer
  path: /v1/load-balancers
- description: Get load balancer details
  method: GET
  name: get-load-balancer
  path: /v1/load-balancers/{id}
- description: Delete a load balancer
  method: DELETE
  name: delete-load-balancer
  path: /v1/load-balancers/{id}
- description: List load balancer backends
  method: GET
  name: list-backends
  path: /v1/load-balancers/{id}/backends
personas: []
provider_name: Scaleway
provider_slug: scaleway
search_terms:
- networking
- vpc
- create a vpc
- manage a specific vpc
- create a load balancer
- list scaleway load balancers
- list load balancers
- storage
- infrastructure
- create a private network within a vpc
- list vpcs
- manage a specific load balancer
- create load balancer
- get details of a specific vpc
- network isolation
- delete load balancer
- serverless
- private network management
- create a new load balancer
- european cloud
- load balancer backend management
- load balancer management
- list subnets in a region
- containers
- ai
- subnet management
- cloud computing
- kubernetes
- get vpc details
- get load balancer details
- list private networks
- create a private network
- create a new scaleway vpc
- create private network
- get details of a specific load balancer
- database
- delete vpc
- list backend server pools for a load balancer
- delete a vpc
- scaleway
- list subnets
- list backends
- get vpc
- delete a load balancer
- get load balancer
- list private networks within vpcs
- load balancing
- list scaleway virtual private clouds
- list load balancer backends
- create vpc
- virtual private cloud management
slug: networking
source_filename: networking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scaleway Networking\n  description: Unified workflow capability for managing Scaleway networking infrastructure including Virtual Private Clouds,\n    private networks, subnets, and load balancers. Used by network engineers and cloud architects to design and manage private\n    connectivity and traffic distribution for Scaleway resources.\n  tags:\n  - Cloud Computing\n  - Load Balancing\n  - Network Isolation\n  - Networking\n  - Scaleway\n  - VPC\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCALEWAY_API_KEY: SCALEWAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scaleway-vpc\n    baseUri: https://api.scaleway.com\n    description: Scaleway VPC API for private network management\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: vpcs\n      path: /vpc/v2/regions/{region}/vpcs\n\
  \      description: VPC management\n      operations:\n      - name: list-vpcs\n        method: GET\n        description: List VPCs\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n          description: Region (e.g., fr-par)\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-vpc\n        method: POST\n        description: Create a VPC\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: vpc\n      path: /vpc/v2/regions/{region}/vpcs/{vpc_id}\n\
  \      description: Manage a specific VPC\n      operations:\n      - name: get-vpc\n        method: GET\n        description: Get VPC details\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: vpc_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-vpc\n        method: DELETE\n        description: Delete a VPC\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: vpc_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: private-networks\n      path: /vpc/v2/regions/{region}/private-networks\n   \
  \   description: Private network management\n      operations:\n      - name: list-private-networks\n        method: GET\n        description: List Private Networks\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-private-network\n        method: POST\n        description: Create a Private Network\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            vpc_id: '{{tools.vpc_id}}'\n    - name: subnets\n      path: /vpc/v2/regions/{region}/subnets\n      description: Subnet management\n\
  \      operations:\n      - name: list-subnets\n        method: GET\n        description: List Subnets\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scaleway-lb\n    baseUri: https://api.scaleway.com\n    description: Scaleway Load Balancer API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: load-balancers\n      path: /lb/v1/zones/{zone}/lbs\n      description: Load balancer management\n      operations:\n      - name: list-load-balancers\n        method: GET\n        description: List Load Balancers\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n          description: Availability\
  \ zone\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-load-balancer\n        method: POST\n        description: Create a Load Balancer\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: load-balancer\n      path: /lb/v1/zones/{zone}/lbs/{lb_id}\n      description: Manage a specific load balancer\n      operations:\n      - name: get-load-balancer\n        method: GET\n        description: Get Load Balancer details\n        inputParameters:\n        - name: zone\n  \
  \        in: path\n          type: string\n          required: true\n        - name: lb_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-load-balancer\n        method: DELETE\n        description: Delete a Load Balancer\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: lb_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backends\n      path: /lb/v1/zones/{zone}/lbs/{lb_id}/backends\n      description: Backend server pool management\n      operations:\n      - name: list-backends\n        method: GET\n        description: List Backends\n        inputParameters:\n        -\
  \ name: zone\n          in: path\n          type: string\n          required: true\n        - name: lb_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-backend\n        method: POST\n        description: Create a Backend\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: lb_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            forward_protocol: '{{tools.forward_protocol}}'\n            server_ip: '{{tools.server_ip}}'\n    - name: frontends\n      path: /lb/v1/zones/{zone}/lbs/{lb_id}/frontends\n\
  \      description: Frontend listener management\n      operations:\n      - name: list-frontends\n        method: GET\n        description: List Frontends\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: lb_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ips\n      path: /lb/v1/zones/{zone}/ips\n      description: Load balancer IP management\n      operations:\n      - name: list-ips\n        method: GET\n        description: List IP Addresses\n        inputParameters:\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace:\
  \ scaleway-networking-api\n    description: Unified REST API for Scaleway network infrastructure management.\n    resources:\n    - path: /v1/vpcs\n      name: vpcs\n      description: Virtual Private Cloud management\n      operations:\n      - method: GET\n        name: list-vpcs\n        description: List VPCs\n        call: scaleway-vpc.list-vpcs\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-vpc\n        description: Create a VPC\n        call: scaleway-vpc.create-vpc\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vpcs/{id}\n      name: vpc\n      description: Manage a specific VPC\n      operations:\n      - method: GET\n        name: get-vpc\n        description: Get VPC details\n        call: scaleway-vpc.get-vpc\n        with:\n          region: rest.region\n          vpc_id:\
  \ rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-vpc\n        description: Delete a VPC\n        call: scaleway-vpc.delete-vpc\n        with:\n          region: rest.region\n          vpc_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/private-networks\n      name: private-networks\n      description: Private network management\n      operations:\n      - method: GET\n        name: list-private-networks\n        description: List private networks\n        call: scaleway-vpc.list-private-networks\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-private-network\n        description: Create a private network\n        call: scaleway-vpc.create-private-network\n        with:\n          region: rest.region\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/subnets\n      name: subnets\n      description: Subnet management\n      operations:\n      - method: GET\n        name: list-subnets\n        description: List subnets\n        call: scaleway-vpc.list-subnets\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/load-balancers\n      name: load-balancers\n      description: Load balancer management\n      operations:\n      - method: GET\n        name: list-load-balancers\n        description: List load balancers\n        call: scaleway-lb.list-load-balancers\n        with:\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-load-balancer\n        description: Create a load balancer\n        call: scaleway-lb.create-load-balancer\n        with:\n          zone: rest.zone\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/load-balancers/{id}\n      name: load-balancer\n      description: Manage a specific load balancer\n      operations:\n      - method: GET\n        name: get-load-balancer\n        description: Get load balancer details\n        call: scaleway-lb.get-load-balancer\n        with:\n          zone: rest.zone\n          lb_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-load-balancer\n        description: Delete a load balancer\n        call: scaleway-lb.delete-load-balancer\n        with:\n          zone: rest.zone\n          lb_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/load-balancers/{id}/backends\n      name: lb-backends\n      description: Load balancer backend management\n      operations:\n      - method: GET\n        name: list-backends\n        description: List load balancer backends\n    \
  \    call: scaleway-lb.list-backends\n        with:\n          zone: rest.zone\n          lb_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: scaleway-networking-mcp\n    transport: http\n    description: MCP server for AI-assisted Scaleway network infrastructure management.\n    tools:\n    - name: list-vpcs\n      description: List Scaleway Virtual Private Clouds\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-vpc.list-vpcs\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-vpc\n      description: Create a new Scaleway VPC\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-vpc.create-vpc\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vpc\n   \
  \   description: Get details of a specific VPC\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-vpc.get-vpc\n      with:\n        region: tools.region\n        vpc_id: tools.vpc_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-private-networks\n      description: List private networks within VPCs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-vpc.list-private-networks\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-private-network\n      description: Create a private network within a VPC\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-vpc.create-private-network\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subnets\n      description: List subnets\
  \ in a region\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-vpc.list-subnets\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-load-balancers\n      description: List Scaleway load balancers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-lb.list-load-balancers\n      with:\n        zone: tools.zone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-load-balancer\n      description: Create a new load balancer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-lb.create-load-balancer\n      with:\n        zone: tools.zone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-load-balancer\n      description: Get details of a specific load balancer\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: scaleway-lb.get-load-balancer\n      with:\n        zone: tools.zone\n        lb_id: tools.lb_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-backends\n      description: List backend server pools for a load balancer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-lb.list-backends\n      with:\n        zone: tools.zone\n        lb_id: tools.lb_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-load-balancer\n      description: Delete a load balancer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-lb.delete-load-balancer\n      with:\n        zone: tools.zone\n        lb_id: tools.lb_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scaleway/refs/heads/main/capabilities/networking.yaml
tags:
- Cloud Computing
- Load Balancing
- Network Isolation
- Networking
- Scaleway
- VPC
tools:
- description: List Scaleway Virtual Private Clouds
  hints:
    openWorld: true
    readOnly: true
  name: list-vpcs
- description: Create a new Scaleway VPC
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-vpc
- description: Get details of a specific VPC
  hints:
    openWorld: false
    readOnly: true
  name: get-vpc
- description: List private networks within VPCs
  hints:
    openWorld: true
    readOnly: true
  name: list-private-networks
- description: Create a private network within a VPC
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-private-network
- description: List subnets in a region
  hints:
    openWorld: true
    readOnly: true
  name: list-subnets
- description: List Scaleway load balancers
  hints:
    openWorld: true
    readOnly: true
  name: list-load-balancers
- description: Create a new load balancer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-load-balancer
- description: Get details of a specific load balancer
  hints:
    openWorld: false
    readOnly: true
  name: get-load-balancer
- description: List backend server pools for a load balancer
  hints:
    openWorld: false
    readOnly: true
  name: list-backends
- description: Delete a load balancer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-load-balancer
---
