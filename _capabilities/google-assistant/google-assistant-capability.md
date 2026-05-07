---
categories: []
consumed_apis: []
description: The Google Assistant API enables developers to embed the Google Assistant into devices and applications. It provides a conversational interface through gRPC and REST endpoints, allowing applications to send text or audio queries to the Assistant and receive responses. The Actions API allows developers to build conversational Actions that extend the Assistant's capabilities with custom intents, scenes, and fulfillment logic.
layout: capability
name: Google Assistant API
operations:
- description: Google Assistant List Device Models
  method: GET
  name: listdevicemodels
  path: /v1alpha2/projects/{projectId}/deviceModels
- description: Google Assistant Create Device Model
  method: POST
  name: createdevicemodel
  path: /v1alpha2/projects/{projectId}/deviceModels
- description: Google Assistant Get Device Model
  method: GET
  name: getdevicemodel
  path: /v1alpha2/projects/{projectId}/deviceModels/{deviceModelId}
- description: Google Assistant Delete Device Model
  method: DELETE
  name: deletedevicemodel
  path: /v1alpha2/projects/{projectId}/deviceModels/{deviceModelId}
- description: Google Assistant List Device Instances
  method: GET
  name: listdeviceinstances
  path: /v1alpha2/projects/{projectId}/devices
- description: Google Assistant Create Device Instance
  method: POST
  name: createdeviceinstance
  path: /v1alpha2/projects/{projectId}/devices
personas: []
provider_name: Google Assistant
provider_slug: google-assistant
search_terms:
- google assistant delete device model
- listdeviceinstances
- api
- google assistant get device model
- actions on google
- google assistant list device models
- google assistant create device instance
- conversational ai
- google
- voice assistant
- createdevicemodel
- deletedevicemodel
- smart home
- natural language
- google assistant create device model
- listdevicemodels
- assistant
- google assistant
- createdeviceinstance
- google assistant list device instances
- getdevicemodel
slug: google-assistant-capability
source_filename: google-assistant-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Assistant API\n  description: The Google Assistant API enables developers to embed the Google Assistant into devices and applications. It\n    provides a conversational interface through gRPC and REST endpoints, allowing applications to send text or audio queries\n    to the Assistant and receive responses. The Actions API allows developers to build conversational Actions that extend\n    the Assistant's capabilities with custom intents, scenes, and fulfillment logic.\n  tags:\n  - Google\n  - Assistant\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-assistant\n    baseUri: https://embeddedassistant.googleapis.com\n    description: Google Assistant API HTTP API.\n    resources:\n    - name: v1alpha2-projects-projectid-devicemodels\n      path: /v1alpha2/projects/{projectId}/deviceModels\n      operations:\n      - name: listdevicemodels\n        method:\
  \ GET\n        description: Google Assistant List Device Models\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The Google Cloud project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdevicemodel\n        method: POST\n        description: Google Assistant Create Device Model\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1alpha2-projects-projectid-devicemodels-devicem\n      path: /v1alpha2/projects/{projectId}/deviceModels/{deviceModelId}\n      operations:\n      - name: getdevicemodel\n        method: GET\n        description: Google Assistant Get Device Model\n      \
  \  inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: deviceModelId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedevicemodel\n        method: DELETE\n        description: Google Assistant Delete Device Model\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: deviceModelId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1alpha2-projects-projectid-devices\n      path: /v1alpha2/projects/{projectId}/devices\n      operations:\n      - name: listdeviceinstances\n        method: GET\n        description:\
  \ Google Assistant List Device Instances\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeviceinstance\n        method: POST\n        description: Google Assistant Create Device Instance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-assistant-rest\n    description: REST adapter for Google Assistant API.\n    resources:\n    - path: /v1alpha2/projects/{projectId}/deviceModels\n      name: listdevicemodels\n      operations:\n      - method: GET\n        name: listdevicemodels\n        description: Google\
  \ Assistant List Device Models\n        call: google-assistant.listdevicemodels\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha2/projects/{projectId}/deviceModels\n      name: createdevicemodel\n      operations:\n      - method: POST\n        name: createdevicemodel\n        description: Google Assistant Create Device Model\n        call: google-assistant.createdevicemodel\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha2/projects/{projectId}/deviceModels/{deviceModelId}\n      name: getdevicemodel\n      operations:\n      - method: GET\n        name: getdevicemodel\n        description: Google Assistant Get Device Model\n        call: google-assistant.getdevicemodel\n        with:\n          projectId: rest.projectId\n          deviceModelId: rest.deviceModelId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1alpha2/projects/{projectId}/deviceModels/{deviceModelId}\n      name: deletedevicemodel\n      operations:\n      - method: DELETE\n        name: deletedevicemodel\n        description: Google Assistant Delete Device Model\n        call: google-assistant.deletedevicemodel\n        with:\n          projectId: rest.projectId\n          deviceModelId: rest.deviceModelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha2/projects/{projectId}/devices\n      name: listdeviceinstances\n      operations:\n      - method: GET\n        name: listdeviceinstances\n        description: Google Assistant List Device Instances\n        call: google-assistant.listdeviceinstances\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha2/projects/{projectId}/devices\n      name: createdeviceinstance\n      operations:\n\
  \      - method: POST\n        name: createdeviceinstance\n        description: Google Assistant Create Device Instance\n        call: google-assistant.createdeviceinstance\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-assistant-mcp\n    transport: http\n    description: MCP adapter for Google Assistant API for AI agent use.\n    tools:\n    - name: listdevicemodels\n      description: Google Assistant List Device Models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-assistant.listdevicemodels\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: The Google Cloud project ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdevicemodel\n      description:\
  \ Google Assistant Create Device Model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-assistant.createdevicemodel\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdevicemodel\n      description: Google Assistant Get Device Model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-assistant.getdevicemodel\n      with:\n        projectId: tools.projectId\n        deviceModelId: tools.deviceModelId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: deviceModelId\n        type: string\n        description: deviceModelId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deletedevicemodel\n      description: Google Assistant Delete Device Model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-assistant.deletedevicemodel\n      with:\n        projectId: tools.projectId\n        deviceModelId: tools.deviceModelId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: deviceModelId\n        type: string\n        description: deviceModelId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeviceinstances\n      description: Google Assistant List Device Instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-assistant.listdeviceinstances\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n\
  \        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeviceinstance\n      description: Google Assistant Create Device Instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-assistant.createdeviceinstance\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-assistant/refs/heads/main/capabilities/google-assistant-capability.yaml
tags:
- Google
- Assistant
- API
tools:
- description: Google Assistant List Device Models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevicemodels
- description: Google Assistant Create Device Model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdevicemodel
- description: Google Assistant Get Device Model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdevicemodel
- description: Google Assistant Delete Device Model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedevicemodel
- description: Google Assistant List Device Instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeviceinstances
- description: Google Assistant Create Device Instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeviceinstance
---
