---
categories: []
consumed_apis: []
description: The Cloud Data Fusion API provides programmatic access to create, manage, and monitor Data Fusion instances on Google Cloud Platform. It supports instance lifecycle management, namespace operations, and pipeline configuration.
layout: capability
name: Google Cloud Data Fusion API
operations:
- description: Google Cloud Data Fusion List available locations
  method: GET
  name: listlocations
  path: /projects/{projectId}/locations
- description: Google Cloud Data Fusion List Data Fusion instances
  method: GET
  name: listinstances
  path: /projects/{projectId}/locations/{location}/instances
- description: Google Cloud Data Fusion Create a Data Fusion instance
  method: POST
  name: createinstance
  path: /projects/{projectId}/locations/{location}/instances
- description: Google Cloud Data Fusion Get a Data Fusion instance
  method: GET
  name: getinstance
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}
- description: Google Cloud Data Fusion Update a Data Fusion instance
  method: PATCH
  name: updateinstance
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}
- description: Google Cloud Data Fusion Delete a Data Fusion instance
  method: DELETE
  name: deleteinstance
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}
- description: Google Cloud Data Fusion Restart a Data Fusion instance
  method: POST
  name: restartinstance
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}:restart
- description: Google Cloud Data Fusion List operations
  method: GET
  name: listoperations
  path: /projects/{projectId}/locations/{location}/operations
- description: Google Cloud Data Fusion Get an operation
  method: GET
  name: getoperation
  path: /projects/{projectId}/locations/{location}/operations/{operationId}
