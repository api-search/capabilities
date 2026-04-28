---
categories: []
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
- list observed shadow apis.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- api hub
- discover undocumented shadow apis in google cloud infrastructure using apim.
- api discovery
- API Governance Lead
- api management
- hybrid
- list all apis in the apigee api hub catalog.
- analytics
- monetization
- microservices
- google cloud
- enterprise
- Platform Architect
- api gateway
- list observed apis
- integrations
- developer portal
- engineer managing api proxies, deployments, and policies in apigee.
- apigee
- api catalog from api hub.
- architect overseeing api platform strategy and governance across the organization.
- api governance
- list api specifications tracked in the apigee registry.
- manager packaging api products and managing developer relationships.
- list apis
- API Product Manager
- list api specs
- discover shadow apis
- list catalogued apis
- api catalog
- list all catalogued apis.
- API Platform Engineer
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
