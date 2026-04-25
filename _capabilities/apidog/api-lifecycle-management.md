---
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
- documentation
- import
- collaboration
- mocking
- import openapi
- import an openapi/swagger specification into an apidog project for design-first development.
- Platform Engineer
- import openapi specification into apidog project.
- import a postman collection into apidog for converting to openapi-based workflows.
- import api specifications from various formats.
- unified workflow for managing api specifications lifecycle.
- export openapi
- api design
- export an openapi specification from an apidog project for sharing or ci/cd integration.
- api testing
- import postman collection
- export
- api lifecycle
- platform
- export openapi spec
- engineer automating api specification workflows via ci/cd integration.
- apidog
- export openapi specification from apidog project.
- design-first
- export api specifications to standard formats.
- import openapi spec
- API Developer
- managing the complete lifecycle of api specifications from design to deployment.
- developer building and managing apis using apidog's design-first platform.
slug: api-lifecycle-management
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
