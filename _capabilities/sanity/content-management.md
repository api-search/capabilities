---
categories: []
consumed_apis:
- sanity-content
- sanity-projects
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
- update document
- create webhook
- mutate documents
- sanity project management
- dataset management for a project
- delete document
- list webhooks for a project
- list tokens
- update an existing document in sanity content lake
- create a new webhook
- structured content
- developer platform
- create a new document in sanity content lake
- query content
- apply create, update, patch, or delete mutations
- list projects
- webhook configuration for content events
- query sanity content lake documents using groq syntax
- real-time
- api token management
- query content lake documents using groq
- list all sanity projects accessible with the current token
- list webhooks
- groq
- delete a document from sanity content lake
- create document
- write operations on content lake documents
- headless cms
- query documents
- list all accessible sanity projects
- list api tokens for a project
- configure a webhook to receive sanity content change notifications
- list datasets in a project
- list datasets
- content management
- execute a groq query against a dataset
- list datasets in a sanity project
- sanity
- project administration
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sanity Content Management\"\n  description: >-\n    Unified capability combining Sanity's Content API and Projects API for\n    full content lifecycle management. Used by developers, content engineers,\n    and editorial teams to query, create, update, and manage content in\n    Sanity Content Lake, as well as manage projects, datasets, and webhooks.\n  tags:\n    - Content Management\n    - Headless CMS\n    - GROQ\n    - Project Administration\n    - Sanity\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SANITY_API_TOKEN: SANITY_API_TOKEN\n      SANITY_PROJECT_ID: SANITY_PROJECT_ID\n\ncapability:\n  consumes:\n    - import: sanity-content\n      location: ./shared/sanity-content.yaml\n    - import: sanity-projects\n      location: ./shared/sanity-projects.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sanity-content-management-api\n      description:\
  \ \"Unified REST API for Sanity content and project management.\"\n      resources:\n        - path: /v1/content/query\n          name: content-query\n          description: \"Query Content Lake documents using GROQ\"\n          operations:\n            - method: POST\n              name: query-documents\n              description: \"Execute a GROQ query against a dataset\"\n              call: \"sanity-content.query-documents-post\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/content/mutate\n          name: content-mutate\n          description: \"Write operations on Content Lake documents\"\n          operations:\n            - method: POST\n              name: mutate-documents\n              description: \"Apply create, update, patch, or delete mutations\"\n              call: \"sanity-content.mutate-documents\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n\n        - path: /v1/projects\n          name: projects\n          description: \"Sanity project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all accessible Sanity projects\"\n              call: \"sanity-projects.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/datasets\n          name: datasets\n          description: \"Dataset management for a project\"\n          operations:\n            - method: GET\n              name: list-datasets\n              description: \"List datasets in a project\"\n              call: \"sanity-projects.list-datasets\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/tokens\n          name:\
  \ tokens\n          description: \"API token management\"\n          operations:\n            - method: GET\n              name: list-tokens\n              description: \"List API tokens for a project\"\n              call: \"sanity-projects.list-tokens\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/webhooks\n          name: webhooks\n          description: \"Webhook configuration for content events\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhooks for a project\"\n              call: \"sanity-projects.list-webhooks\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n\
  \              description: \"Create a new webhook\"\n              call: \"sanity-projects.create-webhook\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sanity-content-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sanity content management and querying.\"\n      tools:\n        - name: query-content\n          description: \"Query Sanity Content Lake documents using GROQ syntax\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sanity-content.query-documents-post\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-document\n          description: \"Create a new document in Sanity Content Lake\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n          call: \"sanity-content.mutate-documents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-document\n          description: \"Update an existing document in Sanity Content Lake\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sanity-content.mutate-documents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-document\n          description: \"Delete a document from Sanity Content Lake\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sanity-content.mutate-documents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-projects\n          description: \"List all Sanity projects accessible with the current\
  \ token\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sanity-projects.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-datasets\n          description: \"List datasets in a Sanity project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sanity-projects.list-datasets\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-webhook\n          description: \"Configure a webhook to receive Sanity content change notifications\"\n          hints:\n            readOnly: false\n          call: \"sanity-projects.create-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
