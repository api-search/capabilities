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
- list apis
- list catalogued apis
- hybrid
- analytics
- apigee
- architect overseeing api platform strategy and governance across the organization.
- API Platform Engineer
- integrations
- developer portal
- enterprise
- api governance
- api catalog from api hub.
- microservices
- API Product Manager
- list all apis in the apigee api hub catalog.
- api hub
- list observed shadow apis.
- monetization
- api gateway
- discover shadow apis
- api catalog
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list api specs
- API Governance Lead
- api discovery
- discover undocumented shadow apis in google cloud infrastructure using apim.
- shadow apis discovered via apim.
- google cloud
- list all catalogued apis.
- Platform Architect
- manager packaging api products and managing developer relationships.
- api management
- list observed apis
- engineer managing api proxies, deployments, and policies in apigee.
- list api specifications tracked in the apigee registry.
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
