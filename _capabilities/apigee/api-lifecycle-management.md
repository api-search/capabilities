---
categories:
- api-management
consumed_apis: []
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
- manage api developers.
- list developers
- API Platform Engineer
- API Governance Lead
- list environments
- list api products.
- analytics
- developer portal
- Platform Architect
- enterprise
- manage api proxies.
- api lifecycle
- apigee
- api governance
- integrations
- list api products
- list all environments (e.g., dev, staging, prod) in the organization.
- list api proxies.
- API Product Manager
- hybrid
- monetization
- list all apis catalogued in apigee api hub for discovery and governance.
- list api proxies
- list hub apis
- api hub
- list all registered api developers in the organization.
- list proxies
- api gateway
- api management
- list all api proxies in an apigee organization.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- manager packaging api products and managing developer relationships.
- manage api products.
- list products
- list developers.
- engineer managing api proxies, deployments, and policies in apigee.
- architect overseeing api platform strategy and governance across the organization.
- microservices
- google cloud
- list all api products packaged for developer consumption.
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apigee API Lifecycle Management\n  description: Unified workflow for managing the full API lifecycle on Google Apigee - from API proxy creation and deployment\n    to developer portal management, product packaging, and analytics.\n  tags:\n  - Apigee\n  - API Management\n  - API Lifecycle\n  - Google Cloud\n  - Developer Portal\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: api-management\n    baseUri: https://apigee.googleapis.com/v1\n    description: Apigee API Management REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: api-proxies\n      path: /organizations/{organizationId}/apis\n      operations:\n      - name: listApiProxies\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n\
  \        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: proxies\n          type: array\n          value: $.proxies\n    - name: api-proxy\n      path: /organizations/{organizationId}/apis/{apiId}\n      operations:\n      - name: getApiProxy\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: apiId\n          in: path\n        outputParameters:\n        - name: proxy\n          type: object\n          value: $.\n    - name: api-products\n      path: /organizations/{organizationId}/apiproducts\n      operations:\n      - name: listApiProducts\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: products\n          type:\
  \ array\n          value: $.products\n    - name: api-product\n      path: /organizations/{organizationId}/apiproducts/{productId}\n      operations:\n      - name: getApiProduct\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: productId\n          in: path\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n    - name: developers\n      path: /organizations/{organizationId}/developers\n      operations:\n      - name: listDevelopers\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: developers\n          type: array\n          value: $.developers\n    - name: developer\n      path: /organizations/{organizationId}/developers/{developerId}\n      operations:\n\
  \      - name: getDeveloper\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        outputParameters:\n        - name: developer\n          type: object\n          value: $.\n    - name: developer-apps\n      path: /organizations/{organizationId}/developers/{developerId}/apps\n      operations:\n      - name: listDeveloperApps\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apps\n          type: array\n          value: $.apps\n    - name: developer-app\n      path: /organizations/{organizationId}/developers/{developerId}/apps/{appId}\n      operations:\n      - name: getDeveloperApp\n        method: GET\n        inputParameters:\n        - name: organizationId\n\
  \          in: path\n        - name: developerId\n          in: path\n        - name: appId\n          in: path\n        outputParameters:\n        - name: app\n          type: object\n          value: $.\n    - name: environments\n      path: /organizations/{organizationId}/environments\n      operations:\n      - name: listEnvironments\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: environments\n          type: array\n          value: $.environments\n    - name: environment\n      path: /organizations/{organizationId}/environments/{environmentId}\n      operations:\n      - name: getEnvironment\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        outputParameters:\n        - name: environment\n\
  \          type: object\n          value: $.\n    - name: deployments\n      path: /organizations/{organizationId}/deployments\n      operations:\n      - name: listOrganizationDeployments\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: deployments\n          type: array\n          value: $.deployments\n    - name: proxy-deployment\n      path: /organizations/{organizationId}/environments/{environmentId}/apis/{apiId}/revisions/{revisionId}/deployments\n      operations:\n      - name: deployApiProxyRevision\n        method: POST\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: apiId\n          in: path\n        - name: revisionId\n          in: path\n        -\
  \ name: override\n          in: query\n        outputParameters:\n        - name: deployment\n          type: object\n          value: $.\n      - name: undeployApiProxyRevision\n        method: DELETE\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: apiId\n          in: path\n        - name: revisionId\n          in: path\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shared-flows\n      path: /organizations/{organizationId}/sharedflows\n      operations:\n      - name: listSharedFlows\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: sharedFlows\n          type: array\n          value: $.sharedFlows\n    - name: target-servers\n      path: /organizations/{organizationId}/environments/{environmentId}/targetservers\n\
  \      operations:\n      - name: listTargetServers\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: targetServers\n          type: array\n          value: $.targetServers\n    - name: analytics-stats\n      path: /organizations/{organizationId}/environments/{environmentId}/stats/{statsType}\n      operations:\n      - name: getEnvironmentStats\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: statsType\n          in: path\n        - name: timeRange\n          in: query\n        - name: timeUnit\n          in: query\n        - name: filter\n          in: query\n        - name: limit\n          in: query\n        outputParameters:\n   \
  \     - name: stats\n          type: object\n          value: $.\n  - type: http\n    namespace: api-hub\n    baseUri: https://apihub.googleapis.com/v1\n    description: Apigee API Hub REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: apis\n      path: /projects/{projectId}/locations/{locationId}/apis\n      operations:\n      - name: listApis\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: apis\n          type: array\n          value: $.apis\n    - name: api\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}\n      operations:\n      - name: getApi\n        method: GET\n        inputParameters:\n        - name: projectId\n\
  \          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        outputParameters:\n        - name: api\n          type: object\n          value: $.\n    - name: api-versions\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions\n      operations:\n      - name: listApiVersions\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: versions\n          type: array\n          value: $.versions\n    - name: api-specs\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs\n      operations:\n      - name: listApiSpecs\n        method: GET\n        inputParameters:\n        - name: projectId\n          in:\
  \ path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: specs\n          type: array\n          value: $.specs\n    - name: api-spec-contents\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs/{specId}:getContents\n      operations:\n      - name: getApiSpecContents\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: specId\n          in: path\n        outputParameters:\n        - name: contents\n          type: object\n          value: $.\n    - name: api-spec-lint\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs/{specId}:lint\n\
  \      operations:\n      - name: lintApiSpec\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: specId\n          in: path\n        outputParameters:\n        - name: operation\n          type: object\n          value: $.\n    - name: deployments\n      path: /projects/{projectId}/locations/{locationId}/deployments\n      operations:\n      - name: listDeployments\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: deployments\n          type: array\n          value: $.deployments\n    - name: dependencies\n      path: /projects/{projectId}/locations/{locationId}/dependencies\n\
  \      operations:\n      - name: listDependencies\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: dependencies\n          type: array\n          value: $.dependencies\n    - name: search\n      path: /projects/{projectId}/locations/{locationId}:searchResources\n      operations:\n      - name: searchResources\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        outputParameters:\n        - name: searchResults\n          type: array\n          value: $.searchResults\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apigee-lifecycle-api\n    description: Unified REST API for Apigee API lifecycle management.\n\
  \    resources:\n    - path: /v1/proxies\n      name: api-proxies\n      description: Manage API proxies.\n      operations:\n      - method: GET\n        name: list-proxies\n        description: List API proxies.\n        call: api-management.listApiProxies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: api-products\n      description: Manage API products.\n      operations:\n      - method: GET\n        name: list-products\n        description: List API products.\n        call: api-management.listApiProducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/developers\n      name: developers\n      description: Manage API developers.\n      operations:\n      - method: GET\n        name: list-developers\n        description: List developers.\n        call: api-management.listDevelopers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n   \
  \ port: 9090\n    namespace: apigee-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Apigee API lifecycle management.\n    tools:\n    - name: list-api-proxies\n      description: List all API proxies in an Apigee organization.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listApiProxies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-products\n      description: List all API products packaged for developer consumption.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listApiProducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-developers\n      description: List all registered API developers in the organization.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listDevelopers\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List all environments (e.g., dev, staging, prod) in the organization.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listEnvironments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hub-apis\n      description: List all APIs catalogued in Apigee API Hub for discovery and governance.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-hub.listApis\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/api-lifecycle-management.yaml
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
