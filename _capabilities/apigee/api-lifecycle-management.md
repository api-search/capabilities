---
categories:
- api-management
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
- API Platform Engineer
- hybrid
- API Product Manager
- list proxies
- API Governance Lead
- manager packaging api products and managing developer relationships.
- architect overseeing api platform strategy and governance across the organization.
- list api products.
- list all api products packaged for developer consumption.
- manage api developers.
- list all apis catalogued in apigee api hub for discovery and governance.
- enterprise
- list all registered api developers in the organization.
- engineer managing api proxies, deployments, and policies in apigee.
- monetization
- api lifecycle
- manage api products.
- list all environments (e.g., dev, staging, prod) in the organization.
- api gateway
- Platform Architect
- list environments
- api hub
- api governance
- list hub apis
- integrations
- api management
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- developer portal
- microservices
- list all api proxies in an apigee organization.
- apigee
- list developers.
- list api proxies
- analytics
- list developers
- list api products
- list api proxies.
- list products
- manage api proxies.
- google cloud
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
