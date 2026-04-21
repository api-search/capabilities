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
- google cloud
- list api products
- API Governance Lead
- get details for a specific developer app including its credentials and product subscriptions.
- api gateway
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- Platform Architect
- engineer managing api proxies, deployments, and policies in apigee.
- analytics
- api hub
- get developer
- enterprise
- API Platform Engineer
- get details for a specific developer including their registered apps.
- list all apps registered by a developer, including their api product subscriptions.
- developer portal
- list all api products available in the developer portal for subscription.
- API Product Manager
- list developer apps
- get details for a specific api product including its quota limits and proxy bindings.
- get api product
- list all api products.
- api management
- hybrid
- api governance
- apigee
- app management
- api products available for subscription.
- list apps for a developer.
- registered api developers.
- list developers
- monetization
- list all registered developers.
- get developer app
- apps registered by a developer.
- list all developers registered in the apigee organization.
- manager packaging api products and managing developer relationships.
- integrations
- microservices
- architect overseeing api platform strategy and governance across the organization.
- list products
- api monetization
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
