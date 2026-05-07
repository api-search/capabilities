---
categories:
- api-management
consumed_apis: []
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
- integrations
- API Platform Engineer
- API Governance Lead
- architect overseeing api platform strategy and governance across the organization.
- analytics
- API Product Manager
- Platform Architect
- get details for a specific api product including its quota limits and proxy bindings.
- app management
- list products
- list all api products.
- apps registered by a developer.
- api management
- api hub
- api governance
- get developer
- hybrid
- developer portal
- get developer app
- list all apps registered by a developer, including their api product subscriptions.
- api gateway
- engineer managing api proxies, deployments, and policies in apigee.
- get api product
- api products available for subscription.
- list apps for a developer.
- get details for a specific developer including their registered apps.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- enterprise
- list all developers registered in the apigee organization.
- monetization
- apigee
- list all api products available in the developer portal for subscription.
- api monetization
- list api products
- google cloud
- list developers
- manager packaging api products and managing developer relationships.
- list developer apps
- list all registered developers.
- microservices
- get details for a specific developer app including its credentials and product subscriptions.
- registered api developers.
slug: developer-portal-app-management
source_filename: developer-portal-app-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apigee Developer Portal and App Management\n  description: Unified workflow for managing the Apigee developer ecosystem — developers, applications, API product subscriptions,\n    and key management. Provides platform operations teams and API monetization owners a governed surface for onboarding developers,\n    approving apps, and managing API access across products and environments.\n  tags:\n  - Apigee\n  - Developer Portal\n  - App Management\n  - API Monetization\n  - Google Cloud\n  created: '2026-04-20'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: api-management\n    baseUri: https://apigee.googleapis.com/v1\n    description: Apigee API Management REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: api-proxies\n      path: /organizations/{organizationId}/apis\n\
  \      operations:\n      - name: listApiProxies\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: proxies\n          type: array\n          value: $.proxies\n    - name: api-proxy\n      path: /organizations/{organizationId}/apis/{apiId}\n      operations:\n      - name: getApiProxy\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: apiId\n          in: path\n        outputParameters:\n        - name: proxy\n          type: object\n          value: $.\n    - name: api-products\n      path: /organizations/{organizationId}/apiproducts\n      operations:\n      - name: listApiProducts\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        -\
  \ name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: products\n          type: array\n          value: $.products\n    - name: api-product\n      path: /organizations/{organizationId}/apiproducts/{productId}\n      operations:\n      - name: getApiProduct\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: productId\n          in: path\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n    - name: developers\n      path: /organizations/{organizationId}/developers\n      operations:\n      - name: listDevelopers\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: developers\n \
  \         type: array\n          value: $.developers\n    - name: developer\n      path: /organizations/{organizationId}/developers/{developerId}\n      operations:\n      - name: getDeveloper\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        outputParameters:\n        - name: developer\n          type: object\n          value: $.\n    - name: developer-apps\n      path: /organizations/{organizationId}/developers/{developerId}/apps\n      operations:\n      - name: listDeveloperApps\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apps\n          type: array\n          value: $.apps\n    - name: developer-app\n      path: /organizations/{organizationId}/developers/{developerId}/apps/{appId}\n\
  \      operations:\n      - name: getDeveloperApp\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        - name: appId\n          in: path\n        outputParameters:\n        - name: app\n          type: object\n          value: $.\n    - name: environments\n      path: /organizations/{organizationId}/environments\n      operations:\n      - name: listEnvironments\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: environments\n          type: array\n          value: $.environments\n    - name: environment\n      path: /organizations/{organizationId}/environments/{environmentId}\n      operations:\n      - name: getEnvironment\n        method: GET\n        inputParameters:\n        - name: organizationId\n\
  \          in: path\n        - name: environmentId\n          in: path\n        outputParameters:\n        - name: environment\n          type: object\n          value: $.\n    - name: deployments\n      path: /organizations/{organizationId}/deployments\n      operations:\n      - name: listOrganizationDeployments\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: deployments\n          type: array\n          value: $.deployments\n    - name: proxy-deployment\n      path: /organizations/{organizationId}/environments/{environmentId}/apis/{apiId}/revisions/{revisionId}/deployments\n      operations:\n      - name: deployApiProxyRevision\n        method: POST\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n\
  \          in: path\n        - name: apiId\n          in: path\n        - name: revisionId\n          in: path\n        - name: override\n          in: query\n        outputParameters:\n        - name: deployment\n          type: object\n          value: $.\n      - name: undeployApiProxyRevision\n        method: DELETE\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: apiId\n          in: path\n        - name: revisionId\n          in: path\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shared-flows\n      path: /organizations/{organizationId}/sharedflows\n      operations:\n      - name: listSharedFlows\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n      \
  \  - name: sharedFlows\n          type: array\n          value: $.sharedFlows\n    - name: target-servers\n      path: /organizations/{organizationId}/environments/{environmentId}/targetservers\n      operations:\n      - name: listTargetServers\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: targetServers\n          type: array\n          value: $.targetServers\n    - name: analytics-stats\n      path: /organizations/{organizationId}/environments/{environmentId}/stats/{statsType}\n      operations:\n      - name: getEnvironmentStats\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: statsType\n          in: path\n        - name: timeRange\n\
  \          in: query\n        - name: timeUnit\n          in: query\n        - name: filter\n          in: query\n        - name: limit\n          in: query\n        outputParameters:\n        - name: stats\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: apigee-devportal-api\n    description: Unified REST API for Apigee developer portal and app management.\n    resources:\n    - path: /v1/developers\n      name: developers\n      description: Registered API developers.\n      operations:\n      - method: GET\n        name: list-developers\n        description: List all registered developers.\n        call: api-management.listDevelopers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/developer-apps\n      name: developer-apps\n      description: Apps registered by a developer.\n      operations:\n      - method: GET\n        name: list-developer-apps\n        description: List apps for a\
  \ developer.\n        call: api-management.listDeveloperApps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: api-products\n      description: API products available for subscription.\n      operations:\n      - method: GET\n        name: list-products\n        description: List all API products.\n        call: api-management.listApiProducts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: apigee-devportal-mcp\n    transport: http\n    description: MCP server for AI-assisted developer portal and app management.\n    tools:\n    - name: list-developers\n      description: List all developers registered in the Apigee organization.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listDevelopers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-developer\n\
  \      description: Get details for a specific developer including their registered apps.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.getDeveloper\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-developer-apps\n      description: List all apps registered by a developer, including their API product subscriptions.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listDeveloperApps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-developer-app\n      description: Get details for a specific developer app including its credentials and product subscriptions.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.getDeveloperApp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-products\n\
  \      description: List all API products available in the developer portal for subscription.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listApiProducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-product\n      description: Get details for a specific API product including its quota limits and proxy bindings.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.getApiProduct\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
