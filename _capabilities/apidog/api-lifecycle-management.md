---
categories: []
consumed_apis:
- apidog
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
- apidog
- export openapi spec
- export openapi specification from apidog project.
- Platform Engineer
- design-first
- import openapi
- import a postman collection into apidog for converting to openapi-based workflows.
- platform
- export
- import api specifications from various formats.
- api design
- export an openapi specification from an apidog project for sharing or ci/cd integration.
- import postman collection
- managing the complete lifecycle of api specifications from design to deployment.
- api lifecycle
- documentation
- engineer automating api specification workflows via ci/cd integration.
- import openapi specification into apidog project.
- import an openapi/swagger specification into an apidog project for design-first development.
- unified workflow for managing api specifications lifecycle.
- api testing
- import openapi spec
- export openapi
- developer building and managing apis using apidog's design-first platform.
- mocking
- collaboration
- export api specifications to standard formats.
- import
- API Developer
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apidog API Lifecycle Management\"\n  description: \"Unified workflow for managing API specifications lifecycle with Apidog - importing from various sources, exporting to standard formats, and maintaining API definitions programmatically.\"\n  tags:\n    - Apidog\n    - API Lifecycle\n    - API Design\n    - Import\n    - Export\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APIDOG_BEARER_TOKEN: APIDOG_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: apidog\n      location: ./shared/apidog.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apidog-lifecycle-api\n      description: \"Unified REST API for Apidog API lifecycle management.\"\n      resources:\n        - path: /v1/specs/import\n          name: spec-import\n          description: \"Import API specifications from various formats.\"\n          operations:\n            - method: POST\n  \
  \            name: import-openapi\n              description: \"Import OpenAPI specification into Apidog project.\"\n              call: \"apidog.import-openapi\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/specs/export\n          name: spec-export\n          description: \"Export API specifications to standard formats.\"\n          operations:\n            - method: POST\n              name: export-openapi\n              description: \"Export OpenAPI specification from Apidog project.\"\n              call: \"apidog.export-openapi\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apidog-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ Apidog API lifecycle management.\"\n      tools:\n        - name: import-openapi-spec\n          description: \"Import an OpenAPI/Swagger specification into an Apidog project for design-first development.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"apidog.import-openapi\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-openapi-spec\n          description: \"Export an OpenAPI specification from an Apidog project for sharing or CI/CD integration.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apidog.export-openapi\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-postman-collection\n\
  \          description: \"Import a Postman collection into Apidog for converting to OpenAPI-based workflows.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"apidog.import-postman\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
