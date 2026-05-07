---
categories: []
consumed_apis: []
description: The Google Earth Engine REST API provides programmatic access to Earth Engine's planetary-scale geospatial analysis capabilities. You can manage projects, compute satellite imagery analysis, export data, work with image collections, feature collections, and perform large-scale geospatial computations.
layout: capability
name: Google Earth Engine REST API
operations:
- description: List assets
  method: GET
  name: listassets
  path: /projects/{project}/assets
- description: Get an asset
  method: GET
  name: getasset
  path: /projects/{project}/assets/{assetId}
- description: Delete an asset
  method: DELETE
  name: deleteasset
  path: /projects/{project}/assets/{assetId}
- description: Compute pixels
  method: POST
  name: computepixels
  path: /projects/{project}/image:computePixels
- description: Export an image
  method: POST
  name: exportimage
  path: /projects/{project}/image:export
- description: Compute features
  method: POST
  name: computefeatures
  path: /projects/{project}/table:computeFeatures
- description: Export a table
  method: POST
  name: exporttable
  path: /projects/{project}/table:export
- description: Compute a value
  method: POST
  name: computevalue
  path: /projects/{project}/value:compute
- description: Create a map
  method: POST
  name: createmap
  path: /projects/{project}/maps
- description: List operations
  method: GET
  name: listoperations
  path: /projects/{project}/operations
- description: Get an operation
  method: GET
  name: getoperation
  path: /projects/{project}/operations/{operationId}
