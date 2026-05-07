---
categories: []
consumed_apis: []
description: The Google Fit REST API enables you to store and access health and wellness data in the fitness store. You can manage data sources, datasets, sessions, and aggregate fitness data from apps on any platform.
layout: capability
name: Google Fit REST API
operations:
- description: List data sources
  method: GET
  name: listdatasources
  path: /users/{userId}/dataSources
- description: Create a data source
  method: POST
  name: createdatasource
  path: /users/{userId}/dataSources
- description: Get a data source
  method: GET
  name: getdatasource
  path: /users/{userId}/dataSources/{dataSourceId}
- description: Get a dataset
  method: GET
  name: getdataset
  path: /users/{userId}/dataSources/{dataSourceId}/datasets/{datasetId}
- description: Add data points to a dataset
  method: PATCH
  name: patchdataset
  path: /users/{userId}/dataSources/{dataSourceId}/datasets/{datasetId}
- description: Aggregate data
  method: POST
  name: aggregatedataset
  path: /users/{userId}/dataset:aggregate
- description: List sessions
  method: GET
  name: listsessions
  path: /users/{userId}/sessions
- description: Update or insert a session
  method: PUT
  name: updatesession
  path: /users/{userId}/sessions/{sessionId}
- description: Delete a session
  method: DELETE
  name: deletesession
  path: /users/{userId}/sessions/{sessionId}
