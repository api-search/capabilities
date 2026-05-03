---
categories: []
consumed_apis:
- nexus
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
- invalidate cache
- artifact management
- assets
- repository management and configuration
- invalidate the cache for a proxy or group repository
- delete an asset by id
- package management
- software supply chain
- get repository details by name
- delete a repository by name
- docker
- get component
- list components in a repository
- delete asset
- list assets
- delete a repository
- binary asset management
- get a single component by id
- get a single asset by id
- delete an asset
- delete component
- get asset
- list all nexus repositories
- get repository
- get details for a specific component by id
- list all repositories
- invalidate repository cache
- sonatype nexus
- search components
- get details for a specific repository
- software component lifecycle management
- delete a component
- delete a component by id
- search for binary assets across repositories
- search for components across nexus repositories by name, version, format, or query
- search assets
- delete repository
- get details for a specific asset by id
- components
- component and asset search
- list assets in a repository
- search for components across repositories
- maven
- list components
- devops
- npm
- repository
- list repositories
- search for assets
- list binary assets in a repository
slug: artifact-management
source_filename: artifact-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sonatype Nexus Artifact Management\"\n  description: >-\n    Workflow capability for managing software artifacts, components, assets, and\n    repositories in Sonatype Nexus Repository Manager. Supports DevOps engineers,\n    build engineers, and platform teams performing artifact lifecycle management\n    including publishing, searching, organizing, and cleaning up artifacts across\n    Maven, npm, Docker, PyPI, NuGet, and other formats.\n  tags:\n    - Sonatype Nexus\n    - Artifact Management\n    - DevOps\n    - Repository\n    - Components\n    - Assets\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEXUS_USERNAME: NEXUS_USERNAME\n      NEXUS_PASSWORD: NEXUS_PASSWORD\n\ncapability:\n  consumes:\n    - import: nexus\n      location: ./shared/nexus-repository.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: nexus-artifact-management-api\n      description:\
  \ \"Unified REST API for Nexus artifact lifecycle management.\"\n      resources:\n        - path: /v1/repositories\n          name: repositories\n          description: \"Repository management and configuration\"\n          operations:\n            - method: GET\n              name: list-repositories\n              description: \"List all repositories\"\n              call: \"nexus.list-repositories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-repository\n              description: \"Get repository details by name\"\n              call: \"nexus.get-repository\"\n              with:\n                repositoryName: \"rest.repositoryName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-repository\n              description: \"Delete a repository\"\n              call: \"\
  nexus.delete-repository\"\n              with:\n                repositoryName: \"rest.repositoryName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: invalidate-cache\n              description: \"Invalidate repository cache\"\n              call: \"nexus.invalidate-repository-cache\"\n              with:\n                repositoryName: \"rest.repositoryName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/components\n          name: components\n          description: \"Software component lifecycle management\"\n          operations:\n            - method: GET\n              name: list-components\n              description: \"List components in a repository\"\n              call: \"nexus.list-components\"\n              with:\n                repository: \"rest.repository\"\n                continuationToken: \"\
  rest.continuationToken\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-component\n              description: \"Get a single component by ID\"\n              call: \"nexus.get-component\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-component\n              description: \"Delete a component\"\n              call: \"nexus.delete-component\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n          description: \"Binary asset management\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List assets in\
  \ a repository\"\n              call: \"nexus.list-assets\"\n              with:\n                repository: \"rest.repository\"\n                continuationToken: \"rest.continuationToken\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-asset\n              description: \"Get a single asset by ID\"\n              call: \"nexus.get-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-asset\n              description: \"Delete an asset\"\n              call: \"nexus.delete-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Component\
  \ and asset search\"\n          operations:\n            - method: GET\n              name: search-components\n              description: \"Search for components across repositories\"\n              call: \"nexus.search-components\"\n              with:\n                q: \"rest.q\"\n                repository: \"rest.repository\"\n                format: \"rest.format\"\n                name: \"rest.name\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: search-assets\n              description: \"Search for assets\"\n              call: \"nexus.search-assets\"\n              with:\n                q: \"rest.q\"\n                repository: \"rest.repository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: nexus-artifact-management-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted artifact management in Sonatype Nexus.\"\n      tools:\n        - name: list-repositories\n          description: \"List all Nexus repositories\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.list-repositories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-repository\n          description: \"Get details for a specific repository\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.get-repository\"\n          with:\n            repositoryName: \"tools.repositoryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-repository\n          description: \"Delete a repository by name\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n\
  \          call: \"nexus.delete-repository\"\n          with:\n            repositoryName: \"tools.repositoryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: invalidate-repository-cache\n          description: \"Invalidate the cache for a proxy or group repository\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"nexus.invalidate-repository-cache\"\n          with:\n            repositoryName: \"tools.repositoryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-components\n          description: \"List components in a repository\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.list-components\"\n          with:\n            repository: \"tools.repository\"\n            continuationToken: \"tools.continuationToken\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-component\n          description: \"Get details for a specific component by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.get-component\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-component\n          description: \"Delete a component by ID\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"nexus.delete-component\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List binary assets in a repository\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.list-assets\"\
  \n          with:\n            repository: \"tools.repository\"\n            continuationToken: \"tools.continuationToken\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-asset\n          description: \"Get details for a specific asset by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.get-asset\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-asset\n          description: \"Delete an asset by ID\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"nexus.delete-asset\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-components\n          description: \"Search for components\
  \ across Nexus repositories by name, version, format, or query\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.search-components\"\n          with:\n            q: \"tools.q\"\n            repository: \"tools.repository\"\n            format: \"tools.format\"\n            name: \"tools.name\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-assets\n          description: \"Search for binary assets across repositories\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.search-assets\"\n          with:\n            q: \"tools.q\"\n            repository: \"tools.repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
