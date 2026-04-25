---
consumed_apis:
- adt-platform
description: Unified workflow capability for managing ADT smart home security systems, monitoring alarm events, controlling devices, managing access codes, and retrieving video clips. Designed for homeowners, property managers, and smart home integration developers.
layout: capability
name: ADT Home Security Management
operations:
- description: List all security systems.
  method: GET
  name: list-systems
  path: /v1/systems
- description: Arm a security system.
  method: POST
  name: arm-system
  path: /v1/systems/{systemId}/arm
- description: Disarm a security system.
  method: POST
  name: disarm-system
  path: /v1/systems/{systemId}/disarm
- description: List devices in a system.
  method: GET
  name: list-devices
  path: /v1/systems/{systemId}/devices
- description: List security events.
  method: GET
  name: list-events
  path: /v1/systems/{systemId}/events
- description: List access codes.
  method: GET
  name: list-access-codes
  path: /v1/systems/{systemId}/access-codes
- description: Create an access code.
  method: POST
  name: create-access-code
  path: /v1/systems/{systemId}/access-codes
personas: []
provider_name: ADT
provider_slug: adt
search_terms:
- list all security devices (sensors, cameras, locks) in an adt system.
- adt
- list all security systems.
- list all adt security systems associated with the account.
- access control
- list security systems
- automation
- home security
- create temporary access code
- property manager
- list video clips
- unified workflow for managing adt smart home security
- smart home
- disarm a security system.
- get security events
- arm away
- create access code
- get system status
- security
- security devices.
- list all access codes configured for an adt security system.
- create an access code.
- arm a security system.
- list events
- retrieve recent security events, alarm history, and activity log.
- monitoring
- disarm system
- security events.
- arm an adt security system in away mode (all zones active).
- security system management.
- manager overseeing multiple residential properties
- list access codes
- list security events.
- arm system
- list recorded video clips from an adt camera.
- arm stay
- access code management.
- list systems
- list devices
- residential customer managing their home security system
- list access codes.
- list devices in a system.
- disarm an adt security system.
- create a temporary access code for contractors or guests with optional expiry time.
- check the current arming status of an adt security system.
- arm an adt security system in stay mode (perimeter zones only).
- business security administrator managing multi-site deployments
- homeowner
- iot
slug: home-security-management
tags:
- ADT
- Home Security
- Smart Home
- IoT
- Monitoring
- Access Control
tools:
- description: List all ADT security systems associated with the account.
  hints:
    openWorld: true
    readOnly: true
  name: list-security-systems
- description: Check the current arming status of an ADT security system.
  hints:
    openWorld: false
    readOnly: true
  name: get-system-status
- description: Arm an ADT security system in away mode (all zones active).
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: arm-away
- description: Arm an ADT security system in stay mode (perimeter zones only).
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: arm-stay
- description: Disarm an ADT security system.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: disarm-system
- description: List all security devices (sensors, cameras, locks) in an ADT system.
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Retrieve recent security events, alarm history, and activity log.
  hints:
    openWorld: true
    readOnly: true
  name: get-security-events
- description: List all access codes configured for an ADT security system.
  hints:
    openWorld: true
    readOnly: true
  name: list-access-codes
- description: Create a temporary access code for contractors or guests with optional expiry time.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-temporary-access-code
- description: List recorded video clips from an ADT camera.
  hints:
    openWorld: true
    readOnly: true
  name: list-video-clips
---
