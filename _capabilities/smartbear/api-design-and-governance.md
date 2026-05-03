---
categories: []
consumed_apis:
- swaggerhub
description: Unified workflow capability for API design, documentation, and governance using SmartBear's SwaggerHub platform. Supports API teams in discovering existing APIs, managing API definitions through their lifecycle, enforcing design standards via Spectral rulesets, and collaborating through projects and integrations.
layout: capability
name: SmartBear API Design And Governance
operations:
- description: List all APIs for an organization or user
  method: GET
  name: get-owner-apis
  path: /v1/apis/{owner}
- description: Get all versions of a specific API
  method: GET
  name: get-api-versions
  path: /v1/apis/{owner}/{api}/versions
- description: Retrieve the OpenAPI definition for a specific version
  method: GET
  name: get-definition
  path: /v1/apis/{owner}/{api}/{version}/definition
- description: Publish a specific API version
  method: POST
  name: publish-api
  path: /v1/apis/{owner}/{api}/{version}/publish
- description: List integrations for an API version
  method: GET
  name: get-api-integrations
  path: /v1/apis/{owner}/{api}/{version}/integrations
- description: Create a new CI/CD or third-party integration
  method: POST
  name: create-api-integration
  path: /v1/apis/{owner}/{api}/{version}/integrations
- description: List all domains for an owner
  method: GET
  name: get-owner-domains
  path: /v1/domains/{owner}
- description: List all projects for an owner
  method: GET
  name: get-owner-projects
  path: /v1/projects/{owner}
- description: Create a new API project
  method: POST
  name: create-project
  path: /v1/projects/{owner}
- description: Search the public SwaggerHub API catalog
  method: GET
  name: search-apis
  path: /v1/search
