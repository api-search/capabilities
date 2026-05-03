---
categories: []
consumed_apis:
- direct-connect
description: Workflow capability for network engineers and cloud architects to manage dedicated private connections between on-premises networks and AWS using Amazon Direct Connect. Covers connection provisioning, virtual interface management, gateway associations, LAG configuration, and network troubleshooting.
layout: capability
name: Amazon Direct Connect Hybrid Network Connectivity
operations:
- description: List all Direct Connect connections
  method: GET
  name: describe-connections
  path: /v1/connections
- description: Create a new dedicated connection
  method: POST
  name: create-connection
  path: /v1/connections
- description: List all virtual interfaces
  method: GET
  name: describe-virtual-interfaces
  path: /v1/virtual-interfaces
- description: Create a private virtual interface for VPC access
  method: POST
  name: create-private-vif
  path: /v1/virtual-interfaces
- description: Create a transit virtual interface for Transit Gateway
  method: POST
  name: create-transit-vif
  path: /v1/virtual-interfaces
- description: List Direct Connect gateways
  method: GET
  name: describe-gateways
  path: /v1/gateways
- description: Create a Direct Connect gateway
  method: POST
  name: create-gateway
  path: /v1/gateways
- description: List link aggregation groups
  method: GET
  name: describe-lags
  path: /v1/lags
- description: Create a link aggregation group
  method: POST
  name: create-lag
  path: /v1/lags
- description: List Direct Connect colocation facilities
  method: GET
  name: describe-locations
  path: /v1/locations
personas: []
provider_name: Amazon Direct Connect
provider_slug: amazon-direct-connect
search_terms:
- create transit vif
- amazon direct connect
- create a private virtual interface for vpc access
- network engineering
- networking
- create private virtual interface
- link aggregation groups for redundant connections
- list link aggregation groups
- delete a direct connect connection
- describe virtual interfaces
- list all direct connect connections
- list all virtual interfaces configured on direct connect connections
- hybrid cloud
- create a private virtual interface for accessing a vpc via direct connect
- create a direct connect gateway
- list all available direct connect colocation facility locations
- create lag
- create a link aggregation group to bundle multiple connections for redundancy
- cloud architect designing hybrid network connectivity between on-premises and aws
- create connection
- list all virtual interfaces
- network engineer provisioning and managing dedicated connections and virtual interfaces
- aws
- describe connections
- end-to-end hybrid network management using amazon direct connect
- create private vif
- list direct connect gateways for multi-region and multi-vpc connectivity
- Cloud Architect
- create a new dedicated connection
- describe direct connect gateways
- create a direct connect gateway to attach multiple vpcs across regions
- multi-vpc and multi-region access via direct connect gateways
- list link aggregation groups providing redundant bundled connections
- describe lags
- delete virtual interface
- create a transit virtual interface for transit gateway
- create a new dedicated physical connection at a direct connect location
- list direct connect gateways
- delete a virtual interface from a direct connect connection
- create gateway
- provisioning and managing physical dedicated connections
- create a transit virtual interface for accessing transit gateway via direct connect
- Network Engineer
- available direct connect locations
- describe gateways
- create a link aggregation group
- create transit virtual interface
- dedicated physical connections to aws
- dedicated connection
- describe locations
- list all direct connect dedicated connections in the account
- delete connection
- direct connect
- direct connect gateways for multi-vpc and multi-region access
- managing virtual interfaces and bgp peering
- create direct connect gateway
- list direct connect colocation facilities
- virtual interfaces providing network access
slug: hybrid-network-connectivity
source_filename: hybrid-network-connectivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Direct Connect Hybrid Network Connectivity\n  description: >-\n    Workflow capability for network engineers and cloud architects to manage\n    dedicated private connections between on-premises networks and AWS using\n    Amazon Direct Connect. Covers connection provisioning, virtual interface\n    management, gateway associations, LAG configuration, and network troubleshooting.\n  tags:\n    - Amazon Direct Connect\n    - Hybrid Cloud\n    - Network Engineering\n    - Dedicated Connection\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: direct-connect\n      location: ./shared/direct-connect-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hybrid-network-connectivity-api\n\
  \      description: Unified REST API for Amazon Direct Connect hybrid network connectivity workflows.\n      resources:\n        - path: /v1/connections\n          name: connections\n          description: Dedicated physical connections to AWS\n          operations:\n            - method: GET\n              name: describe-connections\n              description: List all Direct Connect connections\n              call: \"direct-connect.describe-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-connection\n              description: Create a new dedicated connection\n              call: \"direct-connect.create-connection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/virtual-interfaces\n          name: virtual-interfaces\n          description: Virtual interfaces providing network access\n    \
  \      operations:\n            - method: GET\n              name: describe-virtual-interfaces\n              description: List all virtual interfaces\n              call: \"direct-connect.describe-virtual-interfaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-private-vif\n              description: Create a private virtual interface for VPC access\n              call: \"direct-connect.create-private-virtual-interface\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-transit-vif\n              description: Create a transit virtual interface for Transit Gateway\n              call: \"direct-connect.create-transit-virtual-interface\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/gateways\n    \
  \      name: gateways\n          description: Direct Connect gateways for multi-VPC and multi-region access\n          operations:\n            - method: GET\n              name: describe-gateways\n              description: List Direct Connect gateways\n              call: \"direct-connect.describe-direct-connect-gateways\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-gateway\n              description: Create a Direct Connect gateway\n              call: \"direct-connect.create-direct-connect-gateway\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/lags\n          name: lags\n          description: Link aggregation groups for redundant connections\n          operations:\n            - method: GET\n              name: describe-lags\n              description: List link aggregation groups\n           \
  \   call: \"direct-connect.describe-lags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lag\n              description: Create a link aggregation group\n              call: \"direct-connect.create-lag\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations\n          name: locations\n          description: Available Direct Connect locations\n          operations:\n            - method: GET\n              name: describe-locations\n              description: List Direct Connect colocation facilities\n              call: \"direct-connect.describe-locations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: hybrid-network-connectivity-mcp\n      transport: http\n      description: MCP server for AI-assisted\
  \ Direct Connect hybrid network management.\n      tools:\n        - name: describe-connections\n          description: List all Direct Connect dedicated connections in the account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"direct-connect.describe-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-connection\n          description: Create a new dedicated physical connection at a Direct Connect location\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"direct-connect.create-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-connection\n          description: Delete a Direct Connect connection\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"direct-connect.delete-connection\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-virtual-interfaces\n          description: List all virtual interfaces configured on Direct Connect connections\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"direct-connect.describe-virtual-interfaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-private-virtual-interface\n          description: Create a private virtual interface for accessing a VPC via Direct Connect\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"direct-connect.create-private-virtual-interface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-transit-virtual-interface\n          description: Create a transit virtual interface for accessing Transit Gateway via Direct Connect\n\
  \          hints:\n            readOnly: false\n            destructive: false\n          call: \"direct-connect.create-transit-virtual-interface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-virtual-interface\n          description: Delete a virtual interface from a Direct Connect connection\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"direct-connect.delete-virtual-interface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-direct-connect-gateways\n          description: List Direct Connect gateways for multi-region and multi-VPC connectivity\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"direct-connect.describe-direct-connect-gateways\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: create-direct-connect-gateway\n          description: Create a Direct Connect gateway to attach multiple VPCs across regions\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"direct-connect.create-direct-connect-gateway\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-lags\n          description: List link aggregation groups providing redundant bundled connections\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"direct-connect.describe-lags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-lag\n          description: Create a link aggregation group to bundle multiple connections for redundancy\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"direct-connect.create-lag\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: describe-locations\n          description: List all available Direct Connect colocation facility locations\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"direct-connect.describe-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-direct-connect/refs/heads/main/capabilities/hybrid-network-connectivity.yaml
