---
categories: []
consumed_apis: []
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
- sdk generation
- developer experience
- list documentation sites
- deploy or update an api documentation site for an api project version
- create a new api project
- list sdk generations
- get an api project by id
- deploy mock server
- list documentation sites deployed for an api project
- list all api keys for the sideko organization
- create a new api project in sideko
- deploy a documentation site
- api key management
- platform
- update an api project
- mock server management
- single api project operations
- get details of a specific api project
- deploy a mock server that simulates api responses for an api project version
- get api project
- mock servers
- list sdks
- documentation
- api tooling
- list versions
- delete an api project
- list mock servers
- list all api projects
- api project management
- trigger sdk generation for a language (python, typescript, java, go, ruby, rust)
- delete project
- create project
- list projects
- list all versions of an api project
- create api project
- create a new sideko api key
- sdk generation jobs
- list docs
- cli
- list api projects
- list api keys
- list api versions
- list sdk generation jobs
- deploy documentation site
- list all api projects in the sideko organization
- deploy a mock server
- list sdk generation jobs for an api project
- delete api project
- get project
- generate sdk
- update api project
- update an existing api project name or description
- sdks
- api version management
- trigger sdk generation
- documentation sites
- deploy docs
- create a new api key
- list mock server instances for an api project
- update project
- delete an api project and all its versions, sdks, docs, and mock servers
- create api key
slug: api-tooling-lifecycle
source_filename: api-tooling-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sideko API Tooling Lifecycle\n  description: Unified workflow capability for managing the complete API tooling lifecycle on the Sideko platform. Enables\n    API platform teams to programmatically manage API projects, upload specifications, generate multi-language SDKs, deploy\n    documentation sites, and run mock servers — all through a single unified interface. Designed for API platform engineers\n    and DevOps teams automating their API developer experience pipeline.\n  tags:\n  - API Tooling\n  - SDK Generation\n  - Documentation\n  - Mock Servers\n  - Platform\n  - Developer Experience\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SIDEKO_API_KEY: SIDEKO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sideko\n    baseUri: https://api.sideko.dev/v1\n    description: Sideko platform API for managing API tooling lifecycle\n    authentication:\n      type: apikey\n      key:\
  \ x-sideko-key\n      value: '{{SIDEKO_API_KEY}}'\n      placement: header\n    resources:\n    - name: api-projects\n      path: /api-projects\n      description: API project management\n      operations:\n      - name: list-api-projects\n        method: GET\n        description: List all API projects\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-project\n        method: POST\n        description: Create a new API project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n      \
  \    data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: api-project\n      path: /api-projects/{projectId}\n      description: Single API project operations\n      operations:\n      - name: get-api-project\n        method: GET\n        description: Get an API project by ID\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-api-project\n        method: PUT\n        description: Update an API project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: delete-api-project\n        method: DELETE\n        description: Delete an API project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-versions\n      path: /api-projects/{projectId}/versions\n      description: API version management\n      operations:\n      - name: list-api-versions\n        method: GET\n        description: List all versions of an API project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: sdk-generations\n      path: /api-projects/{projectId}/sdks\n      description: SDK generation job management\n      operations:\n      - name: list-sdk-generations\n        method: GET\n        description: List SDK generation jobs for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: trigger-sdk-generation\n        method: POST\n        description: Trigger an SDK generation job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n        body:\n          type: json\n          data:\n            language: '{{tools.language}}'\n            versionId: '{{tools.versionId}}'\n    - name: documentation-sites\n      path: /api-projects/{projectId}/docs\n      description: Documentation site management\n      operations:\n      - name: list-documentation-sites\n        method: GET\n        description: List documentation sites for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-documentation-site\n        method: POST\n        description: Deploy an API documentation site\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            versionId: '{{tools.versionId}}'\n    - name: mock-servers\n      path: /api-projects/{projectId}/mock-servers\n      description: Mock server management\n      operations:\n      - name: list-mock-servers\n        method: GET\n        description: List mock server instances for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-mock-server\n        method: POST\n        description: Deploy a mock server instance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n   \
  \       description: Project UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            versionId: '{{tools.versionId}}'\n    - name: api-keys\n      path: /auth/api-keys\n      description: API key management\n      operations:\n      - name: list-api-keys\n        method: GET\n        description: List all API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create a new API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sideko-tooling-api\n    description: Unified\
  \ REST API for managing the complete Sideko API tooling lifecycle.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: API project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all API projects\n        call: sideko.list-api-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new API project\n        call: sideko.create-api-project\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: project\n      description: Single API project operations\n      operations:\n      - method: GET\n        name: get-project\n        description: Get an API project by ID\n        call: sideko.get-api-project\n        with:\n          projectId: rest.projectId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-project\n        description: Update an API project\n        call: sideko.update-api-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete an API project\n        call: sideko.delete-api-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/versions\n      name: versions\n      description: API version management\n      operations:\n      - method: GET\n        name: list-versions\n        description: List API versions\n        call: sideko.list-api-versions\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/projects/{projectId}/sdks\n      name: sdks\n      description: SDK generation jobs\n      operations:\n      - method: GET\n        name: list-sdks\n        description: List SDK generation jobs\n        call: sideko.list-sdk-generations\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: generate-sdk\n        description: Trigger SDK generation\n        call: sideko.trigger-sdk-generation\n        with:\n          projectId: rest.projectId\n          language: rest.language\n          versionId: rest.versionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/docs\n      name: documentation\n      description: Documentation sites\n      operations:\n      - method: GET\n        name: list-docs\n        description: List documentation sites\n        call: sideko.list-documentation-sites\n        with:\n     \
  \     projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: deploy-docs\n        description: Deploy a documentation site\n        call: sideko.deploy-documentation-site\n        with:\n          projectId: rest.projectId\n          versionId: rest.versionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/mock-servers\n      name: mock-servers\n      description: Mock server management\n      operations:\n      - method: GET\n        name: list-mock-servers\n        description: List mock servers\n        call: sideko.list-mock-servers\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: deploy-mock-server\n        description: Deploy a mock server\n        call: sideko.deploy-mock-server\n        with:\n          projectId: rest.projectId\n\
  \          versionId: rest.versionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: api-keys\n      description: API key management\n      operations:\n      - method: GET\n        name: list-api-keys\n        description: List API keys\n        call: sideko.list-api-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-key\n        description: Create a new API key\n        call: sideko.create-api-key\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sideko-tooling-mcp\n    transport: http\n    description: MCP server for AI-assisted API tooling lifecycle management on the Sideko platform.\n    tools:\n    - name: list-api-projects\n      description: List all API projects in the Sideko organization\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: sideko.list-api-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-project\n      description: Create a new API project in Sideko\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sideko.create-api-project\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-project\n      description: Get details of a specific API project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sideko.get-api-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-api-project\n      description: Update an existing API project name or description\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n\
  \      call: sideko.update-api-project\n      with:\n        projectId: tools.projectId\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-project\n      description: Delete an API project and all its versions, SDKs, docs, and mock servers\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sideko.delete-api-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-versions\n      description: List all versions of an API project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sideko.list-api-versions\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sdk-generations\n      description: List SDK generation jobs for an API project\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: sideko.list-sdk-generations\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-sdk-generation\n      description: Trigger SDK generation for a language (python, typescript, java, go, ruby, rust)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sideko.trigger-sdk-generation\n      with:\n        projectId: tools.projectId\n        language: tools.language\n        versionId: tools.versionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-documentation-sites\n      description: List documentation sites deployed for an API project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sideko.list-documentation-sites\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: deploy-documentation-site\n      description: Deploy or update an API documentation site for an API project version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sideko.deploy-documentation-site\n      with:\n        projectId: tools.projectId\n        versionId: tools.versionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mock-servers\n      description: List mock server instances for an API project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sideko.list-mock-servers\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-mock-server\n      description: Deploy a mock server that simulates API responses for an API project version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sideko.deploy-mock-server\n\
  \      with:\n        projectId: tools.projectId\n        versionId: tools.versionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List all API keys for the Sideko organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sideko.list-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create a new Sideko API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sideko.create-api-key\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
