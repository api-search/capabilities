---
categories: []
consumed_apis:
- supermicro-redfish
description: Unified server management workflow combining Supermicro Redfish API capabilities for data center operations teams. Covers server health monitoring, power and thermal management, firmware lifecycle, user account administration, and event alerting across Supermicro server infrastructure.
layout: capability
name: Supermicro Server Management
operations:
- description: List all computer systems
  method: GET
  name: list-systems
  path: /v1/systems
- description: Get details of a specific computer system
  method: GET
  name: get-system
  path: /v1/systems
- description: Reset or power cycle a computer system
  method: POST
  name: reset-system
  path: /v1/systems/{systemId}/reset
- description: List all chassis
  method: GET
  name: list-chassis
  path: /v1/chassis
- description: Get a specific chassis
  method: GET
  name: get-chassis
  path: /v1/chassis
- description: Get power consumption and supply data
  method: GET
  name: get-chassis-power
  path: /v1/chassis/{chassisId}/power
- description: Get temperature and fan speed data
  method: GET
  name: get-chassis-thermal
  path: /v1/chassis/{chassisId}/thermal
- description: List all BMC managers
  method: GET
  name: list-managers
  path: /v1/managers
- description: Get a specific BMC manager
  method: GET
  name: get-manager
  path: /v1/managers
- description: List current firmware versions
  method: GET
  name: list-firmware-inventory
  path: /v1/firmware
- description: Initiate firmware update
  method: POST
  name: perform-firmware-update
  path: /v1/firmware
- description: List all BMC user accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new BMC user account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get a specific user account
  method: GET
  name: get-account
  path: /v1/accounts
- description: Update a user account
  method: PATCH
  name: update-account
  path: /v1/accounts
- description: Delete a user account
  method: DELETE
  name: delete-account
  path: /v1/accounts
- description: List all event subscriptions
  method: GET
  name: list-event-subscriptions
  path: /v1/events/subscriptions
- description: Create an event notification subscription
  method: POST
  name: create-event-subscription
  path: /v1/events/subscriptions
