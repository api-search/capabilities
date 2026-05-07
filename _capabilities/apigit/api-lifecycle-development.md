---
categories: []
consumed_apis: []
description: Workflow for Git-native API lifecycle development using APIGit - managing API repositories, designing APIs with visual tools, running mock servers for development, and executing automated tests.
layout: capability
name: APIGit API Lifecycle Development
operations:
- description: List repositories.
  method: GET
  name: list-repositories
  path: /v1/repos
- description: Create repository.
  method: POST
  name: create-repository
  path: /v1/repos
personas: []
provider_name: APIGit
provider_slug: apigit
search_terms:
- governance
- API Developer
- create api repository
- testing
- git
- mocking
- start a dynamic mock server from an api definition for development testing.
- platform
- developer designing and building apis using git-native workflows.
- create a new git-native api repository in apigit.
- documentation
- api design
- Backend Engineer
- engineer using mock servers for frontend/backend parallel development.
- list api repositories
- list repositories.
- create repository
- create repository.
- list all api git repositories in apigit.
- api lifecycle
- start mock server
- apigit
- list repositories
slug: api-lifecycle-development
source_filename: api-lifecycle-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: APIGit API Lifecycle Development\n  description: Workflow for Git-native API lifecycle development using APIGit - managing API repositories, designing APIs\n    with visual tools, running mock servers for development, and executing automated tests.\n  tags:\n  - APIGit\n  - API Lifecycle\n  - Git\n  - Mocking\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APIGIT_API_KEY: APIGIT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: apigit\n    baseUri: https://api.apigit.com/v1\n    description: APIGit REST API.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{APIGIT_API_KEY}}'\n      placement: header\n    resources:\n    - name: repositories\n      path: /repos\n      description: Manage API Git repositories.\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List all API repositories.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repository\n        method: POST\n        description: Create a new API repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mocks\n      path: /repos/{repoId}/mock\n      description: Manage mock servers.\n      operations:\n      - name: start-mock\n        method: POST\n        description: Start a dynamic mock server.\n        inputParameters:\n        - name: repoId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apigit-lifecycle-api\n    description: Unified REST API for APIGit lifecycle management.\n    resources:\n    - path: /v1/repos\n      operations:\n\
  \      - method: GET\n        name: list-repositories\n        description: List repositories.\n        call: apigit.list-repositories\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-repository\n        description: Create repository.\n        call: apigit.create-repository\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apigit-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted API lifecycle development with APIGit.\n    tools:\n    - name: list-api-repositories\n      description: List all API Git repositories in APIGit.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apigit.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-repository\n      description: Create a new Git-native API repository in APIGit.\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apigit.create-repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-mock-server\n      description: Start a dynamic mock server from an API definition for development testing.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apigit.start-mock\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigit/refs/heads/main/capabilities/api-lifecycle-development.yaml
tags:
- APIGit
- API Lifecycle
- Git
- Mocking
tools:
- description: List all API Git repositories in APIGit.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-repositories
- description: Create a new Git-native API repository in APIGit.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-repository
- description: Start a dynamic mock server from an API definition for development testing.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-mock-server
---
