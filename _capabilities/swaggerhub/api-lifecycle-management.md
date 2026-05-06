---
categories: []
consumed_apis: []
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
- list projects in a swaggerhub organization
- api definition management
- get api definition
- retrieve the openapi definition for a specific swaggerhub api version
- get owner apis
- create a new project
- list all members of a swaggerhub organization with their roles
- search apis, domains, and templates
- add organization members
- list all apis for an owner
- list organization members
- create or update api definition
- team management
- api registry
- smartbear
- swaggerhub
- api design
- documentation
- project management
- create project
- openapi
- apis for an owner
- organization member management
- create a new swaggerhub project to organize related apis
- get organization members
- invite users to organization
- ci/cd integrations
- list all teams within a swaggerhub organization
- list organization teams
- list integrations
- get api definition for a version
- create or update an api definition in swaggerhub
- delete api
- search the swaggerhub registry
- list ci/cd integrations configured for a swaggerhub api version
- create or update api
- list integrations for an api version
- search specs
- invite users to a swaggerhub organization
- delete an api
- api management
- list projects
- get organization teams
- search the swaggerhub registry for apis, domains, and templates
- api lifecycle management
- search apis
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SwaggerHub API Lifecycle Management\n  description: 'Workflow capability for managing the full API lifecycle in SwaggerHub: discovering APIs, creating and updating\n    definitions, managing versions, controlling lifecycle settings (publish/unpublish), running integrations, and organizing\n    APIs into projects. Combines the Registry API and User Management API for end-to-end API governance.'\n  tags:\n  - API Design\n  - API Management\n  - API Registry\n  - Documentation\n  - OpenAPI\n  - SmartBear\n  - SwaggerHub\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SWAGGERHUB_API_KEY: SWAGGERHUB_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: swaggerhub-registry\n    baseUri: https://api.swaggerhub.com\n    description: SwaggerHub Registry API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{SWAGGERHUB_API_KEY}}'\n      placement: header\n  \
  \  resources:\n    - name: search\n      path: /specs\n      description: Search APIs, domains, and templates\n      operations:\n      - name: search-specs\n        method: GET\n        description: Search SwaggerHub registry for APIs, domains, and templates\n        inputParameters:\n        - name: specType\n          in: query\n          type: string\n          required: false\n          description: 'Filter by type: API, DOMAIN, TEMPLATE'\n        - name: owner\n          in: query\n          type: string\n          required: false\n        - name: query\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: owner-apis\n      path: /apis/{owner}\n\
  \      description: Owner API management\n      operations:\n      - name: get-owner-apis\n        method: GET\n        description: List APIs for an owner\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-versions\n      path: /apis/{owner}/{api}\n      description: API version management\n      operations:\n      - name: get-api-versions\n        method: GET\n        description: Get all versions of an API\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-or-update-api\n\
  \        method: POST\n        description: Create or update an API definition\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: string\n          required: false\n        - name: isPrivate\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: yaml\n          data:\n            spec: '{{tools.spec}}'\n      - name: delete-api\n        method: DELETE\n        description: Delete all versions of an API\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n         \
  \ required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-definition\n      path: /apis/{owner}/{api}/{version}\n      description: API definition retrieval\n      operations:\n      - name: get-api-definition\n        method: GET\n        description: Get API definition for a specific version\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /apis/{owner}/{api}/{version}/integrations\n      description: CI/CD integration management\n      operations:\n      - name: list-integrations\n\
  \        method: GET\n        description: List integrations for an API version\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects/{owner}\n      description: Project management\n      operations:\n      - name: list-projects\n        method: GET\n        description: List projects for an organization\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n\
  \        method: POST\n        description: Create a new project\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n  - type: http\n    namespace: swaggerhub-user-mgmt\n    baseUri: https://api.swaggerhub.com\n    description: SwaggerHub User Management API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{SWAGGERHUB_API_KEY}}'\n      placement: header\n    resources:\n    - name: org-members\n      path: /orgs/{org}/members\n      description: Organization member management\n      operations:\n      - name: get-organization-members\n        method: GET\n        description: List all members of an organization\n        inputParameters:\n\
  \        - name: org\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: q\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-organization-members\n        method: POST\n        description: Invite users to an organization\n        inputParameters:\n        - name: org\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            members: '{{tools.members}}'\n    - name: org-teams\n      path: /orgs/{org}/teams\n\
  \      description: Team management\n      operations:\n      - name: get-organization-teams\n        method: GET\n        description: List all teams in an organization\n        inputParameters:\n        - name: org\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n        method: POST\n        description: Create a new team\n        inputParameters:\n        - name: org\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: swaggerhub-api-lifecycle-api\n    description: Unified\
  \ REST API for SwaggerHub API lifecycle management.\n    resources:\n    - path: /v1/search\n      name: search\n      description: Search the SwaggerHub registry\n      operations:\n      - method: GET\n        name: search-specs\n        description: Search APIs, domains, and templates\n        call: swaggerhub-registry.search-specs\n        with:\n          query: rest.query\n          specType: rest.specType\n          owner: rest.owner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{owner}\n      name: owner-apis\n      description: APIs for an owner\n      operations:\n      - method: GET\n        name: get-owner-apis\n        description: List all APIs for an owner\n        call: swaggerhub-registry.get-owner-apis\n        with:\n          owner: rest.owner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{owner}/{api}/{version}\n      name: api-definition\n      description: API definition\
  \ management\n      operations:\n      - method: GET\n        name: get-api-definition\n        description: Get API definition for a version\n        call: swaggerhub-registry.get-api-definition\n        with:\n          owner: rest.owner\n          api: rest.api\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{owner}/{api}\n      name: api-management\n      description: API lifecycle management\n      operations:\n      - method: POST\n        name: create-or-update-api\n        description: Create or update API definition\n        call: swaggerhub-registry.create-or-update-api\n        with:\n          owner: rest.owner\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-api\n        description: Delete an API\n        call: swaggerhub-registry.delete-api\n        with:\n          owner: rest.owner\n          api:\
  \ rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations/{owner}/{api}/{version}\n      name: integrations\n      description: CI/CD integrations\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List integrations for an API version\n        call: swaggerhub-registry.list-integrations\n        with:\n          owner: rest.owner\n          api: rest.api\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{owner}\n      name: projects\n      description: Project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List projects\n        call: swaggerhub-registry.list-projects\n        with:\n          owner: rest.owner\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description:\
  \ Create a new project\n        call: swaggerhub-registry.create-project\n        with:\n          owner: rest.owner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orgs/{org}/members\n      name: org-members\n      description: Organization member management\n      operations:\n      - method: GET\n        name: get-organization-members\n        description: List organization members\n        call: swaggerhub-user-mgmt.get-organization-members\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-organization-members\n        description: Invite users to organization\n        call: swaggerhub-user-mgmt.add-organization-members\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orgs/{org}/teams\n      name: org-teams\n      description: Team management\n      operations:\n\
  \      - method: GET\n        name: get-organization-teams\n        description: List organization teams\n        call: swaggerhub-user-mgmt.get-organization-teams\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: swaggerhub-api-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted SwaggerHub API lifecycle management.\n    tools:\n    - name: search-apis\n      description: Search the SwaggerHub registry for APIs, domains, and templates\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swaggerhub-registry.search-specs\n      with:\n        query: tools.query\n        specType: tools.specType\n        owner: tools.owner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-definition\n      description: Retrieve the OpenAPI definition for a specific SwaggerHub API version\n      hints:\n   \
  \     readOnly: true\n        idempotent: true\n      call: swaggerhub-registry.get-api-definition\n      with:\n        owner: tools.owner\n        api: tools.api\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-or-update-api\n      description: Create or update an API definition in SwaggerHub\n      hints:\n        readOnly: false\n        idempotent: true\n      call: swaggerhub-registry.create-or-update-api\n      with:\n        owner: tools.owner\n        api: tools.api\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-integrations\n      description: List CI/CD integrations configured for a SwaggerHub API version\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swaggerhub-registry.list-integrations\n      with:\n        owner: tools.owner\n        api: tools.api\n        version: tools.version\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List projects in a SwaggerHub organization\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swaggerhub-registry.list-projects\n      with:\n        owner: tools.owner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new SwaggerHub project to organize related APIs\n      hints:\n        readOnly: false\n        idempotent: false\n      call: swaggerhub-registry.create-project\n      with:\n        owner: tools.owner\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization-members\n      description: List all members of a SwaggerHub organization with their roles\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swaggerhub-user-mgmt.get-organization-members\n      with:\n\
  \        org: tools.org\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-organization-members\n      description: Invite users to a SwaggerHub organization\n      hints:\n        readOnly: false\n        idempotent: false\n      call: swaggerhub-user-mgmt.add-organization-members\n      with:\n        org: tools.org\n        members: tools.members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization-teams\n      description: List all teams within a SwaggerHub organization\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swaggerhub-user-mgmt.get-organization-teams\n      with:\n        org: tools.org\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
