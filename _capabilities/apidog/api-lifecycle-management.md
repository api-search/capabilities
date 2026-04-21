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
- export openapi spec
- Platform Engineer
- export
- import an openapi/swagger specification into an apidog project for design-first development.
- API Developer
- managing the complete lifecycle of api specifications from design to deployment.
- design-first
- import a postman collection into apidog for converting to openapi-based workflows.
- import openapi specification into apidog project.
- documentation
- export openapi
- apidog
- api lifecycle
- unified workflow for managing api specifications lifecycle.
- import openapi
- api testing
- export an openapi specification from an apidog project for sharing or ci/cd integration.
- collaboration
- engineer automating api specification workflows via ci/cd integration.
- import
- export openapi specification from apidog project.
- platform
- import postman collection
- api design
- import openapi spec
- import api specifications from various formats.
- export api specifications to standard formats.
- mocking
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
