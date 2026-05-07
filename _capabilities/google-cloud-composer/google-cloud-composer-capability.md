---
categories: []
consumed_apis: []
description: The Cloud Composer API manages Apache Airflow environments on Google Cloud Platform. It provides methods to create, update, and delete environments, query available image versions, and monitor long-running operations.
layout: capability
name: Google Cloud Composer API
operations:
- description: Google Cloud Composer List Composer environments
  method: GET
  name: listenvironments
  path: /projects/{projectId}/locations/{location}/environments
- description: Google Cloud Composer Create a Composer environment
  method: POST
  name: createenvironment
  path: /projects/{projectId}/locations/{location}/environments
- description: Google Cloud Composer Get a Composer environment
  method: GET
  name: getenvironment
  path: /projects/{projectId}/locations/{location}/environments/{environmentId}
- description: Google Cloud Composer Update a Composer environment
  method: PATCH
  name: updateenvironment
  path: /projects/{projectId}/locations/{location}/environments/{environmentId}
- description: Google Cloud Composer Delete a Composer environment
  method: DELETE
  name: deleteenvironment
  path: /projects/{projectId}/locations/{location}/environments/{environmentId}
- description: Google Cloud Composer List image versions
  method: GET
  name: listimageversions
  path: /projects/{projectId}/locations/{location}/imageVersions
- description: Google Cloud Composer List operations
  method: GET
  name: listoperations
  path: /projects/{projectId}/locations/{location}/operations
- description: Google Cloud Composer Get an operation
  method: GET
  name: getoperation
  path: /projects/{projectId}/locations/{location}/operations/{operationId}
personas: []
provider_name: Google Cloud Composer
provider_slug: google-cloud-composer
search_terms:
- google cloud composer create a composer environment
- google cloud composer get an operation
- google cloud composer get a composer environment
- listoperations
- api
- getenvironment
- google cloud composer list image versions
- google
- createenvironment
- listimageversions
- google cloud composer delete a composer environment
- apache airflow
- google cloud composer list operations
- workflow orchestration
- composer
- getoperation
- google cloud composer update a composer environment
- google cloud composer list composer environments
- updateenvironment
- cloud
- listenvironments
- data pipelines
- deleteenvironment
- google cloud
slug: google-cloud-composer-capability
source_filename: google-cloud-composer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Composer API\n  description: The Cloud Composer API manages Apache Airflow environments on Google Cloud Platform. It provides methods to\n    create, update, and delete environments, query available image versions, and monitor long-running operations.\n  tags:\n  - Google\n  - Cloud\n  - Composer\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-composer\n    baseUri: https://composer.googleapis.com/v1\n    description: Google Cloud Composer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_COMPOSER_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-environmen\n      path: /projects/{projectId}/locations/{location}/environments\n      operations:\n      - name: listenvironments\n        method: GET\n        description: Google Cloud Composer List Composer environments\n        inputParameters:\n\
  \        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvironment\n        method: POST\n        description: Google Cloud Composer Create a Composer environment\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-environmen\n\
  \      path: /projects/{projectId}/locations/{location}/environments/{environmentId}\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Google Cloud Composer Get a Composer environment\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateenvironment\n        method: PATCH\n        description: Google Cloud Composer Update a Composer environment\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n  \
  \        required: true\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteenvironment\n        method: DELETE\n        description: Google Cloud Composer Delete a Composer environment\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-imageversi\n      path: /projects/{projectId}/locations/{location}/imageVersions\n\
  \      operations:\n      - name: listimageversions\n        method: GET\n        description: Google Cloud Composer List image versions\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations\n      operations:\n      - name: listoperations\n        method: GET\n        description: Google Cloud Composer List operations\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      operations:\n      - name: getoperation\n        method: GET\n        description: Google Cloud Composer Get an operation\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-composer-rest\n    description: REST adapter for Google Cloud Composer API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/environments\n      name: listenvironments\n      operations:\n      - method: GET\n        name: listenvironments\n        description: Google Cloud Composer List Composer environments\n        call: google-cloud-composer.listenvironments\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/environments\n      name: createenvironment\n      operations:\n      - method: POST\n        name: createenvironment\n        description: Google Cloud Composer Create a Composer environment\n        call: google-cloud-composer.createenvironment\n\
  \        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/environments/{environmentId}\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Google Cloud Composer Get a Composer environment\n        call: google-cloud-composer.getenvironment\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/environments/{environmentId}\n      name: updateenvironment\n      operations:\n      - method: PATCH\n        name: updateenvironment\n        description: Google Cloud Composer Update a Composer environment\n        call: google-cloud-composer.updateenvironment\n     \
  \   with:\n          projectId: rest.projectId\n          location: rest.location\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/environments/{environmentId}\n      name: deleteenvironment\n      operations:\n      - method: DELETE\n        name: deleteenvironment\n        description: Google Cloud Composer Delete a Composer environment\n        call: google-cloud-composer.deleteenvironment\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/imageVersions\n      name: listimageversions\n      operations:\n      - method: GET\n        name: listimageversions\n        description: Google Cloud Composer List image versions\n        call: google-cloud-composer.listimageversions\n\
  \        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations\n      name: listoperations\n      operations:\n      - method: GET\n        name: listoperations\n        description: Google Cloud Composer List operations\n        call: google-cloud-composer.listoperations\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n        description: Google Cloud Composer Get an operation\n        call: google-cloud-composer.getoperation\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          operationId: rest.operationId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-composer-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Composer API for AI agent use.\n    tools:\n    - name: listenvironments\n      description: Google Cloud Composer List Composer environments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-composer.listenvironments\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type:\
  \ string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createenvironment\n      description: Google Cloud Composer Create a Composer environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-composer.createenvironment\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvironment\n      description: Google Cloud Composer Get a Composer environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-composer.getenvironment\n      with:\n        projectId:\
  \ tools.projectId\n        location: tools.location\n        environmentId: tools.environmentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: environmentId\n        type: string\n        description: environmentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateenvironment\n      description: Google Cloud Composer Update a Composer environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-composer.updateenvironment\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        environmentId: tools.environmentId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description:\
  \ projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: environmentId\n        type: string\n        description: environmentId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteenvironment\n      description: Google Cloud Composer Delete a Composer environment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-composer.deleteenvironment\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        environmentId: tools.environmentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n\
  \      - name: environmentId\n        type: string\n        description: environmentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listimageversions\n      description: Google Cloud Composer List image versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-composer.listimageversions\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listoperations\n      description: Google Cloud Composer List operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-composer.listoperations\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description: Google Cloud Composer Get an operation\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-cloud-composer.getoperation\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        operationId: tools.operationId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_COMPOSER_TOKEN: GOOGLE_CLOUD_COMPOSER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-composer/refs/heads/main/capabilities/google-cloud-composer-capability.yaml
tags:
- Google
- Cloud
- Composer
- API
tools:
- description: Google Cloud Composer List Composer environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
- description: Google Cloud Composer Create a Composer environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironment
- description: Google Cloud Composer Get a Composer environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Google Cloud Composer Update a Composer environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateenvironment
- description: Google Cloud Composer Delete a Composer environment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvironment
- description: Google Cloud Composer List image versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listimageversions
- description: Google Cloud Composer List operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoperations
- description: Google Cloud Composer Get an operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
---
