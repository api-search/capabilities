---
consumed_apis:
- api-management
description: Unified workflow for managing the Apigee developer ecosystem — developers, applications, API product subscriptions, and key management. Provides platform operations teams and API monetization owners a governed surface for onboarding developers, approving apps, and managing API access across products and environments.
layout: capability
name: Apigee Developer Portal and App Management
operations:
- description: List all registered developers.
  method: GET
  name: list-developers
  path: /v1/developers
- description: List apps for a developer.
  method: GET
  name: list-developer-apps
  path: /v1/developer-apps
- description: List all API products.
  method: GET
  name: list-products
  path: /v1/products
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- enterprise
- app management
- get api product
- list all apps registered by a developer, including their api product subscriptions.
- api products available for subscription.
- API Governance Lead
- integrations
- architect overseeing api platform strategy and governance across the organization.
- api management
- google cloud
- microservices
- get developer app
- list all api products available in the developer portal for subscription.
- apps registered by a developer.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- get details for a specific developer including their registered apps.
- list products
- API Product Manager
- registered api developers.
- list apps for a developer.
- API Platform Engineer
- get details for a specific developer app including its credentials and product subscriptions.
- get details for a specific api product including its quota limits and proxy bindings.
- hybrid
- engineer managing api proxies, deployments, and policies in apigee.
- list all registered developers.
- api governance
- list developers
- list all developers registered in the apigee organization.
- list api products
- manager packaging api products and managing developer relationships.
- list developer apps
- monetization
- Platform Architect
- api gateway
- analytics
- api hub
- api monetization
- apigee
- developer portal
- get developer
- list all api products.
slug: developer-portal-app-management
tags:
- Apigee
- Developer Portal
- App Management
- API Monetization
- Google Cloud
tools:
- description: List all developers registered in the Apigee organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-developers
- description: Get details for a specific developer including their registered apps.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-developer
- description: List all apps registered by a developer, including their API product subscriptions.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-developer-apps
- description: Get details for a specific developer app including its credentials and product subscriptions.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-developer-app
- description: List all API products available in the developer portal for subscription.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-products
- description: Get details for a specific API product including its quota limits and proxy bindings.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-product
---
