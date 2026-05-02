---
categories:
- iot
consumed_apis: []
description: Manage FreeRTOS software configurations and OTA firmware updates for microcontroller IoT devices.
layout: capability
name: Amazon FreeRTOS Device Management
operations: []
personas: []
provider_name: Amazon FreeRTOS
provider_slug: amazon-freertos
search_terms:
- firmware
- iot
- embedded systems
- microcontrollers
- rtos
- ota updates
- aws
slug: amazon-freertos-device-management
source_filename: amazon-freertos-device-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon FreeRTOS Device Management\n  description: Manage FreeRTOS software configurations and OTA firmware updates for microcontroller IoT devices.\n  tags:\n  - IoT\n  - Embedded Systems\n  - RTOS\n  - OTA Updates\n  - Firmware\n  - AWS\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - namespace: freertos\n    ref: capabilities/shared/freertos.yaml\n  exposes:\n  - type: rest\n    port: 8080\n  - type: mcp\n    port: 9090\n  tools:\n  - name: createSoftwareConfiguration\n    description: Create a FreeRTOS software configuration\n    inputSchema:\n      type: object\n      properties:\n        name:\n          type: string\n        hardwarePlatform:\n          type: string\n        description:\n          type: string\n      required:\n      - name\n      - hardwarePlatform\n  - name: listSoftwareConfigurations\n\
  \    description: List FreeRTOS software configurations\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type: integer\n        nextToken:\n          type: string\n  - name: describeSoftwareConfiguration\n    description: Get a FreeRTOS software configuration\n    inputSchema:\n      type: object\n      properties:\n        configId:\n          type: string\n      required:\n      - configId\n  - name: updateSoftwareConfiguration\n    description: Update a FreeRTOS software configuration\n    inputSchema:\n      type: object\n      properties:\n        configId:\n          type: string\n        name:\n          type: string\n        description:\n          type: string\n      required:\n      - configId\n  - name: deleteSoftwareConfiguration\n    description: Delete a FreeRTOS software configuration\n    inputSchema:\n      type: object\n      properties:\n        configId:\n          type: string\n      required:\n      - configId\n  - name: createOtaUpdate\n\
  \    description: Create an OTA firmware update for FreeRTOS devices\n    inputSchema:\n      type: object\n      properties:\n        otaUpdateId:\n          type: string\n        targets:\n          type: array\n        files:\n          type: array\n        roleArn:\n          type: string\n        protocols:\n          type: array\n        description:\n          type: string\n      required:\n      - otaUpdateId\n      - targets\n      - files\n  - name: listOtaUpdates\n    description: List OTA updates\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type: integer\n        nextToken:\n          type: string\n        otaUpdateStatus:\n          type: string\n  - name: getOtaUpdate\n    description: Get an OTA update\n    inputSchema:\n      type: object\n      properties:\n        otaUpdateId:\n          type: string\n      required:\n      - otaUpdateId\n  - name: deleteOtaUpdate\n    description: Delete an OTA update\n    inputSchema:\n  \
  \    type: object\n      properties:\n        otaUpdateId:\n          type: string\n        deleteStream:\n          type: boolean\n        forceDeleteAWSJob:\n          type: boolean\n      required:\n      - otaUpdateId\n  - name: listTagsForResource\n    description: List tags for a FreeRTOS resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n      required:\n      - resourceArn\n  - name: tagResource\n    description: Tag a FreeRTOS resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n        tags:\n          type: object\n      required:\n      - resourceArn\n      - tags\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-freertos/refs/heads/main/capabilities/amazon-freertos-device-management.yaml
tags:
- IoT
- Embedded Systems
- RTOS
- OTA Updates
- Firmware
tools: []
---
