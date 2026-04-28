---
categories: []
consumed_apis:
- zones-mgmt
description: Unified zone lifecycle workflow combining zone creation, configuration, administration, monitoring, and migration. Used by system administrators and platform engineers to manage Solaris virtualization infrastructure.
layout: capability
name: Solaris Zone Lifecycle Management
operations:
- description: List all zones.
  method: GET
  name: list-zones
  path: /v1/zones
- description: Create a new zone.
  method: POST
  name: create-zone
  path: /v1/zones
- description: Get zone details.
  method: GET
  name: get-zone
  path: /v1/zones/{zoneName}
- description: Delete a zone.
  method: DELETE
  name: delete-zone
  path: /v1/zones/{zoneName}
- description: Get current zone state.
  method: GET
  name: get-zone-state
  path: /v1/zones/{zoneName}/state
- description: Boot the zone.
  method: POST
  name: boot-zone
  path: /v1/zones/{zoneName}/boot
- description: Gracefully shutdown.
  method: POST
  name: shutdown-zone
  path: /v1/zones/{zoneName}/shutdown
- description: Reboot the zone.
  method: POST
  name: reboot-zone
  path: /v1/zones/{zoneName}/reboot
- description: Migrate to another host.
  method: POST
  name: migrate-zone
  path: /v1/zones/{zoneName}/migrate
personas: []
provider_name: Solaris Zones
provider_slug: solaris-zones
search_terms:
- create zone
- boot a solaris zone.
- zone state operations.
- halt zone
- reboot zone
- individual zone operations.
- containers
- migrate a zone to another host.
- get solaris zone details.
- verify zone configuration integrity.
- gracefully shutdown.
- lifecycle management
- install zone
- get zone details.
- install a solaris zone.
- list zones
- rad
- list all solaris zones with status.
- uninstall zone
- reboot the zone.
- zone inventory and creation.
- virtualization
- uninstall a solaris zone.
- shutdown zone
- oracle
- kernel zones
- clone zone
- delete a zone.
- boot the zone.
- create a new solaris zone.
- gracefully shutdown a zone.
- clone a solaris zone.
- halt a zone immediately.
- list all zones.
- delete zone
- reboot a zone.
- solaris
- shutdown a zone.
- get zone state
- statsstore
- migrate a zone.
- boot zone
- operating systems
- reboot a solaris zone.
- delete a solaris zone.
- get zone
- migrate zone
- get current zone state.
- migrate to another host.
- verify zone
- resource management
- create a new zone.
- zones
- boot a zone.
slug: zone-lifecycle
tags:
- Solaris
- Zones
- Virtualization
- Lifecycle Management
tools:
- description: List all Solaris zones with status.
  hints:
    idempotent: true
    readOnly: true
  name: list-zones
- description: Create a new Solaris zone.
  hints:
    readOnly: false
  name: create-zone
- description: Get Solaris zone details.
  hints:
    idempotent: true
    readOnly: true
  name: get-zone
- description: Get current zone state.
  hints:
    idempotent: true
    readOnly: true
  name: get-zone-state
- description: Boot a Solaris zone.
  hints:
    readOnly: false
  name: boot-zone
- description: Halt a zone immediately.
  hints:
    destructive: true
    readOnly: false
  name: halt-zone
- description: Gracefully shutdown a zone.
  hints:
    readOnly: false
  name: shutdown-zone
- description: Reboot a Solaris zone.
  hints:
    readOnly: false
  name: reboot-zone
- description: Install a Solaris zone.
  hints:
    readOnly: false
  name: install-zone
- description: Uninstall a Solaris zone.
  hints:
    destructive: true
    readOnly: false
  name: uninstall-zone
- description: Clone a Solaris zone.
  hints:
    readOnly: false
  name: clone-zone
- description: Migrate a zone to another host.
  hints:
    readOnly: false
  name: migrate-zone
- description: Verify zone configuration integrity.
  hints:
    idempotent: true
    readOnly: true
  name: verify-zone
- description: Delete a Solaris zone.
  hints:
    destructive: true
    readOnly: false
  name: delete-zone
---
