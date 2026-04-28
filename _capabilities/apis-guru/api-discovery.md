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
- apis for a specific provider
- services for a specific provider
- retrieve the openapi definition for a specific service api version (for multi-service providers)
- get directory-wide metrics
- get api spec
- api discovery
- list all api providers
- get service api definition
- list providers
- specific api version spec
- list all api provider domain names available in the apis.guru directory
- get all api definitions for a specific provider by domain name (e.g. 'stripe.com', 'twilio.com')
- get provider services
- community
- get a specific api version definition
- openapi
- graphql
- list api providers
- apis.guru
- API Developer
- list all apis in the apis.guru directory
- all apis in the directory
- get provider apis
- a developer building integrations who needs to discover and retrieve api specifications
- directory metrics and statistics
- api catalog
- Platform Engineer
- statistics and health metrics for the apis.guru directory
- discover, browse, and retrieve api definitions from the apis.guru directory
- get all apis for a provider
- a platform or devx engineer building api catalogs, portals, or governance tooling
- retrieve the openapi definition for a specific api version from the directory
- list apis
- list all apis in the apis.guru directory with their openapi definition links and metadata
- api providers in the directory
- api directory
- open source
- get directory metrics
- 'get metrics for the apis.guru directory: total api count, endpoints, providers, and weekly additions'
- get metrics
- finding and retrieving api definitions from public directories
- list service names for a provider
- get api definition
- list all apis
- list all service names for a provider that has multiple services
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
