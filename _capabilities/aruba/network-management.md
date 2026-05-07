---
categories:
- monitoring
consumed_apis: []
description: Unified network management workflow combining Aruba Central API for device inventory, configuration groups, sites, access points, clients, and gateway monitoring. Used by network administrators to manage campus and branch infrastructure.
layout: capability
name: Aruba Network Management
operations:
- description: List all devices in the network inventory
  method: GET
  name: list-devices
  path: /v1/devices
- description: Get device details by serial number
  method: GET
  name: get-device
  path: /v1/devices/{serial}
- description: Remove a device from inventory
  method: DELETE
  name: remove-device
  path: /v1/devices/{serial}
- description: List all configuration groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a new configuration group
  method: POST
  name: create-group
  path: /v1/groups
- description: List all sites
  method: GET
  name: list-sites
  path: /v1/sites
- description: Create a new site
  method: POST
  name: create-site
  path: /v1/sites
- description: List all access points with status
  method: GET
  name: list-access-points
  path: /v1/access-points
- description: List all connected clients
  method: GET
  name: list-clients
  path: /v1/clients
- description: List all networks
  method: GET
  name: list-networks
  path: /v1/networks
- description: List all gateways
  method: GET
  name: list-gateways
  path: /v1/gateways
personas: []
provider_name: Aruba
provider_slug: aruba
search_terms:
- create a new site
- create group
- device inventory management
- aruba
- list all devices in the network inventory
- device details
- get access point details by serial number
- get access point
- networking
- list all access points with status and statistics
- switches
- get device
- list groups
- list all configuration groups
- sd-wan
- cloud management
- network management
- get group details by name
- remove device
- create site
- list all access points with status
- associate devices to site
- list all sites
- list networks
- monitoring
- get device details by serial number
- get site
- list access points
- client connectivity
- configuration group management
- remove a device from inventory
- list sites
- list all gateways
- get group
- list all connected clients
- infrastructure
- gateway monitoring
- list clients
- site management
- create a new configuration group
- list all devices in the aruba central device inventory
- access point monitoring
- list gateways
- cloud
- list devices
- delete a site
- network monitoring
- associate devices to a site
- delete site
- delete group
- list all networks
- security
- delete a configuration group
- get site details by id
- wireless
slug: network-management
source_filename: network-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Aruba Network Management\n  description: Unified network management workflow combining Aruba Central API for device inventory, configuration groups,\n    sites, access points, clients, and gateway monitoring. Used by network administrators to manage campus and branch infrastructure.\n  tags:\n  - Aruba\n  - Network Management\n  - Cloud Management\n  - Monitoring\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ARUBA_CENTRAL_TOKEN: ARUBA_CENTRAL_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: aruba-central\n    baseUri: https://apigw-prod2.central.arubanetworks.com\n    description: Aruba Central cloud networking management API\n    authentication:\n      type: bearer\n      token: '{{ARUBA_CENTRAL_TOKEN}}'\n    resources:\n    - name: devices\n      path: /platform/device_inventory/v1\n      description: Device inventory management\n      operations:\n      - name: get-devices\n\
  \        method: GET\n        description: List all devices in the Aruba Central device inventory\n        inputParameters:\n        - name: sku_type\n          in: query\n          type: string\n          required: false\n          description: Filter by device type (IAP, HP, CONTROLLER, GATEWAY, SWITCH, VGW)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-device-by-serial\n        method: GET\n        description: Get device details by serial number\n        inputParameters:\n        - name: serial\n          in: path\n          type: string\n          required: true\n          description: The serial\
  \ number of the device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-device\n        method: DELETE\n        description: Delete a device from the inventory\n        inputParameters:\n        - name: serial\n          in: path\n          type: string\n          required: true\n          description: The serial number of the device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /configuration/v2\n      description: Configuration group management\n      operations:\n      - name: get-groups\n        method: GET\n        description: List all configuration groups\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n      \
  \    type: integer\n          required: false\n          description: Maximum number of items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new configuration group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            group: '{{tools.group}}'\n      - name: get-group-by-name\n        method: GET\n        description: Get group details by name\n        inputParameters:\n        - name: group_name\n          in: path\n          type: string\n          required: true\n          description: The name of the group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-group\n        method: PATCH\n\
  \        description: Update a configuration group\n        inputParameters:\n        - name: group_name\n          in: path\n          type: string\n          required: true\n          description: The name of the group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Delete a configuration group\n        inputParameters:\n        - name: group_name\n          in: path\n          type: string\n          required: true\n          description: The name of the group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites\n      path: /central/v2\n      description: Site and location management\n      operations:\n      - name: get-sites\n        method: GET\n        description: List all sites\n        inputParameters:\n        - name: offset\n     \
  \     in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-site\n        method: POST\n        description: Create a new site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            site_name: '{{tools.site_name}}'\n      - name: get-site-by-id\n        method: GET\n        description: Get site details by ID\n        inputParameters:\n        - name: site_id\n          in: path\n          type: integer\n          required: true\n          description: The site ID\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-site\n        method: PATCH\n        description: Update a site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: integer\n          required: true\n          description: The site ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-site\n        method: DELETE\n        description: Delete a site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: integer\n          required: true\n          description: The site ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: associate-devices-to-site\n        method: POST\n        description: Associate devices to a site\n        inputParameters:\n        - name: site_id\n \
  \         in: path\n          type: integer\n          required: true\n          description: The site ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /monitoring/v2\n      description: Network monitoring and access points\n      operations:\n      - name: get-access-points\n        method: GET\n        description: List all access points with status and statistics\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-access-point-by-serial\n        method: GET\n  \
  \      description: Get access point details by serial number\n        inputParameters:\n        - name: serial\n          in: path\n          type: string\n          required: true\n          description: The serial number of the access point\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-clients\n        method: GET\n        description: List all connected clients\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-networks\n        method: GET\n        description: List all networks\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gateways\n        method: GET\n        description: List all gateways\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aruba-network-mgmt-api\n    description: Unified REST API for Aruba network management operations.\n    resources:\n    - path: /v1/devices\n      name: devices\n      description: Device inventory management\n      operations:\n      - method: GET\n        name: list-devices\n        description: List all devices in the network inventory\n        call: aruba-central.get-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/{serial}\n      name: device-detail\n      description: Device details\n      operations:\n      - method: GET\n   \
  \     name: get-device\n        description: Get device details by serial number\n        call: aruba-central.get-device-by-serial\n        with:\n          serial: rest.serial\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-device\n        description: Remove a device from inventory\n        call: aruba-central.delete-device\n        with:\n          serial: rest.serial\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Configuration group management\n      operations:\n      - method: GET\n        name: list-groups\n        description: List all configuration groups\n        call: aruba-central.get-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a new configuration group\n        call: aruba-central.create-group\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites\n      name: sites\n      description: Site management\n      operations:\n      - method: GET\n        name: list-sites\n        description: List all sites\n        call: aruba-central.get-sites\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-site\n        description: Create a new site\n        call: aruba-central.create-site\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/access-points\n      name: access-points\n      description: Access point monitoring\n      operations:\n      - method: GET\n        name: list-access-points\n        description: List all access points with status\n        call: aruba-central.get-access-points\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clients\n      name: clients\n      description: Client connectivity\n\
  \      operations:\n      - method: GET\n        name: list-clients\n        description: List all connected clients\n        call: aruba-central.get-clients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/networks\n      name: networks\n      description: Network monitoring\n      operations:\n      - method: GET\n        name: list-networks\n        description: List all networks\n        call: aruba-central.get-networks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      name: gateways\n      description: Gateway monitoring\n      operations:\n      - method: GET\n        name: list-gateways\n        description: List all gateways\n        call: aruba-central.get-gateways\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aruba-network-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted Aruba network\
  \ management.\n    tools:\n    - name: list-devices\n      description: List all devices in the Aruba Central device inventory\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aruba-central.get-devices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-device\n      description: Get device details by serial number\n      hints:\n        readOnly: true\n      call: aruba-central.get-device-by-serial\n      with:\n        serial: tools.serial\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-device\n      description: Remove a device from inventory\n      hints:\n        destructive: true\n      call: aruba-central.delete-device\n      with:\n        serial: tools.serial\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List all configuration groups\n      hints:\n        readOnly: true\n      call: aruba-central.get-groups\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new configuration group\n      hints:\n        readOnly: false\n      call: aruba-central.create-group\n      with:\n        group: tools.group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-group\n      description: Get group details by name\n      hints:\n        readOnly: true\n      call: aruba-central.get-group-by-name\n      with:\n        group_name: tools.group_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-group\n      description: Delete a configuration group\n      hints:\n        destructive: true\n      call: aruba-central.delete-group\n      with:\n        group_name: tools.group_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sites\n      description: List all sites\n      hints:\n        readOnly: true\n      call: aruba-central.get-sites\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-site\n      description: Create a new site\n      hints:\n        readOnly: false\n      call: aruba-central.create-site\n      with:\n        site_name: tools.site_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-site\n      description: Get site details by ID\n      hints:\n        readOnly: true\n      call: aruba-central.get-site-by-id\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-site\n      description: Delete a site\n      hints:\n        destructive: true\n      call: aruba-central.delete-site\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associate-devices-to-site\n      description: Associate devices to a site\n      hints:\n        readOnly: false\n      call: aruba-central.associate-devices-to-site\n\
  \      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-access-points\n      description: List all access points with status and statistics\n      hints:\n        readOnly: true\n      call: aruba-central.get-access-points\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-access-point\n      description: Get access point details by serial number\n      hints:\n        readOnly: true\n      call: aruba-central.get-access-point-by-serial\n      with:\n        serial: tools.serial\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clients\n      description: List all connected clients\n      hints:\n        readOnly: true\n      call: aruba-central.get-clients\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-networks\n      description: List all networks\n      hints:\n        readOnly: true\n      call: aruba-central.get-networks\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-gateways\n      description: List all gateways\n      hints:\n        readOnly: true\n      call: aruba-central.get-gateways\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aruba/refs/heads/main/capabilities/network-management.yaml
