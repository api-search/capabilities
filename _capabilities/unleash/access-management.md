---
categories: []
consumed_apis: []
description: Workflow capability for managing access control in Unleash, including user management, API token lifecycle, service accounts, and personal access tokens. Used by platform admins and security teams to govern who can access Unleash and with what permissions.
layout: capability
name: Unleash Access Management
operations:
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: List all API tokens
  method: GET
  name: list-tokens
  path: /v1/tokens
- description: Create a new API token
  method: POST
  name: create-token
  path: /v1/tokens
personas: []
provider_name: Unleash
provider_slug: unleash
search_terms:
- list all users in the unleash instance
- developer tools
- create api token
- a/b testing
- feature management
- users
- progressive delivery
- create a new user
- create user
- api token management
- list api tokens
- list tokens
- list all users
- create a new unleash user with email and role assignment
- open source
- list all api tokens
- create a new api token
- unleash
- api tokens
- administration
- create a new api token for an unleash sdk or integration
- access control
- feature flags
- list users
- create token
- user management
- list all api tokens in the unleash instance
slug: access-management
source_filename: access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unleash Access Management\n  description: Workflow capability for managing access control in Unleash, including user management, API token lifecycle,\n    service accounts, and personal access tokens. Used by platform admins and security teams to govern who can access Unleash\n    and with what permissions.\n  tags:\n  - Unleash\n  - Access Control\n  - Users\n  - API Tokens\n  - Administration\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNLEASH_API_TOKEN: UNLEASH_API_TOKEN\n    UNLEASH_BASE_URL: UNLEASH_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: unleash-admin\n    baseUri: '{{UNLEASH_BASE_URL}}'\n    description: Unleash Admin API for feature flag management\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{UNLEASH_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: features\n      path: /api/admin/projects\n      description:\
  \ Feature flag management scoped to projects\n      operations:\n      - name: list-features\n        method: GET\n        description: List All Feature Flags\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-feature\n        method: POST\n        description: Create Feature Flag\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            type: '{{tools.type}}'\n\
  \      - name: get-feature\n        method: GET\n        description: Get Feature Flag\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: featureName\n          in: path\n          type: string\n          required: true\n          description: Feature flag name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enable-feature\n        method: POST\n        description: Enable Feature Flag\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: featureName\n          in: path\n          type: string\n          required: true\n          description: Feature flag name\n        - name: environment\n          in: path\n          type: string\n   \
  \       required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disable-feature\n        method: POST\n        description: Disable Feature Flag\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: featureName\n          in: path\n          type: string\n          required: true\n          description: Feature flag name\n        - name: environment\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /api/admin/projects\n      description: Project management\n      operations:\n      - name: list-projects\n\
  \        method: GET\n        description: List All Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: environments\n      path: /api/admin/environments\n      description: Environment management\n      operations:\n      - name: list-environments\n        method: GET\n        description: List All Environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/admin/user-admin\n      description:\
  \ User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List All Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            name: '{{tools.name}}'\n            rootRole: '{{tools.rootRole}}'\n    - name: api-tokens\n      path: /api/admin/api-tokens\n      description: API token management\n      operations:\n      - name: list-tokens\n        method: GET\n        description: List All API Tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-token\n    \
  \    method: POST\n        description: Create API Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            type: '{{tools.type}}'\n            environment: '{{tools.environment}}'\n            project: '{{tools.project}}'\n    - name: segments\n      path: /api/admin/segments\n      description: Segment management\n      operations:\n      - name: list-segments\n        method: GET\n        description: List All Segments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-segment\n        method: POST\n        description: Create Segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n     \
  \     data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            constraints: '{{tools.constraints}}'\n    - name: events\n      path: /api/admin/events\n      description: Event log access\n      operations:\n      - name: list-events\n        method: GET\n        description: List All Events\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          required: false\n          description: Filter events by project\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of events to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: unleash-access-api\n    description: Unified REST API for Unleash access and token management.\n    resources:\n    - path: /v1/users\n      name: users\n\
  \      description: User management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: unleash-admin.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user\n        call: unleash-admin.create-user\n        with:\n          email: rest.email\n          name: rest.name\n          rootRole: rest.rootRole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: api-tokens\n      description: API token management\n      operations:\n      - method: GET\n        name: list-tokens\n        description: List all API tokens\n        call: unleash-admin.list-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-token\n        description: Create a new API token\n        call: unleash-admin.create-token\n\
  \        with:\n          username: rest.username\n          type: rest.type\n          environment: rest.environment\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: unleash-access-mcp\n    transport: http\n    description: MCP server for AI-assisted Unleash access management.\n    tools:\n    - name: list-users\n      description: List all users in the Unleash instance\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unleash-admin.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new Unleash user with email and role assignment\n      hints:\n        readOnly: false\n        destructive: false\n      call: unleash-admin.create-user\n      with:\n        email: tools.email\n        name: tools.name\n        rootRole: tools.rootRole\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-api-tokens\n      description: List all API tokens in the Unleash instance\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unleash-admin.list-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-token\n      description: Create a new API token for an Unleash SDK or integration\n      hints:\n        readOnly: false\n        destructive: false\n      call: unleash-admin.create-token\n      with:\n        username: tools.username\n        type: tools.type\n        environment: tools.environment\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unleash/refs/heads/main/capabilities/access-management.yaml
tags:
- Unleash
- Access Control
- Users
- API Tokens
- Administration
tools:
- description: List all users in the Unleash instance
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Create a new Unleash user with email and role assignment
  hints:
    destructive: false
    readOnly: false
  name: create-user
- description: List all API tokens in the Unleash instance
  hints:
    openWorld: false
    readOnly: true
  name: list-api-tokens
- description: Create a new API token for an Unleash SDK or integration
  hints:
    destructive: false
    readOnly: false
  name: create-api-token
---
