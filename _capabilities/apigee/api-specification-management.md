---
categories:
- api-management
consumed_apis:
- api-hub
- registry
description: Unified workflow for managing API specifications on Apigee — browsing the API Hub catalog, retrieving spec contents, linting for compliance, and cross-referencing with Registry artifacts. Provides API product managers and governance teams a single surface to inspect, validate, and govern the specifications that define your API contracts.
layout: capability
name: Apigee API Specification Management
operations:
- description: List all APIs in the API Hub catalog.
  method: GET
  name: list-hub-apis
  path: /v1/hub/apis
- description: List specs for an API version.
  method: GET
  name: list-hub-specs
  path: /v1/hub/specs
- description: List APIs in the Registry.
  method: GET
  name: list-registry-apis
  path: /v1/registry/apis
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- manager packaging api products and managing developer relationships.
- list hub specs
- architect overseeing api platform strategy and governance across the organization.
- monetization
- apis tracked in the apigee registry.
- API Governance Lead
- specs for a given api version in hub.
- list all apis catalogued in apigee api hub — the primary api inventory for governance.
- analytics
- list openapi and other specs attached to an api version in the hub.
- list registry apis
- list hub apis
- list spec artifacts in the apigee registry for a specific api version.
- apigee
- API Product Manager
- list all apis in the api hub catalog.
- list registry specs
- apis catalogued in api hub.
- get api spec contents
- microservices
- list api versions
- enterprise
- api management
- api specifications
- list apis tracked in the apigee registry (legacy spec store, use for orgs not yet migrated to hub).
- Platform Architect
- api hub
- integrations
- list apis in the registry.
- api governance
- retrieve the raw contents of an api spec — useful for inspection, diffing, or feeding to an ai agent.
- lint api spec
- openapi
- engineer managing api proxies, deployments, and policies in apigee.
- lint an api spec for compliance and quality violations — returns issues with severity and location.
- api gateway
- list api specs
- hybrid
- list versions of a specific api in the hub catalog.
- google cloud
- API Platform Engineer
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list specs for an api version.
- developer portal
slug: api-specification-management
source_filename: api-specification-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apigee API Specification Management\"\n  description: \"Unified workflow for managing API specifications on Apigee — browsing the API Hub catalog, retrieving spec contents, linting for compliance, and cross-referencing with Registry artifacts. Provides API product managers and governance teams a single surface to inspect, validate, and govern the specifications that define your API contracts.\"\n  tags:\n    - Apigee\n    - API Specifications\n    - API Governance\n    - OpenAPI\n    - Google Cloud\n  created: \"2026-04-20\"\n  modified: \"2026-04-20\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: api-hub\n      location: ./shared/api-hub.yaml\n    - import: registry\n      location: ./shared/registry.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: apigee-specs-api\n      description: \"Unified REST API for Apigee API\
  \ specification management.\"\n      resources:\n        - path: /v1/hub/apis\n          name: hub-apis\n          description: \"APIs catalogued in API Hub.\"\n          operations:\n            - method: GET\n              name: list-hub-apis\n              description: \"List all APIs in the API Hub catalog.\"\n              call: \"api-hub.listApis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hub/specs\n          name: hub-specs\n          description: \"Specs for a given API version in Hub.\"\n          operations:\n            - method: GET\n              name: list-hub-specs\n              description: \"List specs for an API version.\"\n              call: \"api-hub.listApiSpecs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/registry/apis\n          name: registry-apis\n          description: \"APIs tracked in the Apigee Registry.\"\
  \n          operations:\n            - method: GET\n              name: list-registry-apis\n              description: \"List APIs in the Registry.\"\n              call: \"registry.listApis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: apigee-specs-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API specification management and governance.\"\n      tools:\n        - name: list-hub-apis\n          description: \"List all APIs catalogued in Apigee API Hub — the primary API inventory for governance.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-hub.listApis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-versions\n          description: \"List versions of a specific API in the Hub catalog.\"\n   \
  \       hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-hub.listApiVersions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-specs\n          description: \"List OpenAPI and other specs attached to an API version in the Hub.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-hub.listApiSpecs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api-spec-contents\n          description: \"Retrieve the raw contents of an API spec — useful for inspection, diffing, or feeding to an AI agent.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-hub.getApiSpecContents\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n\n        - name: lint-api-spec\n          description: \"Lint an API spec for compliance and quality violations — returns issues with severity and location.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"api-hub.lintApiSpec\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-registry-apis\n          description: \"List APIs tracked in the Apigee Registry (legacy spec store, use for orgs not yet migrated to Hub).\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"registry.listApis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-registry-specs\n          description: \"List spec artifacts in the Apigee Registry for a specific API version.\"\n          hints:\n            readOnly:\
  \ true\n            destructive: false\n            idempotent: true\n          call: \"registry.listApiSpecs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/api-specification-management.yaml
tags:
- Apigee
- API Specifications
- API Governance
- OpenAPI
- Google Cloud
tools:
- description: List all APIs catalogued in Apigee API Hub — the primary API inventory for governance.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-hub-apis
- description: List versions of a specific API in the Hub catalog.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-versions
- description: List OpenAPI and other specs attached to an API version in the Hub.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-specs
- description: Retrieve the raw contents of an API spec — useful for inspection, diffing, or feeding to an AI agent.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-spec-contents
- description: Lint an API spec for compliance and quality violations — returns issues with severity and location.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: lint-api-spec
- description: List APIs tracked in the Apigee Registry (legacy spec store, use for orgs not yet migrated to Hub).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-registry-apis
- description: List spec artifacts in the Apigee Registry for a specific API version.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-registry-specs
---
