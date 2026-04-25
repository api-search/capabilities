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
- list all apis catalogued in apigee api hub — the primary api inventory for governance.
- lint an api spec for compliance and quality violations — returns issues with severity and location.
- enterprise
- API Governance Lead
- get api spec contents
- architect overseeing api platform strategy and governance across the organization.
- integrations
- api management
- list registry specs
- google cloud
- list versions of a specific api in the hub catalog.
- list all apis in the api hub catalog.
- list apis tracked in the apigee registry (legacy spec store, use for orgs not yet migrated to hub).
- microservices
- list registry apis
- specs for a given api version in hub.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list openapi and other specs attached to an api version in the hub.
- list spec artifacts in the apigee registry for a specific api version.
- list api specs
- API Product Manager
- API Platform Engineer
- list hub apis
- list apis in the registry.
- hybrid
- apis catalogued in api hub.
- retrieve the raw contents of an api spec — useful for inspection, diffing, or feeding to an ai agent.
- engineer managing api proxies, deployments, and policies in apigee.
- api governance
- openapi
- manager packaging api products and managing developer relationships.
- lint api spec
- apis tracked in the apigee registry.
- monetization
- Platform Architect
- api gateway
- list hub specs
- analytics
- api hub
- list api versions
- api specifications
- apigee
- developer portal
- list specs for an api version.
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
