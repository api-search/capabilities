---
categories: []
consumed_apis: []
description: The Cloud Functions API manages lightweight user-provided functions executed in response to events. It supports creating, updating, deleting, and listing functions, as well as managing their runtimes, build configurations, and triggers.
layout: capability
name: Google Cloud Functions API
operations:
- description: Google Cloud Functions List available locations
  method: GET
  name: listlocations
  path: /projects/{projectId}/locations
- description: Google Cloud Functions List functions
  method: GET
  name: listfunctions
  path: /projects/{projectId}/locations/{location}/functions
- description: Google Cloud Functions Create a function
  method: POST
  name: createfunction
  path: /projects/{projectId}/locations/{location}/functions
- description: Google Cloud Functions Get a function
  method: GET
  name: getfunction
  path: /projects/{projectId}/locations/{location}/functions/{functionId}
- description: Google Cloud Functions Update a function
  method: PATCH
  name: updatefunction
  path: /projects/{projectId}/locations/{location}/functions/{functionId}
- description: Google Cloud Functions Delete a function
  method: DELETE
  name: deletefunction
  path: /projects/{projectId}/locations/{location}/functions/{functionId}
- description: Google Cloud Functions List runtimes
  method: GET
  name: listruntimes
  path: /projects/{projectId}/locations/{location}/runtimes
- description: Google Cloud Functions Generate upload URL
  method: POST
  name: generateuploadurl
  path: /projects/{projectId}/locations/{location}/functions/{functionId}:generateUploadUrl
- description: Google Cloud Functions Get an operation
  method: GET
  name: getoperation
  path: /projects/{projectId}/locations/{location}/operations/{operationId}
