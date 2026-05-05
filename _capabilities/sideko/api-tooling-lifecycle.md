---
categories: []
consumed_apis:
- sideko
description: Unified workflow capability for managing the complete API tooling lifecycle on the Sideko platform. Enables API platform teams to programmatically manage API projects, upload specifications, generate multi-language SDKs, deploy documentation sites, and run mock servers — all through a single unified interface. Designed for API platform engineers and DevOps teams automating their API developer experience pipeline.
layout: capability
name: Sideko API Tooling Lifecycle
operations:
- description: List all API projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new API project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get an API project by ID
  method: GET
  name: get-project
  path: /v1/projects/{projectId}
- description: Update an API project
  method: PUT
  name: update-project
  path: /v1/projects/{projectId}
- description: Delete an API project
  method: DELETE
  name: delete-project
  path: /v1/projects/{projectId}
- description: List API versions
  method: GET
  name: list-versions
  path: /v1/projects/{projectId}/versions
- description: List SDK generation jobs
  method: GET
  name: list-sdks
  path: /v1/projects/{projectId}/sdks
- description: Trigger SDK generation
  method: POST
  name: generate-sdk
  path: /v1/projects/{projectId}/sdks
- description: List documentation sites
  method: GET
  name: list-docs
  path: /v1/projects/{projectId}/docs
- description: Deploy a documentation site
  method: POST
  name: deploy-docs
  path: /v1/projects/{projectId}/docs
- description: List mock servers
  method: GET
  name: list-mock-servers
  path: /v1/projects/{projectId}/mock-servers
- description: Deploy a mock server
  method: POST
  name: deploy-mock-server
  path: /v1/projects/{projectId}/mock-servers
- description: List API keys
  method: GET
  name: list-api-keys
  path: /v1/api-keys
- description: Create a new API key
  method: POST
  name: create-api-key
  path: /v1/api-keys
