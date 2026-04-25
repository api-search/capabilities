---
consumed_apis:
- api-management
- api-hub
description: Unified workflow for managing the full API lifecycle on Google Apigee - from API proxy creation and deployment to developer portal management, product packaging, and analytics.
layout: capability
name: Apigee API Lifecycle Management
operations:
- description: List API proxies.
  method: GET
  name: list-proxies
  path: /v1/proxies
- description: List API products.
  method: GET
  name: list-products
  path: /v1/products
- description: List developers.
  method: GET
  name: list-developers
  path: /v1/developers
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- hybrid
- analytics
- apigee
- manage api proxies.
- architect overseeing api platform strategy and governance across the organization.
- manage api products.
- list products
- list api products.
- API Platform Engineer
- integrations
- developer portal
- enterprise
- list developers.
- api governance
- microservices
- API Product Manager
- api hub
- list all registered api developers in the organization.
- monetization
- api gateway
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list developers
- list hub apis
- list api proxies
- API Governance Lead
- list all api proxies in an apigee organization.
- api lifecycle
- list proxies
- google cloud
- list all api products packaged for developer consumption.
- list all environments (e.g., dev, staging, prod) in the organization.
- list api proxies.
- Platform Architect
- manager packaging api products and managing developer relationships.
- manage api developers.
- api management
- engineer managing api proxies, deployments, and policies in apigee.
- list api products
- list all apis catalogued in apigee api hub for discovery and governance.
- list environments
slug: api-lifecycle-management
tags:
- Apigee
- API Management
- API Lifecycle
- Google Cloud
- Developer Portal
tools:
- description: List all API proxies in an Apigee organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-proxies
- description: List all API products packaged for developer consumption.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-products
- description: List all registered API developers in the organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-developers
- description: List all environments (e.g., dev, staging, prod) in the organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-environments
- description: List all APIs catalogued in Apigee API Hub for discovery and governance.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-hub-apis
---
