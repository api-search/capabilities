---
categories:
- iot
consumed_apis:
- iot-greengrass
description: Unified capability for IoT Developer, Edge Computing Engineer to manage extend aws compute and services to edge devices operations.
layout: capability
name: Amazon IoT Greengrass - Edge Device Management
operations:
- description: List Components
  method: GET
  name: list-components
  path: /v1/resources
personas: []
provider_name: Amazon IoT Greengrass
provider_slug: amazon-iot-greengrass
search_terms:
- amazon iot greengrass create deployment
- get core device
- machine learning
- create component version
- aws
- edge computing
- extend aws compute and services to edge devices.
- amazon iot greengrass get core device
- lambda
- manages amazon iot greengrass resources and operations
- amazon iot greengrass resources
- list components
- create deployment
- amazon iot greengrass list components
- amazon iot greengrass describe component
- amazon iot greengrass list core devices
- amazon iot greengrass create component version
- list component versions
- amazon iot greengrass list component versions
- Edge Computing Engineer
- device management
- list core devices
- amazon iot greengrass list deployments
- describe component
- iot
- IoT Developer
- real-time processing
- list deployments
slug: edge-device-management
source_filename: edge-device-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT Greengrass - Edge Device Management\n  description: Unified capability for IoT Developer, Edge Computing Engineer to manage extend aws compute and services to edge devices operations.\n  tags:\n    - IoT\n    - AWS\n    - Edge Computing\n    - Lambda\n    - Device Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-greengrass\n      location: ./shared/iot-greengrass.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: edge-device-management-api\n      description: Unified REST API for edge device management.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT Greengrass resources\n          operations:\n            - method: GET\n              name: list-components\n\
  \              description: List Components\n              call: \"iot-greengrass.list-components\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: edge-device-management-mcp\n      transport: http\n      description: MCP server for AI-assisted edge device management.\n      tools:\n        - name: list-components\n          description: Amazon IoT Greengrass List Components\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-greengrass.list-components\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-component-version\n          description: Amazon IoT Greengrass Create Component Version\n          hints:\n            readOnly: false\n            \n          call: \"iot-greengrass.create-component-version\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n\n        - name: list-core-devices\n          description: Amazon IoT Greengrass List Core Devices\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-greengrass.list-core-devices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-deployments\n          description: Amazon IoT Greengrass List Deployments\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-greengrass.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-deployment\n          description: Amazon IoT Greengrass Create Deployment\n          hints:\n            readOnly: false\n            \n          call: \"iot-greengrass.create-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-component\n\
  \          description: Amazon IoT Greengrass Describe Component\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-greengrass.describe-component\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-core-device\n          description: Amazon IoT Greengrass Get Core Device\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-greengrass.get-core-device\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-component-versions\n          description: Amazon IoT Greengrass List Component Versions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-greengrass.list-component-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-greengrass/refs/heads/main/capabilities/edge-device-management.yaml
tags:
- IoT
- AWS
- Edge Computing
- Lambda
- Device Management
tools:
- description: Amazon IoT Greengrass List Components
  hints:
    openWorld: true
    readOnly: true
  name: list-components
- description: Amazon IoT Greengrass Create Component Version
  hints:
    readOnly: false
  name: create-component-version
- description: Amazon IoT Greengrass List Core Devices
  hints:
    openWorld: true
    readOnly: true
  name: list-core-devices
- description: Amazon IoT Greengrass List Deployments
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Amazon IoT Greengrass Create Deployment
  hints:
    readOnly: false
  name: create-deployment
- description: Amazon IoT Greengrass Describe Component
  hints:
    openWorld: true
    readOnly: true
  name: describe-component
- description: Amazon IoT Greengrass Get Core Device
  hints:
    openWorld: true
    readOnly: true
  name: get-core-device
- description: Amazon IoT Greengrass List Component Versions
  hints:
    openWorld: true
    readOnly: true
  name: list-component-versions
---
