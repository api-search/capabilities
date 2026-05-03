---
categories:
- iot
consumed_apis:
- iot-core
description: Unified capability for IoT Developer, Solutions Architect to manage managed cloud service for iot device connectivity and message routing operations.
layout: capability
name: Amazon IoT Core - Iot Device Connectivity
operations:
- description: List Things
  method: GET
  name: list-things
  path: /v1/resources
personas: []
provider_name: Amazon IoT Core
provider_slug: amazon-iot-core
search_terms:
- Solutions Architect
- IoT Developer
- manages amazon iot core resources and operations
- amazon iot core get thing
- amazon iot core create topic rule
- delete thing
- managed cloud service for iot device connectivity and message routing.
- aws
- attach policy
- mqtt
- amazon iot core attach policy
- create policy
- amazon iot core list things
- amazon iot core resources
- device management
- create topic rule
- create thing
- get thing
- list things
- amazon iot core create policy
- message routing
- amazon iot core list rules
- list rules
- iot
- amazon iot core delete thing
- amazon iot core create thing
slug: iot-device-connectivity
source_filename: iot-device-connectivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT Core - Iot Device Connectivity\n  description: Unified capability for IoT Developer, Solutions Architect to manage managed cloud service for iot device connectivity and message routing operations.\n  tags:\n    - IoT\n    - AWS\n    - Device Management\n    - MQTT\n    - Message Routing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-core\n      location: ./shared/iot-core.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: iot-device-connectivity-api\n      description: Unified REST API for iot device connectivity.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT Core resources\n          operations:\n            - method: GET\n              name: list-things\n\
  \              description: List Things\n              call: \"iot-core.list-things\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: iot-device-connectivity-mcp\n      transport: http\n      description: MCP server for AI-assisted iot device connectivity.\n      tools:\n        - name: list-things\n          description: Amazon IoT Core List Things\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-core.list-things\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-thing\n          description: Amazon IoT Core Create Thing\n          hints:\n            readOnly: false\n            \n          call: \"iot-core.create-thing\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-thing\n          description: Amazon\
  \ IoT Core Delete Thing\n          hints:\n            readOnly: false\n            \n          call: \"iot-core.delete-thing\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-thing\n          description: Amazon IoT Core Get Thing\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-core.get-thing\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: attach-policy\n          description: Amazon IoT Core Attach Policy\n          hints:\n            readOnly: false\n            \n          call: \"iot-core.attach-policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-policy\n          description: Amazon IoT Core Create Policy\n          hints:\n            readOnly: false\n            \n          call: \"iot-core.create-policy\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-rules\n          description: Amazon IoT Core List Rules\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-core.list-rules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-topic-rule\n          description: Amazon IoT Core Create Topic Rule\n          hints:\n            readOnly: false\n            \n          call: \"iot-core.create-topic-rule\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-core/refs/heads/main/capabilities/iot-device-connectivity.yaml
tags:
- IoT
- Device Management
- MQTT
- Message Routing
tools:
- description: Amazon IoT Core List Things
  hints:
    openWorld: true
    readOnly: true
  name: list-things
- description: Amazon IoT Core Create Thing
  hints:
    readOnly: false
  name: create-thing
- description: Amazon IoT Core Delete Thing
  hints:
    readOnly: false
  name: delete-thing
- description: Amazon IoT Core Get Thing
  hints:
    openWorld: true
    readOnly: true
  name: get-thing
- description: Amazon IoT Core Attach Policy
  hints:
    readOnly: false
  name: attach-policy
- description: Amazon IoT Core Create Policy
  hints:
    readOnly: false
  name: create-policy
- description: Amazon IoT Core List Rules
  hints:
    openWorld: true
    readOnly: true
  name: list-rules
- description: Amazon IoT Core Create Topic Rule
  hints:
    readOnly: false
  name: create-topic-rule
---
