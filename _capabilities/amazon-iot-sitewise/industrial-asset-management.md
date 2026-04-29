---
categories:
- iot
consumed_apis:
- iot-sitewise
description: Unified capability for OT Engineer, Data Analyst to manage collect, organize, and analyze industrial equipment data operations.
layout: capability
name: Amazon IoT SiteWise - Industrial Asset Management
operations:
- description: List Assets
  method: GET
  name: list-assets
  path: /v1/resources
personas: []
provider_name: Amazon IoT SiteWise
provider_slug: amazon-iot-sitewise
search_terms:
- amazon iot sitewise batch put asset property value
- amazon iot sitewise list portals
- manages amazon iot sitewise resources and operations
- asset management
- amazon iot sitewise create asset model
- amazon iot sitewise resources
- amazon iot sitewise create portal
- amazon iot sitewise list asset models
- amazon iot sitewise list assets
- aws
- Data Analyst
- create asset
- list asset models
- iot
- create portal
- amazon iot sitewise create asset
- collect, organize, and analyze industrial equipment data.
- OT Engineer
- industrial iot
- amazon iot sitewise get asset property value
- list portals
- list assets
- get asset property value
- create asset model
- batch put asset property value
- time series data
slug: industrial-asset-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT SiteWise - Industrial Asset Management\n  description: Unified capability for OT Engineer, Data Analyst to manage collect, organize, and analyze industrial equipment data operations.\n  tags:\n    - IoT\n    - AWS\n    - Industrial IoT\n    - Asset Management\n    - Time Series Data\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-sitewise\n      location: ./shared/iot-sitewise.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: industrial-asset-management-api\n      description: Unified REST API for industrial asset management.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT SiteWise resources\n          operations:\n            - method: GET\n            \
  \  name: list-assets\n              description: List Assets\n              call: \"iot-sitewise.list-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: industrial-asset-management-mcp\n      transport: http\n      description: MCP server for AI-assisted industrial asset management.\n      tools:\n        - name: list-assets\n          description: Amazon IoT SiteWise List Assets\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-sitewise.list-assets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-asset\n          description: Amazon IoT SiteWise Create Asset\n          hints:\n            readOnly: false\n            \n          call: \"iot-sitewise.create-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        -\
  \ name: list-asset-models\n          description: Amazon IoT SiteWise List Asset Models\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-sitewise.list-asset-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-asset-model\n          description: Amazon IoT SiteWise Create Asset Model\n          hints:\n            readOnly: false\n            \n          call: \"iot-sitewise.create-asset-model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-asset-property-value\n          description: Amazon IoT SiteWise Get Asset Property Value\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-sitewise.get-asset-property-value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-portals\n          description: Amazon\
  \ IoT SiteWise List Portals\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-sitewise.list-portals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-portal\n          description: Amazon IoT SiteWise Create Portal\n          hints:\n            readOnly: false\n            \n          call: \"iot-sitewise.create-portal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-put-asset-property-value\n          description: Amazon IoT SiteWise Batch Put Asset Property Value\n          hints:\n            readOnly: false\n            \n          call: \"iot-sitewise.batch-put-asset-property-value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-sitewise/refs/heads/main/capabilities/industrial-asset-management.yaml
tags:
- IoT
- AWS
- Industrial IoT
- Asset Management
- Time Series Data
tools:
- description: Amazon IoT SiteWise List Assets
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: Amazon IoT SiteWise Create Asset
  hints:
    readOnly: false
  name: create-asset
- description: Amazon IoT SiteWise List Asset Models
  hints:
    openWorld: true
    readOnly: true
  name: list-asset-models
- description: Amazon IoT SiteWise Create Asset Model
  hints:
    readOnly: false
  name: create-asset-model
- description: Amazon IoT SiteWise Get Asset Property Value
  hints:
    openWorld: true
    readOnly: true
  name: get-asset-property-value
- description: Amazon IoT SiteWise List Portals
  hints:
    openWorld: true
    readOnly: true
  name: list-portals
- description: Amazon IoT SiteWise Create Portal
  hints:
    readOnly: false
  name: create-portal
- description: Amazon IoT SiteWise Batch Put Asset Property Value
  hints:
    readOnly: false
  name: batch-put-asset-property-value
---
