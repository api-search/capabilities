---
categories: []
consumed_apis: []
description: The Cloud Build API provides programmatic access to create, manage, and monitor builds on Google Cloud infrastructure. It supports build triggers, worker pools, source repository connections, and build configuration management for CI/CD workflows.
layout: capability
name: Google Cloud Build API
operations:
- description: Google Cloud Build List builds
  method: GET
  name: listbuilds
  path: /projects/{projectId}/builds
- description: Google Cloud Build Create a build
  method: POST
  name: createbuild
  path: /projects/{projectId}/builds
- description: Google Cloud Build Get a build
  method: GET
  name: getbuild
  path: /projects/{projectId}/builds/{buildId}
- description: Google Cloud Build Cancel a build
  method: POST
  name: cancelbuild
  path: /projects/{projectId}/builds/{buildId}:cancel
- description: Google Cloud Build List build triggers
  method: GET
  name: listtriggers
  path: /projects/{projectId}/triggers
- description: Google Cloud Build Create a build trigger
  method: POST
  name: createtrigger
  path: /projects/{projectId}/triggers
- description: Google Cloud Build Get a build trigger
  method: GET
  name: gettrigger
  path: /projects/{projectId}/triggers/{triggerId}
- description: Google Cloud Build Update a build trigger
  method: PATCH
  name: updatetrigger
  path: /projects/{projectId}/triggers/{triggerId}
- description: Google Cloud Build Delete a build trigger
  method: DELETE
  name: deletetrigger
  path: /projects/{projectId}/triggers/{triggerId}
- description: Google Cloud Build List worker pools
  method: GET
  name: listworkerpools
  path: /projects/{projectId}/locations/{location}/workerPools
- description: Google Cloud Build Create a worker pool
  method: POST
  name: createworkerpool
  path: /projects/{projectId}/locations/{location}/workerPools