tags:
- Amazon Direct Connect
- Hybrid Cloud
- Network Engineering
- Dedicated Connection
tools:
- description: List all Direct Connect dedicated connections in the account
  hints:
    openWorld: true
    readOnly: true
  name: describe-connections
- description: Create a new dedicated physical connection at a Direct Connect location
  hints:
    destructive: false
    readOnly: false
  name: create-connection
- description: Delete a Direct Connect connection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-connection
- description: List all virtual interfaces configured on Direct Connect connections
  hints:
    openWorld: true
    readOnly: true
  name: describe-virtual-interfaces
- description: Create a private virtual interface for accessing a VPC via Direct Connect
  hints:
    destructive: false
    readOnly: false
  name: create-private-virtual-interface
- description: Create a transit virtual interface for accessing Transit Gateway via Direct Connect
  hints:
    destructive: false
    readOnly: false
  name: create-transit-virtual-interface
- description: Delete a virtual interface from a Direct Connect connection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-virtual-interface
- description: List Direct Connect gateways for multi-region and multi-VPC connectivity
  hints:
    openWorld: true
    readOnly: true
  name: describe-direct-connect-gateways
- description: Create a Direct Connect gateway to attach multiple VPCs across regions
  hints:
    destructive: false
    readOnly: false
  name: create-direct-connect-gateway
- description: List link aggregation groups providing redundant bundled connections
  hints:
    openWorld: true
    readOnly: true
  name: describe-lags
- description: Create a link aggregation group to bundle multiple connections for redundancy
  hints:
    destructive: false
    readOnly: false
  name: create-lag
- description: List all available Direct Connect colocation facility locations
  hints:
    openWorld: true
    readOnly: true
  name: describe-locations
---
