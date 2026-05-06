---
categories: []
consumed_apis: []
description: Workflow capability for managing the full development lifecycle on Replit. Covers creating and managing Repls (coding environments), deploying applications to production, and managing user profiles. Designed for developers, educators, and platform teams automating coding workflows.
layout: capability
name: Replit Development Workflow
operations:
- description: List all Repls for the authenticated user.
  method: GET
  name: list-repls
  path: /v1/repls
- description: Create a new Repl.
  method: POST
  name: create-repl
  path: /v1/repls
- description: Get Repl details.
  method: GET
  name: get-repl
  path: /v1/repls/{id}
- description: Update Repl metadata.
  method: PATCH
  name: update-repl
  path: /v1/repls/{id}
- description: Delete a Repl permanently.
  method: DELETE
  name: delete-repl
  path: /v1/repls/{id}
- description: List deployments for a Repl.
  method: GET
  name: list-repl-deployments
  path: /v1/repls/{id}/deployments
- description: Deploy a Repl to production.
  method: POST
  name: create-repl-deployment
  path: /v1/repls/{id}/deployments
- description: Get deployment details and status.
  method: GET
  name: get-deployment
  path: /v1/deployments/{id}
- description: Remove a deployment from production.
  method: DELETE
  name: delete-deployment
  path: /v1/deployments/{id}
- description: Get the authenticated user's profile.
  method: GET
  name: get-current-user
  path: /v1/user
- description: Get a user's public profile.
  method: GET
  name: get-user
  path: /v1/users/{username}
- description: List public Repls for a user.
  method: GET
  name: list-user-repls
  path: /v1/users/{username}/repls
