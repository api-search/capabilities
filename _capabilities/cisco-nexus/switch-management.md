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
- static route management
- create a vlan
- create or modify a vlan bridge domain
- list routes
- switches
- get svi
- list all vlan bridge domains on the switch
- get vlan
- get nexus switch system information including hostname, serial, and nx-os version
- interface management
- list all ipv4 static routes across all vrfs
- infrastructure
- get system info
- create or modify a switch virtual interface for layer 3 routing
- get bgp config
- networking
- get interface details
- list all physical ethernet interfaces on the switch
- configure static route
- sdn
- configure svi
- get static route
- enable or disable nx-os features (interface-vlan, bgp, ospf, lacp)
- vlan management
- configure features
- single vlan operations
- list interfaces
- list all vlans
- configure system
- data center
- cisco
- delete vlan
- delete a vlan
- get configuration and operational state of a physical interface
- single interface operations
- get switch virtual interface configuration
- get the full bgp configuration tree
- system information
- network automation
- get vlan bridge domain details
- get system information
- list all static routes
- get interface
- get vlan details
- create vlan
- nexus
- list all physical interfaces
- configure a physical ethernet interface (admin state, speed, vlan, etc.)
- configure interface
- delete a vlan bridge domain from the switch
- network management
- list static routes
- create or modify ipv4 static routes
- apply system-level configuration changes
- list vlans
- get a specific static route by vrf and prefix
slug: switch-management
source_filename: switch-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cisco Nexus Switch Management\"\n  description: \"Unified workflow for network administrators to configure and monitor Cisco Nexus switches including interfaces, VLANs, routing, and system features via the NX-API REST DME object model.\"\n  tags:\n    - Cisco\n    - Nexus\n    - Network Management\n    - Data Center\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEXUS_USERNAME: NEXUS_USERNAME\n      NEXUS_PASSWORD: NEXUS_PASSWORD\n\ncapability:\n  consumes:\n    - import: nxapi-rest\n      location: ./shared/nxapi-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: switch-management-api\n      description: \"Unified REST API for Cisco Nexus switch management.\"\n      resources:\n        - path: /v1/system\n          name: system\n          description: \"System information\"\n          operations:\n            - method: GET\n              name: get-system-info\n\
  \              description: \"Get system information\"\n              call: \"nxapi-rest.get-system-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/interfaces\n          name: interfaces\n          description: \"Interface management\"\n          operations:\n            - method: GET\n              name: list-interfaces\n              description: \"List all physical interfaces\"\n              call: \"nxapi-rest.list-physical-interfaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/interfaces/{interfaceId}\n          name: interface-detail\n          description: \"Single interface operations\"\n          operations:\n            - method: GET\n              name: get-interface\n              description: \"Get interface details\"\n              call: \"nxapi-rest.get-physical-interface\"\n              with:\n                interfaceId:\
  \ \"rest.interfaceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vlans\n          name: vlans\n          description: \"VLAN management\"\n          operations:\n            - method: GET\n              name: list-vlans\n              description: \"List all VLANs\"\n              call: \"nxapi-rest.list-vlans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-vlan\n              description: \"Create a VLAN\"\n              call: \"nxapi-rest.create-vlan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vlans/{vlanEncap}\n          name: vlan-detail\n          description: \"Single VLAN operations\"\n          operations:\n            - method: GET\n              name: get-vlan\n              description: \"Get VLAN details\"\n  \
  \            call: \"nxapi-rest.get-vlan\"\n              with:\n                vlanEncap: \"rest.vlanEncap\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-vlan\n              description: \"Delete a VLAN\"\n              call: \"nxapi-rest.delete-vlan\"\n              with:\n                vlanEncap: \"rest.vlanEncap\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"Static route management\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List all static routes\"\n              call: \"nxapi-rest.list-static-routes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: switch-management-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted Cisco Nexus switch management.\"\n      tools:\n        - name: get-system-info\n          description: \"Get Nexus switch system information including hostname, serial, and NX-OS version\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nxapi-rest.get-system-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-interfaces\n          description: \"List all physical Ethernet interfaces on the switch\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.list-physical-interfaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-interface\n          description: \"Get configuration and operational state of a physical interface\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.get-physical-interface\"\
  \n          with:\n            interfaceId: \"tools.interfaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: configure-interface\n          description: \"Configure a physical Ethernet interface (admin state, speed, VLAN, etc.)\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"nxapi-rest.configure-physical-interface\"\n          with:\n            interfaceEntity: \"tools.interfaceEntity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vlans\n          description: \"List all VLAN bridge domains on the switch\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.list-vlans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-vlan\n          description: \"Create or modify a VLAN bridge domain\"\n          hints:\n            readOnly:\
  \ false\n          call: \"nxapi-rest.create-vlan\"\n          with:\n            bdEntity: \"tools.bdEntity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vlan\n          description: \"Get VLAN bridge domain details\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.get-vlan\"\n          with:\n            vlanEncap: \"tools.vlanEncap\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-vlan\n          description: \"Delete a VLAN bridge domain from the switch\"\n          hints:\n            destructive: true\n          call: \"nxapi-rest.delete-vlan\"\n          with:\n            vlanEncap: \"tools.vlanEncap\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-svi\n          description: \"Get Switch Virtual Interface configuration\"\n          hints:\n            readOnly:\
  \ true\n          call: \"nxapi-rest.get-svi-interface\"\n          with:\n            sviId: \"tools.sviId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: configure-svi\n          description: \"Create or modify a Switch Virtual Interface for Layer 3 routing\"\n          hints:\n            readOnly: false\n          call: \"nxapi-rest.configure-svi-interface\"\n          with:\n            sviId: \"tools.sviId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-static-routes\n          description: \"List all IPv4 static routes across all VRFs\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.list-static-routes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: configure-static-route\n          description: \"Create or modify IPv4 static routes\"\n          hints:\n            readOnly:\
  \ false\n          call: \"nxapi-rest.configure-static-route\"\n          with:\n            ipv4Inst: \"tools.ipv4Inst\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-static-route\n          description: \"Get a specific static route by VRF and prefix\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.get-static-route\"\n          with:\n            vrfName: \"tools.vrfName\"\n            prefix: \"tools.prefix\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bgp-config\n          description: \"Get the full BGP configuration tree\"\n          hints:\n            readOnly: true\n          call: \"nxapi-rest.get-bgp-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: configure-features\n          description: \"Enable or disable NX-OS features (interface-vlan, BGP, OSPF,\
  \ LACP)\"\n          hints:\n            readOnly: false\n          call: \"nxapi-rest.configure-features\"\n          with:\n            fmEntity: \"tools.fmEntity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: configure-system\n          description: \"Apply system-level configuration changes\"\n          hints:\n            readOnly: false\n          call: \"nxapi-rest.configure-system\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cisco-nexus/refs/heads/main/capabilities/switch-management.yaml
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
