---
categories:
- iot
consumed_apis:
- iot-events
description: Unified capability for IoT Developer, Solutions Architect to manage detect and respond to events from iot sensors and applications operations.
layout: capability
name: Amazon IoT Events - Iot Event Management
operations:
- description: List Detector Models
  method: GET
  name: list-detector-models
  path: /v1/resources
personas: []
provider_name: Amazon IoT Events
provider_slug: amazon-iot-events
search_terms:
- amazon iot events create input
- describe detector model
- amazon iot events list detector models
- state machine
- Solutions Architect
- amazon iot events resources
- create detector model
- detect and respond to events from iot sensors and applications.
- automation
- manages amazon iot events resources and operations
- amazon iot events create alarm model
- list detector models
- iot
- aws
- list alarms
- event detection
- amazon iot events describe alarm model
- amazon iot events list alarms
- create alarm model
- create input
- list inputs
- IoT Developer
- describe alarm model
- amazon iot events list inputs
- amazon iot events create detector model
- amazon iot events describe detector model
slug: iot-event-management
source_filename: iot-event-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT Events - Iot Event Management\n  description: Unified capability for IoT Developer, Solutions Architect to manage detect and respond to events from iot sensors and applications operations.\n  tags:\n    - IoT\n    - AWS\n    - Event Detection\n    - Automation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-events\n      location: ./shared/iot-events.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: iot-event-management-api\n      description: Unified REST API for iot event management.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT Events resources\n          operations:\n            - method: GET\n              name: list-detector-models\n             \
  \ description: List Detector Models\n              call: \"iot-events.list-detector-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: iot-event-management-mcp\n      transport: http\n      description: MCP server for AI-assisted iot event management.\n      tools:\n        - name: list-detector-models\n          description: Amazon IoT Events List Detector Models\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-events.list-detector-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-detector-model\n          description: Amazon IoT Events Create Detector Model\n          hints:\n            readOnly: false\n            \n          call: \"iot-events.create-detector-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: list-inputs\n          description: Amazon IoT Events List Inputs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-events.list-inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-input\n          description: Amazon IoT Events Create Input\n          hints:\n            readOnly: false\n            \n          call: \"iot-events.create-input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-detector-model\n          description: Amazon IoT Events Describe Detector Model\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-events.describe-detector-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-alarms\n          description: Amazon IoT Events List Alarms\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"iot-events.list-alarms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-alarm-model\n          description: Amazon IoT Events Create Alarm Model\n          hints:\n            readOnly: false\n            \n          call: \"iot-events.create-alarm-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-alarm-model\n          description: Amazon IoT Events Describe Alarm Model\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-events.describe-alarm-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-events/refs/heads/main/capabilities/iot-event-management.yaml
tags:
- IoT
- Event Detection
- Automation
tools:
- description: Amazon IoT Events List Detector Models
  hints:
    openWorld: true
    readOnly: true
  name: list-detector-models
- description: Amazon IoT Events Create Detector Model
  hints:
    readOnly: false
  name: create-detector-model
- description: Amazon IoT Events List Inputs
  hints:
    openWorld: true
    readOnly: true
  name: list-inputs
- description: Amazon IoT Events Create Input
  hints:
    readOnly: false
  name: create-input
- description: Amazon IoT Events Describe Detector Model
  hints:
    openWorld: true
    readOnly: true
  name: describe-detector-model
- description: Amazon IoT Events List Alarms
  hints:
    openWorld: true
    readOnly: true
  name: list-alarms
- description: Amazon IoT Events Create Alarm Model
  hints:
    readOnly: false
  name: create-alarm-model
- description: Amazon IoT Events Describe Alarm Model
  hints:
    openWorld: true
    readOnly: true
  name: describe-alarm-model
---
