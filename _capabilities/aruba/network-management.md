---
consumed_apis:
- aruba-central
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
- switches
- get group
- list all access points with status
- get access point
- delete a site
- list devices
- get site
- list clients
- network management
- create a new site
- security
- get device
- list all gateways
- list groups
- list all connected clients
- access point monitoring
- list all networks
- list gateways
- site management
- get group details by name
- create group
- list all devices in the network inventory
- list networks
- cloud
- associate devices to site
- remove device
- network monitoring
- list all sites
- get device details by serial number
- create site
- list all access points with status and statistics
- configuration group management
- monitoring
- client connectivity
- list all devices in the aruba central device inventory
- wireless
- delete site
- get access point details by serial number
- associate devices to a site
- device inventory management
- remove a device from inventory
- device details
- infrastructure
- delete a configuration group
- list sites
- networking
- delete group
- list all configuration groups
- sd-wan
- aruba
- list access points
- get site details by id
- cloud management
- create a new configuration group
- gateway monitoring
slug: network-management
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
