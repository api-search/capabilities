---
categories: []
consumed_apis: []
description: The Datastream API enables serverless change data capture and replication across heterogeneous databases and storage systems. It provides methods to manage connection profiles, streams, and private connections.
layout: capability
name: Google Cloud Datastream API
operations:
- description: Google Cloud Datastream List connection profiles
  method: GET
  name: listconnectionprofiles
  path: /projects/{projectId}/locations/{location}/connectionProfiles
- description: Google Cloud Datastream Create a connection profile
  method: POST
  name: createconnectionprofile
  path: /projects/{projectId}/locations/{location}/connectionProfiles
- description: Google Cloud Datastream Get a connection profile
  method: GET
  name: getconnectionprofile
  path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}
- description: Google Cloud Datastream Update a connection profile
  method: PATCH
  name: updateconnectionprofile
  path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}
- description: Google Cloud Datastream Delete a connection profile
  method: DELETE
  name: deleteconnectionprofile
  path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}
- description: Google Cloud Datastream List streams
  method: GET
  name: liststreams
  path: /projects/{projectId}/locations/{location}/streams
- description: Google Cloud Datastream Create a stream
  method: POST
  name: createstream
  path: /projects/{projectId}/locations/{location}/streams
- description: Google Cloud Datastream Get a stream
  method: GET
  name: getstream
  path: /projects/{projectId}/locations/{location}/streams/{streamId}
- description: Google Cloud Datastream Update a stream
  method: PATCH
  name: updatestream
  path: /projects/{projectId}/locations/{location}/streams/{streamId}
- description: Google Cloud Datastream Delete a stream
  method: DELETE
  name: deletestream
  path: /projects/{projectId}/locations/{location}/streams/{streamId}
- description: Google Cloud Datastream Get an operation
  method: GET
  name: getoperation
  path: /projects/{projectId}/locations/{location}/operations/{operationId}
