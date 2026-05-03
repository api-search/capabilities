---
api_specs:
- filename: theneo-api-openapi.yml
  format: yaml
  label: theneo
  slug: theneo
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/theneo/refs/heads/main/openapi/theneo-api-openapi.yml
categories: []
consumed_apis:
- theneo
description: Workflow capability for managing API documentation projects on the Theneo platform. Covers project lifecycle from creation through import, collaboration, and publishing.
layout: capability
name: Theneo API Documentation Management
operations:
- description: Retrieve all API documentation projects.
  method: GET
  name: get-all-projects
  path: /v1/projects
- description: Create a new API documentation project.
  method: POST
  name: add-new-project
  path: /v1/projects
- description: Get details for a specific project.
  method: GET
  name: get-project
  path: /v1/projects/{projectId}
- description: Delete a specific project.
  method: DELETE
  name: delete-project
  path: /v1/projects/{projectId}
- description: List users with access to a project.
  method: GET
  name: get-project-users
  path: /v1/projects/{projectId}/users
- description: Share the project with a user by email.
  method: POST
  name: share-project
  path: /v1/projects/{projectId}/share
- description: Update a user's role on a project.
  method: PATCH
  name: change-user-access
  path: /v1/projects/{projectId}/users/{userId}
- description: Import an API specification into a project.
  method: POST
  name: import-api-spec
  path: /v1/projects/{projectId}/import
- description: Publish the project documentation publicly.
  method: POST
  name: publish-project
  path: /v1/projects/{projectId}/publish
- description: Get a preview link for project docs before publishing.
  method: GET
  name: get-preview-link
  path: /v1/projects/{projectId}/preview
- description: List all workspaces for the authenticated user.
  method: GET
  name: list-workspaces
  path: /v1/workspaces