personas: []
provider_name: Google Earth Engine REST
provider_slug: google-earth-engine
search_terms:
- compute a value
- list operations
- listoperations
- api
- deleteasset
- remote sensing
- earth
- earth observation
- exportimage
- get an operation
- google
- compute features
- geospatial
- export an image
- getoperation
- satellite imagery
- computevalue
- delete an asset
- listassets
- engine
- climate
- computepixels
- export a table
- gis
- environmental
- compute pixels
- computefeatures
- getasset
- create a map
- get an asset
- createmap
- exporttable
- list assets
slug: google-earth-engine-capability
source_filename: google-earth-engine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Earth Engine REST API\n  description: The Google Earth Engine REST API provides programmatic access to Earth Engine's planetary-scale geospatial\n    analysis capabilities. You can manage projects, compute satellite imagery analysis, export data, work with image collections,\n    feature collections, and perform large-scale geospatial computations.\n  tags:\n  - Google\n  - Earth\n  - Engine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-earth-engine\n    baseUri: https://earthengine.googleapis.com/v1\n    description: Google Earth Engine REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_EARTH_ENGINE_TOKEN}}'\n    resources:\n    - name: projects-project-assets\n      path: /projects/{project}/assets\n      operations:\n      - name: listassets\n        method: GET\n        description: List assets\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-assets-assetid\n      path: /projects/{project}/assets/{assetId}\n      operations:\n      - name: getasset\n        method: GET\n        description: Get an asset\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: assetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteasset\n        method: DELETE\n        description: Delete an asset\n      \
  \  inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: assetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-image-computepixels\n      path: /projects/{project}/image:computePixels\n      operations:\n      - name: computepixels\n        method: POST\n        description: Compute pixels\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-image-export\n      path: /projects/{project}/image:export\n      operations:\n      - name: exportimage\n        method: POST\n        description: Export an image\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-table-computefeatures\n      path: /projects/{project}/table:computeFeatures\n      operations:\n      - name: computefeatures\n        method: POST\n        description: Compute features\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-table-export\n      path: /projects/{project}/table:export\n      operations:\n      - name: exporttable\n        method: POST\n        description: Export a table\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-value-compute\n      path: /projects/{project}/value:compute\n      operations:\n      - name: computevalue\n        method: POST\n        description: Compute a value\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-maps\n      path: /projects/{project}/maps\n      operations:\n      - name: createmap\n        method: POST\n        description: Create a map\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: projects-project-operations\n      path: /projects/{project}/operations\n      operations:\n      - name: listoperations\n        method: GET\n        description: List operations\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-operations-operationid\n      path: /projects/{project}/operations/{operationId}\n      operations:\n      - name: getoperation\n        method: GET\n        description: Get an operation\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: operationId\n          in: path\n          type: string\n    \
  \      required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-earth-engine-rest\n    description: REST adapter for Google Earth Engine REST API.\n    resources:\n    - path: /projects/{project}/assets\n      name: listassets\n      operations:\n      - method: GET\n        name: listassets\n        description: List assets\n        call: google-earth-engine.listassets\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/assets/{assetId}\n      name: getasset\n      operations:\n      - method: GET\n        name: getasset\n        description: Get an asset\n        call: google-earth-engine.getasset\n        with:\n          project: rest.project\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /projects/{project}/assets/{assetId}\n      name: deleteasset\n      operations:\n      - method: DELETE\n        name: deleteasset\n        description: Delete an asset\n        call: google-earth-engine.deleteasset\n        with:\n          project: rest.project\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/image:computePixels\n      name: computepixels\n      operations:\n      - method: POST\n        name: computepixels\n        description: Compute pixels\n        call: google-earth-engine.computepixels\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/image:export\n      name: exportimage\n      operations:\n      - method: POST\n        name: exportimage\n        description: Export an image\n        call: google-earth-engine.exportimage\n        with:\n\
  \          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/table:computeFeatures\n      name: computefeatures\n      operations:\n      - method: POST\n        name: computefeatures\n        description: Compute features\n        call: google-earth-engine.computefeatures\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/table:export\n      name: exporttable\n      operations:\n      - method: POST\n        name: exporttable\n        description: Export a table\n        call: google-earth-engine.exporttable\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/value:compute\n      name: computevalue\n      operations:\n      - method: POST\n        name: computevalue\n        description: Compute a value\n\
  \        call: google-earth-engine.computevalue\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/maps\n      name: createmap\n      operations:\n      - method: POST\n        name: createmap\n        description: Create a map\n        call: google-earth-engine.createmap\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/operations\n      name: listoperations\n      operations:\n      - method: GET\n        name: listoperations\n        description: List operations\n        call: google-earth-engine.listoperations\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n\
  \        description: Get an operation\n        call: google-earth-engine.getoperation\n        with:\n          project: rest.project\n          operationId: rest.operationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-earth-engine-mcp\n    transport: http\n    description: MCP adapter for Google Earth Engine REST API for AI agent use.\n    tools:\n    - name: listassets\n      description: List assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-earth-engine.listassets\n      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description:\
  \ pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getasset\n      description: Get an asset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-earth-engine.getasset\n      with:\n        project: tools.project\n        assetId: tools.assetId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: assetId\n        type: string\n        description: assetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteasset\n      description: Delete an asset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-earth-engine.deleteasset\n      with:\n        project: tools.project\n        assetId: tools.assetId\n      inputParameters:\n      - name: project\n        type: string\n        description:\
  \ project\n        required: true\n      - name: assetId\n        type: string\n        description: assetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: computepixels\n      description: Compute pixels\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-earth-engine.computepixels\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportimage\n      description: Export an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-earth-engine.exportimage\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: computefeatures\n      description: Compute features\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-earth-engine.computefeatures\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exporttable\n      description: Export a table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-earth-engine.exporttable\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: computevalue\n      description:\
  \ Compute a value\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-earth-engine.computevalue\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmap\n      description: Create a map\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-earth-engine.createmap\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoperations\n      description: List operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-earth-engine.listoperations\n\
  \      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description: Get an operation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-earth-engine.getoperation\n      with:\n        project: tools.project\n        operationId: tools.operationId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_EARTH_ENGINE_TOKEN: GOOGLE_EARTH_ENGINE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-earth-engine/refs/heads/main/capabilities/google-earth-engine-capability.yaml
tags:
- Google
- Earth
- Engine
- API
tools:
- description: List assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassets
- description: Get an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getasset
- description: Delete an asset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteasset
- description: Compute pixels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: computepixels
- description: Export an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportimage
- description: Compute features
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: computefeatures
- description: Export a table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exporttable
- description: Compute a value
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: computevalue
- description: Create a map
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmap
- description: List operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoperations
- description: Get an operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
---
