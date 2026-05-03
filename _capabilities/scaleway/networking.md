---
categories: []
consumed_apis:
- scaleway-vpc
- scaleway-lb
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
- create a private network within a vpc
- load balancing
- get details of a specific load balancer
- storage
- delete vpc
- get load balancer details
- delete load balancer
- european cloud
- list scaleway load balancers
- network isolation
- list backend server pools for a load balancer
- list load balancer backends
- subnet management
- list vpcs
- create a new scaleway vpc
- get details of a specific vpc
- list private networks
- create vpc
- delete a vpc
- list load balancers
- create a load balancer
- list private networks within vpcs
- manage a specific load balancer
- list subnets in a region
- get vpc
- load balancer backend management
- kubernetes
- load balancer management
- private network management
- list backends
- vpc
- database
- networking
- delete a load balancer
- containers
- create a private network
- virtual private cloud management
- create private network
- ai
- scaleway
- create a new load balancer
- list scaleway virtual private clouds
- create a vpc
- get vpc details
- infrastructure
- serverless
- get load balancer
- manage a specific vpc
- cloud computing
- create load balancer
- list subnets
slug: networking
source_filename: networking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Scaleway Networking\"\n  description: >-\n    Unified workflow capability for managing Scaleway networking infrastructure including\n    Virtual Private Clouds, private networks, subnets, and load balancers. Used by\n    network engineers and cloud architects to design and manage private connectivity\n    and traffic distribution for Scaleway resources.\n  tags:\n    - Cloud Computing\n    - Load Balancing\n    - Network Isolation\n    - Networking\n    - Scaleway\n    - VPC\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCALEWAY_API_KEY: SCALEWAY_API_KEY\n\ncapability:\n  consumes:\n    - import: scaleway-vpc\n      location: ./shared/vpc.yaml\n    - import: scaleway-lb\n      location: ./shared/load-balancer.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: scaleway-networking-api\n      description: \"Unified REST API for Scaleway network infrastructure\
  \ management.\"\n      resources:\n        - path: /v1/vpcs\n          name: vpcs\n          description: \"Virtual Private Cloud management\"\n          operations:\n            - method: GET\n              name: list-vpcs\n              description: \"List VPCs\"\n              call: \"scaleway-vpc.list-vpcs\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-vpc\n              description: \"Create a VPC\"\n              call: \"scaleway-vpc.create-vpc\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vpcs/{id}\n          name: vpc\n          description: \"Manage a specific VPC\"\n          operations:\n            - method: GET\n              name: get-vpc\n              description:\
  \ \"Get VPC details\"\n              call: \"scaleway-vpc.get-vpc\"\n              with:\n                region: \"rest.region\"\n                vpc_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-vpc\n              description: \"Delete a VPC\"\n              call: \"scaleway-vpc.delete-vpc\"\n              with:\n                region: \"rest.region\"\n                vpc_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/private-networks\n          name: private-networks\n          description: \"Private network management\"\n          operations:\n            - method: GET\n              name: list-private-networks\n              description: \"List private networks\"\n              call: \"scaleway-vpc.list-private-networks\"\n              with:\n                region:\
  \ \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-private-network\n              description: \"Create a private network\"\n              call: \"scaleway-vpc.create-private-network\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subnets\n          name: subnets\n          description: \"Subnet management\"\n          operations:\n            - method: GET\n              name: list-subnets\n              description: \"List subnets\"\n              call: \"scaleway-vpc.list-subnets\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/load-balancers\n          name: load-balancers\n          description:\
  \ \"Load balancer management\"\n          operations:\n            - method: GET\n              name: list-load-balancers\n              description: \"List load balancers\"\n              call: \"scaleway-lb.list-load-balancers\"\n              with:\n                zone: \"rest.zone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-load-balancer\n              description: \"Create a load balancer\"\n              call: \"scaleway-lb.create-load-balancer\"\n              with:\n                zone: \"rest.zone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/load-balancers/{id}\n          name: load-balancer\n          description: \"Manage a specific load balancer\"\n          operations:\n            - method: GET\n              name: get-load-balancer\n              description: \"Get load balancer details\"\
  \n              call: \"scaleway-lb.get-load-balancer\"\n              with:\n                zone: \"rest.zone\"\n                lb_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-load-balancer\n              description: \"Delete a load balancer\"\n              call: \"scaleway-lb.delete-load-balancer\"\n              with:\n                zone: \"rest.zone\"\n                lb_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/load-balancers/{id}/backends\n          name: lb-backends\n          description: \"Load balancer backend management\"\n          operations:\n            - method: GET\n              name: list-backends\n              description: \"List load balancer backends\"\n              call: \"scaleway-lb.list-backends\"\n              with:\n            \
  \    zone: \"rest.zone\"\n                lb_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: scaleway-networking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Scaleway network infrastructure management.\"\n      tools:\n        - name: list-vpcs\n          description: \"List Scaleway Virtual Private Clouds\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-vpc.list-vpcs\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-vpc\n          description: \"Create a new Scaleway VPC\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-vpc.create-vpc\"\n          with:\n            region:\
  \ \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vpc\n          description: \"Get details of a specific VPC\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-vpc.get-vpc\"\n          with:\n            region: \"tools.region\"\n            vpc_id: \"tools.vpc_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-private-networks\n          description: \"List private networks within VPCs\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-vpc.list-private-networks\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-private-network\n          description: \"Create a private network within a VPC\"\n          hints:\n          \
  \  readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-vpc.create-private-network\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subnets\n          description: \"List subnets in a region\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-vpc.list-subnets\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-load-balancers\n          description: \"List Scaleway load balancers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-lb.list-load-balancers\"\n          with:\n            zone: \"tools.zone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n       \
  \ - name: create-load-balancer\n          description: \"Create a new load balancer\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-lb.create-load-balancer\"\n          with:\n            zone: \"tools.zone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-load-balancer\n          description: \"Get details of a specific load balancer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-lb.get-load-balancer\"\n          with:\n            zone: \"tools.zone\"\n            lb_id: \"tools.lb_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-backends\n          description: \"List backend server pools for a load balancer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-lb.list-backends\"\
  \n          with:\n            zone: \"tools.zone\"\n            lb_id: \"tools.lb_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-load-balancer\n          description: \"Delete a load balancer\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-lb.delete-load-balancer\"\n          with:\n            zone: \"tools.zone\"\n            lb_id: \"tools.lb_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
