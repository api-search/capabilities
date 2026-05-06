---
categories: []
consumed_apis: []
description: The APIMatic Platform API provides programmatic access to APIMatic's capabilities including SDK generation, API documentation portal generation, API specification validation and linting, and API specification transformation. Integrate APIMatic into your CI/CD workflows to automate your developer experience suite.
layout: capability
name: APIMatic Platform API
operations:
- description: List API Entities
  method: GET
  name: listapientities
  path: /api-entities
- description: Import API Definition
  method: POST
  name: importapidefinition
  path: /api-entities
- description: Generate SDK
  method: POST
  name: generatesdk
  path: /api-entities/{apiEntityId}/generate-sdk
- description: Validate API Definition
  method: POST
  name: validateapidefinition
  path: /api-entities/{apiEntityId}/validate
- description: Transform API Definition
  method: POST
  name: transformapidefinition
  path: /api-entities/{apiEntityId}/transform
- description: Generate API Portal
  method: POST
  name: generateportal
  path: /api-entities/{apiEntityId}/portal
personas: []
provider_name: APIMatic
provider_slug: apimatic
search_terms:
- generate api portal
- api transformation
- code generation
- importapidefinition
- developer experience
- generatesdk
- apimatic
- generate sdk
- documentation
- sdk generation
- validateapidefinition
- generateportal
- api
- transformapidefinition
- list api entities
- import api definition
- validate api definition
- listapientities
- transform api definition
slug: apimatic-capability
source_filename: apimatic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: APIMatic Platform API\n  description: The APIMatic Platform API provides programmatic access to APIMatic's capabilities including SDK generation,\n    API documentation portal generation, API specification validation and linting, and API specification transformation. Integrate\n    APIMatic into your CI/CD workflows to automate your developer experience suite.\n  tags:\n  - Apimatic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: apimatic\n    baseUri: https://api.apimatic.io\n    description: APIMatic Platform API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{APIMATIC_TOKEN}}'\n    resources:\n    - name: api-entities\n      path: /api-entities\n      operations:\n      - name: listapientities\n        method: GET\n        description: List API Entities\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: importapidefinition\n        method: POST\n        description: Import API Definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-entities-apientityid-generate-sdk\n      path: /api-entities/{apiEntityId}/generate-sdk\n      operations:\n      - name: generatesdk\n        method: POST\n        description: Generate SDK\n        inputParameters:\n        - name: apiEntityId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-entities-apientityid-validate\n      path: /api-entities/{apiEntityId}/validate\n      operations:\n      - name: validateapidefinition\n        method: POST\n      \
  \  description: Validate API Definition\n        inputParameters:\n        - name: apiEntityId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-entities-apientityid-transform\n      path: /api-entities/{apiEntityId}/transform\n      operations:\n      - name: transformapidefinition\n        method: POST\n        description: Transform API Definition\n        inputParameters:\n        - name: apiEntityId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-entities-apientityid-portal\n      path: /api-entities/{apiEntityId}/portal\n      operations:\n\
  \      - name: generateportal\n        method: POST\n        description: Generate API Portal\n        inputParameters:\n        - name: apiEntityId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apimatic-rest\n    description: REST adapter for APIMatic Platform API.\n    resources:\n    - path: /api-entities\n      name: listapientities\n      operations:\n      - method: GET\n        name: listapientities\n        description: List API Entities\n        call: apimatic.listapientities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-entities\n      name: importapidefinition\n      operations:\n      - method: POST\n        name: importapidefinition\n        description: Import\
  \ API Definition\n        call: apimatic.importapidefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-entities/{apiEntityId}/generate-sdk\n      name: generatesdk\n      operations:\n      - method: POST\n        name: generatesdk\n        description: Generate SDK\n        call: apimatic.generatesdk\n        with:\n          apiEntityId: rest.apiEntityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-entities/{apiEntityId}/validate\n      name: validateapidefinition\n      operations:\n      - method: POST\n        name: validateapidefinition\n        description: Validate API Definition\n        call: apimatic.validateapidefinition\n        with:\n          apiEntityId: rest.apiEntityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-entities/{apiEntityId}/transform\n      name: transformapidefinition\n      operations:\n      - method: POST\n  \
  \      name: transformapidefinition\n        description: Transform API Definition\n        call: apimatic.transformapidefinition\n        with:\n          apiEntityId: rest.apiEntityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-entities/{apiEntityId}/portal\n      name: generateportal\n      operations:\n      - method: POST\n        name: generateportal\n        description: Generate API Portal\n        call: apimatic.generateportal\n        with:\n          apiEntityId: rest.apiEntityId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apimatic-mcp\n    transport: http\n    description: MCP adapter for APIMatic Platform API for AI agent use.\n    tools:\n    - name: listapientities\n      description: List API Entities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apimatic.listapientities\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: importapidefinition\n      description: Import API Definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apimatic.importapidefinition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatesdk\n      description: Generate SDK\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apimatic.generatesdk\n      with:\n        apiEntityId: tools.apiEntityId\n      inputParameters:\n      - name: apiEntityId\n        type: string\n        description: Unique identifier of the API entity\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validateapidefinition\n      description: Validate API Definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apimatic.validateapidefinition\n\
  \      with:\n        apiEntityId: tools.apiEntityId\n      inputParameters:\n      - name: apiEntityId\n        type: string\n        description: Unique identifier of the API entity\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transformapidefinition\n      description: Transform API Definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apimatic.transformapidefinition\n      with:\n        apiEntityId: tools.apiEntityId\n      inputParameters:\n      - name: apiEntityId\n        type: string\n        description: Unique identifier of the API entity\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateportal\n      description: Generate API Portal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apimatic.generateportal\n      with:\n        apiEntityId:\
  \ tools.apiEntityId\n      inputParameters:\n      - name: apiEntityId\n        type: string\n        description: Unique identifier of the API entity\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    APIMATIC_TOKEN: APIMATIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apimatic/refs/heads/main/capabilities/apimatic-capability.yaml
tags:
- Apimatic
- API
tools:
- description: List API Entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapientities
- description: Import API Definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importapidefinition
- description: Generate SDK
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatesdk
- description: Validate API Definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateapidefinition
- description: Transform API Definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: transformapidefinition
- description: Generate API Portal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateportal
---
