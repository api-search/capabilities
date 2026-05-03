---
api_specs:
- filename: swaggerhub-user-management-openapi.yml
  format: yaml
  label: swaggerhub-user-mgmt
  slug: swaggerhub-user-mgmt
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/swaggerhub/refs/heads/main/openapi/swaggerhub-user-management-openapi.yml
categories: []
consumed_apis:
- swaggerhub-registry
- swaggerhub-user-mgmt
description: 'Workflow capability for managing the full API lifecycle in SwaggerHub: discovering APIs, creating and updating definitions, managing versions, controlling lifecycle settings (publish/unpublish), running integrations, and organizing APIs into projects. Combines the Registry API and User Management API for end-to-end API governance.'
layout: capability
name: SwaggerHub API Lifecycle Management
operations:
- description: Search APIs, domains, and templates
  method: GET
  name: search-specs
  path: /v1/search
- description: List all APIs for an owner
  method: GET
  name: get-owner-apis
  path: /v1/apis/{owner}
- description: Get API definition for a version
  method: GET
  name: get-api-definition
  path: /v1/apis/{owner}/{api}/{version}
- description: Create or update API definition
  method: POST
  name: create-or-update-api
  path: /v1/apis/{owner}/{api}
- description: Delete an API
  method: DELETE
  name: delete-api
  path: /v1/apis/{owner}/{api}
- description: List integrations for an API version
  method: GET
  name: list-integrations
  path: /v1/integrations/{owner}/{api}/{version}
- description: List projects
  method: GET
  name: list-projects
  path: /v1/projects/{owner}
- description: Create a new project
  method: POST
  name: create-project
  path: /v1/projects/{owner}
- description: List organization members
  method: GET
  name: get-organization-members
  path: /v1/orgs/{org}/members
- description: Invite users to organization
  method: POST
  name: add-organization-members
  path: /v1/orgs/{org}/members
- description: List organization teams
  method: GET
  name: get-organization-teams
  path: /v1/orgs/{org}/teams