personas: []
provider_name: Replit
provider_slug: replit
search_terms:
- create repl
- deploy a repl to production.
- manage a specific deployment.
- create and manage replit coding environments.
- list deployments for a repl.
- update repl metadata.
- get detailed information about a specific repl.
- get, update, or delete a specific repl.
- get deployment
- get the authenticated user's replit profile.
- delete deployment
- get repl details.
- remove a deployment from production.
- public user profile.
- list repl deployments
- get a user's public profile.
- deployments
- browse public repls for a user.
- create a new repl.
- current authenticated user profile.
- list user repls
- browse public repls for any replit user.
- deploy repls to production hosting.
- create a new repl coding environment with the specified language.
- update repl
- list public repls for a user.
- repls
- get the authenticated user's profile.
- deploy a repl to production hosting.
- code
- create repl deployment
- list all repls accessible to the authenticated user.
- get deployment details and status.
- get repl
- version control
- delete repl
- check the status and details of a deployment.
- get user
- delete a repl permanently.
- get current user
- permanently delete a repl.
- update a repl's title, description, or privacy setting.
- list all repls for the authenticated user.
- development environment
- list repls
- compiling
- deploy repl
- programming languages
slug: development-workflow
source_filename: development-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Replit Development Workflow\n  description: Workflow capability for managing the full development lifecycle on Replit. Covers creating and managing Repls\n    (coding environments), deploying applications to production, and managing user profiles. Designed for developers, educators,\n    and platform teams automating coding workflows.\n  tags:\n  - Code\n  - Development Environment\n  - Deployments\n  - Repls\n  - Programming Languages\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REPLIT_API_TOKEN: REPLIT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: replit\n    baseUri: https://replit.com/api/v1\n    description: Replit REST API for programmatic management of coding environments and deployments.\n    authentication:\n      type: bearer\n      token: '{{REPLIT_API_TOKEN}}'\n    resources:\n    - name: repls\n      path: /repls\n      description: Manage Replit coding environments.\n\
  \      operations:\n      - name: list-repls\n        method: GET\n        description: List all Repls for the authenticated user.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repl\n        method: POST\n        description: Create a new Repl.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            language: '{{tools.language}}'\n            description: '{{tools.description}}'\n            isPrivate: '{{tools.isPrivate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: get-repl\n        method: GET\n        description: Get details for a specific Repl.\n        inputParameters:\n        - name: replId\n          in: path\n          type: string\n          required: true\n          description: The Repl ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-repl\n        method: PATCH\n        description: Update a Repl's title, description, or privacy.\n        inputParameters:\n        - name: replId\n          in: path\n          type: string\n          required: true\n          description: The Repl ID.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            isPrivate: '{{tools.isPrivate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: delete-repl\n        method: DELETE\n        description: Permanently delete a Repl.\n        inputParameters:\n        - name: replId\n          in: path\n          type: string\n          required: true\n          description: The Repl ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repl-deployments\n      path: /repls/{replId}/deployments\n      description: Manage deployments for a Repl.\n      operations:\n      - name: list-repl-deployments\n        method: GET\n        description: List all deployments for a Repl.\n        inputParameters:\n        - name: replId\n          in: path\n          type: string\n          required: true\n          description: The Repl ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repl-deployment\n        method: POST\n        description:\
  \ Deploy a Repl to production hosting.\n        inputParameters:\n        - name: replId\n          in: path\n          type: string\n          required: true\n          description: The Repl ID to deploy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      description: Manage production deployments.\n      operations:\n      - name: get-deployment\n        method: GET\n        description: Get details for a specific deployment.\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The deployment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-deployment\n        method: DELETE\n        description: Remove a deployment from production.\n        inputParameters:\n\
  \        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The deployment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      description: Current authenticated user.\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Get information about the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User profiles and their Repls.\n      operations:\n      - name: get-user\n        method: GET\n        description: Get public profile for a user.\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The user's username.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-user-repls\n        method: GET\n        description: List all public Repls for a user.\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The user's username.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: replit-workflow-api\n    description: Unified REST API for Replit development workflow management.\n    resources:\n    - path: /v1/repls\n\
  \      name: repls\n      description: Create and manage Replit coding environments.\n      operations:\n      - method: GET\n        name: list-repls\n        description: List all Repls for the authenticated user.\n        call: replit.list-repls\n        with:\n          limit: rest.limit\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-repl\n        description: Create a new Repl.\n        call: replit.create-repl\n        with:\n          title: rest.title\n          language: rest.language\n          description: rest.description\n          isPrivate: rest.isPrivate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repls/{id}\n      name: repl\n      description: Get, update, or delete a specific Repl.\n      operations:\n      - method: GET\n        name: get-repl\n        description: Get Repl details.\n        call: replit.get-repl\n    \
  \    with:\n          replId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-repl\n        description: Update Repl metadata.\n        call: replit.update-repl\n        with:\n          replId: rest.id\n          title: rest.title\n          description: rest.description\n          isPrivate: rest.isPrivate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-repl\n        description: Delete a Repl permanently.\n        call: replit.delete-repl\n        with:\n          replId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repls/{id}/deployments\n      name: repl-deployments\n      description: Deploy Repls to production hosting.\n      operations:\n      - method: GET\n        name: list-repl-deployments\n        description: List deployments for a Repl.\n        call: replit.list-repl-deployments\n\
  \        with:\n          replId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-repl-deployment\n        description: Deploy a Repl to production.\n        call: replit.create-repl-deployment\n        with:\n          replId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{id}\n      name: deployment\n      description: Manage a specific deployment.\n      operations:\n      - method: GET\n        name: get-deployment\n        description: Get deployment details and status.\n        call: replit.get-deployment\n        with:\n          deploymentId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-deployment\n        description: Remove a deployment from production.\n        call: replit.delete-deployment\n        with:\n          deploymentId: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/user\n      name: current-user\n      description: Current authenticated user profile.\n      operations:\n      - method: GET\n        name: get-current-user\n        description: Get the authenticated user's profile.\n        call: replit.get-current-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{username}\n      name: user\n      description: Public user profile.\n      operations:\n      - method: GET\n        name: get-user\n        description: Get a user's public profile.\n        call: replit.get-user\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{username}/repls\n      name: user-repls\n      description: Browse public Repls for a user.\n      operations:\n      - method: GET\n        name: list-user-repls\n        description: List public Repls for a user.\n\
  \        call: replit.list-user-repls\n        with:\n          username: rest.username\n          limit: rest.limit\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: replit-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Replit development workflow management.\n    tools:\n    - name: list-repls\n      description: List all Repls accessible to the authenticated user.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replit.list-repls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-repl\n      description: Create a new Repl coding environment with the specified language.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replit.create-repl\n      with:\n        title: tools.title\n        language: tools.language\n        description:\
  \ tools.description\n        isPrivate: tools.isPrivate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-repl\n      description: Get detailed information about a specific Repl.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replit.get-repl\n      with:\n        replId: tools.replId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-repl\n      description: Update a Repl's title, description, or privacy setting.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: replit.update-repl\n      with:\n        replId: tools.replId\n        title: tools.title\n        description: tools.description\n        isPrivate: tools.isPrivate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-repl\n      description: Permanently delete a Repl.\n      hints:\n        readOnly: false\n        destructive: true\n \
  \       idempotent: true\n      call: replit.delete-repl\n      with:\n        replId: tools.replId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-repl\n      description: Deploy a Repl to production hosting.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: replit.create-repl-deployment\n      with:\n        replId: tools.replId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Check the status and details of a deployment.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replit.get-deployment\n      with:\n        deploymentId: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-user-repls\n      description: Browse public Repls for any Replit user.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: replit.list-user-repls\n\
  \      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-user\n      description: Get the authenticated user's Replit profile.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: replit.get-current-user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/replit/refs/heads/main/capabilities/development-workflow.yaml
tags:
- Code
- Development Environment
- Deployments
- Repls
- Programming Languages
tools:
- description: List all Repls accessible to the authenticated user.
  hints:
    openWorld: false
    readOnly: true
  name: list-repls
- description: Create a new Repl coding environment with the specified language.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-repl
- description: Get detailed information about a specific Repl.
  hints:
    openWorld: false
    readOnly: true
  name: get-repl
- description: Update a Repl's title, description, or privacy setting.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-repl
- description: Permanently delete a Repl.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-repl
- description: Deploy a Repl to production hosting.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-repl
- description: Check the status and details of a deployment.
  hints:
    openWorld: false
    readOnly: true
  name: get-deployment
- description: Browse public Repls for any Replit user.
  hints:
    openWorld: true
    readOnly: true
  name: list-user-repls
- description: Get the authenticated user's Replit profile.
  hints:
    openWorld: false
    readOnly: true
  name: get-current-user
---