personas: []
provider_name: Super Micro Computer
provider_slug: super-micro-computer
search_terms:
- list current firmware versions
- reset system
- list firmware inventory
- reset or power cycle a server (on, forceoff, gracefulrestart, etc.)
- bmc
- get account
- list accounts
- get health status and details of a specific computer system
- initiate a bios or bmc firmware update from a specified uri
- cloud
- list managers
- list all bmc user accounts
- list all bmc managers
- get bmc manager details including firmware version
- get details of a specific computer system
- restart the bmc management controller
- computer system inventory and management
- get manager
- create account
- reset or power cycle a computer system
- chassis inventory
- list all server event notification subscriptions
- get chassis power
- get chassis
- bmc manager management
- perform firmware update
- list all computer systems managed by this bmc
- get system
- get chassis thermal
- chassis power data
- servers
- fortune 500
- server management
- list all chassis in the data center
- get a specific bmc manager
- reset manager
- list chassis
- chassis thermal data
- event notification subscriptions
- list current firmware versions for bios, bmc, and components
- list event subscriptions
- list all bmc user accounts and their roles
- delete account
- list all event subscriptions
- data center
- ipmi
- get real-time power consumption and supply status for a chassis
- list all computer systems
- system power control
- infrastructure
- firmware lifecycle management
- supermicro
- get temperature and fan speed data
- delete a user account
- create a new bmc user account with specified role
- delete a bmc user account
- subscribe to server events via webhook
- update account
- update a user account
- list all chassis
- list systems
- create an event notification subscription
- create event subscription
- initiate firmware update
- bmc user account management
- create a new bmc user account
- get power consumption and supply data
- get a specific user account
- redfish
- get temperature sensor readings and fan speeds for a chassis
- hardware
- get a specific chassis
slug: server-management
source_filename: server-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Supermicro Server Management\"\n  description: >-\n    Unified server management workflow combining Supermicro Redfish API capabilities\n    for data center operations teams. Covers server health monitoring, power and\n    thermal management, firmware lifecycle, user account administration, and event\n    alerting across Supermicro server infrastructure.\n  tags:\n    - Supermicro\n    - Server Management\n    - Data Center\n    - Redfish\n    - BMC\n    - Infrastructure\n    - Hardware\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SUPERMICRO_BMC_HOST: SUPERMICRO_BMC_HOST\n      SUPERMICRO_AUTH_TOKEN: SUPERMICRO_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: supermicro-redfish\n      location: ./shared/redfish.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: supermicro-server-management-api\n      description: \"Unified REST API for Supermicro\
  \ server management operations.\"\n      resources:\n        - path: /v1/systems\n          name: systems\n          description: \"Computer system inventory and management\"\n          operations:\n            - method: GET\n              name: list-systems\n              description: \"List all computer systems\"\n              call: \"supermicro-redfish.list-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-system\n              description: \"Get details of a specific computer system\"\n              call: \"supermicro-redfish.get-system\"\n              with:\n                systemId: \"rest.systemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/systems/{systemId}/reset\n          name: system-reset\n          description: \"System power control\"\n          operations:\n            - method:\
  \ POST\n              name: reset-system\n              description: \"Reset or power cycle a computer system\"\n              call: \"supermicro-redfish.reset-system\"\n              with:\n                systemId: \"rest.systemId\"\n                reset_type: \"rest.reset_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/chassis\n          name: chassis\n          description: \"Chassis inventory\"\n          operations:\n            - method: GET\n              name: list-chassis\n              description: \"List all chassis\"\n              call: \"supermicro-redfish.list-chassis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-chassis\n              description: \"Get a specific chassis\"\n              call: \"supermicro-redfish.get-chassis\"\n              with:\n                chassisId: \"rest.chassisId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/chassis/{chassisId}/power\n          name: chassis-power\n          description: \"Chassis power data\"\n          operations:\n            - method: GET\n              name: get-chassis-power\n              description: \"Get power consumption and supply data\"\n              call: \"supermicro-redfish.get-chassis-power\"\n              with:\n                chassisId: \"rest.chassisId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/chassis/{chassisId}/thermal\n          name: chassis-thermal\n          description: \"Chassis thermal data\"\n          operations:\n            - method: GET\n              name: get-chassis-thermal\n              description: \"Get temperature and fan speed data\"\n              call: \"supermicro-redfish.get-chassis-thermal\"\n              with:\n     \
  \           chassisId: \"rest.chassisId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/managers\n          name: managers\n          description: \"BMC manager management\"\n          operations:\n            - method: GET\n              name: list-managers\n              description: \"List all BMC managers\"\n              call: \"supermicro-redfish.list-managers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-manager\n              description: \"Get a specific BMC manager\"\n              call: \"supermicro-redfish.get-manager\"\n              with:\n                managerId: \"rest.managerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/firmware\n          name: firmware\n          description: \"Firmware lifecycle management\"\
  \n          operations:\n            - method: GET\n              name: list-firmware-inventory\n              description: \"List current firmware versions\"\n              call: \"supermicro-redfish.list-firmware-inventory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: perform-firmware-update\n              description: \"Initiate firmware update\"\n              call: \"supermicro-redfish.perform-firmware-update\"\n              with:\n                image_uri: \"rest.image_uri\"\n                targets: \"rest.targets\"\n                transfer_protocol: \"rest.transfer_protocol\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts\n          name: accounts\n          description: \"BMC user account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n\
  \              description: \"List all BMC user accounts\"\n              call: \"supermicro-redfish.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new BMC user account\"\n              call: \"supermicro-redfish.create-account\"\n              with:\n                username: \"rest.username\"\n                password: \"rest.password\"\n                role_id: \"rest.role_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-account\n              description: \"Get a specific user account\"\n              call: \"supermicro-redfish.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: PATCH\n              name: update-account\n              description: \"Update a user account\"\n              call: \"supermicro-redfish.update-account\"\n              with:\n                accountId: \"rest.accountId\"\n                password: \"rest.password\"\n                role_id: \"rest.role_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-account\n              description: \"Delete a user account\"\n              call: \"supermicro-redfish.delete-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/subscriptions\n          name: event-subscriptions\n          description: \"Event notification subscriptions\"\n          operations:\n            - method: GET\n              name: list-event-subscriptions\n\
  \              description: \"List all event subscriptions\"\n              call: \"supermicro-redfish.list-event-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-event-subscription\n              description: \"Create an event notification subscription\"\n              call: \"supermicro-redfish.create-event-subscription\"\n              with:\n                destination: \"rest.destination\"\n                context: \"rest.context\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: supermicro-server-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Supermicro server management and data center operations.\"\n      tools:\n        - name: list-systems\n          description: \"List all computer systems managed by this BMC\"\
  \n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.list-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-system\n          description: \"Get health status and details of a specific computer system\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.get-system\"\n          with:\n            systemId: \"tools.systemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reset-system\n          description: \"Reset or power cycle a server (On, ForceOff, GracefulRestart, etc.)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"supermicro-redfish.reset-system\"\n          with:\n            systemId: \"tools.systemId\"\n            reset_type: \"tools.reset_type\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-chassis\n          description: \"List all chassis in the data center\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.list-chassis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-chassis-power\n          description: \"Get real-time power consumption and supply status for a chassis\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.get-chassis-power\"\n          with:\n            chassisId: \"tools.chassisId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-chassis-thermal\n          description: \"Get temperature sensor readings and fan speeds for a chassis\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"supermicro-redfish.get-chassis-thermal\"\n          with:\n            chassisId: \"tools.chassisId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-managers\n          description: \"List all BMC managers\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.list-managers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-manager\n          description: \"Get BMC manager details including firmware version\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.get-manager\"\n          with:\n            managerId: \"tools.managerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reset-manager\n          description: \"Restart the BMC management controller\"\n \
  \         hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"supermicro-redfish.reset-manager\"\n          with:\n            managerId: \"tools.managerId\"\n            reset_type: \"tools.reset_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-firmware-inventory\n          description: \"List current firmware versions for BIOS, BMC, and components\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.list-firmware-inventory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: perform-firmware-update\n          description: \"Initiate a BIOS or BMC firmware update from a specified URI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"supermicro-redfish.perform-firmware-update\"\
  \n          with:\n            image_uri: \"tools.image_uri\"\n            targets: \"tools.targets\"\n            transfer_protocol: \"tools.transfer_protocol\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List all BMC user accounts and their roles\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: \"Create a new BMC user account with specified role\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"supermicro-redfish.create-account\"\n          with:\n            username: \"tools.username\"\n            password: \"tools.password\"\n            role_id: \"tools.role_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: delete-account\n          description: \"Delete a BMC user account\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"supermicro-redfish.delete-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-event-subscriptions\n          description: \"List all server event notification subscriptions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"supermicro-redfish.list-event-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-event-subscription\n          description: \"Subscribe to server events via webhook\"\n          hints:\n            readOnly: false\n            destructive: false\n    \
  \        idempotent: false\n          call: \"supermicro-redfish.create-event-subscription\"\n          with:\n            destination: \"tools.destination\"\n            context: \"tools.context\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/super-micro-computer/refs/heads/main/capabilities/server-management.yaml