personas: []
provider_name: SwaggerHub
provider_slug: swaggerhub
search_terms:
- get api definition for a version
- list projects
- invite users to a swaggerhub organization
- api definition management
- search the swaggerhub registry
- list organization members
- create project
- api management
- list organization teams
- smartbear
- api design
- get organization members
- team management
- create or update an api definition in swaggerhub
- project management
- search apis, domains, and templates
- search the swaggerhub registry for apis, domains, and templates
- api lifecycle management
- retrieve the openapi definition for a specific swaggerhub api version
- get api definition
- list all teams within a swaggerhub organization
- apis for an owner
- list projects in a swaggerhub organization
- add organization members
- search specs
- get organization teams
- create or update api definition
- openapi
- create or update api
- documentation
- get owner apis
- delete an api
- api registry
- list integrations
- create a new project
- ci/cd integrations
- list all members of a swaggerhub organization with their roles
- invite users to organization
- delete api
- create a new swaggerhub project to organize related apis
- swaggerhub
- list ci/cd integrations configured for a swaggerhub api version
- list all apis for an owner
- organization member management
- list integrations for an api version
- search apis
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SwaggerHub API Lifecycle Management\"\n  description: >-\n    Workflow capability for managing the full API lifecycle in SwaggerHub:\n    discovering APIs, creating and updating definitions, managing versions,\n    controlling lifecycle settings (publish/unpublish), running integrations,\n    and organizing APIs into projects. Combines the Registry API and User\n    Management API for end-to-end API governance.\n  tags:\n    - API Design\n    - API Management\n    - API Registry\n    - Documentation\n    - OpenAPI\n    - SmartBear\n    - SwaggerHub\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SWAGGERHUB_API_KEY: SWAGGERHUB_API_KEY\n\ncapability:\n  consumes:\n    - import: swaggerhub-registry\n      location: ./shared/swaggerhub-registry.yaml\n    - import: swaggerhub-user-mgmt\n      location: ./shared/swaggerhub-user-management.yaml\n\n  exposes:\n    - type: rest\n  \
  \    port: 8080\n      namespace: swaggerhub-api-lifecycle-api\n      description: \"Unified REST API for SwaggerHub API lifecycle management.\"\n      resources:\n        - path: /v1/search\n          name: search\n          description: \"Search the SwaggerHub registry\"\n          operations:\n            - method: GET\n              name: search-specs\n              description: \"Search APIs, domains, and templates\"\n              call: \"swaggerhub-registry.search-specs\"\n              with:\n                query: \"rest.query\"\n                specType: \"rest.specType\"\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apis/{owner}\n          name: owner-apis\n          description: \"APIs for an owner\"\n          operations:\n            - method: GET\n              name: get-owner-apis\n              description: \"List all APIs for an owner\"\n              call:\
  \ \"swaggerhub-registry.get-owner-apis\"\n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apis/{owner}/{api}/{version}\n          name: api-definition\n          description: \"API definition management\"\n          operations:\n            - method: GET\n              name: get-api-definition\n              description: \"Get API definition for a version\"\n              call: \"swaggerhub-registry.get-api-definition\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apis/{owner}/{api}\n          name: api-management\n          description: \"API lifecycle management\"\n          operations:\n            - method: POST\n              name: create-or-update-api\n\
  \              description: \"Create or update API definition\"\n              call: \"swaggerhub-registry.create-or-update-api\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-api\n              description: \"Delete an API\"\n              call: \"swaggerhub-registry.delete-api\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integrations/{owner}/{api}/{version}\n          name: integrations\n          description: \"CI/CD integrations\"\n          operations:\n            - method: GET\n              name: list-integrations\n              description: \"List integrations for an API version\"\n              call:\
  \ \"swaggerhub-registry.list-integrations\"\n              with:\n                owner: \"rest.owner\"\n                api: \"rest.api\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{owner}\n          name: projects\n          description: \"Project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List projects\"\n              call: \"swaggerhub-registry.list-projects\"\n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new project\"\n              call: \"swaggerhub-registry.create-project\"\n              with:\n                owner: \"rest.owner\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orgs/{org}/members\n          name: org-members\n          description: \"Organization member management\"\n          operations:\n            - method: GET\n              name: get-organization-members\n              description: \"List organization members\"\n              call: \"swaggerhub-user-mgmt.get-organization-members\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-organization-members\n              description: \"Invite users to organization\"\n              call: \"swaggerhub-user-mgmt.add-organization-members\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orgs/{org}/teams\n          name: org-teams\n\
  \          description: \"Team management\"\n          operations:\n            - method: GET\n              name: get-organization-teams\n              description: \"List organization teams\"\n              call: \"swaggerhub-user-mgmt.get-organization-teams\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: swaggerhub-api-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SwaggerHub API lifecycle management.\"\n      tools:\n        - name: search-apis\n          description: \"Search the SwaggerHub registry for APIs, domains, and templates\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swaggerhub-registry.search-specs\"\n          with:\n            query: \"tools.query\"\n            specType: \"tools.specType\"\n            owner: \"tools.owner\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api-definition\n          description: \"Retrieve the OpenAPI definition for a specific SwaggerHub API version\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swaggerhub-registry.get-api-definition\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-or-update-api\n          description: \"Create or update an API definition in SwaggerHub\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"swaggerhub-registry.create-or-update-api\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: list-integrations\n          description: \"List CI/CD integrations configured for a SwaggerHub API version\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swaggerhub-registry.list-integrations\"\n          with:\n            owner: \"tools.owner\"\n            api: \"tools.api\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-projects\n          description: \"List projects in a SwaggerHub organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swaggerhub-registry.list-projects\"\n          with:\n            owner: \"tools.owner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-project\n          description: \"Create a new SwaggerHub project to organize related\
  \ APIs\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"swaggerhub-registry.create-project\"\n          with:\n            owner: \"tools.owner\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-organization-members\n          description: \"List all members of a SwaggerHub organization with their roles\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swaggerhub-user-mgmt.get-organization-members\"\n          with:\n            org: \"tools.org\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-organization-members\n          description: \"Invite users to a SwaggerHub organization\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"swaggerhub-user-mgmt.add-organization-members\"\
  \n          with:\n            org: \"tools.org\"\n            members: \"tools.members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-organization-teams\n          description: \"List all teams within a SwaggerHub organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swaggerhub-user-mgmt.get-organization-teams\"\n          with:\n            org: \"tools.org\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/swaggerhub/refs/heads/main/capabilities/api-lifecycle-management.yaml
tags:
- API Design
- API Management
- API Registry
- Documentation
- OpenAPI
- SmartBear
- SwaggerHub
tools:
- description: Search the SwaggerHub registry for APIs, domains, and templates
  hints:
    idempotent: true
    readOnly: true
  name: search-apis
- description: Retrieve the OpenAPI definition for a specific SwaggerHub API version
  hints:
    idempotent: true
    readOnly: true
  name: get-api-definition
- description: Create or update an API definition in SwaggerHub
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-api
- description: List CI/CD integrations configured for a SwaggerHub API version
  hints:
    idempotent: true
    readOnly: true
  name: list-integrations
- description: List projects in a SwaggerHub organization
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new SwaggerHub project to organize related APIs
  hints:
    idempotent: false
    readOnly: false
  name: create-project
- description: List all members of a SwaggerHub organization with their roles
  hints:
    idempotent: true
    readOnly: true
  name: get-organization-members
- description: Invite users to a SwaggerHub organization
  hints:
    idempotent: false
    readOnly: false
  name: add-organization-members
- description: List all teams within a SwaggerHub organization
  hints:
    idempotent: true
    readOnly: true
  name: get-organization-teams
---
