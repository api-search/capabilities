---
categories: []
consumed_apis:
- apis-guru
description: Workflow capability for discovering, browsing, and retrieving API definitions from the APIs.guru directory. Enables developers and platform teams to programmatically find public APIs, retrieve their OpenAPI specifications, and explore the catalog by provider. The primary persona is an API developer or platform engineer building integrations or cataloging APIs.
layout: capability
name: APIs.guru API Discovery
operations:
- description: List all APIs in the APIs.guru directory
  method: GET
  name: list-apis
  path: /v1/apis
- description: Get directory-wide metrics
  method: GET
  name: get-metrics
  path: /v1/metrics
- description: List all API providers
  method: GET
  name: list-providers
  path: /v1/providers
- description: Get all APIs for a provider
  method: GET
  name: get-provider-apis
  path: /v1/providers/{provider}
- description: List service names for a provider
  method: GET
  name: get-provider-services
  path: /v1/providers/{provider}/services
- description: Get a specific API version definition
  method: GET
  name: get-api-spec
  path: /v1/specs/{provider}/{api}
personas: []
provider_name: APIs.guru
provider_slug: apis-guru
search_terms:
- get api definition
- retrieve the openapi definition for a specific service api version (for multi-service providers)
- a developer building integrations who needs to discover and retrieve api specifications
- list all service names for a provider that has multiple services
- openapi
- get metrics
- get directory-wide metrics
- list providers
- api catalog
- community
- api directory
- list all api provider domain names available in the apis.guru directory
- get provider apis
- services for a specific provider
- directory metrics and statistics
- get all api definitions for a specific provider by domain name (e.g. 'stripe.com', 'twilio.com')
- 'get metrics for the apis.guru directory: total api count, endpoints, providers, and weekly additions'
- finding and retrieving api definitions from public directories
- open source
- statistics and health metrics for the apis.guru directory
- apis for a specific provider
- Platform Engineer
- get provider services
- list all apis in the apis.guru directory
- get directory metrics
- retrieve the openapi definition for a specific api version from the directory
- api providers in the directory
- list all apis in the apis.guru directory with their openapi definition links and metadata
- API Developer
- apis.guru
- list api providers
- all apis in the directory
- get a specific api version definition
- get api spec
- graphql
- list apis
- list service names for a provider
- discover, browse, and retrieve api definitions from the apis.guru directory
- a platform or devx engineer building api catalogs, portals, or governance tooling
- specific api version spec
- api discovery
- list all api providers
- list all apis
- get service api definition
- get all apis for a provider
slug: api-discovery
source_filename: api-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"APIs.guru API Discovery\"\n  description: \"Workflow capability for discovering, browsing, and retrieving API definitions from the APIs.guru directory. Enables developers and platform teams to programmatically find public APIs, retrieve their OpenAPI specifications, and explore the catalog by provider. The primary persona is an API developer or platform engineer building integrations or cataloging APIs.\"\n  tags:\n    - API Catalog\n    - API Directory\n    - API Discovery\n    - APIs.guru\n    - OpenAPI\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: apis-guru\n      location: ./shared/apis-guru-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: api-discovery-api\n      description: \"Unified REST API for API discovery and catalog browsing via APIs.guru.\"\n      resources:\n        - path: /v1/apis\n      \
  \    name: apis\n          description: \"All APIs in the directory\"\n          operations:\n            - method: GET\n              name: list-apis\n              description: \"List all APIs in the APIs.guru directory\"\n              call: \"apis-guru.list-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics\n          name: metrics\n          description: \"Directory metrics and statistics\"\n          operations:\n            - method: GET\n              name: get-metrics\n              description: \"Get directory-wide metrics\"\n              call: \"apis-guru.get-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/providers\n          name: providers\n          description: \"API providers in the directory\"\n          operations:\n            - method: GET\n              name: list-providers\n              description:\
  \ \"List all API providers\"\n              call: \"apis-guru.list-providers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/providers/{provider}\n          name: provider-apis\n          description: \"APIs for a specific provider\"\n          operations:\n            - method: GET\n              name: get-provider-apis\n              description: \"Get all APIs for a provider\"\n              call: \"apis-guru.get-provider\"\n              with:\n                provider: \"rest.provider\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/providers/{provider}/services\n          name: provider-services\n          description: \"Services for a specific provider\"\n          operations:\n            - method: GET\n              name: get-provider-services\n              description: \"List service names for a provider\"\n              call:\
  \ \"apis-guru.get-services\"\n              with:\n                provider: \"rest.provider\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/specs/{provider}/{api}\n          name: api-spec\n          description: \"Specific API version spec\"\n          operations:\n            - method: GET\n              name: get-api-spec\n              description: \"Get a specific API version definition\"\n              call: \"apis-guru.get-api\"\n              with:\n                provider: \"rest.provider\"\n                api: \"rest.api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: api-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API discovery and catalog exploration.\"\n      tools:\n        - name: list-all-apis\n          description: \"List all APIs in the APIs.guru\
  \ directory with their OpenAPI definition links and metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"apis-guru.list-apis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-directory-metrics\n          description: \"Get metrics for the APIs.guru directory: total API count, endpoints, providers, and weekly additions\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"apis-guru.get-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-providers\n          description: \"List all API provider domain names available in the APIs.guru directory\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"apis-guru.list-providers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n     \
  \   - name: get-provider-apis\n          description: \"Get all API definitions for a specific provider by domain name (e.g. 'stripe.com', 'twilio.com')\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"apis-guru.get-provider\"\n          with:\n            provider: \"tools.provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-provider-services\n          description: \"List all service names for a provider that has multiple services\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"apis-guru.get-services\"\n          with:\n            provider: \"tools.provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api-definition\n          description: \"Retrieve the OpenAPI definition for a specific API version from the directory\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"apis-guru.get-api\"\n          with:\n            provider: \"tools.provider\"\n            api: \"tools.api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-service-api-definition\n          description: \"Retrieve the OpenAPI definition for a specific service API version (for multi-service providers)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"apis-guru.get-service-api\"\n          with:\n            provider: \"tools.provider\"\n            service: \"tools.service\"\n            api: \"tools.api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apis-guru/refs/heads/main/capabilities/api-discovery.yaml
tags:
- API Catalog
- API Directory
- API Discovery
- APIs.guru
- OpenAPI
tools:
- description: List all APIs in the APIs.guru directory with their OpenAPI definition links and metadata
  hints:
    openWorld: true
    readOnly: true
  name: list-all-apis
- description: 'Get metrics for the APIs.guru directory: total API count, endpoints, providers, and weekly additions'
  hints:
    openWorld: false
    readOnly: true
  name: get-directory-metrics
- description: List all API provider domain names available in the APIs.guru directory
  hints:
    openWorld: true
    readOnly: true
  name: list-api-providers
- description: Get all API definitions for a specific provider by domain name (e.g. 'stripe.com', 'twilio.com')
  hints:
    openWorld: true
    readOnly: true
  name: get-provider-apis
- description: List all service names for a provider that has multiple services
  hints:
    openWorld: true
    readOnly: true
  name: get-provider-services
- description: Retrieve the OpenAPI definition for a specific API version from the directory
  hints:
    openWorld: true
    readOnly: true
  name: get-api-definition
- description: Retrieve the OpenAPI definition for a specific service API version (for multi-service providers)
  hints:
    openWorld: true
    readOnly: true
  name: get-service-api-definition
---