tags:
- Supermicro
- Server Management
- Data Center
- Redfish
- BMC
- Infrastructure
- Hardware
tools:
- description: List all computer systems managed by this BMC
  hints:
    idempotent: true
    readOnly: true
  name: list-systems
- description: Get health status and details of a specific computer system
  hints:
    idempotent: true
    readOnly: true
  name: get-system
- description: Reset or power cycle a server (On, ForceOff, GracefulRestart, etc.)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reset-system
- description: List all chassis in the data center
  hints:
    idempotent: true
    readOnly: true
  name: list-chassis
- description: Get real-time power consumption and supply status for a chassis
  hints:
    idempotent: true
    readOnly: true
  name: get-chassis-power
- description: Get temperature sensor readings and fan speeds for a chassis
  hints:
    idempotent: true
    readOnly: true
  name: get-chassis-thermal
- description: List all BMC managers
  hints:
    idempotent: true
    readOnly: true
  name: list-managers
- description: Get BMC manager details including firmware version
  hints:
    idempotent: true
    readOnly: true
  name: get-manager
- description: Restart the BMC management controller
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reset-manager
- description: List current firmware versions for BIOS, BMC, and components
  hints:
    idempotent: true
    readOnly: true
  name: list-firmware-inventory
- description: Initiate a BIOS or BMC firmware update from a specified URI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: perform-firmware-update
- description: List all BMC user accounts and their roles
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: Create a new BMC user account with specified role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-account
- description: Delete a BMC user account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-account
- description: List all server event notification subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: list-event-subscriptions
- description: Subscribe to server events via webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-event-subscription
---
