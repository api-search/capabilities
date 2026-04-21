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
- monetization
- list api specs
- api catalog
- engineer managing api proxies, deployments, and policies in apigee.
- api management
- list api specifications tracked in the apigee registry.
- developer portal
- list apis
- api discovery
- enterprise
- api gateway
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list all catalogued apis.
- hybrid
- list observed apis
- apigee
- Platform Architect
- api hub
- microservices
- list catalogued apis
- API Governance Lead
- list all apis in the apigee api hub catalog.
- analytics
- integrations
- api governance
- API Product Manager
- discover shadow apis
- shadow apis discovered via apim.
- list observed shadow apis.
- google cloud
- API Platform Engineer
- discover undocumented shadow apis in google cloud infrastructure using apim.
- architect overseeing api platform strategy and governance across the organization.
- manager packaging api products and managing developer relationships.
- api catalog from api hub.
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
