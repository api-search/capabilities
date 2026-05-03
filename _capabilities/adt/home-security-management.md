---
categories:
- monitoring
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
- adt
- list security systems
- get system status
- residential customer managing their home security system
- list all access codes configured for an adt security system.
- manager overseeing multiple residential properties
- list all adt security systems associated with the account.
- list devices in a system.
- arm away
- list all security devices (sensors, cameras, locks) in an adt system.
- smart home
- list all security systems.
- arm an adt security system in away mode (all zones active).
- security system management.
- automation
- homeowner
- list security events.
- disarm a security system.
- list access codes
- list devices
- iot
- access code management.
- arm system
- security
- get security events
- check the current arming status of an adt security system.
- security events.
- property manager
- list events
- monitoring
- list access codes.
- list video clips
- home security
- arm stay
- create temporary access code
- arm a security system.
- retrieve recent security events, alarm history, and activity log.
- arm an adt security system in stay mode (perimeter zones only).
- access control
- create a temporary access code for contractors or guests with optional expiry time.
- list systems
- disarm system
- create access code
- create an access code.
- disarm an adt security system.
- security devices.
- unified workflow for managing adt smart home security
- list recorded video clips from an adt camera.
- business security administrator managing multi-site deployments
slug: home-security-management
source_filename: home-security-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ADT Home Security Management\"\n  description: \"Unified workflow capability for managing ADT smart home security systems, monitoring alarm events, controlling devices, managing access codes, and retrieving video clips. Designed for homeowners, property managers, and smart home integration developers.\"\n  tags:\n    - ADT\n    - Home Security\n    - Smart Home\n    - IoT\n    - Monitoring\n    - Access Control\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADT_ACCESS_TOKEN: ADT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: adt-platform\n      location: ./shared/platform-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: home-security-api\n      description: \"Unified REST API for ADT smart home security management — systems, devices, events, access codes, and video.\"\n      resources:\n        - path: /v1/systems\n          name: systems\n\
  \          description: \"Security system management.\"\n          operations:\n            - method: GET\n              name: list-systems\n              description: \"List all security systems.\"\n              call: \"adt-platform.list-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems/{systemId}/arm\n          name: arm-system\n          description: \"Arm a security system.\"\n          operations:\n            - method: POST\n              name: arm-system\n              description: \"Arm a security system.\"\n              call: \"adt-platform.arm-system\"\n              with:\n                systemId: \"rest.systemId\"\n                mode: \"rest.mode\"\n                accessCode: \"rest.accessCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems/{systemId}/disarm\n          name: disarm-system\n        \
  \  description: \"Disarm a security system.\"\n          operations:\n            - method: POST\n              name: disarm-system\n              description: \"Disarm a security system.\"\n              call: \"adt-platform.disarm-system\"\n              with:\n                systemId: \"rest.systemId\"\n                accessCode: \"rest.accessCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems/{systemId}/devices\n          name: devices\n          description: \"Security devices.\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List devices in a system.\"\n              call: \"adt-platform.list-devices\"\n              with:\n                systemId: \"rest.systemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems/{systemId}/events\n          name: events\n\
  \          description: \"Security events.\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List security events.\"\n              call: \"adt-platform.list-events\"\n              with:\n                systemId: \"rest.systemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems/{systemId}/access-codes\n          name: access-codes\n          description: \"Access code management.\"\n          operations:\n            - method: GET\n              name: list-access-codes\n              description: \"List access codes.\"\n              call: \"adt-platform.list-access-codes\"\n              with:\n                systemId: \"rest.systemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-access-code\n              description: \"Create\
  \ an access code.\"\n              call: \"adt-platform.create-access-code\"\n              with:\n                systemId: \"rest.systemId\"\n                name: \"rest.name\"\n                code: \"rest.code\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: home-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted ADT home security management — monitor status, control arming, manage access, and review events.\"\n      tools:\n        - name: list-security-systems\n          description: \"List all ADT security systems associated with the account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"adt-platform.list-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-system-status\n          description:\
  \ \"Check the current arming status of an ADT security system.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"adt-platform.get-system\"\n          with:\n            systemId: \"tools.systemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: arm-away\n          description: \"Arm an ADT security system in away mode (all zones active).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"adt-platform.arm-system\"\n          with:\n            systemId: \"tools.systemId\"\n            mode: \"away\"\n            accessCode: \"tools.accessCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: arm-stay\n          description: \"Arm an ADT security system in stay mode (perimeter zones only).\"\n          hints:\n            readOnly: false\n           \
  \ destructive: false\n            idempotent: true\n          call: \"adt-platform.arm-system\"\n          with:\n            systemId: \"tools.systemId\"\n            mode: \"stay\"\n            accessCode: \"tools.accessCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: disarm-system\n          description: \"Disarm an ADT security system.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"adt-platform.disarm-system\"\n          with:\n            systemId: \"tools.systemId\"\n            accessCode: \"tools.accessCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-devices\n          description: \"List all security devices (sensors, cameras, locks) in an ADT system.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"adt-platform.list-devices\"\
  \n          with:\n            systemId: \"tools.systemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-security-events\n          description: \"Retrieve recent security events, alarm history, and activity log.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"adt-platform.list-events\"\n          with:\n            systemId: \"tools.systemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-access-codes\n          description: \"List all access codes configured for an ADT security system.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"adt-platform.list-access-codes\"\n          with:\n            systemId: \"tools.systemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-temporary-access-code\n       \
  \   description: \"Create a temporary access code for contractors or guests with optional expiry time.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"adt-platform.create-access-code\"\n          with:\n            systemId: \"tools.systemId\"\n            name: \"tools.name\"\n            code: \"tools.code\"\n            type: \"temporary\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-video-clips\n          description: \"List recorded video clips from an ADT camera.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"adt-platform.list-video-clips\"\n          with:\n            systemId: \"tools.systemId\"\n            cameraId: \"tools.cameraId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adt/refs/heads/main/capabilities/home-security-management.yaml
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
