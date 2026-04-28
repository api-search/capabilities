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
- virtualization
- shutdown a zone.
- boot a zone.
- get zone
- clone a solaris zone.
- verify zone configuration integrity.
- get solaris zone details.
- delete a zone.
- migrate to another host.
- install a solaris zone.
- zone state operations.
- operating systems
- halt a zone immediately.
- list all solaris zones with status.
- shutdown zone
- zone inventory and creation.
- get zone state
- reboot a zone.
- reboot the zone.
- migrate a zone to another host.
- delete zone
- create a new zone.
- boot a solaris zone.
- clone zone
- oracle
- containers
- statsstore
- solaris
- boot zone
- create zone
- reboot a solaris zone.
- rad
- list zones
- gracefully shutdown.
- halt zone
- delete a solaris zone.
- migrate a zone.
- individual zone operations.
- gracefully shutdown a zone.
- boot the zone.
- migrate zone
- resource management
- create a new solaris zone.
- zones
- list all zones.
- reboot zone
- verify zone
- lifecycle management
- uninstall a solaris zone.
- kernel zones
- get current zone state.
- uninstall zone
- install zone
- get zone details.
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
