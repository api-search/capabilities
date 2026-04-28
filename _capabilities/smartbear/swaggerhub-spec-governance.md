---
categories:
- api-management
- api-governance
consumed_apis:
- swaggerhub-registry
description: Workflow capability for API platform owners publishing, versioning, and governing OpenAPI specs in SwaggerHub as the source of truth for downstream artifacts — including MCP servers generated from the same governed spec. Implements the pattern Jeff Seifert pointed at: govern the OpenAPI spec, generate MCP from it, treat composite tools the same way you treat any other API.
layout: capability
name: SmartBear SwaggerHub Spec Governance
operations:
- description: Publish a new OpenAPI spec or version to the SwaggerHub registry
  method: POST
  name: publish-spec
  path: /apis/{owner}/{api}
- description: Get a published OpenAPI spec by owner, name, and version
  method: GET
  name: get-spec
  path: /apis/{owner}/{api}/{version}
- description: List all versions of an API for lifecycle and deprecation review
  method: GET
  name: list-versions
  path: /apis/{owner}/{api}/settings/lifecycle
- description: Run a standardization-rules style guide against a spec to score governance compliance
  method: POST
  name: run-style-guide
  path: /apis/{owner}/{api}/{version}/standardization
- description: Compare two versions of a spec to surface breaking changes before promotion
  method: GET
  name: compare-versions
  path: /apis/{owner}/{api}/compare
- description: Set the visibility, tags, and lifecycle stage on a spec for catalog governance
  method: PUT
  name: update-spec-metadata
  path: /apis/{owner}/{api}/settings
personas:
- API Platform Engineer
- API Architect
provider_name: SmartBear
provider_slug: smartbear
search_terms:
- publish openapi spec to swaggerhub
- governed openapi registry
- swaggerhub style guide compliance
- compare openapi spec versions
- breaking change detection in openapi
- openapi spec source of truth
- generate mcp from governed openapi
- swaggerhub api lifecycle
- standardize openapi specs across teams
- list openapi spec versions
- openapi spec governance
- swaggerhub
- smartbear
- api standardization
- spec compliance
- mcp generation from openapi
- composite api governance
- api architect tooling
- openapi
- spec registry
- api governance
- versioned spec publishing
slug: swaggerhub-spec-governance
tags:
- SmartBear
- SwaggerHub
- OpenAPI
- API Governance
- Spec Lifecycle
tools:
- description: Publish a new OpenAPI spec or version to SwaggerHub as the governed source of truth for downstream MCP and SDK generation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publish-spec
- description: Get a published OpenAPI spec by owner, name, and version for review or generation
  hints:
    openWorld: false
    readOnly: true
  name: get-spec
- description: List all versions of an API in SwaggerHub to support lifecycle and deprecation review
  hints:
    openWorld: false
    readOnly: true
  name: list-spec-versions
- description: Run a SwaggerHub style guide against a spec to score governance compliance before promotion
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: run-style-guide
- description: Compare two versions of a spec to surface breaking changes that would block promotion
  hints:
    openWorld: false
    readOnly: true
  name: compare-spec-versions
- description: Update spec metadata — visibility, tags, lifecycle stage — for catalog and governance signals
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-spec-metadata
---