personas: []
provider_name: Google Cloud Functions
provider_slug: google-cloud-functions
search_terms:
- listlocations
- google cloud functions get a function
- event-driven
- google cloud functions list available locations
- deletefunction
- api
- generateuploadurl
- createfunction
- getfunction
- google
- google cloud functions create a function
- listfunctions
- listruntimes
- serverless
- getoperation
- google cloud functions list functions
- cloud
- updatefunction
- google cloud functions get an operation
- google cloud functions delete a function
- google cloud functions list runtimes
- google cloud functions generate upload url
- google cloud functions update a function
- google cloud
- functions
slug: google-cloud-functions-capability
source_filename: google-cloud-functions-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Functions API\n  description: The Cloud Functions API manages lightweight user-provided functions executed in response to events. It supports\n    creating, updating, deleting, and listing functions, as well as managing their runtimes, build configurations, and triggers.\n  tags:\n  - Google\n  - Cloud\n  - Functions\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-functions\n    baseUri: https://cloudfunctions.googleapis.com/v2\n    description: Google Cloud Functions API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_FUNCTIONS_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations\n      path: /projects/{projectId}/locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: Google Cloud Functions List available locations\n        inputParameters:\n      \
  \  - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-functions\n      path: /projects/{projectId}/locations/{location}/functions\n      operations:\n      - name: listfunctions\n        method: GET\n        description: Google Cloud Functions List functions\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n\
  \          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfunction\n        method: POST\n        description: Google Cloud Functions Create a function\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: functionId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-functions-\n      path: /projects/{projectId}/locations/{location}/functions/{functionId}\n      operations:\n      - name: getfunction\n        method: GET\n        description:\
  \ Google Cloud Functions Get a function\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: functionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefunction\n        method: PATCH\n        description: Google Cloud Functions Update a function\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: functionId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefunction\n        method: DELETE\n        description: Google Cloud Functions Delete a function\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: functionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-runtimes\n      path: /projects/{projectId}/locations/{location}/runtimes\n      operations:\n      - name: listruntimes\n        method: GET\n        description: Google Cloud Functions List runtimes\n        inputParameters:\n        - name: projectId\n          in: path\n         \
  \ type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-functions-\n      path: /projects/{projectId}/locations/{location}/functions/{functionId}:generateUploadUrl\n      operations:\n      - name: generateuploadurl\n        method: POST\n        description: Google Cloud Functions Generate upload URL\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: functionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      operations:\n      - name: getoperation\n        method: GET\n        description: Google Cloud Functions Get an operation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-functions-rest\n    description: REST adapter for Google Cloud Functions API.\n    resources:\n    - path: /projects/{projectId}/locations\n\
  \      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: Google Cloud Functions List available locations\n        call: google-cloud-functions.listlocations\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/functions\n      name: listfunctions\n      operations:\n      - method: GET\n        name: listfunctions\n        description: Google Cloud Functions List functions\n        call: google-cloud-functions.listfunctions\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/functions\n      name: createfunction\n      operations:\n      - method: POST\n        name: createfunction\n        description: Google Cloud Functions Create a function\n\
  \        call: google-cloud-functions.createfunction\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/functions/{functionId}\n      name: getfunction\n      operations:\n      - method: GET\n        name: getfunction\n        description: Google Cloud Functions Get a function\n        call: google-cloud-functions.getfunction\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          functionId: rest.functionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/functions/{functionId}\n      name: updatefunction\n      operations:\n      - method: PATCH\n        name: updatefunction\n        description: Google Cloud Functions Update a function\n        call: google-cloud-functions.updatefunction\n        with:\n\
  \          projectId: rest.projectId\n          location: rest.location\n          functionId: rest.functionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/functions/{functionId}\n      name: deletefunction\n      operations:\n      - method: DELETE\n        name: deletefunction\n        description: Google Cloud Functions Delete a function\n        call: google-cloud-functions.deletefunction\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          functionId: rest.functionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/runtimes\n      name: listruntimes\n      operations:\n      - method: GET\n        name: listruntimes\n        description: Google Cloud Functions List runtimes\n        call: google-cloud-functions.listruntimes\n        with:\n          projectId: rest.projectId\n\
  \          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/functions/{functionId}:generateUploadUrl\n      name: generateuploadurl\n      operations:\n      - method: POST\n        name: generateuploadurl\n        description: Google Cloud Functions Generate upload URL\n        call: google-cloud-functions.generateuploadurl\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          functionId: rest.functionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n        description: Google Cloud Functions Get an operation\n        call: google-cloud-functions.getoperation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n\
  \          operationId: rest.operationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-functions-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Functions API for AI agent use.\n    tools:\n    - name: listlocations\n      description: Google Cloud Functions List available locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-functions.listlocations\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listfunctions\n      description: Google Cloud Functions List functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-functions.listfunctions\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createfunction\n      description: Google Cloud Functions Create a function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-functions.createfunction\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        functionId: tools.functionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: functionId\n        type: string\n        description: functionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfunction\n      description: Google Cloud Functions Get a function\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-functions.getfunction\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n        functionId: tools.functionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: functionId\n        type: string\n        description: functionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefunction\n      description: Google Cloud Functions Update a function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-functions.updatefunction\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        functionId: tools.functionId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description:\
  \ projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: functionId\n        type: string\n        description: functionId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefunction\n      description: Google Cloud Functions Delete a function\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-functions.deletefunction\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        functionId: tools.functionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: functionId\n\
  \        type: string\n        description: functionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listruntimes\n      description: Google Cloud Functions List runtimes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-functions.listruntimes\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        filter: tools.filter\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateuploadurl\n      description: Google Cloud Functions Generate upload URL\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: google-cloud-functions.generateuploadurl\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        functionId: tools.functionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: functionId\n        type: string\n        description: functionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description: Google Cloud Functions Get an operation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-functions.getoperation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        operationId: tools.operationId\n      inputParameters:\n      - name:\
  \ projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_FUNCTIONS_TOKEN: GOOGLE_CLOUD_FUNCTIONS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-functions/refs/heads/main/capabilities/google-cloud-functions-capability.yaml
tags:
- Google
- Cloud
- Functions
- API
tools:
- description: Google Cloud Functions List available locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: Google Cloud Functions List functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfunctions
- description: Google Cloud Functions Create a function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfunction
- description: Google Cloud Functions Get a function
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfunction
- description: Google Cloud Functions Update a function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefunction
- description: Google Cloud Functions Delete a function
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefunction
- description: Google Cloud Functions List runtimes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listruntimes
- description: Google Cloud Functions Generate upload URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateuploadurl
- description: Google Cloud Functions Get an operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
---
