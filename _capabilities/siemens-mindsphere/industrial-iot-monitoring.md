---
categories: []
consumed_apis:
- mindsphere-assets
- mindsphere-timeseries
description: Unified workflow capability combining MindSphere Asset Management and IoT Time Series APIs for industrial equipment monitoring. Enables operations teams and industrial engineers to manage digital twins, ingest sensor telemetry, and query historical machine data for predictive maintenance, OEE analysis, and condition monitoring use cases.
layout: capability
name: Siemens MindSphere Industrial IoT Monitoring
operations:
- description: List all industrial IoT assets
  method: GET
  name: list-assets
  path: /v1/assets
- description: Create a new digital twin asset
  method: POST
  name: create-asset
  path: /v1/assets
- description: Get asset details by ID
  method: GET
  name: get-asset
  path: /v1/assets/{assetId}
- description: Delete an asset and its digital twin
  method: DELETE
  name: delete-asset
  path: /v1/assets/{assetId}
- description: List all aspect type schemas
  method: GET
  name: list-aspect-types
  path: /v1/aspect-types
- description: List all asset type templates
  method: GET
  name: list-asset-types
  path: /v1/asset-types
- description: Query time-series sensor data for an asset aspect
  method: GET
  name: get-timeseries
  path: /v1/timeseries/{assetId}/{aspectName}
- description: Ingest sensor readings into time series
  method: PUT
  name: ingest-timeseries
  path: /v1/timeseries/{assetId}/{aspectName}