personas: []
provider_name: Google Cloud Data Fusion
provider_slug: google-cloud-data-fusion
search_terms:
- listlocations
- google cloud data fusion get a data fusion instance
- google cloud data fusion restart a data fusion instance
- updateinstance
- restartinstance
- google cloud data fusion delete a data fusion instance
- createinstance
- listoperations
- api
- google cloud data fusion create a data fusion instance
- google cloud data fusion list data fusion instances
- fusion
- deleteinstance
- google
- getinstance
- google cloud data fusion list available locations
- google cloud data fusion update a data fusion instance
- getoperation
- cloud
- data pipelines
- google cloud data fusion list operations
- etl
- data
- data integration
- google cloud
- listinstances
- google cloud data fusion get an operation
slug: google-cloud-data-fusion-capability
source_filename: google-cloud-data-fusion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Data Fusion API\n  description: The Cloud Data Fusion API provides programmatic access to create, manage, and monitor Data Fusion instances\n    on Google Cloud Platform. It supports instance lifecycle management, namespace operations, and pipeline configuration.\n  tags:\n  - Google\n  - Cloud\n  - Data\n  - Fusion\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-data-fusion\n    baseUri: https://datafusion.googleapis.com/v1\n    description: Google Cloud Data Fusion API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DATA_FUSION_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations\n      path: /projects/{projectId}/locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: Google Cloud Data Fusion List available locations\n        inputParameters:\n   \
  \     - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The project ID.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances\n      path: /projects/{projectId}/locations/{location}/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: Google Cloud Data Fusion List Data Fusion instances\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The project ID.\n        - name: location\n          in: path\n  \
  \        type: string\n          required: true\n          description: The location (region).\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of instances to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Google Cloud Data Fusion Create a Data Fusion instance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: query\n          type: string\n          required: true\n          description: The name of the instance to create.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}\n      operations:\n      - name: getinstance\n        method: GET\n        description: Google Cloud Data Fusion Get a Data Fusion instance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n        method: PATCH\n        description: Google Cloud Data Fusion Update a Data Fusion instance\n        inputParameters:\n        - name:\
  \ projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n          description: Field mask for update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Google Cloud Data Fusion Delete a Data Fusion instance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}:restart\n      operations:\n      - name: restartinstance\n        method: POST\n        description: Google Cloud Data Fusion Restart a Data Fusion instance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations\n      operations:\n      - name:\
  \ listoperations\n        method: GET\n        description: Google Cloud Data Fusion List operations\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      operations:\n      - name: getoperation\n        method: GET\n        description: Google Cloud Data Fusion Get an operation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        -\
  \ name: location\n          in: path\n          type: string\n          required: true\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-data-fusion-rest\n    description: REST adapter for Google Cloud Data Fusion API.\n    resources:\n    - path: /projects/{projectId}/locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: Google Cloud Data Fusion List available locations\n        call: google-cloud-data-fusion.listlocations\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances\n      name: listinstances\n      operations:\n      - method:\
  \ GET\n        name: listinstances\n        description: Google Cloud Data Fusion List Data Fusion instances\n        call: google-cloud-data-fusion.listinstances\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Google Cloud Data Fusion Create a Data Fusion instance\n        call: google-cloud-data-fusion.createinstance\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Google Cloud Data Fusion\
  \ Get a Data Fusion instance\n        call: google-cloud-data-fusion.getinstance\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}\n      name: updateinstance\n      operations:\n      - method: PATCH\n        name: updateinstance\n        description: Google Cloud Data Fusion Update a Data Fusion instance\n        call: google-cloud-data-fusion.updateinstance\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Google\
  \ Cloud Data Fusion Delete a Data Fusion instance\n        call: google-cloud-data-fusion.deleteinstance\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}:restart\n      name: restartinstance\n      operations:\n      - method: POST\n        name: restartinstance\n        description: Google Cloud Data Fusion Restart a Data Fusion instance\n        call: google-cloud-data-fusion.restartinstance\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations\n      name: listoperations\n      operations:\n      - method: GET\n        name: listoperations\n      \
  \  description: Google Cloud Data Fusion List operations\n        call: google-cloud-data-fusion.listoperations\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n        description: Google Cloud Data Fusion Get an operation\n        call: google-cloud-data-fusion.getoperation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          operationId: rest.operationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-data-fusion-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Data Fusion API for AI agent use.\n    tools:\n    - name: listlocations\n      description:\
  \ Google Cloud Data Fusion List available locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-fusion.listlocations\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: The project ID.\n        required: true\n      - name: pageSize\n        type: integer\n        description: Maximum number of results to return.\n      - name: pageToken\n        type: string\n        description: Page token for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstances\n      description: Google Cloud Data Fusion List Data Fusion instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-fusion.listinstances\n      with:\n        projectId: tools.projectId\n\
  \        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: The project ID.\n        required: true\n      - name: location\n        type: string\n        description: The location (region).\n        required: true\n      - name: pageSize\n        type: integer\n        description: Maximum number of instances to return.\n      - name: pageToken\n        type: string\n        description: Page token for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Google Cloud Data Fusion Create a Data Fusion instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-fusion.createinstance\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        instanceId: tools.instanceId\n   \
  \   inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instanceId\n        type: string\n        description: The name of the instance to create.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Google Cloud Data Fusion Get a Data Fusion instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-fusion.getinstance\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required:\
  \ true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstance\n      description: Google Cloud Data Fusion Update a Data Fusion instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-fusion.updateinstance\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        instanceId: tools.instanceId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: updateMask\n        type: string\n        description: Field mask\
  \ for update.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Google Cloud Data Fusion Delete a Data Fusion instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-data-fusion.deleteinstance\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartinstance\n      description: Google Cloud Data Fusion Restart a Data Fusion instance\n      hints:\n        readOnly: false\n  \
  \      destructive: false\n        idempotent: false\n      call: google-cloud-data-fusion.restartinstance\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoperations\n      description: Google Cloud Data Fusion List operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-fusion.listoperations\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken:\
  \ tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description: Google Cloud Data Fusion Get an operation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-fusion.getoperation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        operationId: tools.operationId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n\
  \        description: location\n        required: true\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_DATA_FUSION_TOKEN: GOOGLE_CLOUD_DATA_FUSION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-data-fusion/refs/heads/main/capabilities/google-cloud-data-fusion-capability.yaml
tags:
- Google
- Cloud
- Data
- Fusion
- API
tools:
- description: Google Cloud Data Fusion List available locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: Google Cloud Data Fusion List Data Fusion instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Google Cloud Data Fusion Create a Data Fusion instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Google Cloud Data Fusion Get a Data Fusion instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Google Cloud Data Fusion Update a Data Fusion instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateinstance
- description: Google Cloud Data Fusion Delete a Data Fusion instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Google Cloud Data Fusion Restart a Data Fusion instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartinstance
- description: Google Cloud Data Fusion List operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoperations
- description: Google Cloud Data Fusion Get an operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
---
