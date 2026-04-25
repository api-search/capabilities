---
consumed_apis:
- api-hub
- apim
- registry
description: Unified workflow for API governance, discovery, and observability using Apigee API Hub for cataloguing, API Observation (APIM) for shadow API discovery, and Registry for tracking specifications.
layout: capability
name: Apigee API Governance and Observability
operations:
- description: List all catalogued APIs.
  method: GET
  name: list-apis
  path: /v1/apis
- description: List observed shadow APIs.
  method: GET
  name: list-observed-apis
  path: /v1/observed-apis
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- enterprise
- API Governance Lead
- list apis
- integrations
- architect overseeing api platform strategy and governance across the organization.
- api management
- api catalog from api hub.
- google cloud
- shadow apis discovered via apim.
- list observed apis
- microservices
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- api discovery
- API Product Manager
- list api specs
- API Platform Engineer
- hybrid
- engineer managing api proxies, deployments, and policies in apigee.
- list all catalogued apis.
- api governance
- list api specifications tracked in the apigee registry.
- api catalog
- manager packaging api products and managing developer relationships.
- discover undocumented shadow apis in google cloud infrastructure using apim.
- list all apis in the apigee api hub catalog.
- monetization
- discover shadow apis
- Platform Architect
- api gateway
- analytics
- api hub
- apigee
- developer portal
- list catalogued apis
- list observed shadow apis.
slug: api-governance-observability
tags:
- Apigee
- API Governance
- API Catalog
- API Discovery
- Google Cloud
tools:
- description: List all APIs in the Apigee API Hub catalog.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-catalogued-apis
- description: Discover undocumented shadow APIs in Google Cloud infrastructure using APIM.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: discover-shadow-apis
- description: List API specifications tracked in the Apigee Registry.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-specs
---
