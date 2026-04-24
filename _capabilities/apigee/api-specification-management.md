---
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
- API Product Manager
- google cloud
- API Platform Engineer
- manager packaging api products and managing developer relationships.
- api specifications
- list openapi and other specs attached to an api version in the hub.
- list api versions
- lint an api spec for compliance and quality violations — returns issues with severity and location.
- list registry specs
- list all apis catalogued in apigee api hub — the primary api inventory for governance.
- specs for a given api version in hub.
- architect overseeing api platform strategy and governance across the organization.
- retrieve the raw contents of an api spec — useful for inspection, diffing, or feeding to an ai agent.
- apigee
- analytics
- developer portal
- hybrid
- monetization
- list specs for an api version.
- openapi
- engineer managing api proxies, deployments, and policies in apigee.
- api management
- list apis in the registry.
- api hub
- list hub apis
- api governance
- apis tracked in the apigee registry.
- list hub specs
- get api spec contents
- API Governance Lead
- apis catalogued in api hub.
- list api specs
- list all apis in the api hub catalog.
- integrations
- enterprise
- api gateway
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- Platform Architect
- lint api spec
- list registry apis
- list apis tracked in the apigee registry (legacy spec store, use for orgs not yet migrated to hub).
- microservices
- list versions of a specific api in the hub catalog.
- list spec artifacts in the apigee registry for a specific api version.
slug: api-specification-management
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
