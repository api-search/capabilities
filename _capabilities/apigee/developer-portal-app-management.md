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
- engineer managing api proxies, deployments, and policies in apigee.
- get details for a specific developer including their registered apps.
- list all registered developers.
- integrations
- api hub
- analytics
- api gateway
- enterprise
- apigee
- list all api products.
- apps registered by a developer.
- list all developers registered in the apigee organization.
- get developer
- Platform Architect
- get details for a specific developer app including its credentials and product subscriptions.
- list developers
- list apps for a developer.
- api monetization
- api management
- developer portal
- list developer apps
- microservices
- get developer app
- list api products
- api governance
- architect overseeing api platform strategy and governance across the organization.
- registered api developers.
- get api product
- manager packaging api products and managing developer relationships.
- list products
- API Product Manager
- list all api products available in the developer portal for subscription.
- get details for a specific api product including its quota limits and proxy bindings.
- google cloud
- app management
- API Platform Engineer
- hybrid
- list all apps registered by a developer, including their api product subscriptions.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- API Governance Lead
- api products available for subscription.
- monetization
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
