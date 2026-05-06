---
categories: []
consumed_apis: []
description: Unified capability for managing content in Strapi headless CMS. Combines the REST content API, admin panel API, and users/permissions API into a single workflow for content authors, developers, and platform admins. Enables creating, reading, updating, publishing, and deleting content entries; managing media uploads; configuring roles and permissions; and administering API tokens and webhooks.
layout: capability
name: Strapi Content Management
operations:
- description: List content entries with filtering and pagination
  method: GET
  name: find-entries
  path: /v1/content/{pluralApiId}
- description: Create a new content entry
  method: POST
  name: create-entry
  path: /v1/content/{pluralApiId}
- description: Get a single content entry
  method: GET
  name: find-one-entry
  path: /v1/content/{pluralApiId}/{documentId}
- description: Update a content entry
  method: PUT
  name: update-entry
  path: /v1/content/{pluralApiId}/{documentId}
- description: Delete a content entry
  method: DELETE
  name: delete-entry
  path: /v1/content/{pluralApiId}/{documentId}
- description: List all files in the media library
  method: GET
  name: list-media-files
  path: /v1/media
- description: List administrator accounts
  method: GET
  name: list-admin-users
  path: /v1/admin/users
- description: Create a new administrator
  method: POST
  name: create-admin-user
  path: /v1/admin/users
- description: List administrator roles
  method: GET
  name: list-admin-roles
  path: /v1/admin/roles
- description: List all API tokens
  method: GET
  name: list-api-tokens
  path: /v1/admin/api-tokens
- description: Create a new API token
  method: POST
  name: create-api-token
  path: /v1/admin/api-tokens
- description: List webhook configurations
  method: GET
  name: list-webhooks
  path: /v1/admin/webhooks
- description: Create a new webhook
  method: POST
  name: create-webhook
  path: /v1/admin/webhooks
- description: List registered end-users
  method: GET
  name: list-users
  path: /v1/users
- description: Authenticate a user
  method: POST
  name: login-user
  path: /v1/auth/login