personas: []
provider_name: Google Cloud Build
provider_slug: google-cloud-build
search_terms:
- google cloud build cancel a build
- google cloud build create a build trigger
- devops
- getbuild
- google cloud build create a worker pool
- google cloud build list build triggers
- cloud
- google cloud build get a build
- google
- build
- google cloud build list worker pools
- google cloud build create a build
- createbuild
- deletetrigger
- continuous integration
- google cloud build update a build trigger
- google cloud build list builds
- ci/cd
- api
- listtriggers
- createtrigger
- createworkerpool
- container build
- cancelbuild
- google cloud build get a build trigger
- updatetrigger
- google cloud build delete a build trigger
- listbuilds
- build automation
- continuous delivery
- gettrigger
- listworkerpools
slug: google-cloud-build-capability
source_filename: google-cloud-build-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Build API\n  description: The Cloud Build API provides programmatic access to create, manage, and monitor builds on Google Cloud infrastructure.\n    It supports build triggers, worker pools, source repository connections, and build configuration management for CI/CD\n    workflows.\n  tags:\n  - Google\n  - Cloud\n  - Build\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-build\n    baseUri: https://cloudbuild.googleapis.com/v1\n    description: Google Cloud Build API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_BUILD_TOKEN}}'\n    resources:\n    - name: projects-projectid-builds\n      path: /projects/{projectId}/builds\n      operations:\n      - name: listbuilds\n        method: GET\n        description: Google Cloud Build List builds\n        inputParameters:\n        - name: filter\n          in: query\n\
  \          type: string\n          description: The raw filter text to constrain the results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbuild\n        method: POST\n        description: Google Cloud Build Create a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-builds-buildid\n      path: /projects/{projectId}/builds/{buildId}\n      operations:\n      - name: getbuild\n        method: GET\n        description: Google Cloud Build Get a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-builds-buildid-cancel\n      path: /projects/{projectId}/builds/{buildId}:cancel\n      operations:\n      - name: cancelbuild\n        method: POST\n        description: Google\
  \ Cloud Build Cancel a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-triggers\n      path: /projects/{projectId}/triggers\n      operations:\n      - name: listtriggers\n        method: GET\n        description: Google Cloud Build List build triggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtrigger\n        method: POST\n        description: Google Cloud Build Create a build trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-triggers-triggerid\n      path: /projects/{projectId}/triggers/{triggerId}\n      operations:\n      - name: gettrigger\n        method: GET\n        description: Google Cloud Build Get a build trigger\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetrigger\n        method: PATCH\n        description: Google Cloud Build Update a build trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetrigger\n        method: DELETE\n        description: Google Cloud Build Delete a build trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-workerpool\n      path: /projects/{projectId}/locations/{location}/workerPools\n      operations:\n      - name: listworkerpools\n        method: GET\n        description: Google Cloud Build List worker pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkerpool\n\
  \        method: POST\n        description: Google Cloud Build Create a worker pool\n        inputParameters:\n        - name: workerPoolId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-build-rest\n    description: REST adapter for Google Cloud Build API.\n    resources:\n    - path: /projects/{projectId}/builds\n      name: listbuilds\n      operations:\n      - method: GET\n        name: listbuilds\n        description: Google Cloud Build List builds\n        call: google-cloud-build.listbuilds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/builds\n      name: createbuild\n      operations:\n      - method: POST\n        name: createbuild\n        description: Google Cloud Build Create a build\n      \
  \  call: google-cloud-build.createbuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/builds/{buildId}\n      name: getbuild\n      operations:\n      - method: GET\n        name: getbuild\n        description: Google Cloud Build Get a build\n        call: google-cloud-build.getbuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/builds/{buildId}:cancel\n      name: cancelbuild\n      operations:\n      - method: POST\n        name: cancelbuild\n        description: Google Cloud Build Cancel a build\n        call: google-cloud-build.cancelbuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/triggers\n      name: listtriggers\n      operations:\n      - method: GET\n        name: listtriggers\n        description: Google Cloud Build List build triggers\n        call: google-cloud-build.listtriggers\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/triggers\n      name: createtrigger\n      operations:\n      - method: POST\n        name: createtrigger\n        description: Google Cloud Build Create a build trigger\n        call: google-cloud-build.createtrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/triggers/{triggerId}\n      name: gettrigger\n      operations:\n      - method: GET\n        name: gettrigger\n        description: Google Cloud Build Get a build trigger\n        call: google-cloud-build.gettrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/triggers/{triggerId}\n      name: updatetrigger\n      operations:\n      - method: PATCH\n        name: updatetrigger\n        description: Google Cloud Build Update a build trigger\n        call: google-cloud-build.updatetrigger\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/triggers/{triggerId}\n      name: deletetrigger\n      operations:\n      - method: DELETE\n        name: deletetrigger\n        description: Google Cloud Build Delete a build trigger\n        call: google-cloud-build.deletetrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/workerPools\n      name: listworkerpools\n      operations:\n      - method: GET\n        name: listworkerpools\n        description: Google Cloud Build List worker pools\n        call: google-cloud-build.listworkerpools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/workerPools\n      name: createworkerpool\n      operations:\n      - method: POST\n        name: createworkerpool\n        description: Google Cloud Build Create a worker pool\n      \
  \  call: google-cloud-build.createworkerpool\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-build-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Build API for AI agent use.\n    tools:\n    - name: listbuilds\n      description: Google Cloud Build List builds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-build.listbuilds\n      with:\n        filter: tools.filter\n      inputParameters:\n      - name: filter\n        type: string\n        description: The raw filter text to constrain the results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbuild\n      description: Google Cloud Build Create a build\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-build.createbuild\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: getbuild\n      description: Google Cloud Build Get a build\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-build.getbuild\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelbuild\n      description: Google Cloud Build Cancel a build\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-build.cancelbuild\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtriggers\n      description: Google Cloud Build List build triggers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-build.listtriggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtrigger\n      description: Google Cloud Build Create a build trigger\n      hints:\n      \
  \  readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-build.createtrigger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrigger\n      description: Google Cloud Build Get a build trigger\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-build.gettrigger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetrigger\n      description: Google Cloud Build Update a build trigger\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-build.updatetrigger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetrigger\n      description: Google Cloud Build Delete a build trigger\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-build.deletetrigger\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkerpools\n      description: Google Cloud Build List worker pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-build.listworkerpools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkerpool\n      description: Google Cloud Build Create a worker pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-build.createworkerpool\n      with:\n        workerPoolId: tools.workerPoolId\n      inputParameters:\n      - name: workerPoolId\n        type: string\n        description: workerPoolId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_BUILD_TOKEN: GOOGLE_CLOUD_BUILD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-build/refs/heads/main/capabilities/google-cloud-build-capability.yaml
tags:
- Google
- Cloud
- Build
- API
tools:
- description: Google Cloud Build List builds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuilds
- description: Google Cloud Build Create a build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbuild
- description: Google Cloud Build Get a build
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuild
- description: Google Cloud Build Cancel a build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelbuild
- description: Google Cloud Build List build triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtriggers
- description: Google Cloud Build Create a build trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrigger
- description: Google Cloud Build Get a build trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrigger
- description: Google Cloud Build Update a build trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetrigger
- description: Google Cloud Build Delete a build trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetrigger
- description: Google Cloud Build List worker pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkerpools
- description: Google Cloud Build Create a worker pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkerpool
---
