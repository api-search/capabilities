---
categories:
- iot
consumed_apis:
- iot-device-management
description: Unified capability for IoT Engineer, Operations Engineer to manage onboard, organize, and manage iot devices at scale operations.
layout: capability
name: Amazon IoT Device Management - Iot Fleet Management
operations:
- description: List Thing Groups
  method: GET
  name: list-thing-groups
  path: /v1/resources
personas: []
provider_name: Amazon IoT Device Management
provider_slug: amazon-iot-device-management
search_terms:
- Operations Engineer
- list job executions
- create job
- amazon iot device management add thing to group
- add thing to group
- list jobs
- ota updates
- list thing groups
- amazon iot device management list things in group
- list things in group
- amazon iot device management create thing group
- aws
- amazon iot device management describe job
- onboard, organize, and manage iot devices at scale.
- device management
- amazon iot device management list thing groups
- create thing group
- amazon iot device management create job
- amazon iot device management list job executions
- IoT Engineer
- manages amazon iot device management resources and operations
- amazon iot device management list jobs
- describe job
- fleet management
- amazon iot device management resources
- iot
slug: iot-fleet-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT Device Management - Iot Fleet Management\n  description: Unified capability for IoT Engineer, Operations Engineer to manage onboard, organize, and manage iot devices at scale operations.\n  tags:\n    - IoT\n    - AWS\n    - Device Management\n    - Fleet Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-device-management\n      location: ./shared/iot-device-management.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: iot-fleet-management-api\n      description: Unified REST API for iot fleet management.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT Device Management resources\n          operations:\n            - method: GET\n              name:\
  \ list-thing-groups\n              description: List Thing Groups\n              call: \"iot-device-management.list-thing-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: iot-fleet-management-mcp\n      transport: http\n      description: MCP server for AI-assisted iot fleet management.\n      tools:\n        - name: list-thing-groups\n          description: Amazon IoT Device Management List Thing Groups\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-management.list-thing-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-thing-group\n          description: Amazon IoT Device Management Create Thing Group\n          hints:\n            readOnly: false\n            \n          call: \"iot-device-management.create-thing-group\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobs\n          description: Amazon IoT Device Management List Jobs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-management.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-job\n          description: Amazon IoT Device Management Create Job\n          hints:\n            readOnly: false\n            \n          call: \"iot-device-management.create-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-job\n          description: Amazon IoT Device Management Describe Job\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-management.describe-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ list-job-executions\n          description: Amazon IoT Device Management List Job Executions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-management.list-job-executions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-thing-to-group\n          description: Amazon IoT Device Management Add Thing To Group\n          hints:\n            readOnly: false\n            \n          call: \"iot-device-management.add-thing-to-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-things-in-group\n          description: Amazon IoT Device Management List Things In Group\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-management.list-things-in-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-device-management/refs/heads/main/capabilities/iot-fleet-management.yaml
tags:
- IoT
- AWS
- Device Management
- Fleet Management
tools:
- description: Amazon IoT Device Management List Thing Groups
  hints:
    openWorld: true
    readOnly: true
  name: list-thing-groups
- description: Amazon IoT Device Management Create Thing Group
  hints:
    readOnly: false
  name: create-thing-group
- description: Amazon IoT Device Management List Jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Amazon IoT Device Management Create Job
  hints:
    readOnly: false
  name: create-job
- description: Amazon IoT Device Management Describe Job
  hints:
    openWorld: true
    readOnly: true
  name: describe-job
- description: Amazon IoT Device Management List Job Executions
  hints:
    openWorld: true
    readOnly: true
  name: list-job-executions
- description: Amazon IoT Device Management Add Thing To Group
  hints:
    readOnly: false
  name: add-thing-to-group
- description: Amazon IoT Device Management List Things In Group
  hints:
    openWorld: true
    readOnly: true
  name: list-things-in-group
---