personas: []
provider_name: Strapi
provider_slug: strapi
search_terms:
- list admin roles
- update an existing content entry
- authenticate an end-user and obtain a jwt token
- administrator user management
- create api token
- administrator role management
- list all api tokens configured in strapi
- create a new content entry
- get the currently authenticated user's profile
- user authentication
- end-user account management
- list administrator roles
- authenticate a user
- node.js
- delete a content entry permanently
- list api tokens
- api token management
- webhook configuration management
- create webhook
- register user
- update entry
- find entries
- content management
- find one entry
- create entry
- list user roles and their permissions
- headless cms
- list all administrator roles
- open source
- list all files in the media library
- update a content entry
- delete entry
- list administrator accounts
- list all api tokens
- delete a content entry
- get a single content entry
- create a new api token
- media library management
- list all files in the strapi media library
- list registered end-users
- single content entry management
- content entry collection management
- list admin users
- list content entries with filtering and pagination
- create a new administrator
- create a new administrator account
- cms
- create a new webhook
- list all webhook configurations
- create a new webhook configuration
- list users
- list roles
- list media files
- get authenticated user
- create admin user
- list all registered end-user accounts
- list webhooks
- register a new end-user account
- get a single content entry by document id
- login user
- list content entries for a content-type with filtering and pagination
- list all administrator accounts
- list webhook configurations
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Strapi Content Management\n  description: Unified capability for managing content in Strapi headless CMS. Combines the REST content API, admin panel\n    API, and users/permissions API into a single workflow for content authors, developers, and platform admins. Enables creating,\n    reading, updating, publishing, and deleting content entries; managing media uploads; configuring roles and permissions;\n    and administering API tokens and webhooks.\n  tags:\n  - CMS\n  - Content Management\n  - Headless CMS\n  - Node.js\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STRAPI_JWT_TOKEN: STRAPI_JWT_TOKEN\n    STRAPI_ADMIN_JWT_TOKEN: STRAPI_ADMIN_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: strapi-rest\n    baseUri: https://{host}\n    description: Strapi REST API for content management\n    authentication:\n      type: bearer\n      token: '{{STRAPI_JWT_TOKEN}}'\n    resources:\n\
  \    - name: content-entries\n      path: /api/{pluralApiId}\n      description: CRUD operations on content-type entries\n      operations:\n      - name: find-entries\n        method: GET\n        description: List content entries with filtering, sorting, and pagination\n        inputParameters:\n        - name: pluralApiId\n          in: path\n          type: string\n          required: true\n          description: The plural API identifier of the content-type\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort criteria (e.g., createdAt:desc)\n        - name: pagination[page]\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: pagination[pageSize]\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        - name: populate\n          in: query\n         \
  \ type: string\n          required: false\n          description: Fields to populate (* for all)\n        - name: filters\n          in: query\n          type: object\n          required: false\n          description: Filter criteria using operator syntax\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: Locale code for internationalized content\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Publication status filter (draft or published)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-entry\n        method: POST\n        description: Create a new content entry\n        inputParameters:\n        - name: pluralApiId\n          in: path\n          type: string\n          required: true\n          description: The plural API identifier of the content-type\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: content-entry\n      path: /api/{pluralApiId}/{documentId}\n      description: Single content entry operations\n      operations:\n      - name: find-one-entry\n        method: GET\n        description: Get a single content entry by document ID\n        inputParameters:\n        - name: pluralApiId\n          in: path\n          type: string\n          required: true\n          description: The plural API identifier of the content-type\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: The unique document ID of the entry\n        - name: populate\n          in: query\n          type: string\n          required: false\n          description: Fields to populate\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-entry\n        method: PUT\n        description: Update a content entry by document ID\n        inputParameters:\n        - name: pluralApiId\n          in: path\n          type: string\n          required: true\n          description: The plural API identifier of the content-type\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: The unique document ID of the entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: delete-entry\n        method: DELETE\n        description: Delete a content entry by document ID\n        inputParameters:\n        - name: pluralApiId\n          in: path\n          type: string\n          required:\
  \ true\n          description: The plural API identifier of the content-type\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: The unique document ID of the entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: upload-files\n      path: /api/upload\n      description: File upload and media library management\n      operations:\n      - name: upload-files\n        method: POST\n        description: Upload files to the Strapi media library\n        inputParameters:\n        - name: ref\n          in: query\n          type: string\n          required: false\n          description: API identifier of the content-type to link the file to\n        - name: refId\n          in: query\n          type: string\n          required: false\n          description: Document ID of the entry to link the file to\n        - name: field\n       \
  \   in: query\n          type: string\n          required: false\n          description: Field name on the entry where the file should be linked\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: upload-files-list\n      path: /api/upload/files\n      description: List files in the media library\n      operations:\n      - name: list-upload-files\n        method: GET\n        description: Returns a list of all files in the Strapi media library\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: strapi-admin\n    baseUri: https://{host}\n    description: Strapi Admin Panel API\n    authentication:\n      type: bearer\n      token: '{{STRAPI_ADMIN_JWT_TOKEN}}'\n    resources:\n    - name: admin-users\n      path: /admin/users\n      description: Administrator user account\
  \ management\n      operations:\n      - name: list-admin-users\n        method: GET\n        description: List all administrator accounts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-admin-user\n        method: POST\n        description: Create a new administrator account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstname: '{{tools.firstname}}'\n            lastname: '{{tools.lastname}}'\n            email: '{{tools.email}}'\n\
  \            roles: '{{tools.roles}}'\n    - name: admin-user\n      path: /admin/users/{id}\n      description: Single administrator user operations\n      operations:\n      - name: get-admin-user\n        method: GET\n        description: Get an administrator user by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The administrator user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-admin-user\n        method: PUT\n        description: Update an administrator user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The administrator user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            firstname: '{{tools.firstname}}'\n            lastname: '{{tools.lastname}}'\n            isActive: '{{tools.isActive}}'\n            roles: '{{tools.roles}}'\n      - name: delete-admin-user\n        method: DELETE\n        description: Delete an administrator user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The administrator user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-roles\n      path: /admin/roles\n      description: Administrator role management\n      operations:\n      - name: list-admin-roles\n        method: GET\n        description: List all administrator roles\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-admin-role\n\
  \        method: POST\n        description: Create a custom administrator role\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            permissions: '{{tools.permissions}}'\n    - name: api-tokens\n      path: /admin/api-tokens\n      description: API token management\n      operations:\n      - name: list-api-tokens\n        method: GET\n        description: List all API tokens\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-token\n        method: POST\n        description: Create a new API token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            lifespan: '{{tools.lifespan}}'\n    - name: webhooks\n      path: /admin/webhooks\n      description: Webhook configuration management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhook configurations\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n\
  \            isEnabled: '{{tools.isEnabled}}'\n  - type: http\n    namespace: strapi-users\n    baseUri: https://{host}\n    description: Strapi Users and Permissions API\n    authentication:\n      type: bearer\n      token: '{{STRAPI_JWT_TOKEN}}'\n    resources:\n    - name: user-auth\n      path: /api/auth/local\n      description: User authentication endpoints\n      operations:\n      - name: login-user\n        method: POST\n        description: Authenticate with email/username and password\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n            password: '{{tools.password}}'\n    - name: user-registration\n      path: /api/auth/local/register\n      description: User registration\n      operations:\n      - name: register-user\n        method: POST\n        description:\
  \ Register a new user account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n    - name: users-list\n      path: /api/users\n      description: User account management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all registered user accounts\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: current-user\n      path: /api/users/me\n      description: Current authenticated user profile\n      operations:\n      - name: get-authenticated-user\n        method: GET\n        description: Get the profile of the currently authenticated user\n  \
  \      inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-list\n      path: /api/users-permissions/roles\n      description: User roles management\n      operations:\n      - name: list-roles\n        method: GET\n        description: List all user roles\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: strapi-content-management-api\n    description: Unified REST API for Strapi content management workflows.\n    resources:\n    - path: /v1/content/{pluralApiId}\n      name: content-entries\n      description: Content entry collection management\n      operations:\n      - method: GET\n        name: find-entries\n        description: List content entries with filtering and pagination\n        call: strapi-rest.find-entries\n\
  \        with:\n          pluralApiId: rest.pluralApiId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-entry\n        description: Create a new content entry\n        call: strapi-rest.create-entry\n        with:\n          pluralApiId: rest.pluralApiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/{pluralApiId}/{documentId}\n      name: content-entry\n      description: Single content entry management\n      operations:\n      - method: GET\n        name: find-one-entry\n        description: Get a single content entry\n        call: strapi-rest.find-one-entry\n        with:\n          pluralApiId: rest.pluralApiId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-entry\n        description: Update a content entry\n        call: strapi-rest.update-entry\n    \
  \    with:\n          pluralApiId: rest.pluralApiId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-entry\n        description: Delete a content entry\n        call: strapi-rest.delete-entry\n        with:\n          pluralApiId: rest.pluralApiId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media\n      name: media\n      description: Media library management\n      operations:\n      - method: GET\n        name: list-media-files\n        description: List all files in the media library\n        call: strapi-rest.list-upload-files\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/admin/users\n      name: admin-users\n      description: Administrator user management\n      operations:\n      - method: GET\n        name: list-admin-users\n        description:\
  \ List administrator accounts\n        call: strapi-admin.list-admin-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-admin-user\n        description: Create a new administrator\n        call: strapi-admin.create-admin-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/admin/roles\n      name: admin-roles\n      description: Administrator role management\n      operations:\n      - method: GET\n        name: list-admin-roles\n        description: List administrator roles\n        call: strapi-admin.list-admin-roles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/admin/api-tokens\n      name: api-tokens\n      description: API token management\n      operations:\n      - method: GET\n        name: list-api-tokens\n        description: List all API tokens\n        call: strapi-admin.list-api-tokens\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-token\n        description: Create a new API token\n        call: strapi-admin.create-api-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/admin/webhooks\n      name: webhooks\n      description: Webhook configuration management\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhook configurations\n        call: strapi-admin.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a new webhook\n        call: strapi-admin.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: end-users\n      description: End-user account management\n      operations:\n      - method: GET\n        name: list-users\n        description:\
  \ List registered end-users\n        call: strapi-users.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/login\n      name: auth\n      description: User authentication\n      operations:\n      - method: POST\n        name: login-user\n        description: Authenticate a user\n        call: strapi-users.login-user\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: strapi-content-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Strapi content management.\n    tools:\n    - name: find-entries\n      description: List content entries for a content-type with filtering and pagination\n      hints:\n        readOnly: true\n        openWorld: true\n      call: strapi-rest.find-entries\n      with:\n        pluralApiId: tools.pluralApiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-entry\n   \
  \   description: Create a new content entry\n      hints:\n        readOnly: false\n        destructive: false\n      call: strapi-rest.create-entry\n      with:\n        pluralApiId: tools.pluralApiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-one-entry\n      description: Get a single content entry by document ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: strapi-rest.find-one-entry\n      with:\n        pluralApiId: tools.pluralApiId\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-entry\n      description: Update an existing content entry\n      hints:\n        readOnly: false\n        idempotent: true\n      call: strapi-rest.update-entry\n      with:\n        pluralApiId: tools.pluralApiId\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-entry\n      description:\
  \ Delete a content entry permanently\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: strapi-rest.delete-entry\n      with:\n        pluralApiId: tools.pluralApiId\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-media-files\n      description: List all files in the Strapi media library\n      hints:\n        readOnly: true\n        openWorld: true\n      call: strapi-rest.list-upload-files\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-admin-users\n      description: List all administrator accounts\n      hints:\n        readOnly: true\n      call: strapi-admin.list-admin-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-admin-user\n      description: Create a new administrator account\n      hints:\n        readOnly: false\n      call: strapi-admin.create-admin-user\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-admin-roles\n      description: List all administrator roles\n      hints:\n        readOnly: true\n      call: strapi-admin.list-admin-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-tokens\n      description: List all API tokens configured in Strapi\n      hints:\n        readOnly: true\n      call: strapi-admin.list-api-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-token\n      description: Create a new API token\n      hints:\n        readOnly: false\n      call: strapi-admin.create-api-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List all webhook configurations\n      hints:\n        readOnly: true\n      call: strapi-admin.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n\
  \      description: Create a new webhook configuration\n      hints:\n        readOnly: false\n      call: strapi-admin.create-webhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: login-user\n      description: Authenticate an end-user and obtain a JWT token\n      hints:\n        readOnly: false\n      call: strapi-users.login-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-user\n      description: Register a new end-user account\n      hints:\n        readOnly: false\n      call: strapi-users.register-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-authenticated-user\n      description: Get the currently authenticated user's profile\n      hints:\n        readOnly: true\n      call: strapi-users.get-authenticated-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all registered end-user accounts\n\
  \      hints:\n        readOnly: true\n      call: strapi-users.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List user roles and their permissions\n      hints:\n        readOnly: true\n      call: strapi-users.list-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/strapi/refs/heads/main/capabilities/content-management.yaml
