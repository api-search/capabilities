---
categories:
- api-management
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
- get api product
- api hub
- get developer
- Platform Architect
- apigee
- analytics
- app management
- api monetization
- get developer app
- architect overseeing api platform strategy and governance across the organization.
- api governance
- integrations
- API Governance Lead
- developer portal
- api gateway
- registered api developers.
- list api products
- API Platform Engineer
- list developers
- list all registered developers.
- list all api products available in the developer portal for subscription.
- list all apps registered by a developer, including their api product subscriptions.
- microservices
- list apps for a developer.
- get details for a specific developer app including its credentials and product subscriptions.
- engineer managing api proxies, deployments, and policies in apigee.
- list developer apps
- enterprise
- api products available for subscription.
- list all api products.
- hybrid
- list all developers registered in the apigee organization.
- get details for a specific developer including their registered apps.
- get details for a specific api product including its quota limits and proxy bindings.
- API Product Manager
- api management
- google cloud
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- monetization
- list products
- manager packaging api products and managing developer relationships.
- apps registered by a developer.
slug: developer-portal-app-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apigee Developer Portal and App Management\"\n  description: \"Unified workflow for managing the Apigee developer ecosystem — developers, applications, API product subscriptions, and key management. Provides platform operations teams and API monetization owners a governed surface for onboarding developers, approving apps, and managing API access across products and environments.\"\n  tags:\n    - Apigee\n    - Developer Portal\n    - App Management\n    - API Monetization\n    - Google Cloud\n  created: \"2026-04-20\"\n  modified: \"2026-04-20\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: api-management\n      location: ./shared/api-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: apigee-devportal-api\n      description: \"Unified REST API for Apigee developer portal and app management.\"\n      resources:\n\
  \        - path: /v1/developers\n          name: developers\n          description: \"Registered API developers.\"\n          operations:\n            - method: GET\n              name: list-developers\n              description: \"List all registered developers.\"\n              call: \"api-management.listDevelopers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/developer-apps\n          name: developer-apps\n          description: \"Apps registered by a developer.\"\n          operations:\n            - method: GET\n              name: list-developer-apps\n              description: \"List apps for a developer.\"\n              call: \"api-management.listDeveloperApps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: api-products\n          description: \"API products available for subscription.\"\n          operations:\n\
  \            - method: GET\n              name: list-products\n              description: \"List all API products.\"\n              call: \"api-management.listApiProducts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: apigee-devportal-mcp\n      transport: http\n      description: \"MCP server for AI-assisted developer portal and app management.\"\n      tools:\n        - name: list-developers\n          description: \"List all developers registered in the Apigee organization.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listDevelopers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-developer\n          description: \"Get details for a specific developer including their registered apps.\"\n          hints:\n        \
  \    readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.getDeveloper\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-developer-apps\n          description: \"List all apps registered by a developer, including their API product subscriptions.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listDeveloperApps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-developer-app\n          description: \"Get details for a specific developer app including its credentials and product subscriptions.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.getDeveloperApp\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n\n        - name: list-api-products\n          description: \"List all API products available in the developer portal for subscription.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listApiProducts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api-product\n          description: \"Get details for a specific API product including its quota limits and proxy bindings.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.getApiProduct\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/developer-portal-app-management.yaml
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
