---
categories: []
consumed_apis: []
description: Workflow capability for managing software artifacts, components, assets, and repositories in Sonatype Nexus Repository Manager. Supports DevOps engineers, build engineers, and platform teams performing artifact lifecycle management including publishing, searching, organizing, and cleaning up artifacts across Maven, npm, Docker, PyPI, NuGet, and other formats.
layout: capability
name: Sonatype Nexus Artifact Management
operations:
- description: List all repositories
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: Get repository details by name
  method: GET
  name: get-repository
  path: /v1/repositories
- description: Delete a repository
  method: DELETE
  name: delete-repository
  path: /v1/repositories
- description: Invalidate repository cache
  method: POST
  name: invalidate-cache
  path: /v1/repositories
- description: List components in a repository
  method: GET
  name: list-components
  path: /v1/components
- description: Get a single component by ID
  method: GET
  name: get-component
  path: /v1/components
- description: Delete a component
  method: DELETE
  name: delete-component
  path: /v1/components
- description: List assets in a repository
  method: GET
  name: list-assets
  path: /v1/assets
- description: Get a single asset by ID
  method: GET
  name: get-asset
  path: /v1/assets
- description: Delete an asset
  method: DELETE
  name: delete-asset
  path: /v1/assets
- description: Search for components across repositories
  method: GET
  name: search-components
  path: /v1/search
- description: Search for assets
  method: GET
  name: search-assets
  path: /v1/search
