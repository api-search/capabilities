---
categories: []
consumed_apis: []
description: The National Interagency Fire Center hosts an ArcGIS REST Services Directory exposing FeatureServer services that provide authoritative geospatial data on wildfire incidents, fire perimeters, dispatch boundaries, fuel treatments, weather stations, and related fire management resources. This specification documents the common ArcGIS REST conventions used by NIFC's hosted services.
layout: capability
name: NIFC ArcGIS REST Services API
operations:
- description: List ArcGIS services
  method: GET
  name: listservices
  path: /
- description: Get FeatureServer metadata
  method: GET
  name: getfeatureserver
  path: /{service}/FeatureServer
- description: Get layer metadata
  method: GET
  name: getlayer
  path: /{service}/FeatureServer/{layerId}
- description: Query a layer
  method: GET
  name: querylayer
  path: /{service}/FeatureServer/{layerId}/query
personas: []
provider_name: National Interagency Fire Center
provider_slug: national-interagency-fire-center
search_terms:
- get layer metadata
- wildfire
- getfeatureserver
- federal government
- get featureserver metadata
- fire
- national
- querylayer
- list arcgis services
- emergency management
- api
- getlayer
- query a layer
- center
- listservices
- geospatial
- interagency
slug: national-interagency-fire-center-capability
source_filename: national-interagency-fire-center-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NIFC ArcGIS REST Services API\n  description: The National Interagency Fire Center hosts an ArcGIS REST Services Directory exposing FeatureServer services\n    that provide authoritative geospatial data on wildfire incidents, fire perimeters, dispatch boundaries, fuel treatments,\n    weather stations, and related fire management resources. This specification documents the common ArcGIS REST conventions\n    used by NIFC's hosted services.\n  tags:\n  - National\n  - Interagency\n  - Fire\n  - Center\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-interagency-fire-center\n    baseUri: https://services3.arcgis.com/T4QMspbfLg3qTGWY/ArcGIS/rest/services\n    description: NIFC ArcGIS REST Services API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: listservices\n        method: GET\n        description: List ArcGIS\
  \ services\n        inputParameters:\n        - name: f\n          in: query\n          type: string\n          description: Response format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-featureserver\n      path: /{service}/FeatureServer\n      operations:\n      - name: getfeatureserver\n        method: GET\n        description: Get FeatureServer metadata\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n        - name: f\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-featureserver-layerid\n      path: /{service}/FeatureServer/{layerId}\n      operations:\n      - name: getlayer\n        method: GET\n        description: Get layer metadata\n        inputParameters:\n \
  \       - name: service\n          in: path\n          type: string\n          required: true\n        - name: layerId\n          in: path\n          type: integer\n          required: true\n        - name: f\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-featureserver-layerid-query\n      path: /{service}/FeatureServer/{layerId}/query\n      operations:\n      - name: querylayer\n        method: GET\n        description: Query a layer\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n        - name: layerId\n          in: path\n          type: integer\n          required: true\n        - name: where\n          in: query\n          type: string\n          description: SQL-like attribute filter.\n        - name: objectIds\n          in: query\n          type: string\n    \
  \      description: Comma-separated ObjectIDs to retrieve.\n        - name: geometry\n          in: query\n          type: string\n          description: Geometry filter (point, envelope, polyline, polygon).\n        - name: geometryType\n          in: query\n          type: string\n        - name: inSR\n          in: query\n          type: string\n          description: Spatial reference of the input geometry.\n        - name: spatialRel\n          in: query\n          type: string\n        - name: outFields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return, or '*' for all.\n        - name: outSR\n          in: query\n          type: string\n        - name: returnGeometry\n          in: query\n          type: boolean\n        - name: returnIdsOnly\n          in: query\n          type: boolean\n        - name: returnCountOnly\n          in: query\n          type: boolean\n        - name: orderByFields\n          in: query\n  \
  \        type: string\n        - name: groupByFieldsForStatistics\n          in: query\n          type: string\n        - name: outStatistics\n          in: query\n          type: string\n        - name: resultOffset\n          in: query\n          type: integer\n        - name: resultRecordCount\n          in: query\n          type: integer\n        - name: f\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-interagency-fire-center-rest\n    description: REST adapter for NIFC ArcGIS REST Services API.\n    resources:\n    - path: /\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List ArcGIS services\n        call: national-interagency-fire-center.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /{service}/FeatureServer\n      name: getfeatureserver\n      operations:\n      - method: GET\n        name: getfeatureserver\n        description: Get FeatureServer metadata\n        call: national-interagency-fire-center.getfeatureserver\n        with:\n          service: rest.service\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{service}/FeatureServer/{layerId}\n      name: getlayer\n      operations:\n      - method: GET\n        name: getlayer\n        description: Get layer metadata\n        call: national-interagency-fire-center.getlayer\n        with:\n          service: rest.service\n          layerId: rest.layerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{service}/FeatureServer/{layerId}/query\n      name: querylayer\n      operations:\n      - method: GET\n        name: querylayer\n        description: Query a layer\n        call: national-interagency-fire-center.querylayer\n\
  \        with:\n          service: rest.service\n          layerId: rest.layerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-interagency-fire-center-mcp\n    transport: http\n    description: MCP adapter for NIFC ArcGIS REST Services API for AI agent use.\n    tools:\n    - name: listservices\n      description: List ArcGIS services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-interagency-fire-center.listservices\n      with:\n        f: tools.f\n      inputParameters:\n      - name: f\n        type: string\n        description: Response format.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfeatureserver\n      description: Get FeatureServer metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-interagency-fire-center.getfeatureserver\n\
  \      with:\n        service: tools.service\n        f: tools.f\n      inputParameters:\n      - name: service\n        type: string\n        description: service\n        required: true\n      - name: f\n        type: string\n        description: f\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlayer\n      description: Get layer metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-interagency-fire-center.getlayer\n      with:\n        service: tools.service\n        layerId: tools.layerId\n        f: tools.f\n      inputParameters:\n      - name: service\n        type: string\n        description: service\n        required: true\n      - name: layerId\n        type: integer\n        description: layerId\n        required: true\n      - name: f\n        type: string\n        description: f\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querylayer\n\
  \      description: Query a layer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-interagency-fire-center.querylayer\n      with:\n        service: tools.service\n        layerId: tools.layerId\n        where: tools.where\n        objectIds: tools.objectIds\n        geometry: tools.geometry\n        geometryType: tools.geometryType\n        inSR: tools.inSR\n        spatialRel: tools.spatialRel\n        outFields: tools.outFields\n        outSR: tools.outSR\n        returnGeometry: tools.returnGeometry\n        returnIdsOnly: tools.returnIdsOnly\n        returnCountOnly: tools.returnCountOnly\n        orderByFields: tools.orderByFields\n        groupByFieldsForStatistics: tools.groupByFieldsForStatistics\n        outStatistics: tools.outStatistics\n        resultOffset: tools.resultOffset\n        resultRecordCount: tools.resultRecordCount\n        f: tools.f\n      inputParameters:\n      - name: service\n        type:\
  \ string\n        description: service\n        required: true\n      - name: layerId\n        type: integer\n        description: layerId\n        required: true\n      - name: where\n        type: string\n        description: SQL-like attribute filter.\n      - name: objectIds\n        type: string\n        description: Comma-separated ObjectIDs to retrieve.\n      - name: geometry\n        type: string\n        description: Geometry filter (point, envelope, polyline, polygon).\n      - name: geometryType\n        type: string\n        description: geometryType\n      - name: inSR\n        type: string\n        description: Spatial reference of the input geometry.\n      - name: spatialRel\n        type: string\n        description: spatialRel\n      - name: outFields\n        type: string\n        description: Comma-separated list of fields to return, or '*' for all.\n      - name: outSR\n        type: string\n        description: outSR\n      - name: returnGeometry\n        type: boolean\n\
  \        description: returnGeometry\n      - name: returnIdsOnly\n        type: boolean\n        description: returnIdsOnly\n      - name: returnCountOnly\n        type: boolean\n        description: returnCountOnly\n      - name: orderByFields\n        type: string\n        description: orderByFields\n      - name: groupByFieldsForStatistics\n        type: string\n        description: groupByFieldsForStatistics\n      - name: outStatistics\n        type: string\n        description: outStatistics\n      - name: resultOffset\n        type: integer\n        description: resultOffset\n      - name: resultRecordCount\n        type: integer\n        description: resultRecordCount\n      - name: f\n        type: string\n        description: f\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-interagency-fire-center/refs/heads/main/capabilities/national-interagency-fire-center-capability.yaml
tags:
- National
- Interagency
- Fire
- Center
- API
tools:
- description: List ArcGIS services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Get FeatureServer metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeatureserver
- description: Get layer metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlayer
- description: Query a layer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querylayer
---