personas: []
provider_name: Sideko
provider_slug: sideko
search_terms:
- platform
- api key management
- list all api keys for the sideko organization
- list all api projects in the sideko organization
- deploy a mock server that simulates api responses for an api project version
- list mock servers
- get details of a specific api project
- deploy docs
- deploy or update an api documentation site for an api project version
- get an api project by id
- create a new api project in sideko
- list sdk generation jobs
- deploy a mock server
- sdk generation
- mock servers
- delete an api project and all its versions, sdks, docs, and mock servers
- list api projects
- list sdk generation jobs for an api project
- api tooling
- list sdk generations
- list all api projects
- documentation sites
- list sdks
- mock server management
- create api project
- deploy documentation site
- create a new sideko api key
- delete an api project
- list all versions of an api project
- deploy mock server
- list documentation sites
- list docs
- list projects
- create api key
- update project
- sdk generation jobs
- trigger sdk generation
- update an api project
- trigger sdk generation for a language (python, typescript, java, go, ruby, rust)
- update api project
- create a new api key
- list api versions
- delete project
- get api project
- list mock server instances for an api project
- developer experience
- update an existing api project name or description
- cli
- deploy a documentation site
- delete api project
- documentation
- create a new api project
- list api keys
- generate sdk
- api project management
- create project
- get project
- api version management
- list versions
- list documentation sites deployed for an api project
- single api project operations
- sdks
slug: api-tooling-lifecycle
source_filename: api-tooling-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sideko API Tooling Lifecycle\"\n  description: >-\n    Unified workflow capability for managing the complete API tooling lifecycle\n    on the Sideko platform. Enables API platform teams to programmatically\n    manage API projects, upload specifications, generate multi-language SDKs,\n    deploy documentation sites, and run mock servers — all through a single\n    unified interface. Designed for API platform engineers and DevOps teams\n    automating their API developer experience pipeline.\n  tags:\n    - API Tooling\n    - SDK Generation\n    - Documentation\n    - Mock Servers\n    - Platform\n    - Developer Experience\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIDEKO_API_KEY: SIDEKO_API_KEY\n\ncapability:\n  consumes:\n    - import: sideko\n      location: ./shared/sideko-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sideko-tooling-api\n\
  \      description: \"Unified REST API for managing the complete Sideko API tooling lifecycle.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"API project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all API projects\"\n              call: \"sideko.list-api-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new API project\"\n              call: \"sideko.create-api-project\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}\n          name: project\n          description: \"Single API project\
  \ operations\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get an API project by ID\"\n              call: \"sideko.get-api-project\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-project\n              description: \"Update an API project\"\n              call: \"sideko.update-api-project\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete an API project\"\n              call: \"sideko.delete-api-project\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/versions\n          name: versions\n          description: \"API version management\"\n          operations:\n            - method: GET\n              name: list-versions\n              description: \"List API versions\"\n              call: \"sideko.list-api-versions\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/sdks\n          name: sdks\n          description: \"SDK generation jobs\"\n          operations:\n            - method: GET\n              name: list-sdks\n              description: \"List SDK generation jobs\"\n              call: \"sideko.list-sdk-generations\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: POST\n              name: generate-sdk\n              description: \"Trigger SDK generation\"\n              call: \"sideko.trigger-sdk-generation\"\n              with:\n                projectId: \"rest.projectId\"\n                language: \"rest.language\"\n                versionId: \"rest.versionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/docs\n          name: documentation\n          description: \"Documentation sites\"\n          operations:\n            - method: GET\n              name: list-docs\n              description: \"List documentation sites\"\n              call: \"sideko.list-documentation-sites\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-docs\n         \
  \     description: \"Deploy a documentation site\"\n              call: \"sideko.deploy-documentation-site\"\n              with:\n                projectId: \"rest.projectId\"\n                versionId: \"rest.versionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/mock-servers\n          name: mock-servers\n          description: \"Mock server management\"\n          operations:\n            - method: GET\n              name: list-mock-servers\n              description: \"List mock servers\"\n              call: \"sideko.list-mock-servers\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-mock-server\n              description: \"Deploy a mock server\"\n              call: \"sideko.deploy-mock-server\"\n       \
  \       with:\n                projectId: \"rest.projectId\"\n                versionId: \"rest.versionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/api-keys\n          name: api-keys\n          description: \"API key management\"\n          operations:\n            - method: GET\n              name: list-api-keys\n              description: \"List API keys\"\n              call: \"sideko.list-api-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-key\n              description: \"Create a new API key\"\n              call: \"sideko.create-api-key\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sideko-tooling-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted API tooling lifecycle management on the Sideko platform.\"\n      tools:\n        - name: list-api-projects\n          description: \"List all API projects in the Sideko organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.list-api-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api-project\n          description: \"Create a new API project in Sideko\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sideko.create-api-project\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api-project\n          description: \"Get details of a specific API project\"\n \
  \         hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.get-api-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-api-project\n          description: \"Update an existing API project name or description\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"sideko.update-api-project\"\n          with:\n            projectId: \"tools.projectId\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-api-project\n          description: \"Delete an API project and all its versions, SDKs, docs, and mock servers\"\n          hints:\n            readOnly: false\n            destructive: true\n         \
  \   idempotent: true\n          call: \"sideko.delete-api-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-versions\n          description: \"List all versions of an API project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.list-api-versions\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-sdk-generations\n          description: \"List SDK generation jobs for an API project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.list-sdk-generations\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: trigger-sdk-generation\n\
  \          description: \"Trigger SDK generation for a language (python, typescript, java, go, ruby, rust)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sideko.trigger-sdk-generation\"\n          with:\n            projectId: \"tools.projectId\"\n            language: \"tools.language\"\n            versionId: \"tools.versionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-documentation-sites\n          description: \"List documentation sites deployed for an API project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.list-documentation-sites\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-documentation-site\n          description: \"Deploy or update an API\
  \ documentation site for an API project version\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"sideko.deploy-documentation-site\"\n          with:\n            projectId: \"tools.projectId\"\n            versionId: \"tools.versionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-mock-servers\n          description: \"List mock server instances for an API project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.list-mock-servers\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-mock-server\n          description: \"Deploy a mock server that simulates API responses for an API project version\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"sideko.deploy-mock-server\"\n          with:\n            projectId: \"tools.projectId\"\n            versionId: \"tools.versionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-keys\n          description: \"List all API keys for the Sideko organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sideko.list-api-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api-key\n          description: \"Create a new Sideko API key\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sideko.create-api-key\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sideko/refs/heads/main/capabilities/api-tooling-lifecycle.yaml
tags:
- API Tooling
- SDK Generation
- Documentation
- Mock Servers
- Platform
- Developer Experience
tools:
- description: List all API projects in the Sideko organization
  hints:
    openWorld: false
    readOnly: true
  name: list-api-projects
- description: Create a new API project in Sideko
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-project
- description: Get details of a specific API project
  hints:
    openWorld: false
    readOnly: true
  name: get-api-project
- description: Update an existing API project name or description
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-api-project
- description: Delete an API project and all its versions, SDKs, docs, and mock servers
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-project
- description: List all versions of an API project
  hints:
    openWorld: false
    readOnly: true
  name: list-api-versions
- description: List SDK generation jobs for an API project
  hints:
    openWorld: false
    readOnly: true
  name: list-sdk-generations
- description: Trigger SDK generation for a language (python, typescript, java, go, ruby, rust)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-sdk-generation
- description: List documentation sites deployed for an API project
  hints:
    openWorld: false
    readOnly: true
  name: list-documentation-sites
- description: Deploy or update an API documentation site for an API project version
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deploy-documentation-site
- description: List mock server instances for an API project
  hints:
    openWorld: false
    readOnly: true
  name: list-mock-servers
- description: Deploy a mock server that simulates API responses for an API project version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-mock-server
- description: List all API keys for the Sideko organization
  hints:
    openWorld: false
    readOnly: true
  name: list-api-keys
- description: Create a new Sideko API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-key
---
