---
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
- create a direct connect gateway to attach multiple vpcs across regions
- describe virtual interfaces
- list direct connect gateways
- describe lags
- direct connect
- describe connections
- link aggregation groups for redundant connections
- networking
- dedicated physical connections to aws
- create gateway
- create a private virtual interface for vpc access
- create transit virtual interface
- list link aggregation groups providing redundant bundled connections
- create a private virtual interface for accessing a vpc via direct connect
- list link aggregation groups
- available direct connect locations
- list all direct connect connections
- list direct connect colocation facilities
- Cloud Architect
- network engineer provisioning and managing dedicated connections and virtual interfaces
- managing virtual interfaces and bgp peering
- multi-vpc and multi-region access via direct connect gateways
- create direct connect gateway
- virtual interfaces providing network access
- dedicated connection
- describe gateways
- delete virtual interface
- list all available direct connect colocation facility locations
- create connection
- create private virtual interface
- delete connection
- create transit vif
- network engineering
- create lag
- create a new dedicated physical connection at a direct connect location
- list direct connect gateways for multi-region and multi-vpc connectivity
- create a link aggregation group
- direct connect gateways for multi-vpc and multi-region access
- create a transit virtual interface for transit gateway
- create a transit virtual interface for accessing transit gateway via direct connect
- describe direct connect gateways
- hybrid cloud
- create a link aggregation group to bundle multiple connections for redundancy
- create a direct connect gateway
- provisioning and managing physical dedicated connections
- cloud architect designing hybrid network connectivity between on-premises and aws
- Network Engineer
- list all direct connect dedicated connections in the account
- list all virtual interfaces
- create private vif
- aws
- delete a virtual interface from a direct connect connection
- delete a direct connect connection
- end-to-end hybrid network management using amazon direct connect
- list all virtual interfaces configured on direct connect connections
- describe locations
- create a new dedicated connection
- amazon direct connect
slug: hybrid-network-connectivity
tags:
- Amazon Direct Connect
- Hybrid Cloud
- Network Engineering
- Dedicated Connection
- AWS
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
