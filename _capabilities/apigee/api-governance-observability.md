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
- shadow apis discovered via apim.
- list all apis in the apigee api hub catalog.
- api hub
- Platform Architect
- list all catalogued apis.
- list api specifications tracked in the apigee registry.
- api management
- google cloud
- api catalog
- hybrid
- analytics
- engineer managing api proxies, deployments, and policies in apigee.
- enterprise
- api gateway
- API Platform Engineer
- discover undocumented shadow apis in google cloud infrastructure using apim.
- api catalog from api hub.
- list observed apis
- architect overseeing api platform strategy and governance across the organization.
- API Governance Lead
- monetization
- discover shadow apis
- list observed shadow apis.
- integrations
- api governance
- microservices
- list catalogued apis
- developer portal
- apigee
- list apis
- API Product Manager
- list api specs
- api discovery
- manager packaging api products and managing developer relationships.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
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
