---
categories:
- monitoring
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
- list all access points with status
- get access point
- list all access points with status and statistics
- client connectivity
- list all configuration groups
- list devices
- switches
- delete site
- list sites
- list gateways
- get device details by serial number
- wireless
- list all sites
- list all connected clients
- device details
- get site details by id
- list clients
- get group details by name
- access point monitoring
- site management
- infrastructure
- networking
- remove device
- remove a device from inventory
- create site
- list networks
- list all gateways
- sd-wan
- delete group
- delete a configuration group
- gateway monitoring
- aruba
- monitoring
- list all networks
- configuration group management
- cloud
- list groups
- associate devices to site
- list all devices in the network inventory
- get device
- device inventory management
- cloud management
- create a new configuration group
- get group
- get site
- network management
- create a new site
- list access points
- create group
- delete a site
- list all devices in the aruba central device inventory
- get access point details by serial number
- associate devices to a site
- security
- network monitoring
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
