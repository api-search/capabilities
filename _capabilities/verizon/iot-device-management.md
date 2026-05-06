---
categories: []
consumed_apis: []
description: Unified capability for IoT operations teams to manage Verizon ThingSpace connected devices including device activation, deactivation, account management, SMS commands, and callback notifications. Used by IoT platform engineers and device operations teams to manage large-scale IoT deployments on Verizon's wireless network.
layout: capability
name: Verizon IoT Device Management
operations:
- description: Get account information
  method: GET
  name: get-account
  path: /v1/accounts/{accountName}
- description: List devices with optional filters
  method: POST
  name: list-devices
  path: /v1/devices
- description: Activate devices on Verizon network
  method: POST
  name: activate-devices
  path: /v1/devices/activate
- description: Deactivate devices from Verizon network
  method: POST
  name: deactivate-devices
  path: /v1/devices/deactivate
- description: Send SMS to devices
  method: POST
  name: send-sms
  path: /v1/sms
- description: List registered callbacks
  method: GET
  name: list-callbacks
  path: /v1/callbacks
- description: Register a callback endpoint
  method: POST
  name: register-callback
  path: /v1/callbacks
personas: []
provider_name: Verizon
provider_slug: verizon
search_terms:
- device activation
- account management
- activate one or more iot devices on a verizon service plan
- list all registered callback endpoints for device event notifications
- register a webhook callback url to receive verizon thingspace device events
- deactivate devices
- callback subscriptions
- device management operations
- list iot devices in a verizon thingspace account with optional service plan and state filters
- verizon
- device management
- send sms to devices
- iot
- list devices
- sms messaging to devices
- administrators managing device connectivity and account settings
- lifecycle management of iot devices including activation and deactivation
- send an sms command or message to one or more iot devices
- 5g
- operations managers overseeing large-scale iot device fleet management
- enterprise
- operations
- device connectivity management on verizon wireless network
- send sms
- engineers who build and maintain iot platforms using verizon thingspace apis
- wireless
- activate devices on verizon network
- deactivate devices from verizon network
- list callbacks
- Network Administrator
- register a callback endpoint
- connectivity
- get account information
- device deactivation
- telecommunications
- network apis
- register callback
- activate devices
- list registered callbacks
- get verizon thingspace account information including device count and billing cycle
- deactivate iot devices from the verizon wireless network
- iot device lifecycle management workflow for verizon thingspace
- get account
- operational management of wireless iot deployments
- IoT Platform Engineer
- list devices with optional filters
- Device Operations Manager
slug: iot-device-management
source_filename: iot-device-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Verizon IoT Device Management\n  description: Unified capability for IoT operations teams to manage Verizon ThingSpace connected devices including device\n    activation, deactivation, account management, SMS commands, and callback notifications. Used by IoT platform engineers\n    and device operations teams to manage large-scale IoT deployments on Verizon's wireless network.\n  tags:\n  - IoT\n  - Device Management\n  - Connectivity\n  - Wireless\n  - Verizon\n  - Operations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VERIZON_CLIENT_ID: VERIZON_CLIENT_ID\n    VERIZON_CLIENT_SECRET: VERIZON_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: verizon-thingspace-connectivity\n    baseUri: https://thingspace.verizon.com/api/m2m/v2\n    description: Verizon ThingSpace Connectivity Management REST API\n    authentication:\n      type: bearer\n      token: '{{VERIZON_CLIENT_ID}}'\n\
  \    resources:\n    - name: accounts\n      path: /accounts/{accountName}\n      description: Account information and management\n      operations:\n      - name: get-account-information\n        method: GET\n        description: Get account information and settings\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-list\n      path: /accounts/{accountName}/devices/actions/list\n      description: List devices in an account\n      operations:\n      - name: list-devices\n        method: POST\n        description: List devices in account with optional filtering\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filter: '{{tools.filter}}'\n    - name: device-activate\n      path: /accounts/{accountName}/devices/actions/activate\n      description: Activate devices\n      operations:\n      - name: activate-devices\n        method: POST\n        description: Activate one or more devices to a service plan\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            devices: '{{tools.devices}}'\n    - name: device-deactivate\n      path: /accounts/{accountName}/devices/actions/deactivate\n      description: Deactivate devices\n      operations:\n\
  \      - name: deactivate-devices\n        method: POST\n        description: Deactivate one or more devices\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            devices: '{{tools.devices}}'\n            reasonCode: '{{tools.reasonCode}}'\n    - name: sms\n      path: /sms/{accountName}/actions/send\n      description: SMS messaging to devices\n      operations:\n      - name: send-sms\n        method: POST\n        description: Send SMS message to one or more devices\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            deviceIds: '{{tools.deviceIds}}'\n            smsMessage: '{{tools.smsMessage}}'\n    - name: callbacks\n      path: /callbacks/{accountName}\n      description: Callback subscription management\n      operations:\n      - name: list-callbacks\n        method: GET\n        description: List registered callback endpoints\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-callback\n        method: POST\n        description: Register a callback URL for a service\n        inputParameters:\n        - name: accountName\n          in: path\n          type: string\n          required: true\n          description:\
  \ Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            url: '{{tools.url}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: verizon-iot-management-api\n    description: Unified REST API for IoT device lifecycle management on Verizon ThingSpace.\n    resources:\n    - path: /v1/accounts/{accountName}\n      name: account\n      description: Account management\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account information\n        call: verizon-thingspace-connectivity.get-account-information\n        with:\n          accountName: rest.accountName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices\n      name: devices\n      description: Device management operations\n      operations:\n      -\
  \ method: POST\n        name: list-devices\n        description: List devices with optional filters\n        call: verizon-thingspace-connectivity.list-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/activate\n      name: device-activation\n      description: Device activation\n      operations:\n      - method: POST\n        name: activate-devices\n        description: Activate devices on Verizon network\n        call: verizon-thingspace-connectivity.activate-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/deactivate\n      name: device-deactivation\n      description: Device deactivation\n      operations:\n      - method: POST\n        name: deactivate-devices\n        description: Deactivate devices from Verizon network\n        call: verizon-thingspace-connectivity.deactivate-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/sms\n      name: sms\n      description: SMS messaging to devices\n      operations:\n      - method: POST\n        name: send-sms\n        description: Send SMS to devices\n        call: verizon-thingspace-connectivity.send-sms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/callbacks\n      name: callbacks\n      description: Callback subscriptions\n      operations:\n      - method: GET\n        name: list-callbacks\n        description: List registered callbacks\n        call: verizon-thingspace-connectivity.list-callbacks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-callback\n        description: Register a callback endpoint\n        call: verizon-thingspace-connectivity.register-callback\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: verizon-iot-management-mcp\n    transport: http\n  \
  \  description: MCP server for AI-assisted IoT device management on Verizon ThingSpace.\n    tools:\n    - name: get-account\n      description: Get Verizon ThingSpace account information including device count and billing cycle\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verizon-thingspace-connectivity.get-account-information\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-devices\n      description: List IoT devices in a Verizon ThingSpace account with optional service plan and state filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verizon-thingspace-connectivity.list-devices\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-devices\n      description: Activate one or more IoT devices on a Verizon service plan\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: verizon-thingspace-connectivity.activate-devices\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deactivate-devices\n      description: Deactivate IoT devices from the Verizon wireless network\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: verizon-thingspace-connectivity.deactivate-devices\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-sms-to-devices\n      description: Send an SMS command or message to one or more IoT devices\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: verizon-thingspace-connectivity.send-sms\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: list-callbacks\n      description: List all registered callback endpoints for device event notifications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verizon-thingspace-connectivity.list-callbacks\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-callback\n      description: Register a webhook callback URL to receive Verizon ThingSpace device events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: verizon-thingspace-connectivity.register-callback\n      with:\n        accountName: tools.accountName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/verizon/refs/heads/main/capabilities/iot-device-management.yaml
tags:
- IoT
- Device Management
- Connectivity
- Wireless
- Verizon
- Operations
tools:
- description: Get Verizon ThingSpace account information including device count and billing cycle
  hints:
    openWorld: true
    readOnly: true
  name: get-account
- description: List IoT devices in a Verizon ThingSpace account with optional service plan and state filters
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Activate one or more IoT devices on a Verizon service plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activate-devices
- description: Deactivate IoT devices from the Verizon wireless network
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deactivate-devices
- description: Send an SMS command or message to one or more IoT devices
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-sms-to-devices
- description: List all registered callback endpoints for device event notifications
  hints:
    openWorld: true
    readOnly: true
  name: list-callbacks
- description: Register a webhook callback URL to receive Verizon ThingSpace device events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: register-callback
---
