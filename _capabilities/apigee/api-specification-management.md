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
- apis catalogued in api hub.
- API Platform Engineer
- api hub
- specs for a given api version in hub.
- analytics
- developer portal
- integrations
- get api spec contents
- list registry specs
- API Product Manager
- lint api spec
- list apis tracked in the apigee registry (legacy spec store, use for orgs not yet migrated to hub).
- list spec artifacts in the apigee registry for a specific api version.
- api management
- monetization
- list hub specs
- openapi
- list api versions
- list openapi and other specs attached to an api version in the hub.
- API Governance Lead
- manager packaging api products and managing developer relationships.
- api gateway
- architect overseeing api platform strategy and governance across the organization.
- google cloud
- list apis in the registry.
- Platform Architect
- enterprise
- apis tracked in the apigee registry.
- list hub apis
- api governance
- api specifications
- list specs for an api version.
- apigee
- hybrid
- retrieve the raw contents of an api spec — useful for inspection, diffing, or feeding to an ai agent.
- list versions of a specific api in the hub catalog.
- list all apis in the api hub catalog.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list all apis catalogued in apigee api hub — the primary api inventory for governance.
- engineer managing api proxies, deployments, and policies in apigee.
- list api specs
- list registry apis
- lint an api spec for compliance and quality violations — returns issues with severity and location.
- microservices
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
