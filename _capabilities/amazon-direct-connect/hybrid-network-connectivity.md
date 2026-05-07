---
categories: []
consumed_apis: []
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
- amazon direct connect
- describe virtual interfaces
- list link aggregation groups
- list direct connect colocation facilities
- delete connection
- create a private virtual interface for accessing a vpc via direct connect
- dedicated physical connections to aws
- create a transit virtual interface for accessing transit gateway via direct connect
- list all available direct connect colocation facility locations
- Cloud Architect
- network engineer provisioning and managing dedicated connections and virtual interfaces
- networking
- list all virtual interfaces
- create a new dedicated connection
- create direct connect gateway
- create a link aggregation group to bundle multiple connections for redundancy
- list link aggregation groups providing redundant bundled connections
- create transit virtual interface
- create a new dedicated physical connection at a direct connect location
- network engineering
- create gateway
- list all direct connect connections
- end-to-end hybrid network management using amazon direct connect
- create private vif
- describe lags
- direct connect gateways for multi-vpc and multi-region access
- list direct connect gateways for multi-region and multi-vpc connectivity
- create transit vif
- dedicated connection
- create a private virtual interface for vpc access
- create connection
- create lag
- multi-vpc and multi-region access via direct connect gateways
- list all virtual interfaces configured on direct connect connections
- describe gateways
- describe locations
- delete a direct connect connection
- provisioning and managing physical dedicated connections
- cloud architect designing hybrid network connectivity between on-premises and aws
- create a transit virtual interface for transit gateway
- describe direct connect gateways
- list direct connect gateways
- create a direct connect gateway to attach multiple vpcs across regions
- managing virtual interfaces and bgp peering
- delete virtual interface
- link aggregation groups for redundant connections
- create a link aggregation group
- create a direct connect gateway
- available direct connect locations
- direct connect
- create private virtual interface
- hybrid cloud
- aws
- Network Engineer
- delete a virtual interface from a direct connect connection
- describe connections
- virtual interfaces providing network access
- list all direct connect dedicated connections in the account
slug: hybrid-network-connectivity
source_filename: hybrid-network-connectivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Direct Connect Hybrid Network Connectivity\n  description: Workflow capability for network engineers and cloud architects to manage dedicated private connections between\n    on-premises networks and AWS using Amazon Direct Connect. Covers connection provisioning, virtual interface management,\n    gateway associations, LAG configuration, and network troubleshooting.\n  tags:\n  - Amazon Direct Connect\n  - Hybrid Cloud\n  - Network Engineering\n  - Dedicated Connection\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: direct-connect\n    baseUri: https://directconnect.us-east-1.amazonaws.com\n    description: Amazon Direct Connect REST API for managing hybrid network connectivity.\n    authentication:\n     \
  \ type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: connections\n      path: /\n      description: Dedicated physical connections to AWS\n      operations:\n      - name: describe-connections\n        method: POST\n        description: Displays all connections in this Region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Creates a connection between a customer network and an AWS Direct Connect location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-connection\n        method: POST\n        description: Deletes the specified connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: virtual-interfaces\n      path: /\n      description: Virtual interfaces on connections\n      operations:\n      - name: describe-virtual-interfaces\n        method: POST\n        description: Displays all virtual interfaces for an AWS account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-private-virtual-interface\n        method: POST\n        description: Creates a private virtual interface for access to Amazon VPC\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-public-virtual-interface\n        method: POST\n        description: Creates a public virtual interface for access to public AWS services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-transit-virtual-interface\n\
  \        method: POST\n        description: Creates a transit virtual interface for access to AWS Transit Gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-virtual-interface\n        method: POST\n        description: Deletes a virtual interface\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: direct-connect-gateways\n      path: /\n      description: Direct Connect gateways for multi-VPC and multi-region access\n      operations:\n      - name: describe-direct-connect-gateways\n        method: POST\n        description: Lists all Direct Connect gateways in your AWS account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-direct-connect-gateway\n        method: POST\n        description: Creates\
  \ a Direct Connect gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-direct-connect-gateway\n        method: POST\n        description: Deletes the specified Direct Connect gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lags\n      path: /\n      description: Link aggregation groups (LAGs)\n      operations:\n      - name: describe-lags\n        method: POST\n        description: Describes all Link Aggregation Groups in your account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-lag\n        method: POST\n        description: Creates a link aggregation group (LAG) with the specified number of bundled connections\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-lag\n        method: POST\n        description: Deletes the specified LAG\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /\n      description: Direct Connect locations\n      operations:\n      - name: describe-locations\n        method: POST\n        description: Lists the Direct Connect locations in the current Region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hybrid-network-connectivity-api\n    description: Unified REST API for Amazon Direct Connect hybrid network connectivity workflows.\n    resources:\n    - path: /v1/connections\n      name: connections\n      description: Dedicated physical connections to AWS\n      operations:\n      - method: GET\n\
  \        name: describe-connections\n        description: List all Direct Connect connections\n        call: direct-connect.describe-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-connection\n        description: Create a new dedicated connection\n        call: direct-connect.create-connection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/virtual-interfaces\n      name: virtual-interfaces\n      description: Virtual interfaces providing network access\n      operations:\n      - method: GET\n        name: describe-virtual-interfaces\n        description: List all virtual interfaces\n        call: direct-connect.describe-virtual-interfaces\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-private-vif\n        description: Create a private virtual interface for VPC access\n        call: direct-connect.create-private-virtual-interface\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-transit-vif\n        description: Create a transit virtual interface for Transit Gateway\n        call: direct-connect.create-transit-virtual-interface\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      name: gateways\n      description: Direct Connect gateways for multi-VPC and multi-region access\n      operations:\n      - method: GET\n        name: describe-gateways\n        description: List Direct Connect gateways\n        call: direct-connect.describe-direct-connect-gateways\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-gateway\n        description: Create a Direct Connect gateway\n        call: direct-connect.create-direct-connect-gateway\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lags\n \
  \     name: lags\n      description: Link aggregation groups for redundant connections\n      operations:\n      - method: GET\n        name: describe-lags\n        description: List link aggregation groups\n        call: direct-connect.describe-lags\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-lag\n        description: Create a link aggregation group\n        call: direct-connect.create-lag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Available Direct Connect locations\n      operations:\n      - method: GET\n        name: describe-locations\n        description: List Direct Connect colocation facilities\n        call: direct-connect.describe-locations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hybrid-network-connectivity-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Direct Connect hybrid network management.\n    tools:\n    - name: describe-connections\n      description: List all Direct Connect dedicated connections in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: direct-connect.describe-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-connection\n      description: Create a new dedicated physical connection at a Direct Connect location\n      hints:\n        readOnly: false\n        destructive: false\n      call: direct-connect.create-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-connection\n      description: Delete a Direct Connect connection\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: direct-connect.delete-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: describe-virtual-interfaces\n      description: List all virtual interfaces configured on Direct Connect connections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: direct-connect.describe-virtual-interfaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-private-virtual-interface\n      description: Create a private virtual interface for accessing a VPC via Direct Connect\n      hints:\n        readOnly: false\n        destructive: false\n      call: direct-connect.create-private-virtual-interface\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-transit-virtual-interface\n      description: Create a transit virtual interface for accessing Transit Gateway via Direct Connect\n      hints:\n        readOnly: false\n        destructive: false\n      call: direct-connect.create-transit-virtual-interface\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: delete-virtual-interface\n      description: Delete a virtual interface from a Direct Connect connection\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: direct-connect.delete-virtual-interface\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-direct-connect-gateways\n      description: List Direct Connect gateways for multi-region and multi-VPC connectivity\n      hints:\n        readOnly: true\n        openWorld: true\n      call: direct-connect.describe-direct-connect-gateways\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-direct-connect-gateway\n      description: Create a Direct Connect gateway to attach multiple VPCs across regions\n      hints:\n        readOnly: false\n        destructive: false\n      call: direct-connect.create-direct-connect-gateway\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ describe-lags\n      description: List link aggregation groups providing redundant bundled connections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: direct-connect.describe-lags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-lag\n      description: Create a link aggregation group to bundle multiple connections for redundancy\n      hints:\n        readOnly: false\n        destructive: false\n      call: direct-connect.create-lag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-locations\n      description: List all available Direct Connect colocation facility locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: direct-connect.describe-locations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