tags:
- CMS
- Content Management
- Headless CMS
- Node.js
tools:
- description: List content entries for a content-type with filtering and pagination
  hints:
    openWorld: true
    readOnly: true
  name: find-entries
- description: Create a new content entry
  hints:
    destructive: false
    readOnly: false
  name: create-entry
- description: Get a single content entry by document ID
  hints:
    openWorld: false
    readOnly: true
  name: find-one-entry
- description: Update an existing content entry
  hints:
    idempotent: true
    readOnly: false
  name: update-entry
- description: Delete a content entry permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-entry
- description: List all files in the Strapi media library
  hints:
    openWorld: true
    readOnly: true
  name: list-media-files
- description: List all administrator accounts
  hints:
    readOnly: true
  name: list-admin-users
- description: Create a new administrator account
  hints:
    readOnly: false
  name: create-admin-user
- description: List all administrator roles
  hints:
    readOnly: true
  name: list-admin-roles
- description: List all API tokens configured in Strapi
  hints:
    readOnly: true
  name: list-api-tokens
- description: Create a new API token
  hints:
    readOnly: false
  name: create-api-token
- description: List all webhook configurations
  hints:
    readOnly: true
  name: list-webhooks
- description: Create a new webhook configuration
  hints:
    readOnly: false
  name: create-webhook
- description: Authenticate an end-user and obtain a JWT token
  hints:
    readOnly: false
  name: login-user
- description: Register a new end-user account
  hints:
    readOnly: false
  name: register-user
- description: Get the currently authenticated user's profile
  hints:
    readOnly: true
  name: get-authenticated-user
- description: List all registered end-user accounts
  hints:
    readOnly: true
  name: list-users
- description: List user roles and their permissions
  hints:
    readOnly: true
  name: list-roles
---
