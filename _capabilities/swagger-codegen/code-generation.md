---
categories: []
consumed_apis: []
description: Workflow capability for generating API client libraries, server stubs, and documentation from OpenAPI specifications using the Swagger Generator online service. Covers language discovery, option inspection, and artifact generation for developers and API teams.
layout: capability
name: Swagger Codegen Code Generation
operations:
- description: List available generator languages for a type and version
  method: GET
  name: list-languages
  path: /v1/languages
- description: Get configurable generation options for a language
  method: GET
  name: list-options
  path: /v1/options
- description: Generate a client SDK or server stub from an OpenAPI spec
  method: POST
  name: generate-code
  path: /v1/generate
- description: Generate intermediate model JSON for debugging
  method: POST
  name: generate-model
  path: /v1/model
personas: []
provider_name: Swagger Codegen
provider_slug: swagger-codegen
search_terms:
- generate model
- code generation
- list all available client sdk generator languages for v3 openapi specs
- list options
- list available generator languages for a type and version
- generate a server stub in the specified framework from an openapi specification
- client libraries
- list all available server stub generator languages for v3 openapi specs
- list server languages
- openapi
- get configurable generation options for a language
- open source
- list languages
- sdk
- generator options per language
- generate code
- get all configurable options for a specific swagger codegen generator language
- available generator languages and types
- generate the intermediate bundle model json for a generation request — useful for debugging templates
- generate a client sdk in the specified language from an openapi specification
- intermediate model inspection
- swagger
- list client languages
- generator
- generate intermediate model json for debugging
- generate client sdk
- generate a client sdk or server stub from an openapi spec
- generate server stub
- get language options
slug: code-generation
source_filename: code-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Swagger Codegen Code Generation\n  description: Workflow capability for generating API client libraries, server stubs, and documentation from OpenAPI specifications\n    using the Swagger Generator online service. Covers language discovery, option inspection, and artifact generation for\n    developers and API teams.\n  tags:\n  - Client Libraries\n  - Code Generation\n  - Generator\n  - OpenAPI\n  - SDK\n  - Swagger\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SWAGGER_GENERATOR_URL: SWAGGER_GENERATOR_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: swagger-generator\n    baseUri: https://generator3.swagger.io\n    description: Swagger Generator V3 online code generation service\n    resources:\n    - name: generation\n      path: /generate\n      description: Code generation endpoints\n      operations:\n      - name: generate-code\n        method: POST\n        description: Generate\
  \ client SDK or server stub from OpenAPI spec\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lang: '{{tools.lang}}'\n            type: '{{tools.type}}'\n            codegenVersion: '{{tools.codegenVersion}}'\n            spec: '{{tools.spec}}'\n      - name: generate-code-from-url\n        method: GET\n        description: Generate code from URL-referenced OpenAPI spec configuration\n        inputParameters:\n        - name: codegenOptionsURL\n          in: query\n          type: string\n          required: true\n          description: URL to a GenerationRequest JSON configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: languages\n      path: /{type}/{version}\n      description: Generator language discovery\n      operations:\n      - name: list-languages\n\
  \        method: GET\n        description: List available generator languages by type and version\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: 'Generator type: client, server, documentation, config'\n        - name: version\n          in: path\n          type: string\n          required: true\n          description: 'OpenAPI version: V2 or V3'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: options\n      path: /options\n      description: Generator language options\n      operations:\n      - name: list-options\n        method: GET\n        description: Return configurable options for a generator language\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Generator language identifier\n        - name: version\n\
  \          in: query\n          type: string\n          required: false\n          description: OpenAPI version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model\n      path: /model\n      description: Intermediate model generation\n      operations:\n      - name: generate-model\n        method: POST\n        description: Generate intermediate bundle/model as JSON for debugging\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lang: '{{tools.lang}}'\n            spec: '{{tools.spec}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: code-generation-api\n    description: Unified REST API for Swagger Codegen generation workflows.\n    resources:\n    - path: /v1/languages\n      name: languages\n      description: Available generator languages\
  \ and types\n      operations:\n      - method: GET\n        name: list-languages\n        description: List available generator languages for a type and version\n        call: swagger-generator.list-languages\n        with:\n          type: rest.type\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/options\n      name: options\n      description: Generator options per language\n      operations:\n      - method: GET\n        name: list-options\n        description: Get configurable generation options for a language\n        call: swagger-generator.list-options\n        with:\n          language: rest.language\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generate\n      name: generate\n      description: Code generation\n      operations:\n      - method: POST\n        name: generate-code\n        description: Generate a client SDK or\
  \ server stub from an OpenAPI spec\n        call: swagger-generator.generate-code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/model\n      name: model\n      description: Intermediate model inspection\n      operations:\n      - method: POST\n        name: generate-model\n        description: Generate intermediate model JSON for debugging\n        call: swagger-generator.generate-model\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: code-generation-mcp\n    transport: http\n    description: MCP server for AI-assisted API code generation with Swagger Codegen.\n    tools:\n    - name: list-client-languages\n      description: List all available client SDK generator languages for V3 OpenAPI specs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swagger-generator.list-languages\n      with:\n        type: client\n        version: V3\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-server-languages\n      description: List all available server stub generator languages for V3 OpenAPI specs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swagger-generator.list-languages\n      with:\n        type: server\n        version: V3\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-language-options\n      description: Get all configurable options for a specific Swagger Codegen generator language\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swagger-generator.list-options\n      with:\n        language: tools.language\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-client-sdk\n      description: Generate a client SDK in the specified language from an OpenAPI specification\n      hints:\n        readOnly: false\n        idempotent: false\n      call:\
  \ swagger-generator.generate-code\n      with:\n        lang: tools.lang\n        type: CLIENT\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-server-stub\n      description: Generate a server stub in the specified framework from an OpenAPI specification\n      hints:\n        readOnly: false\n        idempotent: false\n      call: swagger-generator.generate-code\n      with:\n        lang: tools.lang\n        type: SERVER\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-model\n      description: Generate the intermediate bundle model JSON for a generation request — useful for debugging templates\n      hints:\n        readOnly: false\n        idempotent: false\n      call: swagger-generator.generate-model\n      with:\n        lang: tools.lang\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/swagger-codegen/refs/heads/main/capabilities/code-generation.yaml
tags:
- Client Libraries
- Code Generation
- Generator
- OpenAPI
- SDK
- Swagger
tools:
- description: List all available client SDK generator languages for V3 OpenAPI specs
  hints:
    idempotent: true
    readOnly: true
  name: list-client-languages
- description: List all available server stub generator languages for V3 OpenAPI specs
  hints:
    idempotent: true
    readOnly: true
  name: list-server-languages
- description: Get all configurable options for a specific Swagger Codegen generator language
  hints:
    idempotent: true
    readOnly: true
  name: get-language-options
- description: Generate a client SDK in the specified language from an OpenAPI specification
  hints:
    idempotent: false
    readOnly: false
  name: generate-client-sdk
- description: Generate a server stub in the specified framework from an OpenAPI specification
  hints:
    idempotent: false
    readOnly: false
  name: generate-server-stub
- description: Generate the intermediate bundle model JSON for a generation request — useful for debugging templates
  hints:
    idempotent: false
    readOnly: false
  name: generate-model
---
