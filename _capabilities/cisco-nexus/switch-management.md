---
categories: []
consumed_apis:
- nxapi-rest
description: Unified workflow for network administrators to configure and monitor Cisco Nexus switches including interfaces, VLANs, routing, and system features via the NX-API REST DME object model.
layout: capability
name: Cisco Nexus Switch Management
operations:
- description: Get system information
  method: GET
  name: get-system-info
  path: /v1/system
- description: List all physical interfaces
  method: GET
  name: list-interfaces
  path: /v1/interfaces
- description: Get interface details
  method: GET
  name: get-interface
  path: /v1/interfaces/{interfaceId}
- description: List all VLANs
  method: GET
  name: list-vlans
  path: /v1/vlans
- description: Create a VLAN
  method: POST
  name: create-vlan
  path: /v1/vlans
- description: Get VLAN details
  method: GET
  name: get-vlan
  path: /v1/vlans/{vlanEncap}
- description: Delete a VLAN
  method: DELETE
  name: delete-vlan
  path: /v1/vlans/{vlanEncap}
- description: List all static routes
  method: GET
  name: list-routes
  path: /v1/routes
personas: []
provider_name: Cisco Nexus Dashboard
provider_slug: cisco-nexus
search_terms:
- configure static route
- get system info
- interface management
- get svi
- configure system
- delete a vlan
- list all vlans
- single interface operations
- system information
- sdn
- configure interface
- create or modify ipv4 static routes
- network management
- vlan management
- list all ipv4 static routes across all vrfs
- apply system-level configuration changes
- get vlan bridge domain details
- configure svi
- get static route
- configure features
- list all physical interfaces
- create a vlan
- enable or disable nx-os features (interface-vlan, bgp, ospf, lacp)
- static route management
- get nexus switch system information including hostname, serial, and nx-os version
- get a specific static route by vrf and prefix
- list all physical ethernet interfaces on the switch
- list static routes
- create or modify a vlan bridge domain
- single vlan operations
- create or modify a switch virtual interface for layer 3 routing
- data center
- configure a physical ethernet interface (admin state, speed, vlan, etc.)
- delete a vlan bridge domain from the switch
- delete vlan
- nexus
- get bgp config
- infrastructure
- get switch virtual interface configuration
- get interface details
- get vlan
- list all static routes
- list all vlan bridge domains on the switch
- switches
- get system information
- create vlan
- get interface
- list interfaces
- get configuration and operational state of a physical interface
- list vlans
- cisco
- list routes
- networking
- get the full bgp configuration tree
- network automation
- get vlan details
slug: switch-management
tags:
- Cisco
- Nexus
- Network Management
- Data Center
tools:
- description: Get Nexus switch system information including hostname, serial, and NX-OS version
  hints:
    openWorld: true
    readOnly: true
  name: get-system-info
- description: List all physical Ethernet interfaces on the switch
  hints:
    readOnly: true
  name: list-interfaces
- description: Get configuration and operational state of a physical interface
  hints:
    readOnly: true
  name: get-interface
- description: Configure a physical Ethernet interface (admin state, speed, VLAN, etc.)
  hints:
    idempotent: true
    readOnly: false
  name: configure-interface
- description: List all VLAN bridge domains on the switch
  hints:
    readOnly: true
  name: list-vlans
- description: Create or modify a VLAN bridge domain
  hints:
    readOnly: false
  name: create-vlan
- description: Get VLAN bridge domain details
  hints:
    readOnly: true
  name: get-vlan
- description: Delete a VLAN bridge domain from the switch
  hints:
    destructive: true
  name: delete-vlan
- description: Get Switch Virtual Interface configuration
  hints:
    readOnly: true
  name: get-svi
- description: Create or modify a Switch Virtual Interface for Layer 3 routing
  hints:
    readOnly: false
  name: configure-svi
- description: List all IPv4 static routes across all VRFs
  hints:
    readOnly: true
  name: list-static-routes
- description: Create or modify IPv4 static routes
  hints:
    readOnly: false
  name: configure-static-route
- description: Get a specific static route by VRF and prefix
  hints:
    readOnly: true
  name: get-static-route
- description: Get the full BGP configuration tree
  hints:
    readOnly: true
  name: get-bgp-config
- description: Enable or disable NX-OS features (interface-vlan, BGP, OSPF, LACP)
  hints:
    readOnly: false
  name: configure-features
- description: Apply system-level configuration changes
  hints:
    readOnly: false
  name: configure-system
---