personas: []
provider_name: Theneo
provider_slug: theneo
search_terms:
- publish project
- preview project documentation.
- get details for a specific project.
- get or delete a specific project.
- delete a specific project.
- get a preview link for project docs before publishing.
- list projects
- update a user's role on a project.
- manage a user's access role on a project.
- create a new api documentation project on theneo.
- share a theneo project with a user by email address.
- delete a theneo project by id.
- list users with access to a project.
- list project users
- create a new api documentation project.
- publishing
- documentation platform
- get all projects
- delete project
- share project
- import api spec
- create project
- publish the project documentation publicly.
- update a user's access role (viewer, editor, admin) on a theneo project.
- retrieve all api documentation projects.
- list workspaces.
- api documentation
- get details for a specific theneo project.
- get project users
- share the project with a user by email.
- publish theneo project documentation, making it publicly accessible.
- list and create api documentation projects.
- list users with access to a theneo project.
- collaboration
- share a project with users.
- import an api specification into a project.
- list all theneo workspaces available to the authenticated user.
- developer tools
- add new project
- list all api documentation projects on theneo.
- list workspaces
- list all workspaces for the authenticated user.
- import api specifications into projects.
- get a preview url for theneo project documentation before publishing.
- ai
- publish project documentation.
- platform
- get preview link
- import an api specification (openapi, postman, graphql, asyncapi) into a theneo project.
- get project
- change user access
- manage users with access to a project.
slug: api-documentation
source_filename: api-documentation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Theneo API Documentation Management\"\n  description: \"Workflow capability for managing API documentation projects on the Theneo platform. Covers project lifecycle from creation through import, collaboration, and publishing.\"\n  tags:\n    - API Documentation\n    - Developer Tools\n    - Documentation Platform\n    - AI\n    - Publishing\n    - Collaboration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      THENEO_API_KEY: THENEO_API_KEY\n\ncapability:\n  consumes:\n    - import: theneo\n      location: ./shared/theneo-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: theneo-docs-api\n      description: \"Unified REST API for API documentation project management on Theneo.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"List and create API documentation projects.\"\n          operations:\n   \
  \         - method: GET\n              name: get-all-projects\n              description: \"Retrieve all API documentation projects.\"\n              call: \"theneo.get-all-projects\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: add-new-project\n              description: \"Create a new API documentation project.\"\n              call: \"theneo.add-new-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}\n          name: project\n          description: \"Get or delete a specific project.\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get details for a specific project.\"\n              call: \"theneo.get-project-by-id\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete a specific project.\"\n              call: \"theneo.delete-project\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/users\n          name: project-users\n          description: \"Manage users with access to a project.\"\n          operations:\n            - method: GET\n              name: get-project-users\n              description: \"List users with access to a project.\"\n              call: \"theneo.get-accessible-users\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/share\n          name:\
  \ project-share\n          description: \"Share a project with users.\"\n          operations:\n            - method: POST\n              name: share-project\n              description: \"Share the project with a user by email.\"\n              call: \"theneo.share-project\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/users/{userId}\n          name: project-user-access\n          description: \"Manage a user's access role on a project.\"\n          operations:\n            - method: PATCH\n              name: change-user-access\n              description: \"Update a user's role on a project.\"\n              call: \"theneo.change-user-access\"\n              with:\n                projectId: \"rest.projectId\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n    \
  \              mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/import\n          name: project-import\n          description: \"Import API specifications into projects.\"\n          operations:\n            - method: POST\n              name: import-api-spec\n              description: \"Import an API specification into a project.\"\n              call: \"theneo.import-api-specification\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/publish\n          name: project-publish\n          description: \"Publish project documentation.\"\n          operations:\n            - method: POST\n              name: publish-project\n              description: \"Publish the project documentation publicly.\"\n              call: \"theneo.publish-project\"\n              with:\n                projectId: \"rest.projectId\"\n  \
  \            outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/preview\n          name: project-preview\n          description: \"Preview project documentation.\"\n          operations:\n            - method: GET\n              name: get-preview-link\n              description: \"Get a preview link for project docs before publishing.\"\n              call: \"theneo.get-preview-project-link\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"List workspaces.\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List all workspaces for the authenticated user.\"\n              call: \"theneo.list-workspaces\"\n              outputParameters:\n \
  \               - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: theneo-docs-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API documentation management on Theneo.\"\n      tools:\n        - name: list-projects\n          description: \"List all API documentation projects on Theneo.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"theneo.get-all-projects\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-project\n          description: \"Create a new API documentation project on Theneo.\"\n          hints:\n            readOnly: false\n          call: \"theneo.add-new-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-project\n          description: \"Get details for a specific Theneo project.\"\n          hints:\n         \
  \   readOnly: true\n            idempotent: true\n          call: \"theneo.get-project-by-id\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-project\n          description: \"Delete a Theneo project by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"theneo.delete-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-project-users\n          description: \"List users with access to a Theneo project.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"theneo.get-accessible-users\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: array\n         \
  \     mapping: \"$.\"\n\n        - name: share-project\n          description: \"Share a Theneo project with a user by email address.\"\n          hints:\n            readOnly: false\n          call: \"theneo.share-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: change-user-access\n          description: \"Update a user's access role (viewer, editor, admin) on a Theneo project.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"theneo.change-user-access\"\n          with:\n            projectId: \"tools.projectId\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: import-api-spec\n          description: \"Import an API specification (OpenAPI, Postman, GraphQL, AsyncAPI) into a Theneo project.\"\n          hints:\n    \
  \        readOnly: false\n          call: \"theneo.import-api-specification\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-project\n          description: \"Publish Theneo project documentation, making it publicly accessible.\"\n          hints:\n            readOnly: false\n          call: \"theneo.publish-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-preview-link\n          description: \"Get a preview URL for Theneo project documentation before publishing.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"theneo.get-preview-project-link\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: list-workspaces\n          description: \"List all Theneo workspaces available to the authenticated user.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"theneo.list-workspaces\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/theneo/refs/heads/main/capabilities/api-documentation.yaml
tags:
- API Documentation
- Developer Tools
- Documentation Platform
- AI
- Publishing
- Collaboration
tools:
- description: List all API documentation projects on Theneo.
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new API documentation project on Theneo.
  hints:
    readOnly: false
  name: create-project
- description: Get details for a specific Theneo project.
  hints:
    idempotent: true
    readOnly: true
  name: get-project
- description: Delete a Theneo project by ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: List users with access to a Theneo project.
  hints:
    idempotent: true
    readOnly: true
  name: list-project-users
- description: Share a Theneo project with a user by email address.
  hints:
    readOnly: false
  name: share-project
- description: Update a user's access role (viewer, editor, admin) on a Theneo project.
  hints:
    idempotent: true
    readOnly: false
  name: change-user-access
- description: Import an API specification (OpenAPI, Postman, GraphQL, AsyncAPI) into a Theneo project.
  hints:
    readOnly: false
  name: import-api-spec
- description: Publish Theneo project documentation, making it publicly accessible.
  hints:
    readOnly: false
  name: publish-project
- description: Get a preview URL for Theneo project documentation before publishing.
  hints:
    idempotent: true
    readOnly: true
  name: get-preview-link
- description: List all Theneo workspaces available to the authenticated user.
  hints:
    idempotent: true
    readOnly: true
  name: list-workspaces
---
