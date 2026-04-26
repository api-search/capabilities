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
- list api specifications tracked in the apigee registry.
- API Platform Engineer
- api hub
- analytics
- developer portal
- integrations
- list catalogued apis
- discover undocumented shadow apis in google cloud infrastructure using apim.
- list observed shadow apis.
- list all apis in the apigee api hub catalog.
- API Product Manager
- api catalog
- api discovery
- api management
- monetization
- api catalog from api hub.
- list observed apis
- API Governance Lead
- discover shadow apis
- manager packaging api products and managing developer relationships.
- api gateway
- architect overseeing api platform strategy and governance across the organization.
- google cloud
- list all catalogued apis.
- Platform Architect
- enterprise
- api governance
- list apis
- apigee
- hybrid
- shadow apis discovered via apim.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- engineer managing api proxies, deployments, and policies in apigee.
- list api specs
- microservices
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
