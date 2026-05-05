---
api_specs:
- filename: replit-openapi.yml
  format: yaml
  label: replit
  slug: replit
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/replit/refs/heads/main/openapi/replit-openapi.yml
categories: []
consumed_apis:
- replit
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
- get repl details.
- deploy a repl to production.
- create a new repl coding environment with the specified language.
- delete a repl permanently.
- deploy repls to production hosting.
- get repl
- get detailed information about a specific repl.
- get user
- delete repl
- public user profile.
- get current user
- get a user's public profile.
- get deployment details and status.
- list public repls for a user.
- get deployment
- create repl
- remove a deployment from production.
- list user repls
- list all repls accessible to the authenticated user.
- browse public repls for any replit user.
- get, update, or delete a specific repl.
- list all repls for the authenticated user.
- programming languages
- deploy a repl to production hosting.
- get the authenticated user's profile.
- deployments
- update repl metadata.
- delete deployment
- get the authenticated user's replit profile.
- update a repl's title, description, or privacy setting.
- code
- list deployments for a repl.
- deploy repl
- manage a specific deployment.
- list repls
- update repl
- development environment
- browse public repls for a user.
- check the status and details of a deployment.
- repls
- current authenticated user profile.
- create and manage replit coding environments.
- compiling
- create repl deployment
- list repl deployments
- permanently delete a repl.
- create a new repl.
- version control
slug: development-workflow
source_filename: development-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Replit Development Workflow\"\n  description: >-\n    Workflow capability for managing the full development lifecycle on Replit.\n    Covers creating and managing Repls (coding environments), deploying\n    applications to production, and managing user profiles. Designed for\n    developers, educators, and platform teams automating coding workflows.\n  tags:\n    - Code\n    - Development Environment\n    - Deployments\n    - Repls\n    - Programming Languages\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REPLIT_API_TOKEN: REPLIT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: replit\n      location: ./shared/replit.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: replit-workflow-api\n      description: \"Unified REST API for Replit development workflow management.\"\n      resources:\n        - path: /v1/repls\n          name: repls\n       \
  \   description: \"Create and manage Replit coding environments.\"\n          operations:\n            - method: GET\n              name: list-repls\n              description: \"List all Repls for the authenticated user.\"\n              call: \"replit.list-repls\"\n              with:\n                limit: \"rest.limit\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-repl\n              description: \"Create a new Repl.\"\n              call: \"replit.create-repl\"\n              with:\n                title: \"rest.title\"\n                language: \"rest.language\"\n                description: \"rest.description\"\n                isPrivate: \"rest.isPrivate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/repls/{id}\n          name: repl\n          description:\
  \ \"Get, update, or delete a specific Repl.\"\n          operations:\n            - method: GET\n              name: get-repl\n              description: \"Get Repl details.\"\n              call: \"replit.get-repl\"\n              with:\n                replId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-repl\n              description: \"Update Repl metadata.\"\n              call: \"replit.update-repl\"\n              with:\n                replId: \"rest.id\"\n                title: \"rest.title\"\n                description: \"rest.description\"\n                isPrivate: \"rest.isPrivate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-repl\n              description: \"Delete a Repl permanently.\"\n              call: \"replit.delete-repl\"\n  \
  \            with:\n                replId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/repls/{id}/deployments\n          name: repl-deployments\n          description: \"Deploy Repls to production hosting.\"\n          operations:\n            - method: GET\n              name: list-repl-deployments\n              description: \"List deployments for a Repl.\"\n              call: \"replit.list-repl-deployments\"\n              with:\n                replId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-repl-deployment\n              description: \"Deploy a Repl to production.\"\n              call: \"replit.create-repl-deployment\"\n              with:\n                replId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/deployments/{id}\n          name: deployment\n          description: \"Manage a specific deployment.\"\n          operations:\n            - method: GET\n              name: get-deployment\n              description: \"Get deployment details and status.\"\n              call: \"replit.get-deployment\"\n              with:\n                deploymentId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-deployment\n              description: \"Remove a deployment from production.\"\n              call: \"replit.delete-deployment\"\n              with:\n                deploymentId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user\n          name: current-user\n          description: \"Current authenticated user profile.\"\n          operations:\n  \
  \          - method: GET\n              name: get-current-user\n              description: \"Get the authenticated user's profile.\"\n              call: \"replit.get-current-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{username}\n          name: user\n          description: \"Public user profile.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get a user's public profile.\"\n              call: \"replit.get-user\"\n              with:\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{username}/repls\n          name: user-repls\n          description: \"Browse public Repls for a user.\"\n          operations:\n            - method: GET\n              name: list-user-repls\n              description: \"List public\
  \ Repls for a user.\"\n              call: \"replit.list-user-repls\"\n              with:\n                username: \"rest.username\"\n                limit: \"rest.limit\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: replit-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Replit development workflow management.\"\n      tools:\n        - name: list-repls\n          description: \"List all Repls accessible to the authenticated user.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replit.list-repls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-repl\n          description: \"Create a new Repl coding environment with the specified language.\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n            idempotent: false\n          call: \"replit.create-repl\"\n          with:\n            title: \"tools.title\"\n            language: \"tools.language\"\n            description: \"tools.description\"\n            isPrivate: \"tools.isPrivate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-repl\n          description: \"Get detailed information about a specific Repl.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replit.get-repl\"\n          with:\n            replId: \"tools.replId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-repl\n          description: \"Update a Repl's title, description, or privacy setting.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"replit.update-repl\"\
  \n          with:\n            replId: \"tools.replId\"\n            title: \"tools.title\"\n            description: \"tools.description\"\n            isPrivate: \"tools.isPrivate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-repl\n          description: \"Permanently delete a Repl.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"replit.delete-repl\"\n          with:\n            replId: \"tools.replId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-repl\n          description: \"Deploy a Repl to production hosting.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"replit.create-repl-deployment\"\n          with:\n            replId: \"tools.replId\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment\n          description: \"Check the status and details of a deployment.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"replit.get-deployment\"\n          with:\n            deploymentId: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-user-repls\n          description: \"Browse public Repls for any Replit user.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"replit.list-user-repls\"\n          with:\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-current-user\n          description: \"Get the authenticated user's Replit profile.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"replit.get-current-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