personas: []
provider_name: SmartBear
provider_slug: smartbear
search_terms:
- manage api projects
- search the swaggerhub public api catalog for existing apis
- api testing
- list projects
- monitoring
- manage api integrations with ci/cd and third-party tools
- retrieve the complete openapi definition for a specific api version
- list all api projects organized by an owner
- manage api versions
- api governance
- list all domains for an owner
- configure a new ci/cd or third-party integration for an api
- contract testing
- get owner projects
- create a new ci/cd or third-party integration
- create project
- get owner domains
- search the public swaggerhub api catalog
- smartbear
- publish a specific api version to make it publicly available
- list apis
- api design
- list api integrations
- discover apis in the swaggerhub catalog
- manage reusable schema domains
- get api versions
- api documentation
- get all versions of a specific api
- get api definition
- create api integration
- collaboration
- list domains
- publish a specific api version
- list all apis for an organization or user
- list all api definitions for an organization or user in swaggerhub
- list all reusable schema domains for an owner
- documentation
- get owner apis
- publish and lifecycle management
- get all available versions of a specific api
- list all ci/cd and third-party integrations configured for an api version
- create a new api project to organize related apis
- governance
- platform
- create a new api project
- swaggerhub
- retrieve the openapi definition for a specific version
- get api integrations
- list integrations for an api version
- search apis
- access api definitions
- publish api version
- browse and manage api definitions
- search api catalog
- list all projects for an owner
- get definition
- publish api
slug: api-design-and-governance
source_filename: api-design-and-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: SmartBear API Design And Governance\n  description: >-\n    Unified workflow capability for API design, documentation, and governance\n    using SmartBear's SwaggerHub platform. Supports API teams in discovering\n    existing APIs, managing API definitions through their lifecycle, enforcing\n    design standards via Spectral rulesets, and collaborating through projects\n    and integrations.\n  tags:\n    - SmartBear\n    - API Design\n    - API Governance\n    - SwaggerHub\n    - Documentation\n    - Collaboration\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SWAGGERHUB_API_KEY: SWAGGERHUB_API_KEY\n\ncapability:\n  consumes:\n    - import: swaggerhub\n      location: ./shared/swaggerhub.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: smartbear-governance-api\n      description: Unified REST API for API design and governance workflows.\n      resources:\n\
  \        - path: /v1/apis/{owner}\n          name: apis\n          description: Browse and manage API definitions\n          operations:\n            - method: GET\n              name: get-owner-apis\n              description: List all APIs for an organization or user\n              call: \"swaggerhub.get-owner-apis\"\n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{owner}/{api}/versions\n          name: api-versions\n          description: Manage API versions\n          operations:\n            - method: GET\n              name: get-api-versions\n              description: Get all versions of a specific API\n              call: \"swaggerhub.get-api-versions\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/apis/{owner}/{api}/{version}/definition\n          name: api-definition\n          description: Access API definitions\n          operations:\n            - method: GET\n              name: get-definition\n              description: Retrieve the OpenAPI definition for a specific version\n              call: \"swaggerhub.get-definition\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{owner}/{api}/{version}/publish\n          name: api-publish\n          description: Publish and lifecycle management\n          operations:\n            - method: POST\n              name: publish-api\n              description: Publish a specific API version\n              call: \"swaggerhub.publish-api\"\n              with:\n                owner: \"rest.owner\"\n    \
  \            api: \"rest.api\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{owner}/{api}/{version}/integrations\n          name: integrations\n          description: Manage API integrations with CI/CD and third-party tools\n          operations:\n            - method: GET\n              name: get-api-integrations\n              description: List integrations for an API version\n              call: \"swaggerhub.get-api-integrations\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-integration\n              description: Create a new CI/CD or third-party integration\n              call: \"swaggerhub.create-api-integration\"\
  \n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/domains/{owner}\n          name: domains\n          description: Manage reusable schema domains\n          operations:\n            - method: GET\n              name: get-owner-domains\n              description: List all domains for an owner\n              call: \"swaggerhub.get-owner-domains\"\n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{owner}\n          name: projects\n          description: Manage API projects\n          operations:\n            - method: GET\n              name: get-owner-projects\n              description: List all projects for an owner\n              call: \"swaggerhub.get-owner-projects\"\
  \n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: Create a new API project\n              call: \"swaggerhub.create-project\"\n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: Discover APIs in the SwaggerHub catalog\n          operations:\n            - method: GET\n              name: search-apis\n              description: Search the public SwaggerHub API catalog\n              call: \"swaggerhub.search-apis\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n\
  \      namespace: smartbear-governance-mcp\n      transport: http\n      description: MCP server for AI-assisted API design and governance.\n      tools:\n        - name: list-apis\n          description: List all API definitions for an organization or user in SwaggerHub\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"swaggerhub.get-owner-apis\"\n          with:\n            owner: \"tools.owner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-versions\n          description: Get all available versions of a specific API\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"swaggerhub.get-api-versions\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-definition\n          description: Retrieve\
  \ the complete OpenAPI definition for a specific API version\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"swaggerhub.get-definition\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-api-version\n          description: Publish a specific API version to make it publicly available\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"swaggerhub.publish-api\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-api-catalog\n          description: Search the SwaggerHub public API catalog for existing APIs\n          hints:\n       \
  \     readOnly: true\n            openWorld: true\n          call: \"swaggerhub.search-apis\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-integrations\n          description: List all CI/CD and third-party integrations configured for an API version\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"swaggerhub.get-api-integrations\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-api-integration\n          description: Configure a new CI/CD or third-party integration for an API\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"swaggerhub.create-api-integration\"\n          with:\n           \
  \ owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-domains\n          description: List all reusable schema domains for an owner\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"swaggerhub.get-owner-domains\"\n          with:\n            owner: \"tools.owner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: List all API projects organized by an owner\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"swaggerhub.get-owner-projects\"\n          with:\n            owner: \"tools.owner\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-project\n          description: Create a new API project to\
  \ organize related APIs\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"swaggerhub.create-project\"\n          with:\n            owner: \"tools.owner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/smartbear/refs/heads/main/capabilities/api-design-and-governance.yaml
tags:
- SmartBear
- API Design
- API Governance
- SwaggerHub
- Documentation
- Collaboration
tools:
- description: List all API definitions for an organization or user in SwaggerHub
  hints:
    openWorld: true
    readOnly: true
  name: list-apis
- description: Get all available versions of a specific API
  hints:
    openWorld: false
    readOnly: true
  name: get-api-versions
- description: Retrieve the complete OpenAPI definition for a specific API version
  hints:
    openWorld: false
    readOnly: true
  name: get-api-definition
- description: Publish a specific API version to make it publicly available
  hints:
    idempotent: false
    readOnly: false
  name: publish-api-version
- description: Search the SwaggerHub public API catalog for existing APIs
  hints:
    openWorld: true
    readOnly: true
  name: search-api-catalog
- description: List all CI/CD and third-party integrations configured for an API version
  hints:
    openWorld: false
    readOnly: true
  name: list-api-integrations
- description: Configure a new CI/CD or third-party integration for an API
  hints:
    idempotent: false
    readOnly: false
  name: create-api-integration
- description: List all reusable schema domains for an owner
  hints:
    openWorld: false
    readOnly: true
  name: list-domains
- description: List all API projects organized by an owner
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new API project to organize related APIs
  hints:
    idempotent: false
    readOnly: false
  name: create-project
---
