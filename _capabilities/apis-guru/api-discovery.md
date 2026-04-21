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
- get directory metrics
- a platform or devx engineer building api catalogs, portals, or governance tooling
- apis.guru
- get a specific api version definition
- Platform Engineer
- 'get metrics for the apis.guru directory: total api count, endpoints, providers, and weekly additions'
- list all api providers
- list all service names for a provider that has multiple services
- services for a specific provider
- list all api provider domain names available in the apis.guru directory
- retrieve the openapi definition for a specific service api version (for multi-service providers)
- openapi
- discover, browse, and retrieve api definitions from the apis.guru directory
- statistics and health metrics for the apis.guru directory
- get service api definition
- graphql
- api catalog
- api providers in the directory
- list all apis in the apis.guru directory
- get all api definitions for a specific provider by domain name (e.g. 'stripe.com', 'twilio.com')
- get api spec
- list all apis
- get metrics
- get provider services
- open source
- apis for a specific provider
- directory metrics and statistics
- specific api version spec
- list service names for a provider
- list api providers
- get provider apis
- get directory-wide metrics
- list providers
- list all apis in the apis.guru directory with their openapi definition links and metadata
- all apis in the directory
- api directory
- API Developer
- get api definition
- community
- a developer building integrations who needs to discover and retrieve api specifications
- retrieve the openapi definition for a specific api version from the directory
- get all apis for a provider
- list apis
- api discovery
- finding and retrieving api definitions from public directories
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
