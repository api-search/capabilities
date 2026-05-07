---
categories: []
consumed_apis: []
description: Unified capability combining Sanity's Content API and Projects API for full content lifecycle management. Used by developers, content engineers, and editorial teams to query, create, update, and manage content in Sanity Content Lake, as well as manage projects, datasets, and webhooks.
layout: capability
name: Sanity Content Management
operations:
- description: Execute a GROQ query against a dataset
  method: POST
  name: query-documents
  path: /v1/content/query
- description: Apply create, update, patch, or delete mutations
  method: POST
  name: mutate-documents
  path: /v1/content/mutate
- description: List all accessible Sanity projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: List datasets in a project
  method: GET
  name: list-datasets
  path: /v1/projects/{projectId}/datasets
- description: List API tokens for a project
  method: GET
  name: list-tokens
  path: /v1/projects/{projectId}/tokens
- description: List webhooks for a project
  method: GET
  name: list-webhooks
  path: /v1/projects/{projectId}/webhooks
- description: Create a new webhook
  method: POST
  name: create-webhook
  path: /v1/projects/{projectId}/webhooks
personas: []
provider_name: Sanity
provider_slug: sanity
search_terms:
- create a new webhook
- sanity
- list all accessible sanity projects
- write operations on content lake documents
- create a new document in sanity content lake
- create document
- delete a document from sanity content lake
- list tokens
- apply create, update, patch, or delete mutations
- api token management
- mutate documents
- execute a groq query against a dataset
- update document
- query sanity content lake documents using groq syntax
- webhook configuration for content events
- create webhook
- query content
- list all sanity projects accessible with the current token
- dataset management for a project
- list projects
- structured content
- configure a webhook to receive sanity content change notifications
- list webhooks
- groq
- update an existing document in sanity content lake
- content management
- developer platform
- project administration
- query content lake documents using groq
- list api tokens for a project
- query documents
- list datasets
- list datasets in a sanity project
- headless cms
- delete document
- list datasets in a project
- real-time
- list webhooks for a project
- sanity project management
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sanity Content Management\n  description: Unified capability combining Sanity's Content API and Projects API for full content lifecycle management. Used\n    by developers, content engineers, and editorial teams to query, create, update, and manage content in Sanity Content Lake,\n    as well as manage projects, datasets, and webhooks.\n  tags:\n  - Content Management\n  - Headless CMS\n  - GROQ\n  - Project Administration\n  - Sanity\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SANITY_API_TOKEN: SANITY_API_TOKEN\n    SANITY_PROJECT_ID: SANITY_PROJECT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: sanity-content\n    baseUri: https://{{SANITY_PROJECT_ID}}.api.sanity.io/v2024-01-01\n    description: Sanity Content Lake API for querying and mutating structured content\n    authentication:\n      type: bearer\n      token: '{{SANITY_API_TOKEN}}'\n    resources:\n    - name: query\n\
  \      path: /data/query\n      description: GROQ query endpoint for reading content\n      operations:\n      - name: query-documents\n        method: GET\n        description: Query Content Lake documents using GROQ\n        inputParameters:\n        - name: dataset\n          in: path\n          type: string\n          required: true\n          description: Dataset name (e.g., production)\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: GROQ query string\n        - name: perspective\n          in: query\n          type: string\n          required: false\n          description: Content perspective (drafts, published, raw)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-documents-post\n        method: POST\n        description: Query Content Lake via POST for large queries\n        inputParameters:\n        - name: dataset\n\
  \          in: path\n          type: string\n          required: true\n          description: Dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            params: '{{tools.params}}'\n    - name: mutations\n      path: /data/mutate\n      description: Document create, update, and delete operations\n      operations:\n      - name: mutate-documents\n        method: POST\n        description: Apply batch mutations to Content Lake documents\n        inputParameters:\n        - name: dataset\n          in: path\n          type: string\n          required: true\n          description: Dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            mutations: '{{tools.mutations}}'\n\
  \    - name: assets\n      path: /assets/images\n      description: Image asset upload and management\n      operations:\n      - name: upload-image-asset\n        method: POST\n        description: Upload an image asset to Content Lake\n        inputParameters:\n        - name: dataset\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sanity-projects\n    baseUri: https://api.sanity.io/v2024-01-01\n    description: Sanity management API for project, dataset, token, and webhook administration\n    authentication:\n      type: bearer\n      token: '{{SANITY_API_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      description: Project lifecycle management\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects accessible to the authenticated\
  \ user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new Sanity project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n      - name: get-project\n        method: GET\n        description: Get details for a specific project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /projects/{projectId}/datasets\n      description: Dataset management for a project\n      operations:\n      - name: list-datasets\n        method:\
  \ GET\n        description: List all datasets in a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /projects/{projectId}/tokens\n      description: API token management\n      operations:\n      - name: list-tokens\n        method: GET\n        description: List API tokens for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-token\n        method: POST\n        description: Create a new API token for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            label: '{{tools.label}}'\n            roleName: '{{tools.roleName}}'\n    - name: webhooks\n      path: /hooks/projects/{projectId}\n      description: Webhook configuration management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List webhooks for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a webhook for event notifications\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            url: '{{tools.url}}'\n            dataset: '{{tools.dataset}}'\n            true: '{{tools.on}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sanity-content-management-api\n    description: Unified REST API for Sanity content and project management.\n    resources:\n    - path: /v1/content/query\n      name: content-query\n      description: Query Content Lake documents using GROQ\n      operations:\n      - method: POST\n        name: query-documents\n        description: Execute a GROQ query against a dataset\n        call: sanity-content.query-documents-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/mutate\n      name: content-mutate\n      description: Write operations on Content Lake documents\n\
  \      operations:\n      - method: POST\n        name: mutate-documents\n        description: Apply create, update, patch, or delete mutations\n        call: sanity-content.mutate-documents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Sanity project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all accessible Sanity projects\n        call: sanity-projects.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/datasets\n      name: datasets\n      description: Dataset management for a project\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List datasets in a project\n        call: sanity-projects.list-datasets\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/projects/{projectId}/tokens\n      name: tokens\n      description: API token management\n      operations:\n      - method: GET\n        name: list-tokens\n        description: List API tokens for a project\n        call: sanity-projects.list-tokens\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/webhooks\n      name: webhooks\n      description: Webhook configuration for content events\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhooks for a project\n        call: sanity-projects.list-webhooks\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a new webhook\n        call: sanity-projects.create-webhook\n        with:\n          projectId:\
  \ rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sanity-content-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Sanity content management and querying.\n    tools:\n    - name: query-content\n      description: Query Sanity Content Lake documents using GROQ syntax\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sanity-content.query-documents-post\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-document\n      description: Create a new document in Sanity Content Lake\n      hints:\n        readOnly: false\n        destructive: false\n      call: sanity-content.mutate-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-document\n      description: Update an existing document in Sanity Content Lake\n      hints:\n \
  \       readOnly: false\n        idempotent: false\n      call: sanity-content.mutate-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document\n      description: Delete a document from Sanity Content Lake\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sanity-content.mutate-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all Sanity projects accessible with the current token\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sanity-projects.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-datasets\n      description: List datasets in a Sanity project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sanity-projects.list-datasets\n      with:\n        projectId: tools.projectId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Configure a webhook to receive Sanity content change notifications\n      hints:\n        readOnly: false\n      call: sanity-projects.create-webhook\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sanity/refs/heads/main/capabilities/content-management.yaml
tags:
- Content Management
- Headless CMS
- GROQ
- Project Administration
- Sanity
tools:
- description: Query Sanity Content Lake documents using GROQ syntax
  hints:
    openWorld: false
    readOnly: true
  name: query-content
- description: Create a new document in Sanity Content Lake
  hints:
    destructive: false
    readOnly: false
  name: create-document
- description: Update an existing document in Sanity Content Lake
  hints:
    idempotent: false
    readOnly: false
  name: update-document
- description: Delete a document from Sanity Content Lake
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-document
- description: List all Sanity projects accessible with the current token
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: List datasets in a Sanity project
  hints:
    openWorld: false
    readOnly: true
  name: list-datasets
- description: Configure a webhook to receive Sanity content change notifications
  hints:
    readOnly: false
  name: create-webhook
---
