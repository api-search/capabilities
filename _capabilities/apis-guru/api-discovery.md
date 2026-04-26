---
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
- list all api providers
- list all apis in the apis.guru directory with their openapi definition links and metadata
- get api definition
- get metrics
- get provider apis
- get api spec
- get directory-wide metrics
- a platform or devx engineer building api catalogs, portals, or governance tooling
- community
- services for a specific provider
- list all service names for a provider that has multiple services
- all apis in the directory
- specific api version spec
- list all api provider domain names available in the apis.guru directory
- a developer building integrations who needs to discover and retrieve api specifications
- statistics and health metrics for the apis.guru directory
- api catalog
- API Developer
- get a specific api version definition
- api discovery
- api directory
- list providers
- apis for a specific provider
- openapi
- directory metrics and statistics
- list service names for a provider
- finding and retrieving api definitions from public directories
- apis.guru
- api providers in the directory
- get service api definition
- retrieve the openapi definition for a specific service api version (for multi-service providers)
- list all apis in the apis.guru directory
- open source
- 'get metrics for the apis.guru directory: total api count, endpoints, providers, and weekly additions'
- list apis
- Platform Engineer
- graphql
- get all apis for a provider
- discover, browse, and retrieve api definitions from the apis.guru directory
- get directory metrics
- get all api definitions for a specific provider by domain name (e.g. 'stripe.com', 'twilio.com')
- list api providers
- list all apis
- retrieve the openapi definition for a specific api version from the directory
- get provider services
slug: api-discovery
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
