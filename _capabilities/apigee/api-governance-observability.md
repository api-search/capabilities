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
- API Platform Engineer
- hybrid
- API Product Manager
- list catalogued apis
- API Governance Lead
- manager packaging api products and managing developer relationships.
- architect overseeing api platform strategy and governance across the organization.
- list api specs
- google cloud
- list observed shadow apis.
- enterprise
- list all catalogued apis.
- engineer managing api proxies, deployments, and policies in apigee.
- monetization
- api gateway
- discover undocumented shadow apis in google cloud infrastructure using apim.
- Platform Architect
- list observed apis
- api hub
- api governance
- discover shadow apis
- integrations
- api management
- api discovery
- shadow apis discovered via apim.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- developer portal
- api catalog
- microservices
- apigee
- api catalog from api hub.
- analytics
- list all apis in the apigee api hub catalog.
- list apis
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
