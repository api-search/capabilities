---
categories: []
consumed_apis:
- strapi-rest
- strapi-admin
- strapi-users
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
- authenticate an end-user and obtain a jwt token
- cms
- register a new end-user account
- node.js
- list admin roles
- list all files in the strapi media library
- list users
- list all api tokens configured in strapi
- delete a content entry
- create a new webhook configuration
- update a content entry
- list admin users
- list administrator roles
- list all files in the media library
- register user
- list content entries for a content-type with filtering and pagination
- update an existing content entry
- list all administrator roles
- end-user account management
- open source
- list roles
- list all registered end-user accounts
- create a new content entry
- list media files
- administrator role management
- create admin user
- create a new api token
- create webhook
- user authentication
- get a single content entry by document id
- list all webhook configurations
- get authenticated user
- list registered end-users
- list content entries with filtering and pagination
- administrator user management
- api token management
- list all api tokens
- get a single content entry
- login user
- list all administrator accounts
- create api token
- find entries
- create entry
- single content entry management
- create a new webhook
- delete entry
- find one entry
- media library management
- authenticate a user
- get the currently authenticated user's profile
- list user roles and their permissions
- list webhook configurations
- create a new administrator account
- headless cms
- list api tokens
- list administrator accounts
- create a new administrator
- webhook configuration management
- delete a content entry permanently
- content management
- content entry collection management
- list webhooks
- update entry
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Strapi Content Management\"\n  description: >-\n    Unified capability for managing content in Strapi headless CMS. Combines\n    the REST content API, admin panel API, and users/permissions API into a\n    single workflow for content authors, developers, and platform admins.\n    Enables creating, reading, updating, publishing, and deleting content\n    entries; managing media uploads; configuring roles and permissions;\n    and administering API tokens and webhooks.\n  tags:\n    - CMS\n    - Content Management\n    - Headless CMS\n    - Node.js\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STRAPI_JWT_TOKEN: STRAPI_JWT_TOKEN\n      STRAPI_ADMIN_JWT_TOKEN: STRAPI_ADMIN_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: strapi-rest\n      location: ./shared/rest-api.yaml\n    - import: strapi-admin\n      location: ./shared/admin-panel-api.yaml\n    - import: strapi-users\n\
  \      location: ./shared/users-permissions-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: strapi-content-management-api\n      description: \"Unified REST API for Strapi content management workflows.\"\n      resources:\n        - path: /v1/content/{pluralApiId}\n          name: content-entries\n          description: \"Content entry collection management\"\n          operations:\n            - method: GET\n              name: find-entries\n              description: \"List content entries with filtering and pagination\"\n              call: \"strapi-rest.find-entries\"\n              with:\n                pluralApiId: \"rest.pluralApiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-entry\n              description: \"Create a new content entry\"\n              call: \"strapi-rest.create-entry\"\n              with:\n                pluralApiId:\
  \ \"rest.pluralApiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/{pluralApiId}/{documentId}\n          name: content-entry\n          description: \"Single content entry management\"\n          operations:\n            - method: GET\n              name: find-one-entry\n              description: \"Get a single content entry\"\n              call: \"strapi-rest.find-one-entry\"\n              with:\n                pluralApiId: \"rest.pluralApiId\"\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-entry\n              description: \"Update a content entry\"\n              call: \"strapi-rest.update-entry\"\n              with:\n                pluralApiId: \"rest.pluralApiId\"\n                documentId: \"rest.documentId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-entry\n              description: \"Delete a content entry\"\n              call: \"strapi-rest.delete-entry\"\n              with:\n                pluralApiId: \"rest.pluralApiId\"\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/media\n          name: media\n          description: \"Media library management\"\n          operations:\n            - method: GET\n              name: list-media-files\n              description: \"List all files in the media library\"\n              call: \"strapi-rest.list-upload-files\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/admin/users\n          name: admin-users\n          description: \"Administrator user management\"\n       \
  \   operations:\n            - method: GET\n              name: list-admin-users\n              description: \"List administrator accounts\"\n              call: \"strapi-admin.list-admin-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-admin-user\n              description: \"Create a new administrator\"\n              call: \"strapi-admin.create-admin-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/admin/roles\n          name: admin-roles\n          description: \"Administrator role management\"\n          operations:\n            - method: GET\n              name: list-admin-roles\n              description: \"List administrator roles\"\n              call: \"strapi-admin.list-admin-roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/admin/api-tokens\n          name: api-tokens\n          description: \"API token management\"\n          operations:\n            - method: GET\n              name: list-api-tokens\n              description: \"List all API tokens\"\n              call: \"strapi-admin.list-api-tokens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-token\n              description: \"Create a new API token\"\n              call: \"strapi-admin.create-api-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/admin/webhooks\n          name: webhooks\n          description: \"Webhook configuration management\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhook configurations\"\n              call: \"strapi-admin.list-webhooks\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a new webhook\"\n              call: \"strapi-admin.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: end-users\n          description: \"End-user account management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List registered end-users\"\n              call: \"strapi-users.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/auth/login\n          name: auth\n          description: \"User authentication\"\n          operations:\n            - method: POST\n              name: login-user\n              description: \"Authenticate a\
  \ user\"\n              call: \"strapi-users.login-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: strapi-content-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Strapi content management.\"\n      tools:\n        - name: find-entries\n          description: \"List content entries for a content-type with filtering and pagination\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"strapi-rest.find-entries\"\n          with:\n            pluralApiId: \"tools.pluralApiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-entry\n          description: \"Create a new content entry\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"strapi-rest.create-entry\"\n          with:\n           \
  \ pluralApiId: \"tools.pluralApiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-one-entry\n          description: \"Get a single content entry by document ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"strapi-rest.find-one-entry\"\n          with:\n            pluralApiId: \"tools.pluralApiId\"\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-entry\n          description: \"Update an existing content entry\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"strapi-rest.update-entry\"\n          with:\n            pluralApiId: \"tools.pluralApiId\"\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-entry\n     \
  \     description: \"Delete a content entry permanently\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"strapi-rest.delete-entry\"\n          with:\n            pluralApiId: \"tools.pluralApiId\"\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-media-files\n          description: \"List all files in the Strapi media library\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"strapi-rest.list-upload-files\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-admin-users\n          description: \"List all administrator accounts\"\n          hints:\n            readOnly: true\n          call: \"strapi-admin.list-admin-users\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-admin-user\n          description: \"Create a new administrator account\"\n          hints:\n            readOnly: false\n          call: \"strapi-admin.create-admin-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-admin-roles\n          description: \"List all administrator roles\"\n          hints:\n            readOnly: true\n          call: \"strapi-admin.list-admin-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-tokens\n          description: \"List all API tokens configured in Strapi\"\n          hints:\n            readOnly: true\n          call: \"strapi-admin.list-api-tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-token\n          description: \"Create a new API token\"\n          hints:\n            readOnly: false\n          call:\
  \ \"strapi-admin.create-api-token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List all webhook configurations\"\n          hints:\n            readOnly: true\n          call: \"strapi-admin.list-webhooks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Create a new webhook configuration\"\n          hints:\n            readOnly: false\n          call: \"strapi-admin.create-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: login-user\n          description: \"Authenticate an end-user and obtain a JWT token\"\n          hints:\n            readOnly: false\n          call: \"strapi-users.login-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-user\n       \
  \   description: \"Register a new end-user account\"\n          hints:\n            readOnly: false\n          call: \"strapi-users.register-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-authenticated-user\n          description: \"Get the currently authenticated user's profile\"\n          hints:\n            readOnly: true\n          call: \"strapi-users.get-authenticated-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all registered end-user accounts\"\n          hints:\n            readOnly: true\n          call: \"strapi-users.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-roles\n          description: \"List user roles and their permissions\"\n          hints:\n            readOnly: true\n          call: \"strapi-users.list-roles\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