personas: []
provider_name: Siemens MindSphere
provider_slug: siemens-mindsphere
search_terms:
- list all industrial iot assets
- ingest multi timeseries
- list all aspect type schemas
- create asset
- industrial
- asset management
- get asset
- create a new digital twin asset
- list assets
- list all data schema definitions (aspect types) for industrial asset data
- list all industrial iot assets and digital twins in mindsphere
- industrial asset management
- time series
- batch ingest time-series data for multiple industrial assets in one request
- insights hub
- ingest sensor readings into time series
- query historical sensor and machine telemetry from an asset aspect for a time range
- list asset types
- list all asset type templates
- single asset operations
- create a new digital twin for an industrial device or system
- industrial iot
- get details of a specific industrial asset or digital twin
- list aspect types
- predictive maintenance
- delete asset
- query time-series sensor data for an asset aspect
- digital twin
- monitoring
- data schema definitions for asset aspects
- asset type template definitions
- list all asset type templates defining industrial equipment classes
- get asset details by id
- iot
- sensor and machine telemetry time series
- get timeseries
- delete an industrial asset and its digital twin representation
- delete an asset and its digital twin
- ingest sensor readings and telemetry data into mindsphere time series
- ingest timeseries
slug: industrial-iot-monitoring
source_filename: industrial-iot-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Siemens MindSphere Industrial IoT Monitoring\"\n  description: >-\n    Unified workflow capability combining MindSphere Asset Management and IoT\n    Time Series APIs for industrial equipment monitoring. Enables operations\n    teams and industrial engineers to manage digital twins, ingest sensor\n    telemetry, and query historical machine data for predictive maintenance,\n    OEE analysis, and condition monitoring use cases.\n  tags:\n    - IoT\n    - Industrial\n    - Asset Management\n    - Time Series\n    - Digital Twin\n    - Monitoring\n    - Predictive Maintenance\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      MINDSPHERE_BEARER_TOKEN: MINDSPHERE_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: mindsphere-assets\n      location: ./shared/asset-management.yaml\n    - import: mindsphere-timeseries\n      location: ./shared/iot-timeseries.yaml\n\n  exposes:\n \
  \   - type: rest\n      port: 8080\n      namespace: mindsphere-iot-api\n      description: \"Unified REST API for industrial IoT asset monitoring and telemetry on MindSphere.\"\n      resources:\n        - path: /v1/assets\n          name: assets\n          description: \"Industrial asset management\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List all industrial IoT assets\"\n              call: \"mindsphere-assets.list-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-asset\n              description: \"Create a new digital twin asset\"\n              call: \"mindsphere-assets.create-asset\"\n              with:\n                name: \"rest.name\"\n                typeId: \"rest.typeId\"\n                parentId: \"rest.parentId\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n\n        - path: /v1/assets/{assetId}\n          name: asset\n          description: \"Single asset operations\"\n          operations:\n            - method: GET\n              name: get-asset\n              description: \"Get asset details by ID\"\n              call: \"mindsphere-assets.get-asset\"\n              with:\n                assetId: \"rest.assetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-asset\n              description: \"Delete an asset and its digital twin\"\n              call: \"mindsphere-assets.delete-asset\"\n              with:\n                assetId: \"rest.assetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/aspect-types\n          name: aspect-types\n          description: \"Data schema definitions for asset aspects\"\n       \
  \   operations:\n            - method: GET\n              name: list-aspect-types\n              description: \"List all aspect type schemas\"\n              call: \"mindsphere-assets.list-aspect-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/asset-types\n          name: asset-types\n          description: \"Asset type template definitions\"\n          operations:\n            - method: GET\n              name: list-asset-types\n              description: \"List all asset type templates\"\n              call: \"mindsphere-assets.list-asset-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/timeseries/{assetId}/{aspectName}\n          name: timeseries\n          description: \"Sensor and machine telemetry time series\"\n          operations:\n            - method: GET\n              name: get-timeseries\n              description:\
  \ \"Query time-series sensor data for an asset aspect\"\n              call: \"mindsphere-timeseries.get-timeseries\"\n              with:\n                assetId: \"rest.assetId\"\n                aspectName: \"rest.aspectName\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: ingest-timeseries\n              description: \"Ingest sensor readings into time series\"\n              call: \"mindsphere-timeseries.ingest-timeseries\"\n              with:\n                assetId: \"rest.assetId\"\n                aspectName: \"rest.aspectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: mindsphere-iot-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ industrial IoT monitoring and asset management on MindSphere.\"\n      tools:\n        - name: list-assets\n          description: \"List all industrial IoT assets and digital twins in MindSphere\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mindsphere-assets.list-assets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-asset\n          description: \"Get details of a specific industrial asset or digital twin\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mindsphere-assets.get-asset\"\n          with:\n            assetId: \"tools.assetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-asset\n          description: \"Create a new digital twin for an industrial device or system\"\n          hints:\n            readOnly: false\n            destructive: false\n\
  \            idempotent: false\n          call: \"mindsphere-assets.create-asset\"\n          with:\n            name: \"tools.name\"\n            typeId: \"tools.typeId\"\n            parentId: \"tools.parentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-asset\n          description: \"Delete an industrial asset and its digital twin representation\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"mindsphere-assets.delete-asset\"\n          with:\n            assetId: \"tools.assetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-aspect-types\n          description: \"List all data schema definitions (aspect types) for industrial asset data\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mindsphere-assets.list-aspect-types\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-asset-types\n          description: \"List all asset type templates defining industrial equipment classes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mindsphere-assets.list-asset-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-timeseries\n          description: \"Query historical sensor and machine telemetry from an asset aspect for a time range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mindsphere-timeseries.get-timeseries\"\n          with:\n            assetId: \"tools.assetId\"\n            aspectName: \"tools.aspectName\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: ingest-timeseries\n          description: \"Ingest sensor readings and telemetry data into MindSphere time series\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"mindsphere-timeseries.ingest-timeseries\"\n          with:\n            assetId: \"tools.assetId\"\n            aspectName: \"tools.aspectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ingest-multi-timeseries\n          description: \"Batch ingest time-series data for multiple industrial assets in one request\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"mindsphere-timeseries.ingest-multi-timeseries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/siemens-mindsphere/refs/heads/main/capabilities/industrial-iot-monitoring.yaml
tags:
- IoT
- Industrial
- Asset Management
- Time Series
- Digital Twin
- Monitoring
- Predictive Maintenance
tools:
- description: List all industrial IoT assets and digital twins in MindSphere
  hints:
    openWorld: false
    readOnly: true
  name: list-assets
- description: Get details of a specific industrial asset or digital twin
  hints:
    openWorld: false
    readOnly: true
  name: get-asset
- description: Create a new digital twin for an industrial device or system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-asset
- description: Delete an industrial asset and its digital twin representation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-asset
- description: List all data schema definitions (aspect types) for industrial asset data
  hints:
    openWorld: false
    readOnly: true
  name: list-aspect-types
- description: List all asset type templates defining industrial equipment classes
  hints:
    openWorld: false
    readOnly: true
  name: list-asset-types
- description: Query historical sensor and machine telemetry from an asset aspect for a time range
  hints:
    openWorld: false
    readOnly: true
  name: get-timeseries
- description: Ingest sensor readings and telemetry data into MindSphere time series
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: ingest-timeseries
- description: Batch ingest time-series data for multiple industrial assets in one request
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: ingest-multi-timeseries
---
