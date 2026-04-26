---
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
- enable or disable nx-os features (interface-vlan, bgp, ospf, lacp)
- create a vlan
- list all static routes
- get a specific static route by vrf and prefix
- configure static route
- delete a vlan
- create or modify ipv4 static routes
- configure system
- sdn
- switches
- single interface operations
- single vlan operations
- list routes
- network automation
- get system info
- interface management
- apply system-level configuration changes
- list all vlan bridge domains on the switch
- configure features
- system information
- get interface
- delete a vlan bridge domain from the switch
- get svi
- list all vlans
- cisco
- get system information
- configure interface
- create or modify a vlan bridge domain
- get configuration and operational state of a physical interface
- networking
- data center
- list vlans
- configure svi
- get vlan details
- get bgp config
- delete vlan
- infrastructure
- vlan management
- list all physical ethernet interfaces on the switch
- get static route
- configure a physical ethernet interface (admin state, speed, vlan, etc.)
- get vlan
- create or modify a switch virtual interface for layer 3 routing
- create vlan
- get nexus switch system information including hostname, serial, and nx-os version
- get switch virtual interface configuration
- list all ipv4 static routes across all vrfs
- get vlan bridge domain details
- network management
- list all physical interfaces
- static route management
- list static routes
- get the full bgp configuration tree
- list interfaces
- nexus
- get interface details
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