personas: []
provider_name: Google Cloud Datastream
provider_slug: google-cloud-datastream
search_terms:
- google cloud datastream create a stream
- deletestream
- listconnectionprofiles
- liststreams
- google cloud datastream delete a stream
- google cloud datastream update a connection profile
- datastream
- cloud
- google cloud datastream list connection profiles
- google
- updatestream
- google cloud datastream create a connection profile
- getstream
- createstream
- google cloud datastream delete a connection profile
- google cloud datastream update a stream
- api
- createconnectionprofile
- data replication
- getoperation
- google cloud datastream get a connection profile
- google cloud datastream get an operation
- streaming
- getconnectionprofile
- google cloud datastream get a stream
- deleteconnectionprofile
- google cloud
- updateconnectionprofile
- change data capture
- google cloud datastream list streams
slug: google-cloud-datastream-capability
source_filename: google-cloud-datastream-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Datastream API\n  description: The Datastream API enables serverless change data capture and replication across heterogeneous databases and\n    storage systems. It provides methods to manage connection profiles, streams, and private connections.\n  tags:\n  - Google\n  - Cloud\n  - Datastream\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-datastream\n    baseUri: https://datastream.googleapis.com/v1\n    description: Google Cloud Datastream API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DATASTREAM_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-connection\n      path: /projects/{projectId}/locations/{location}/connectionProfiles\n      operations:\n      - name: listconnectionprofiles\n        method: GET\n        description: Google Cloud Datastream List connection profiles\n\
  \        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconnectionprofile\n        method: POST\n        description: Google Cloud Datastream Create a connection profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name:\
  \ connectionProfileId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-connection\n      path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}\n      operations:\n      - name: getconnectionprofile\n        method: GET\n        description: Google Cloud Datastream Get a connection profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: connectionProfileId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateconnectionprofile\n\
  \        method: PATCH\n        description: Google Cloud Datastream Update a connection profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: connectionProfileId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconnectionprofile\n        method: DELETE\n        description: Google Cloud Datastream Delete a connection profile\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: connectionProfileId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-streams\n      path: /projects/{projectId}/locations/{location}/streams\n      operations:\n      - name: liststreams\n        method: GET\n        description: Google Cloud Datastream List streams\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createstream\n        method: POST\n        description: Google Cloud Datastream Create a stream\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: streamId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-streams-st\n      path: /projects/{projectId}/locations/{location}/streams/{streamId}\n      operations:\n      - name: getstream\n        method: GET\n        description: Google Cloud Datastream Get a stream\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: streamId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatestream\n        method: PATCH\n        description: Google Cloud Datastream Update a stream\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: streamId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletestream\n        method: DELETE\n\
  \        description: Google Cloud Datastream Delete a stream\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: streamId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      operations:\n      - name: getoperation\n        method: GET\n        description: Google Cloud Datastream Get an operation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n \
  \       - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-datastream-rest\n    description: REST adapter for Google Cloud Datastream API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/connectionProfiles\n      name: listconnectionprofiles\n      operations:\n      - method: GET\n        name: listconnectionprofiles\n        description: Google Cloud Datastream List connection profiles\n        call: google-cloud-datastream.listconnectionprofiles\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/connectionProfiles\n      name: createconnectionprofile\n      operations:\n\
  \      - method: POST\n        name: createconnectionprofile\n        description: Google Cloud Datastream Create a connection profile\n        call: google-cloud-datastream.createconnectionprofile\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}\n      name: getconnectionprofile\n      operations:\n      - method: GET\n        name: getconnectionprofile\n        description: Google Cloud Datastream Get a connection profile\n        call: google-cloud-datastream.getconnectionprofile\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          connectionProfileId: rest.connectionProfileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}\n\
  \      name: updateconnectionprofile\n      operations:\n      - method: PATCH\n        name: updateconnectionprofile\n        description: Google Cloud Datastream Update a connection profile\n        call: google-cloud-datastream.updateconnectionprofile\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          connectionProfileId: rest.connectionProfileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/connectionProfiles/{connectionProfileId}\n      name: deleteconnectionprofile\n      operations:\n      - method: DELETE\n        name: deleteconnectionprofile\n        description: Google Cloud Datastream Delete a connection profile\n        call: google-cloud-datastream.deleteconnectionprofile\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          connectionProfileId: rest.connectionProfileId\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/streams\n      name: liststreams\n      operations:\n      - method: GET\n        name: liststreams\n        description: Google Cloud Datastream List streams\n        call: google-cloud-datastream.liststreams\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/streams\n      name: createstream\n      operations:\n      - method: POST\n        name: createstream\n        description: Google Cloud Datastream Create a stream\n        call: google-cloud-datastream.createstream\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/streams/{streamId}\n      name: getstream\n\
  \      operations:\n      - method: GET\n        name: getstream\n        description: Google Cloud Datastream Get a stream\n        call: google-cloud-datastream.getstream\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          streamId: rest.streamId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/streams/{streamId}\n      name: updatestream\n      operations:\n      - method: PATCH\n        name: updatestream\n        description: Google Cloud Datastream Update a stream\n        call: google-cloud-datastream.updatestream\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          streamId: rest.streamId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/streams/{streamId}\n      name: deletestream\n      operations:\n      - method: DELETE\n    \
  \    name: deletestream\n        description: Google Cloud Datastream Delete a stream\n        call: google-cloud-datastream.deletestream\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          streamId: rest.streamId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n        description: Google Cloud Datastream Get an operation\n        call: google-cloud-datastream.getoperation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          operationId: rest.operationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-datastream-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Datastream API for AI agent use.\n\
  \    tools:\n    - name: listconnectionprofiles\n      description: Google Cloud Datastream List connection profiles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-datastream.listconnectionprofiles\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      - name: orderBy\n        type: string\n        description:\
  \ orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconnectionprofile\n      description: Google Cloud Datastream Create a connection profile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-datastream.createconnectionprofile\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        connectionProfileId: tools.connectionProfileId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: connectionProfileId\n        type: string\n        description: connectionProfileId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconnectionprofile\n      description: Google Cloud Datastream Get a connection profile\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-datastream.getconnectionprofile\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        connectionProfileId: tools.connectionProfileId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: connectionProfileId\n        type: string\n        description: connectionProfileId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateconnectionprofile\n      description: Google Cloud Datastream Update a connection profile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-datastream.updateconnectionprofile\n      with:\n        projectId:\
  \ tools.projectId\n        location: tools.location\n        connectionProfileId: tools.connectionProfileId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: connectionProfileId\n        type: string\n        description: connectionProfileId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteconnectionprofile\n      description: Google Cloud Datastream Delete a connection profile\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-datastream.deleteconnectionprofile\n      with:\n        projectId: tools.projectId\n        location: tools.location\n       \
  \ connectionProfileId: tools.connectionProfileId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: connectionProfileId\n        type: string\n        description: connectionProfileId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststreams\n      description: Google Cloud Datastream List streams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-datastream.liststreams\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n\
  \        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createstream\n      description: Google Cloud Datastream Create a stream\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-datastream.createstream\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        streamId: tools.streamId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n  \
  \      type: string\n        description: location\n        required: true\n      - name: streamId\n        type: string\n        description: streamId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstream\n      description: Google Cloud Datastream Get a stream\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-datastream.getstream\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        streamId: tools.streamId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: streamId\n        type: string\n        description: streamId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatestream\n\
  \      description: Google Cloud Datastream Update a stream\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-datastream.updatestream\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        streamId: tools.streamId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: streamId\n        type: string\n        description: streamId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletestream\n      description: Google Cloud Datastream Delete a stream\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: google-cloud-datastream.deletestream\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        streamId: tools.streamId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: streamId\n        type: string\n        description: streamId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description: Google Cloud Datastream Get an operation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-datastream.getoperation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        operationId: tools.operationId\n      inputParameters:\n      - name: projectId\n        type: string\n    \
  \    description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_DATASTREAM_TOKEN: GOOGLE_CLOUD_DATASTREAM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-datastream/refs/heads/main/capabilities/google-cloud-datastream-capability.yaml
tags:
- Google
- Cloud
- Datastream
- API
tools:
- description: Google Cloud Datastream List connection profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectionprofiles
- description: Google Cloud Datastream Create a connection profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnectionprofile
- description: Google Cloud Datastream Get a connection profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectionprofile
- description: Google Cloud Datastream Update a connection profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateconnectionprofile
- description: Google Cloud Datastream Delete a connection profile
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconnectionprofile
- description: Google Cloud Datastream List streams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststreams
- description: Google Cloud Datastream Create a stream
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstream
- description: Google Cloud Datastream Get a stream
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstream
- description: Google Cloud Datastream Update a stream
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatestream
- description: Google Cloud Datastream Delete a stream
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletestream
- description: Google Cloud Datastream Get an operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
---