tags:
- Aruba
- Network Management
- Cloud Management
- Monitoring
tools:
- description: List all devices in the Aruba Central device inventory
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get device details by serial number
  hints:
    readOnly: true
  name: get-device
- description: Remove a device from inventory
  hints:
    destructive: true
  name: remove-device
- description: List all configuration groups
  hints:
    readOnly: true
  name: list-groups
- description: Create a new configuration group
  hints:
    readOnly: false
  name: create-group
- description: Get group details by name
  hints:
    readOnly: true
  name: get-group
- description: Delete a configuration group
  hints:
    destructive: true
  name: delete-group
- description: List all sites
  hints:
    readOnly: true
  name: list-sites
- description: Create a new site
  hints:
    readOnly: false
  name: create-site
- description: Get site details by ID
  hints:
    readOnly: true
  name: get-site
- description: Delete a site
  hints:
    destructive: true
  name: delete-site
- description: Associate devices to a site
  hints:
    readOnly: false
  name: associate-devices-to-site
- description: List all access points with status and statistics
  hints:
    readOnly: true
  name: list-access-points
- description: Get access point details by serial number
  hints:
    readOnly: true
  name: get-access-point
- description: List all connected clients
  hints:
    readOnly: true
  name: list-clients
- description: List all networks
  hints:
    readOnly: true
  name: list-networks
- description: List all gateways
  hints:
    readOnly: true
  name: list-gateways
---
