---
categories: []
consumed_apis:
- meraki
description: Unified network management workflow combining Meraki, Catalyst Center, and SD-WAN APIs for network administrators.
layout: capability
name: Cisco Network Management
operations:
- description: List organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List networks
  method: GET
  name: list-networks
  path: /v1/networks
personas: []
provider_name: Cisco
provider_slug: cisco
search_terms:
- network administrators managing cisco infrastructure
- networking
- collaboration
- list networks
- list meraki organizations
- unified network management combining meraki and other cisco apis
- list organizations
- enterprise
- sd-wan
- security
- list devices in network
- cisco
- Network Admin
- network management
- networks
- list devices
- list networks in organization
- network organizations
slug: network-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cisco Network Management\"\n  description: \"Unified network management workflow combining Meraki, Catalyst Center, and SD-WAN APIs for network administrators.\"\n  tags:\n    - Cisco\n    - Network Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MERAKI_API_KEY: MERAKI_API_KEY\n\ncapability:\n  consumes:\n    - import: meraki\n      location: ./shared/meraki.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: network-management-api\n      description: \"Unified REST API for Cisco network management.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"Network organizations\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List organizations\"\n              call: \"meraki.list-organizations\"\n        - path: /v1/networks\n\
  \          name: networks\n          description: \"Networks\"\n          operations:\n            - method: GET\n              name: list-networks\n              description: \"List networks\"\n              call: \"meraki.list-networks\"\n\n    - type: mcp\n      port: 9090\n      namespace: network-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted network management.\"\n      tools:\n        - name: list-organizations\n          description: \"List Meraki organizations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"meraki.list-organizations\"\n        - name: list-networks\n          description: \"List networks in organization\"\n          hints:\n            readOnly: true\n          call: \"meraki.list-networks\"\n        - name: list-devices\n          description: \"List devices in network\"\n          hints:\n            readOnly: true\n          call: \"meraki.list-devices\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cisco/refs/heads/main/capabilities/network-management.yaml
tags:
- Cisco
- Network Management
tools:
- description: List Meraki organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List networks in organization
  hints:
    readOnly: true
  name: list-networks
- description: List devices in network
  hints:
    readOnly: true
  name: list-devices
---