personas: []
provider_name: Google Fit REST
provider_slug: google-fitness
search_terms:
- listdatasources
- listsessions
- sessions
- patchdataset
- delete a session
- get a dataset
- aggregate data
- deletesession
- api
- getdataset
- health
- wellness
- google
- fitness
- add data points to a dataset
- create a data source
- updatesession
- list sessions
- update or insert a session
- createdatasource
- getdatasource
- list data sources
- aggregatedataset
- activity tracking
- get a data source
- wearables
slug: google-fitness-capability
source_filename: google-fitness-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Fit REST API\n  description: The Google Fit REST API enables you to store and access health and wellness data in the fitness store. You\n    can manage data sources, datasets, sessions, and aggregate fitness data from apps on any platform.\n  tags:\n  - Google\n  - Fitness\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-fitness\n    baseUri: https://www.googleapis.com/fitness/v1\n    description: Google Fit REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_FITNESS_TOKEN}}'\n    resources:\n    - name: users-userid-datasources\n      path: /users/{userId}/dataSources\n      operations:\n      - name: listdatasources\n        method: GET\n        description: List data sources\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatasource\n        method: POST\n        description: Create a data source\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-datasources-datasourceid\n      path: /users/{userId}/dataSources/{dataSourceId}\n      operations:\n      - name: getdatasource\n        method: GET\n        description: Get a data source\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: dataSourceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: users-userid-datasources-datasourceid-datasets-d\n      path: /users/{userId}/dataSources/{dataSourceId}/datasets/{datasetId}\n      operations:\n      - name: getdataset\n        method: GET\n        description: Get a dataset\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: dataSourceId\n          in: path\n          type: string\n          required: true\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdataset\n        method: PATCH\n        description: Add data points to a dataset\n        inputParameters:\n        - name: userId\n          in: path\n\
  \          type: string\n          required: true\n        - name: dataSourceId\n          in: path\n          type: string\n          required: true\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-dataset-aggregate\n      path: /users/{userId}/dataset:aggregate\n      operations:\n      - name: aggregatedataset\n        method: POST\n        description: Aggregate data\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-sessions\n      path: /users/{userId}/sessions\n      operations:\n      - name: listsessions\n        method: GET\n        description: List sessions\n\
  \        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-sessions-sessionid\n      path: /users/{userId}/sessions/{sessionId}\n      operations:\n      - name: updatesession\n        method: PUT\n        description: Update or insert a session\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: deletesession\n        method: DELETE\n        description: Delete a session\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-fitness-rest\n    description: REST adapter for Google Fit REST API.\n    resources:\n    - path: /users/{userId}/dataSources\n      name: listdatasources\n      operations:\n      - method: GET\n        name: listdatasources\n        description: List data sources\n        call: google-fitness.listdatasources\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/dataSources\n  \
  \    name: createdatasource\n      operations:\n      - method: POST\n        name: createdatasource\n        description: Create a data source\n        call: google-fitness.createdatasource\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/dataSources/{dataSourceId}\n      name: getdatasource\n      operations:\n      - method: GET\n        name: getdatasource\n        description: Get a data source\n        call: google-fitness.getdatasource\n        with:\n          userId: rest.userId\n          dataSourceId: rest.dataSourceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/dataSources/{dataSourceId}/datasets/{datasetId}\n      name: getdataset\n      operations:\n      - method: GET\n        name: getdataset\n        description: Get a dataset\n        call: google-fitness.getdataset\n        with:\n          userId: rest.userId\n\
  \          dataSourceId: rest.dataSourceId\n          datasetId: rest.datasetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/dataSources/{dataSourceId}/datasets/{datasetId}\n      name: patchdataset\n      operations:\n      - method: PATCH\n        name: patchdataset\n        description: Add data points to a dataset\n        call: google-fitness.patchdataset\n        with:\n          userId: rest.userId\n          dataSourceId: rest.dataSourceId\n          datasetId: rest.datasetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/dataset:aggregate\n      name: aggregatedataset\n      operations:\n      - method: POST\n        name: aggregatedataset\n        description: Aggregate data\n        call: google-fitness.aggregatedataset\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sessions\n\
  \      name: listsessions\n      operations:\n      - method: GET\n        name: listsessions\n        description: List sessions\n        call: google-fitness.listsessions\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sessions/{sessionId}\n      name: updatesession\n      operations:\n      - method: PUT\n        name: updatesession\n        description: Update or insert a session\n        call: google-fitness.updatesession\n        with:\n          userId: rest.userId\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/sessions/{sessionId}\n      name: deletesession\n      operations:\n      - method: DELETE\n        name: deletesession\n        description: Delete a session\n        call: google-fitness.deletesession\n        with:\n          userId: rest.userId\n          sessionId: rest.sessionId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-fitness-mcp\n    transport: http\n    description: MCP adapter for Google Fit REST API for AI agent use.\n    tools:\n    - name: listdatasources\n      description: List data sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-fitness.listdatasources\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatasource\n      description: Create a data source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-fitness.createdatasource\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n\
  \        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatasource\n      description: Get a data source\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-fitness.getdatasource\n      with:\n        userId: tools.userId\n        dataSourceId: tools.dataSourceId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: dataSourceId\n        type: string\n        description: dataSourceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdataset\n      description: Get a dataset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-fitness.getdataset\n      with:\n        userId: tools.userId\n        dataSourceId: tools.dataSourceId\n        datasetId: tools.datasetId\n\
  \        limit: tools.limit\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: dataSourceId\n        type: string\n        description: dataSourceId\n        required: true\n      - name: datasetId\n        type: string\n        description: datasetId\n        required: true\n      - name: limit\n        type: integer\n        description: limit\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchdataset\n      description: Add data points to a dataset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-fitness.patchdataset\n      with:\n        userId: tools.userId\n        dataSourceId: tools.dataSourceId\n        datasetId: tools.datasetId\n      inputParameters:\n      - name: userId\n     \
  \   type: string\n        description: userId\n        required: true\n      - name: dataSourceId\n        type: string\n        description: dataSourceId\n        required: true\n      - name: datasetId\n        type: string\n        description: datasetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aggregatedataset\n      description: Aggregate data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-fitness.aggregatedataset\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsessions\n      description: List sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-fitness.listsessions\n      with:\n      \
  \  userId: tools.userId\n        startTime: tools.startTime\n        endTime: tools.endTime\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: startTime\n        type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesession\n      description: Update or insert a session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-fitness.updatesession\n      with:\n        userId: tools.userId\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: sessionId\n        type: string\n\
  \        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesession\n      description: Delete a session\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-fitness.deletesession\n      with:\n        userId: tools.userId\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_FITNESS_TOKEN: GOOGLE_FITNESS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-fitness/refs/heads/main/capabilities/google-fitness-capability.yaml
tags:
- Google
- Fitness
- API
tools:
- description: List data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasources
- description: Create a data source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatasource
- description: Get a data source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasource
- description: Get a dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataset
- description: Add data points to a dataset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdataset
- description: Aggregate data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: aggregatedataset
- description: List sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessions
- description: Update or insert a session
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesession
- description: Delete a session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesession
---
