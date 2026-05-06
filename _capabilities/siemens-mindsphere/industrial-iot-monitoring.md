---
categories: []
consumed_apis: []
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
- asset type template definitions
- list all industrial iot assets and digital twins in mindsphere
- list all industrial iot assets
- get asset
- list asset types
- list all asset type templates defining industrial equipment classes
- delete an asset and its digital twin
- industrial
- ingest sensor readings into time series
- iot
- insights hub
- list aspect types
- monitoring
- single asset operations
- delete asset
- industrial iot
- create a new digital twin for an industrial device or system
- list all asset type templates
- predictive maintenance
- batch ingest time-series data for multiple industrial assets in one request
- time series
- create asset
- query time-series sensor data for an asset aspect
- data schema definitions for asset aspects
- list assets
- ingest sensor readings and telemetry data into mindsphere time series
- get asset details by id
- digital twin
- create a new digital twin asset
- ingest timeseries
- get timeseries
- query historical sensor and machine telemetry from an asset aspect for a time range
- list all data schema definitions (aspect types) for industrial asset data
- delete an industrial asset and its digital twin representation
- ingest multi timeseries
- asset management
- list all aspect type schemas
- get details of a specific industrial asset or digital twin
- industrial asset management
- sensor and machine telemetry time series
slug: industrial-iot-monitoring
source_filename: industrial-iot-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Siemens MindSphere Industrial IoT Monitoring\n  description: Unified workflow capability combining MindSphere Asset Management and IoT Time Series APIs for industrial equipment\n    monitoring. Enables operations teams and industrial engineers to manage digital twins, ingest sensor telemetry, and query\n    historical machine data for predictive maintenance, OEE analysis, and condition monitoring use cases.\n  tags:\n  - IoT\n  - Industrial\n  - Asset Management\n  - Time Series\n  - Digital Twin\n  - Monitoring\n  - Predictive Maintenance\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MINDSPHERE_BEARER_TOKEN: MINDSPHERE_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: mindsphere-assets\n    baseUri: https://gateway.eu1.mindsphere.io/api/assetmanagement/v3\n    description: MindSphere Asset Management REST API\n    authentication:\n      type: bearer\n      token: '{{MINDSPHERE_BEARER_TOKEN}}'\n\
  \    resources:\n    - name: assets\n      path: /assets\n      description: Asset instance management\n      operations:\n      - name: list-assets\n        method: GET\n        description: List all assets in the tenant\n        inputParameters:\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-asset\n        method: POST\n        description: Create a new asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            typeId: '{{tools.typeId}}'\n            parentId:\
  \ '{{tools.parentId}}'\n    - name: asset\n      path: /assets/{assetId}\n      description: Single asset operations\n      operations:\n      - name: get-asset\n        method: GET\n        description: Get an asset by ID\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-asset\n        method: DELETE\n        description: Delete an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: aspect-types\n      path: /aspecttypes\n      description: Aspect type management\n\
  \      operations:\n      - name: list-aspect-types\n        method: GET\n        description: List all aspect types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asset-types\n      path: /assettypes\n      description: Asset type management\n      operations:\n      - name: list-asset-types\n        method: GET\n        description: List all asset types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: mindsphere-timeseries\n    baseUri: https://gateway.eu1.mindsphere.io/api/iottimeseries/v3\n    description: MindSphere IoT Time Series REST API\n    authentication:\n      type: bearer\n      token: '{{MINDSPHERE_BEARER_TOKEN}}'\n    resources:\n    - name: timeseries-bulk\n      path: /timeseries\n      description: Multi-asset time series ingestion\n      operations:\n      - name: ingest-multi-timeseries\n\
  \        method: PUT\n        description: Ingest time-series data for multiple asset aspects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeseries\n      path: /timeseries/{assetId}/{aspectName}\n      description: Single asset aspect time series operations\n      operations:\n      - name: ingest-timeseries\n        method: PUT\n        description: Ingest time-series data for a specific asset and aspect\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset unique identifier\n        - name: aspectName\n          in: path\n          type: string\n          required: true\n          description: Aspect name containing the time series variables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-timeseries\n\
  \        method: GET\n        description: Query time-series data for a specific asset aspect\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset unique identifier\n        - name: aspectName\n          in: path\n          type: string\n          required: true\n          description: Aspect name to query\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start of time range (ISO 8601)\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of time range (ISO 8601)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of data points to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ delete-timeseries\n        method: DELETE\n        description: Delete time-series data for an asset aspect in a time range\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset unique identifier\n        - name: aspectName\n          in: path\n          type: string\n          required: true\n          description: Aspect name\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: Start of deletion range (ISO 8601)\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: End of deletion range (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mindsphere-iot-api\n    description: Unified REST API for industrial IoT asset monitoring\
  \ and telemetry on MindSphere.\n    resources:\n    - path: /v1/assets\n      name: assets\n      description: Industrial asset management\n      operations:\n      - method: GET\n        name: list-assets\n        description: List all industrial IoT assets\n        call: mindsphere-assets.list-assets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-asset\n        description: Create a new digital twin asset\n        call: mindsphere-assets.create-asset\n        with:\n          name: rest.name\n          typeId: rest.typeId\n          parentId: rest.parentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{assetId}\n      name: asset\n      description: Single asset operations\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get asset details by ID\n        call: mindsphere-assets.get-asset\n        with:\n          assetId: rest.assetId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-asset\n        description: Delete an asset and its digital twin\n        call: mindsphere-assets.delete-asset\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aspect-types\n      name: aspect-types\n      description: Data schema definitions for asset aspects\n      operations:\n      - method: GET\n        name: list-aspect-types\n        description: List all aspect type schemas\n        call: mindsphere-assets.list-aspect-types\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/asset-types\n      name: asset-types\n      description: Asset type template definitions\n      operations:\n      - method: GET\n        name: list-asset-types\n        description: List all asset type templates\n        call: mindsphere-assets.list-asset-types\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timeseries/{assetId}/{aspectName}\n      name: timeseries\n      description: Sensor and machine telemetry time series\n      operations:\n      - method: GET\n        name: get-timeseries\n        description: Query time-series sensor data for an asset aspect\n        call: mindsphere-timeseries.get-timeseries\n        with:\n          assetId: rest.assetId\n          aspectName: rest.aspectName\n          from: rest.from\n          to: rest.to\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: ingest-timeseries\n        description: Ingest sensor readings into time series\n        call: mindsphere-timeseries.ingest-timeseries\n        with:\n          assetId: rest.assetId\n          aspectName: rest.aspectName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: mindsphere-iot-mcp\n    transport: http\n    description: MCP server for AI-assisted industrial IoT monitoring and asset management on MindSphere.\n    tools:\n    - name: list-assets\n      description: List all industrial IoT assets and digital twins in MindSphere\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mindsphere-assets.list-assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get details of a specific industrial asset or digital twin\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mindsphere-assets.get-asset\n      with:\n        assetId: tools.assetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-asset\n      description: Create a new digital twin for an industrial device or system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mindsphere-assets.create-asset\n\
  \      with:\n        name: tools.name\n        typeId: tools.typeId\n        parentId: tools.parentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-asset\n      description: Delete an industrial asset and its digital twin representation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: mindsphere-assets.delete-asset\n      with:\n        assetId: tools.assetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-aspect-types\n      description: List all data schema definitions (aspect types) for industrial asset data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mindsphere-assets.list-aspect-types\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-asset-types\n      description: List all asset type templates defining industrial equipment classes\n      hints:\n        readOnly: true\n       \
  \ openWorld: false\n      call: mindsphere-assets.list-asset-types\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-timeseries\n      description: Query historical sensor and machine telemetry from an asset aspect for a time range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mindsphere-timeseries.get-timeseries\n      with:\n        assetId: tools.assetId\n        aspectName: tools.aspectName\n        from: tools.from\n        to: tools.to\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-timeseries\n      description: Ingest sensor readings and telemetry data into MindSphere time series\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mindsphere-timeseries.ingest-timeseries\n      with:\n        assetId: tools.assetId\n        aspectName: tools.aspectName\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: ingest-multi-timeseries\n      description: Batch ingest time-series data for multiple industrial assets in one request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mindsphere-timeseries.ingest-multi-timeseries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
