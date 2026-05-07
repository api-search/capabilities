---
categories: []
consumed_apis: []
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
- list users with access to a project.
- share project
- list workspaces
- delete a theneo project by id.
- share a theneo project with a user by email address.
- ai
- platform
- publishing
- list project users
- import api spec
- publish project documentation.
- get a preview url for theneo project documentation before publishing.
- change user access
- delete a specific project.
- preview project documentation.
- publish theneo project documentation, making it publicly accessible.
- publish project
- collaboration
- share a project with users.
- import an api specification into a project.
- manage a user's access role on a project.
- list users with access to a theneo project.
- delete project
- developer tools
- share the project with a user by email.
- get preview link
- list projects
- update a user's role on a project.
- list workspaces.
- documentation platform
- create project
- get details for a specific theneo project.
- get project users
- add new project
- get or delete a specific project.
- get a preview link for project docs before publishing.
- get details for a specific project.
- create a new api documentation project on theneo.
- retrieve all api documentation projects.
- get project
- import api specifications into projects.
- list all theneo workspaces available to the authenticated user.
- list all api documentation projects on theneo.
- import an api specification (openapi, postman, graphql, asyncapi) into a theneo project.
- publish the project documentation publicly.
- api documentation
- update a user's access role (viewer, editor, admin) on a theneo project.
- manage users with access to a project.
- list and create api documentation projects.
- list all workspaces for the authenticated user.
- get all projects
- create a new api documentation project.
slug: api-documentation
source_filename: api-documentation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Theneo API Documentation Management\n  description: Workflow capability for managing API documentation projects on the Theneo platform. Covers project lifecycle\n    from creation through import, collaboration, and publishing.\n  tags:\n  - API Documentation\n  - Developer Tools\n  - Documentation Platform\n  - AI\n  - Publishing\n  - Collaboration\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THENEO_API_KEY: THENEO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: theneo\n    baseUri: https://api.theneo.io\n    description: AI-powered API documentation platform for managing projects, workspaces, and publishing.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{THENEO_API_KEY}}'\n      placement: header\n    resources:\n    - name: projects\n      path: /projects\n      description: Manage API documentation projects.\n      operations:\n    \
  \  - name: get-all-projects\n        method: GET\n        description: Retrieves a list of all API documentation projects accessible to the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: add-new-project\n        method: POST\n        description: Creates a new API documentation project in the specified workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            workspace: '{{tools.workspace}}'\n            description: '{{tools.description}}'\n            link: '{{tools.link}}'\n            publish: '{{tools.publish}}'\n    - name: project-by-id\n      path: /projects/{projectId}\n      description: Manage a specific API documentation project.\n      operations:\n      - name: get-project-by-id\n\
  \        method: GET\n        description: Retrieves details of a specific project by its unique identifier.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Deletes an API documentation project by its unique identifier.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-users\n      path: /projects/{projectId}/users\n      description: Manage users with access to a project.\n\
  \      operations:\n      - name: get-accessible-users\n        method: GET\n        description: Retrieves the list of users who have access to the specified project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: project-share\n      path: /projects/{projectId}/share\n      description: Share a project with other users.\n      operations:\n      - name: share-project\n        method: POST\n        description: Shares a project with specified users by granting them access.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            role: '{{tools.role}}'\n    - name: project-user-access\n      path: /projects/{projectId}/users/{userId}\n      description: Manage a specific user's access to a project.\n      operations:\n      - name: change-user-access\n        method: PATCH\n        description: Updates the access role of a user on a specific project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            role: '{{tools.role}}'\n    - name: project-import\n      path: /projects/{projectId}/import\n      description: Import API specifications into a project.\n      operations:\n      - name: import-api-specification\n        method: POST\n        description: Imports an API specification file into an existing project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            link: '{{tools.link}}'\n            importType: '{{tools.importType}}'\n    - name: project-publish\n      path: /projects/{projectId}/publish\n      description: Publish API documentation for a project.\n      operations:\n      - name: publish-project\n        method: POST\n\
  \        description: Publishes the API documentation for a project, making it publicly accessible.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-preview\n      path: /projects/{projectId}/preview\n      description: Get preview link for project documentation.\n      operations:\n      - name: get-preview-project-link\n        method: GET\n        description: Returns a preview link for the project documentation before it is published.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Manage workspaces.\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: Retrieves a list of all workspaces available to the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: theneo-docs-api\n    description: Unified REST API for API documentation project management on Theneo.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: List and create API documentation projects.\n      operations:\n      - method: GET\n        name: get-all-projects\n        description: Retrieve all API documentation projects.\n        call: theneo.get-all-projects\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: add-new-project\n\
  \        description: Create a new API documentation project.\n        call: theneo.add-new-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: project\n      description: Get or delete a specific project.\n      operations:\n      - method: GET\n        name: get-project\n        description: Get details for a specific project.\n        call: theneo.get-project-by-id\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete a specific project.\n        call: theneo.delete-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/users\n      name: project-users\n      description: Manage users with access to a project.\n      operations:\n     \
  \ - method: GET\n        name: get-project-users\n        description: List users with access to a project.\n        call: theneo.get-accessible-users\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/projects/{projectId}/share\n      name: project-share\n      description: Share a project with users.\n      operations:\n      - method: POST\n        name: share-project\n        description: Share the project with a user by email.\n        call: theneo.share-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/users/{userId}\n      name: project-user-access\n      description: Manage a user's access role on a project.\n      operations:\n      - method: PATCH\n        name: change-user-access\n        description: Update a user's role on a project.\n        call: theneo.change-user-access\n\
  \        with:\n          projectId: rest.projectId\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/import\n      name: project-import\n      description: Import API specifications into projects.\n      operations:\n      - method: POST\n        name: import-api-spec\n        description: Import an API specification into a project.\n        call: theneo.import-api-specification\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/publish\n      name: project-publish\n      description: Publish project documentation.\n      operations:\n      - method: POST\n        name: publish-project\n        description: Publish the project documentation publicly.\n        call: theneo.publish-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/projects/{projectId}/preview\n      name: project-preview\n      description: Preview project documentation.\n      operations:\n      - method: GET\n        name: get-preview-link\n        description: Get a preview link for project docs before publishing.\n        call: theneo.get-preview-project-link\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: List workspaces.\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces for the authenticated user.\n        call: theneo.list-workspaces\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: theneo-docs-mcp\n    transport: http\n    description: MCP server for AI-assisted API documentation management on Theneo.\n    tools:\n\
  \    - name: list-projects\n      description: List all API documentation projects on Theneo.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: theneo.get-all-projects\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-project\n      description: Create a new API documentation project on Theneo.\n      hints:\n        readOnly: false\n      call: theneo.add-new-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get details for a specific Theneo project.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: theneo.get-project-by-id\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Delete a Theneo project by ID.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: theneo.delete-project\n\
  \      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-project-users\n      description: List users with access to a Theneo project.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: theneo.get-accessible-users\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: share-project\n      description: Share a Theneo project with a user by email address.\n      hints:\n        readOnly: false\n      call: theneo.share-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: change-user-access\n      description: Update a user's access role (viewer, editor, admin) on a Theneo project.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: theneo.change-user-access\n      with:\n        projectId: tools.projectId\n\
  \        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-api-spec\n      description: Import an API specification (OpenAPI, Postman, GraphQL, AsyncAPI) into a Theneo project.\n      hints:\n        readOnly: false\n      call: theneo.import-api-specification\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-project\n      description: Publish Theneo project documentation, making it publicly accessible.\n      hints:\n        readOnly: false\n      call: theneo.publish-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-preview-link\n      description: Get a preview URL for Theneo project documentation before publishing.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: theneo.get-preview-project-link\n      with:\n        projectId:\
  \ tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all Theneo workspaces available to the authenticated user.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: theneo.list-workspaces\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
