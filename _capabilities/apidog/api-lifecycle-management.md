---
categories: []
consumed_apis: []
description: Unified workflow for managing API specifications lifecycle with Apidog - importing from various sources, exporting to standard formats, and maintaining API definitions programmatically.
layout: capability
name: Apidog API Lifecycle Management
operations:
- description: Import OpenAPI specification into Apidog project.
  method: POST
  name: import-openapi
  path: /v1/specs/import
- description: Export OpenAPI specification from Apidog project.
  method: POST
  name: export-openapi
  path: /v1/specs/export
personas: []
provider_name: Apidog
provider_slug: apidog
search_terms:
- API Developer
- import openapi specification into apidog project.
- import postman collection
- mocking
- import
- design-first
- platform
- import a postman collection into apidog for converting to openapi-based workflows.
- export an openapi specification from an apidog project for sharing or ci/cd integration.
- documentation
- engineer automating api specification workflows via ci/cd integration.
- collaboration
- unified workflow for managing api specifications lifecycle.
- api design
- Platform Engineer
- managing the complete lifecycle of api specifications from design to deployment.
- apidog
- export openapi
- import api specifications from various formats.
- import openapi spec
- export
- import openapi
- api testing
- developer building and managing apis using apidog's design-first platform.
- api lifecycle
- export openapi specification from apidog project.
- export api specifications to standard formats.
- import an openapi/swagger specification into an apidog project for design-first development.
- export openapi spec
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apidog API Lifecycle Management\n  description: Unified workflow for managing API specifications lifecycle with Apidog - importing from various sources, exporting\n    to standard formats, and maintaining API definitions programmatically.\n  tags:\n  - Apidog\n  - API Lifecycle\n  - API Design\n  - Import\n  - Export\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APIDOG_BEARER_TOKEN: APIDOG_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: apidog\n    baseUri: https://api.apidog.com\n    description: Apidog REST API for project management and API spec import/export.\n    authentication:\n      type: bearer\n      token: '{{APIDOG_BEARER_TOKEN}}'\n    resources:\n    - name: import-export\n      path: /v1/projects/{projectId}\n      description: Import and export API specification data.\n      operations:\n      - name: import-openapi\n        method: POST\n        description:\
  \ Import OpenAPI/Swagger specification data into a project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: The unique identifier of the Apidog project.\n        - name: X-Apidog-Api-Version\n          in: header\n          type: string\n          required: false\n          description: The version of the Apidog API to use.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-openapi\n        method: POST\n        description: Export the API specification from a project in OpenAPI/Swagger format.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: The unique identifier of the Apidog project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: import-postman\n        method: POST\n        description: Import API data from a Postman Collection into a project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: The unique identifier of the Apidog project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apidog-lifecycle-api\n    description: Unified REST API for Apidog API lifecycle management.\n    resources:\n    - path: /v1/specs/import\n      name: spec-import\n      description: Import API specifications from various formats.\n      operations:\n      - method: POST\n        name: import-openapi\n        description: Import OpenAPI specification into Apidog project.\n        call: apidog.import-openapi\n        with:\n          projectId: rest.projectId\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/specs/export\n      name: spec-export\n      description: Export API specifications to standard formats.\n      operations:\n      - method: POST\n        name: export-openapi\n        description: Export OpenAPI specification from Apidog project.\n        call: apidog.export-openapi\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apidog-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Apidog API lifecycle management.\n    tools:\n    - name: import-openapi-spec\n      description: Import an OpenAPI/Swagger specification into an Apidog project for design-first development.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apidog.import-openapi\n      with:\n        projectId: tools.projectId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-openapi-spec\n      description: Export an OpenAPI specification from an Apidog project for sharing or CI/CD integration.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apidog.export-openapi\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-postman-collection\n      description: Import a Postman collection into Apidog for converting to OpenAPI-based workflows.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apidog.import-postman\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apidog/refs/heads/main/capabilities/api-lifecycle-management.yaml
tags:
- Apidog
- API Lifecycle
- API Design
- Import
- Export
tools:
- description: Import an OpenAPI/Swagger specification into an Apidog project for design-first development.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: import-openapi-spec
- description: Export an OpenAPI specification from an Apidog project for sharing or CI/CD integration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: export-openapi-spec
- description: Import a Postman collection into Apidog for converting to OpenAPI-based workflows.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: import-postman-collection
---
