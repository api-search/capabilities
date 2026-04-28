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
- describe gateways
- create private virtual interface
- dedicated physical connections to aws
- create a private virtual interface for vpc access
- describe direct connect gateways
- describe virtual interfaces
- list all virtual interfaces
- create a new dedicated physical connection at a direct connect location
- amazon direct connect
- provisioning and managing physical dedicated connections
- network engineer provisioning and managing dedicated connections and virtual interfaces
- link aggregation groups for redundant connections
- multi-vpc and multi-region access via direct connect gateways
- delete a virtual interface from a direct connect connection
- create transit virtual interface
- create a transit virtual interface for transit gateway
- Cloud Architect
- managing virtual interfaces and bgp peering
- direct connect
- create direct connect gateway
- network engineering
- delete virtual interface
- delete connection
- list all virtual interfaces configured on direct connect connections
- end-to-end hybrid network management using amazon direct connect
- create lag
- list link aggregation groups providing redundant bundled connections
- describe connections
- create a direct connect gateway
- list link aggregation groups
- create a link aggregation group
- cloud architect designing hybrid network connectivity between on-premises and aws
- list all direct connect dedicated connections in the account
- describe locations
- describe lags
- create a private virtual interface for accessing a vpc via direct connect
- create a link aggregation group to bundle multiple connections for redundancy
- Network Engineer
- list direct connect colocation facilities
- list direct connect gateways for multi-region and multi-vpc connectivity
- create a new dedicated connection
- create gateway
- list direct connect gateways
- hybrid cloud
- create a direct connect gateway to attach multiple vpcs across regions
- virtual interfaces providing network access
- create transit vif
- create private vif
- delete a direct connect connection
- dedicated connection
- direct connect gateways for multi-vpc and multi-region access
- aws
- list all direct connect connections
- available direct connect locations
- create a transit virtual interface for accessing transit gateway via direct connect
- list all available direct connect colocation facility locations
- networking
- create connection
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
