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
- API Product Manager
- google cloud
- microservices
- API Platform Engineer
- manager packaging api products and managing developer relationships.
- list api proxies.
- list all api products packaged for developer consumption.
- list api proxies
- list developers.
- architect overseeing api platform strategy and governance across the organization.
- apigee
- analytics
- developer portal
- hybrid
- monetization
- list api products
- list proxies
- list environments
- list developers
- api management
- api hub
- manage api developers.
- list hub apis
- api governance
- list all api proxies in an apigee organization.
- list all environments (e.g., dev, staging, prod) in the organization.
- API Governance Lead
- list all registered api developers in the organization.
- list products
- list all apis catalogued in apigee api hub for discovery and governance.
- integrations
- manage api products.
- enterprise
- api gateway
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- api lifecycle
- Platform Architect
- manage api proxies.
- list api products.
- engineer managing api proxies, deployments, and policies in apigee.
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
