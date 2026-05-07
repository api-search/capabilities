---
categories: []
consumed_apis: []
description: The ArchiMate Model Exchange API provides capabilities for importing, exporting, and managing ArchiMate enterprise architecture models using the Open Group ArchiMate Model Exchange File Format (AMEFF). Enables interoperability between EA tools implementing the ArchiMate 3.x standard.
layout: capability
name: ArchiMate Model Exchange API
operations:
- description: ArchiMate List Models
  method: GET
  name: listmodels
  path: /models
- description: ArchiMate Import Model
  method: POST
  name: importmodel
  path: /models
- description: ArchiMate Get Model
  method: GET
  name: getmodel
  path: /models/{modelId}
- description: ArchiMate Delete Model
  method: DELETE
  name: deletemodel
  path: /models/{modelId}
- description: ArchiMate List Elements
  method: GET
  name: listelements
  path: /models/{modelId}/elements
- description: ArchiMate List Relationships
  method: GET
  name: listrelationships
  path: /models/{modelId}/relationships
personas: []
provider_name: ArchiMate
provider_slug: archimate
search_terms:
- archimate get model
- archimate
- archimate delete model
- ea practitioners creating and managing architecture models
- architecture framework
- modeling language
- standards enforcement and architecture review processes
- business architecture
- enterprise architecture
- api
- archimate import model
- business analysts modeling business processes and capabilities
- solution architects documenting application and technology architecture
- archimate list relationships
- deletemodel
- archimate list elements
- open group
- getmodel
- listmodels
- technology architecture
- listrelationships
- standard
- listelements
- business, application, and technology architecture documentation
- model exchange between different ea tools
- importmodel
- archimate list models
slug: archimate-capability
source_filename: archimate-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ArchiMate Model Exchange API\n  description: The ArchiMate Model Exchange API provides capabilities for importing, exporting, and managing ArchiMate enterprise\n    architecture models using the Open Group ArchiMate Model Exchange File Format (AMEFF). Enables interoperability between\n    EA tools implementing the ArchiMate 3.x standard.\n  tags:\n  - Archimate\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: archimate\n    baseUri: https://api.archimate-tools.com/v1\n    description: ArchiMate Model Exchange API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ARCHIMATE_TOKEN}}'\n    resources:\n    - name: models\n      path: /models\n      operations:\n      - name: listmodels\n        method: GET\n        description: ArchiMate List Models\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description:\
  \ Maximum number of models to return\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: importmodel\n        method: POST\n        description: ArchiMate Import Model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-modelid\n      path: /models/{modelId}\n      operations:\n      - name: getmodel\n        method: GET\n        description: ArchiMate Get Model\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: Model identifier\n        - name: format\n          in: query\n          type: string\n          description: Output format (json or xml for AMEFF)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletemodel\n        method: DELETE\n        description: ArchiMate Delete Model\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: Model identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-modelid-elements\n      path: /models/{modelId}/elements\n      operations:\n      - name: listelements\n        method: GET\n        description: ArchiMate List Elements\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: Model identifier\n        - name: layer\n          in: query\n          type: string\n          description: Filter by architecture layer\n        - name: type\n          in: query\n          type: string\n   \
  \       description: Filter by element type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-modelid-relationships\n      path: /models/{modelId}/relationships\n      operations:\n      - name: listrelationships\n        method: GET\n        description: ArchiMate List Relationships\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: Model identifier\n        - name: type\n          in: query\n          type: string\n          description: Filter by relationship type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: archimate-rest\n    description: REST adapter for ArchiMate Model Exchange API.\n    resources:\n    - path: /models\n      name: listmodels\n      operations:\n\
  \      - method: GET\n        name: listmodels\n        description: ArchiMate List Models\n        call: archimate.listmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models\n      name: importmodel\n      operations:\n      - method: POST\n        name: importmodel\n        description: ArchiMate Import Model\n        call: archimate.importmodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{modelId}\n      name: getmodel\n      operations:\n      - method: GET\n        name: getmodel\n        description: ArchiMate Get Model\n        call: archimate.getmodel\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{modelId}\n      name: deletemodel\n      operations:\n      - method: DELETE\n        name: deletemodel\n        description: ArchiMate Delete Model\n        call: archimate.deletemodel\n    \
  \    with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{modelId}/elements\n      name: listelements\n      operations:\n      - method: GET\n        name: listelements\n        description: ArchiMate List Elements\n        call: archimate.listelements\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /models/{modelId}/relationships\n      name: listrelationships\n      operations:\n      - method: GET\n        name: listrelationships\n        description: ArchiMate List Relationships\n        call: archimate.listrelationships\n        with:\n          modelId: rest.modelId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: archimate-mcp\n    transport: http\n    description: MCP adapter for ArchiMate Model Exchange API for AI agent use.\n    tools:\n\
  \    - name: listmodels\n      description: ArchiMate List Models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archimate.listmodels\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: limit\n        type: integer\n        description: Maximum number of models to return\n      - name: offset\n        type: integer\n        description: Pagination offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: importmodel\n      description: ArchiMate Import Model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: archimate.importmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodel\n      description: ArchiMate Get Model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archimate.getmodel\n      with:\n\
  \        modelId: tools.modelId\n        format: tools.format\n      inputParameters:\n      - name: modelId\n        type: string\n        description: Model identifier\n        required: true\n      - name: format\n        type: string\n        description: Output format (json or xml for AMEFF)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemodel\n      description: ArchiMate Delete Model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: archimate.deletemodel\n      with:\n        modelId: tools.modelId\n      inputParameters:\n      - name: modelId\n        type: string\n        description: Model identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listelements\n      description: ArchiMate List Elements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archimate.listelements\n\
  \      with:\n        modelId: tools.modelId\n        layer: tools.layer\n        type: tools.type\n      inputParameters:\n      - name: modelId\n        type: string\n        description: Model identifier\n        required: true\n      - name: layer\n        type: string\n        description: Filter by architecture layer\n      - name: type\n        type: string\n        description: Filter by element type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrelationships\n      description: ArchiMate List Relationships\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archimate.listrelationships\n      with:\n        modelId: tools.modelId\n        type: tools.type\n      inputParameters:\n      - name: modelId\n        type: string\n        description: Model identifier\n        required: true\n      - name: type\n        type: string\n        description: Filter by relationship type\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARCHIMATE_TOKEN: ARCHIMATE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/archimate/refs/heads/main/capabilities/archimate-capability.yaml
tags:
- Archimate
- API
tools:
- description: ArchiMate List Models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: ArchiMate Import Model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importmodel
- description: ArchiMate Get Model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodel
- description: ArchiMate Delete Model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: ArchiMate List Elements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listelements
- description: ArchiMate List Relationships
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrelationships
---