personas: []
provider_name: Sonatype Nexus
provider_slug: sonatype-nexus
search_terms:
- delete an asset by id
- get details for a specific repository
- devops
- get details for a specific asset by id
- delete repository
- get component
- component and asset search
- search assets
- get a single asset by id
- delete a repository by name
- list all nexus repositories
- repository management and configuration
- components
- software component lifecycle management
- invalidate the cache for a proxy or group repository
- npm
- get repository
- search for binary assets across repositories
- list assets in a repository
- package management
- list all repositories
- maven
- software supply chain
- get a single component by id
- delete a repository
- search components
- search for components across nexus repositories by name, version, format, or query
- invalidate repository cache
- get details for a specific component by id
- delete a component by id
- list binary assets in a repository
- invalidate cache
- repository
- search for components across repositories
- delete an asset
- binary asset management
- get repository details by name
- delete component
- artifact management
- list components in a repository
- delete a component
- get asset
- sonatype nexus
- assets
- search for assets
- docker
- list repositories
- list assets
- delete asset
- list components
slug: artifact-management
source_filename: artifact-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sonatype Nexus Artifact Management\n  description: Workflow capability for managing software artifacts, components, assets, and repositories in Sonatype Nexus\n    Repository Manager. Supports DevOps engineers, build engineers, and platform teams performing artifact lifecycle management\n    including publishing, searching, organizing, and cleaning up artifacts across Maven, npm, Docker, PyPI, NuGet, and other\n    formats.\n  tags:\n  - Sonatype Nexus\n  - Artifact Management\n  - DevOps\n  - Repository\n  - Components\n  - Assets\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NEXUS_USERNAME: NEXUS_USERNAME\n    NEXUS_PASSWORD: NEXUS_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: nexus\n    baseUri: https://{nexus-host}/service/rest\n    description: Sonatype Nexus Repository Manager REST API v3\n    authentication:\n      type: basic\n      username: '{{NEXUS_USERNAME}}'\n\
  \      password: '{{NEXUS_PASSWORD}}'\n    resources:\n    - name: repositories\n      path: /v1/repositories\n      description: Manage artifact repositories across all supported formats\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List repositories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-repository\n        method: DELETE\n        description: Delete repository of any format\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Name of the repository to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-repository\n        method: GET\n        description: Get repository details\n        inputParameters:\n        - name: repositoryName\n\
  \          in: path\n          type: string\n          required: true\n          description: Name of the repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invalidate-repository-cache\n        method: POST\n        description: Invalidate repository cache (proxy or group repositories)\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Name of the repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components\n      path: /v1/components\n      description: Manage software components in repositories\n      operations:\n      - name: list-components\n        method: GET\n        description: List components\n        inputParameters:\n        - name: repository\n          in: query\n        \
  \  type: string\n          required: true\n          description: Repository name to list components from\n        - name: continuationToken\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-component\n        method: GET\n        description: Get a single component\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Component ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-component\n        method: DELETE\n        description: Delete a single component\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Component ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /v1/assets\n      description: Manage binary assets in repositories\n      operations:\n      - name: list-assets\n        method: GET\n        description: List assets\n        inputParameters:\n        - name: repository\n          in: query\n          type: string\n          required: true\n          description: Repository name\n        - name: continuationToken\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-asset\n        method: GET\n        description: Get a single asset\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n       \
  \   description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-asset\n        method: DELETE\n        description: Delete a single asset\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /v1/search\n      description: Search for components and assets across repositories\n      operations:\n      - name: search-components\n        method: GET\n        description: Search components\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query string\n        - name: repository\n          in: query\n          type: string\n          required:\
  \ false\n          description: Repository name filter\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Format filter (maven2, npm, docker, etc)\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Component name filter\n        - name: version\n          in: query\n          type: string\n          required: false\n          description: Component version filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-assets\n        method: GET\n        description: Search assets\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query string\n        - name: repository\n          in: query\n          type: string\n          required: false\n          description: Repository\
  \ name filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-users\n      path: /v1/security/users\n      description: Manage Nexus users and authentication\n      operations:\n      - name: list-users\n        method: GET\n        description: Retrieve a list of users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user in the default source\n        body:\n          type: json\n          data:\n            userId: '{{tools.userId}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            emailAddress: '{{tools.emailAddress}}'\n            password: '{{tools.password}}'\n            status: '{{tools.status}}'\n            roles: '{{tools.roles}}'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-roles\n      path: /v1/security/roles\n      description: Manage Nexus roles and permissions\n      operations:\n      - name: list-roles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-role\n        method: POST\n        description: Create role\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            name:\
  \ '{{tools.name}}'\n            description: '{{tools.description}}'\n            privileges: '{{tools.privileges}}'\n            roles: '{{tools.roles}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /v1/tasks\n      description: Manage and execute background tasks\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-task\n        method: GET\n        description: Get a single task by id\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-task\n  \
  \      method: POST\n        description: Run task\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task ID to run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /v1/status\n      description: System health and status checks\n      operations:\n      - name: get-status\n        method: GET\n        description: Health check endpoint that validates server can respond to read requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-status\n        method: GET\n        description: Health check endpoint that returns the results of the system status checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ blob-stores\n      path: /v1/blobstores\n      description: Manage blob storage backends\n      operations:\n      - name: list-blob-stores\n        method: GET\n        description: List the blob stores\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-blob-store\n        method: DELETE\n        description: Delete a blob store by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Blob store name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nexus-artifact-management-api\n    description: Unified REST API for Nexus artifact lifecycle management.\n    resources:\n    - path: /v1/repositories\n      name: repositories\n      description: Repository management\
  \ and configuration\n      operations:\n      - method: GET\n        name: list-repositories\n        description: List all repositories\n        call: nexus.list-repositories\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-repository\n        description: Get repository details by name\n        call: nexus.get-repository\n        with:\n          repositoryName: rest.repositoryName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-repository\n        description: Delete a repository\n        call: nexus.delete-repository\n        with:\n          repositoryName: rest.repositoryName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: invalidate-cache\n        description: Invalidate repository cache\n        call: nexus.invalidate-repository-cache\n        with:\n          repositoryName: rest.repositoryName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/components\n      name: components\n      description: Software component lifecycle management\n      operations:\n      - method: GET\n        name: list-components\n        description: List components in a repository\n        call: nexus.list-components\n        with:\n          repository: rest.repository\n          continuationToken: rest.continuationToken\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-component\n        description: Get a single component by ID\n        call: nexus.get-component\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-component\n        description: Delete a component\n        call: nexus.delete-component\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Binary asset management\n      operations:\n      - method: GET\n        name: list-assets\n        description: List assets in a repository\n        call: nexus.list-assets\n        with:\n          repository: rest.repository\n          continuationToken: rest.continuationToken\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-asset\n        description: Get a single asset by ID\n        call: nexus.get-asset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-asset\n        description: Delete an asset\n        call: nexus.delete-asset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Component and asset search\n\
  \      operations:\n      - method: GET\n        name: search-components\n        description: Search for components across repositories\n        call: nexus.search-components\n        with:\n          q: rest.q\n          repository: rest.repository\n          format: rest.format\n          name: rest.name\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: search-assets\n        description: Search for assets\n        call: nexus.search-assets\n        with:\n          q: rest.q\n          repository: rest.repository\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: nexus-artifact-management-mcp\n    transport: http\n    description: MCP server for AI-assisted artifact management in Sonatype Nexus.\n    tools:\n    - name: list-repositories\n      description: List all Nexus repositories\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: nexus.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-repository\n      description: Get details for a specific repository\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.get-repository\n      with:\n        repositoryName: tools.repositoryName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-repository\n      description: Delete a repository by name\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nexus.delete-repository\n      with:\n        repositoryName: tools.repositoryName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invalidate-repository-cache\n      description: Invalidate the cache for a proxy or group repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nexus.invalidate-repository-cache\n\
  \      with:\n        repositoryName: tools.repositoryName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-components\n      description: List components in a repository\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.list-components\n      with:\n        repository: tools.repository\n        continuationToken: tools.continuationToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-component\n      description: Get details for a specific component by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.get-component\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-component\n      description: Delete a component by ID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nexus.delete-component\n      with:\n        id: tools.id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List binary assets in a repository\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.list-assets\n      with:\n        repository: tools.repository\n        continuationToken: tools.continuationToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get details for a specific asset by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.get-asset\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-asset\n      description: Delete an asset by ID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nexus.delete-asset\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ search-components\n      description: Search for components across Nexus repositories by name, version, format, or query\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.search-components\n      with:\n        q: tools.q\n        repository: tools.repository\n        format: tools.format\n        name: tools.name\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-assets\n      description: Search for binary assets across repositories\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.search-assets\n      with:\n        q: tools.q\n        repository: tools.repository\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sonatype-nexus/refs/heads/main/capabilities/artifact-management.yaml
tags:
- Sonatype Nexus
- Artifact Management
- DevOps
- Repository
- Components
- Assets
tools:
- description: List all Nexus repositories
  hints:
    idempotent: true
    readOnly: true
  name: list-repositories
- description: Get details for a specific repository
  hints:
    idempotent: true
    readOnly: true
  name: get-repository
- description: Delete a repository by name
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-repository
- description: Invalidate the cache for a proxy or group repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invalidate-repository-cache
- description: List components in a repository
  hints:
    idempotent: true
    readOnly: true
  name: list-components
- description: Get details for a specific component by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-component
- description: Delete a component by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-component
- description: List binary assets in a repository
  hints:
    idempotent: true
    readOnly: true
  name: list-assets
- description: Get details for a specific asset by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-asset
- description: Delete an asset by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-asset
- description: Search for components across Nexus repositories by name, version, format, or query
  hints:
    idempotent: true
    readOnly: true
  name: search-components
- description: Search for binary assets across repositories
  hints:
    idempotent: true
    readOnly: true
  name: search-assets
---
