---
categories: []
consumed_apis: []
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
- bmc
- get details of a specific computer system
- list all computer systems
- create a new bmc user account
- reset system
- supermicro
- reset or power cycle a computer system
- reset or power cycle a server (on, forceoff, gracefulrestart, etc.)
- get power consumption and supply data
- list current firmware versions for bios, bmc, and components
- list current firmware versions
- list all server event notification subscriptions
- infrastructure
- initiate firmware update
- get manager
- bmc user account management
- get real-time power consumption and supply status for a chassis
- list event subscriptions
- delete a bmc user account
- event notification subscriptions
- list all chassis in the data center
- list all bmc user accounts and their roles
- cloud
- create a new bmc user account with specified role
- get chassis power
- list firmware inventory
- update account
- get temperature and fan speed data
- list systems
- get a specific chassis
- list all bmc managers
- redfish
- chassis power data
- perform firmware update
- computer system inventory and management
- get chassis
- initiate a bios or bmc firmware update from a specified uri
- update a user account
- reset manager
- subscribe to server events via webhook
- data center
- get temperature sensor readings and fan speeds for a chassis
- list all chassis
- list all event subscriptions
- list chassis
- chassis thermal data
- system power control
- list all computer systems managed by this bmc
- get health status and details of a specific computer system
- fortune 500
- firmware lifecycle management
- server management
- create account
- restart the bmc management controller
- get chassis thermal
- chassis inventory
- bmc manager management
- get a specific bmc manager
- create event subscription
- list accounts
- create an event notification subscription
- get bmc manager details including firmware version
- list managers
- delete a user account
- servers
- get account
- delete account
- hardware
- get system
- get a specific user account
- list all bmc user accounts
- ipmi
slug: server-management
source_filename: server-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Supermicro Server Management\n  description: Unified server management workflow combining Supermicro Redfish API capabilities for data center operations\n    teams. Covers server health monitoring, power and thermal management, firmware lifecycle, user account administration,\n    and event alerting across Supermicro server infrastructure.\n  tags:\n  - Supermicro\n  - Server Management\n  - Data Center\n  - Redfish\n  - BMC\n  - Infrastructure\n  - Hardware\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SUPERMICRO_BMC_HOST: SUPERMICRO_BMC_HOST\n    SUPERMICRO_AUTH_TOKEN: SUPERMICRO_AUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: supermicro-redfish\n    baseUri: https://{{SUPERMICRO_BMC_HOST}}/redfish/v1\n    description: Supermicro BMC Redfish REST API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SUPERMICRO_AUTH_TOKEN}}'\n      placement:\
  \ header\n    resources:\n    - name: service-root\n      path: /\n      description: Root service discovery\n      operations:\n      - name: get-service-root\n        method: GET\n        description: Get service root with links to all top-level collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: systems\n      path: /Systems\n      description: Computer system management\n      operations:\n      - name: list-systems\n        method: GET\n        description: List all computer systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-system\n        method: GET\n        description: Get a specific computer system\n        inputParameters:\n        - name: systemId\n          in: path\n          type: string\n          required: true\n          description: System identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-system\n        method: PATCH\n        description: Update computer system properties\n        inputParameters:\n        - name: systemId\n          in: path\n          type: string\n          required: true\n          description: System identifier\n        body:\n          type: json\n          data:\n            AssetTag: '{{tools.asset_tag}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-system\n        method: POST\n        description: Reset computer system (power on/off/restart)\n        inputParameters:\n        - name: systemId\n          in: path\n          type: string\n          required: true\n          description: System identifier\n        body:\n          type: json\n          data:\n            ResetType: '{{tools.reset_type}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chassis\n      path: /Chassis\n      description: Chassis management\n      operations:\n      - name: list-chassis\n        method: GET\n        description: List all chassis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-chassis\n        method: GET\n        description: Get a specific chassis\n        inputParameters:\n        - name: chassisId\n          in: path\n          type: string\n          required: true\n          description: Chassis identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-chassis-power\n        method: GET\n        description: Get chassis power supply and consumption data\n        inputParameters:\n        - name: chassisId\n          in: path\n\
  \          type: string\n          required: true\n          description: Chassis identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-chassis-thermal\n        method: GET\n        description: Get chassis temperature and fan data\n        inputParameters:\n        - name: chassisId\n          in: path\n          type: string\n          required: true\n          description: Chassis identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: managers\n      path: /Managers\n      description: BMC manager configuration\n      operations:\n      - name: list-managers\n        method: GET\n        description: List all BMC managers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-manager\n        method:\
  \ GET\n        description: Get a specific BMC manager\n        inputParameters:\n        - name: managerId\n          in: path\n          type: string\n          required: true\n          description: Manager identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-manager\n        method: POST\n        description: Reset the BMC manager\n        inputParameters:\n        - name: managerId\n          in: path\n          type: string\n          required: true\n          description: Manager identifier\n        body:\n          type: json\n          data:\n            ResetType: '{{tools.reset_type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /SessionService/Sessions\n      description: Session authentication management\n      operations:\n      - name: list-sessions\n\
  \        method: GET\n        description: List all active sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-session\n        method: POST\n        description: Create a new Redfish session\n        body:\n          type: json\n          data:\n            UserName: '{{tools.username}}'\n            Password: '{{tools.password}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-session\n        method: DELETE\n        description: Delete a specific session\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /AccountService/Accounts\n\
  \      description: User account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all BMC user accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new BMC user account\n        body:\n          type: json\n          data:\n            UserName: '{{tools.username}}'\n            Password: '{{tools.password}}'\n            RoleId: '{{tools.role_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get a specific user account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PATCH\n        description: Update a user account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        body:\n          type: json\n          data:\n            Password: '{{tools.password}}'\n            RoleId: '{{tools.role_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account\n        method: DELETE\n        description: Delete a user account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: events\n      path: /EventService\n      description: Event notification management\n      operations:\n      - name: get-event-service\n        method: GET\n        description: Get event service configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-event-subscriptions\n        method: GET\n        description: List all event subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-event-subscription\n        method: POST\n        description: Create an event notification subscription\n        body:\n          type: json\n          data:\n            Destination: '{{tools.destination}}'\n            Protocol: Redfish\n            Context: '{{tools.context}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: delete-event-subscription\n        method: DELETE\n        description: Delete an event subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firmware\n      path: /UpdateService\n      description: Firmware update management\n      operations:\n      - name: get-update-service\n        method: GET\n        description: Get firmware update service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-firmware-inventory\n        method: GET\n        description: List current firmware inventory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: perform-firmware-update\n        method: POST\n        description: Initiate a firmware update\n        body:\n          type: json\n          data:\n            ImageURI: '{{tools.image_uri}}'\n            Targets: '{{tools.targets}}'\n            TransferProtocol: '{{tools.transfer_protocol}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: supermicro-server-management-api\n    description: Unified REST API for Supermicro server management operations.\n    resources:\n    - path: /v1/systems\n      name: systems\n      description: Computer system inventory and management\n      operations:\n      - method: GET\n        name: list-systems\n        description: List all computer systems\n        call: supermicro-redfish.list-systems\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n      - method: GET\n        name: get-system\n        description: Get details of a specific computer system\n        call: supermicro-redfish.get-system\n        with:\n          systemId: rest.systemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/systems/{systemId}/reset\n      name: system-reset\n      description: System power control\n      operations:\n      - method: POST\n        name: reset-system\n        description: Reset or power cycle a computer system\n        call: supermicro-redfish.reset-system\n        with:\n          systemId: rest.systemId\n          reset_type: rest.reset_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chassis\n      name: chassis\n      description: Chassis inventory\n      operations:\n      - method: GET\n        name: list-chassis\n        description: List all chassis\n        call: supermicro-redfish.list-chassis\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: GET\n        name: get-chassis\n        description: Get a specific chassis\n        call: supermicro-redfish.get-chassis\n        with:\n          chassisId: rest.chassisId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chassis/{chassisId}/power\n      name: chassis-power\n      description: Chassis power data\n      operations:\n      - method: GET\n        name: get-chassis-power\n        description: Get power consumption and supply data\n        call: supermicro-redfish.get-chassis-power\n        with:\n          chassisId: rest.chassisId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chassis/{chassisId}/thermal\n      name: chassis-thermal\n      description: Chassis thermal data\n      operations:\n      - method: GET\n        name: get-chassis-thermal\n        description: Get temperature and fan speed data\n        call: supermicro-redfish.get-chassis-thermal\n\
  \        with:\n          chassisId: rest.chassisId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/managers\n      name: managers\n      description: BMC manager management\n      operations:\n      - method: GET\n        name: list-managers\n        description: List all BMC managers\n        call: supermicro-redfish.list-managers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-manager\n        description: Get a specific BMC manager\n        call: supermicro-redfish.get-manager\n        with:\n          managerId: rest.managerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/firmware\n      name: firmware\n      description: Firmware lifecycle management\n      operations:\n      - method: GET\n        name: list-firmware-inventory\n        description: List current firmware versions\n        call: supermicro-redfish.list-firmware-inventory\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: perform-firmware-update\n        description: Initiate firmware update\n        call: supermicro-redfish.perform-firmware-update\n        with:\n          image_uri: rest.image_uri\n          targets: rest.targets\n          transfer_protocol: rest.transfer_protocol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: BMC user account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all BMC user accounts\n        call: supermicro-redfish.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a new BMC user account\n        call: supermicro-redfish.create-account\n        with:\n          username: rest.username\n       \
  \   password: rest.password\n          role_id: rest.role_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-account\n        description: Get a specific user account\n        call: supermicro-redfish.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-account\n        description: Update a user account\n        call: supermicro-redfish.update-account\n        with:\n          accountId: rest.accountId\n          password: rest.password\n          role_id: rest.role_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-account\n        description: Delete a user account\n        call: supermicro-redfish.delete-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /v1/events/subscriptions\n      name: event-subscriptions\n      description: Event notification subscriptions\n      operations:\n      - method: GET\n        name: list-event-subscriptions\n        description: List all event subscriptions\n        call: supermicro-redfish.list-event-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-event-subscription\n        description: Create an event notification subscription\n        call: supermicro-redfish.create-event-subscription\n        with:\n          destination: rest.destination\n          context: rest.context\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: supermicro-server-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Supermicro server management and data center operations.\n    tools:\n    - name: list-systems\n\
  \      description: List all computer systems managed by this BMC\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.list-systems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-system\n      description: Get health status and details of a specific computer system\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.get-system\n      with:\n        systemId: tools.systemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reset-system\n      description: Reset or power cycle a server (On, ForceOff, GracefulRestart, etc.)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: supermicro-redfish.reset-system\n      with:\n        systemId: tools.systemId\n        reset_type: tools.reset_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-chassis\n\
  \      description: List all chassis in the data center\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.list-chassis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-chassis-power\n      description: Get real-time power consumption and supply status for a chassis\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.get-chassis-power\n      with:\n        chassisId: tools.chassisId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-chassis-thermal\n      description: Get temperature sensor readings and fan speeds for a chassis\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.get-chassis-thermal\n      with:\n        chassisId: tools.chassisId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-managers\n      description: List all BMC managers\n   \
  \   hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.list-managers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-manager\n      description: Get BMC manager details including firmware version\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.get-manager\n      with:\n        managerId: tools.managerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reset-manager\n      description: Restart the BMC management controller\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: supermicro-redfish.reset-manager\n      with:\n        managerId: tools.managerId\n        reset_type: tools.reset_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-firmware-inventory\n      description: List current firmware versions for BIOS, BMC, and components\n    \
  \  hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.list-firmware-inventory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: perform-firmware-update\n      description: Initiate a BIOS or BMC firmware update from a specified URI\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: supermicro-redfish.perform-firmware-update\n      with:\n        image_uri: tools.image_uri\n        targets: tools.targets\n        transfer_protocol: tools.transfer_protocol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List all BMC user accounts and their roles\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-account\n      description: Create a new BMC user account with\
  \ specified role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: supermicro-redfish.create-account\n      with:\n        username: tools.username\n        password: tools.password\n        role_id: tools.role_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-account\n      description: Delete a BMC user account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: supermicro-redfish.delete-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-event-subscriptions\n      description: List all server event notification subscriptions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: supermicro-redfish.list-event-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event-subscription\n\
  \      description: Subscribe to server events via webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: supermicro-redfish.create-event-subscription\n      with:\n        destination: tools.destination\n        context: tools.context\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
