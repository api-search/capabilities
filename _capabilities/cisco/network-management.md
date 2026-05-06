---
categories: []
consumed_apis: []
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
- networking
- collaboration
- unified network management combining meraki and other cisco apis
- list devices
- cisco
- network management
- sd-wan
- Network Admin
- network administrators managing cisco infrastructure
- list networks
- enterprise
- list organizations
- list networks in organization
- security
- list meraki organizations
- networks
- network organizations
- list devices in network
slug: network-management
source_filename: network-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cisco Network Management\n  description: Unified network management workflow combining Meraki, Catalyst Center, and SD-WAN APIs for network administrators.\n  tags:\n  - Cisco\n  - Network Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MERAKI_API_KEY: MERAKI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: meraki\n    baseUri: https://api.meraki.com/api/v1\n    description: Cisco Meraki Dashboard API v1\n    authentication:\n      type: apikey\n      key: X-Cisco-Meraki-API-Key\n      value: '{{MERAKI_API_KEY}}'\n      placement: header\n    resources:\n    - name: organizations\n      path: /organizations\n      description: Meraki organizations\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: networks\n      path: /organizations/{organizationId}/networks\n      description: Networks within an organization\n      operations:\n      - name: list-networks\n        method: GET\n        description: List networks in an organization\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devices\n      path: /networks/{networkId}/devices\n      description: Devices in a network\n      operations:\n      - name: list-devices\n        method: GET\n        description: List devices in a network\n        inputParameters:\n        - name: networkId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: network-management-api\n    description: Unified REST API for Cisco network management.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: Network organizations\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List organizations\n        call: meraki.list-organizations\n    - path: /v1/networks\n      name: networks\n      description: Networks\n      operations:\n      - method: GET\n        name: list-networks\n        description: List networks\n        call: meraki.list-networks\n  - type: mcp\n    port: 9090\n    namespace: network-management-mcp\n    transport: http\n    description: MCP server for AI-assisted network management.\n    tools:\n    - name: list-organizations\n      description: List Meraki organizations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: meraki.list-organizations\n    - name: list-networks\n\
  \      description: List networks in organization\n      hints:\n        readOnly: true\n      call: meraki.list-networks\n    - name: list-devices\n      description: List devices in network\n      hints:\n        readOnly: true\n      call: meraki.list-devices\n"
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
