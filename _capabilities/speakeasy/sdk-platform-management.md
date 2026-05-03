---
api_specs:
- filename: speakeasy-openapi.yml
  format: yaml
  label: speakeasy
  slug: speakeasy
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/speakeasy/refs/heads/main/openapi/speakeasy-openapi.yml
categories: []
consumed_apis:
- speakeasy
description: Unified workflow capability for managing the Speakeasy SDK generation platform. Combines workspace management, organization administration, artifact registry, code sample retrieval, and OpenAPI improvement suggestions into a single workflow interface. Used by platform administrators, API producers, and DevOps engineers managing SDK pipelines.
layout: capability
name: Speakeasy SDK Platform Management
operations:
- description: Get Workspaces for a User
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Get Workspace
  method: GET
  name: get-workspace
  path: /v1/workspace/{workspace_id}
- description: Get Tokens for a Particular Workspace
  method: GET
  name: list-workspace-tokens
  path: /v1/workspace/{workspace_id}/tokens
- description: Create a Token for a Particular Workspace
  method: POST
  name: create-workspace-token
  path: /v1/workspace/{workspace_id}/tokens
- description: Get Organizations for a User
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Get Organization
  method: GET
  name: get-organization
  path: /v1/organizations/{organizationID}
- description: List Artifact Namespaces
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: Retrieve Usage Snippets
  method: GET
  name: get-code-samples
  path: /v1/code-samples
- description: Validate the Current API Key
  method: GET
  name: validate-api-key
  path: /v1/auth/validate
- description: Generate Suggestions for Improving an OpenAPI Document
  method: POST
  name: suggest-openapi
  path: /v1/suggest/openapi
personas: []
provider_name: Speakeasy
provider_slug: speakeasy
search_terms:
- list all organizations the authenticated user belongs to
- get workspaces for a user
- retrieve usage snippets
- generate suggestions for improving an openapi document
- create a new speakeasy organization
- get workspace
- create organization
- list artifact namespaces in the registry
- create a new speakeasy workspace within an organization
- generate openapi improvement suggestions
- list workspace tokens
- get details for a specific workspace by id
- list all workspaces accessible to the authenticated user
- list artifact namespaces in the speakeasy registry containing spec revisions
- terraform
- create a new api token for a workspace
- list artifact namespaces
- suggest openapi improvements
- get a specific workspace by id
- get a specific organization
- get organizations for a user
- code generation
- get information about the authenticated user including email and workspaces
- get current user
- create a token for a particular workspace
- retrieve sdk code samples for namespaces
- get tokens for a particular workspace
- list and manage speakeasy workspaces
- list namespaces
- validate the current speakeasy api key and retrieve workspace details
- get organization
- openapi
- validate api key
- list organizations
- retrieve sdk code samples for a specific namespace and revision
- list api tokens for a specific workspace
- documentation
- list workspaces
- mcp
- sdks
- ai
- list organizations for the authenticated user
- platform
- validate api key and check access
- validate the current api key
- create workspace token
- suggest openapi
- get code samples
- create workspace
- get details for a specific organization by id
- testing
- manage workspace access tokens
- generate ai-powered suggestions for improving an openapi document
slug: sdk-platform-management
source_filename: sdk-platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Speakeasy SDK Platform Management\"\n  description: >-\n    Unified workflow capability for managing the Speakeasy SDK generation platform.\n    Combines workspace management, organization administration, artifact registry,\n    code sample retrieval, and OpenAPI improvement suggestions into a single\n    workflow interface. Used by platform administrators, API producers, and\n    DevOps engineers managing SDK pipelines.\n  tags:\n    - AI\n    - Code Generation\n    - MCP\n    - OpenAPI\n    - Platform\n    - SDKs\n    - Terraform\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPEAKEASY_API_KEY: SPEAKEASY_API_KEY\n\ncapability:\n  consumes:\n    - import: speakeasy\n      location: ./shared/speakeasy.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: speakeasy-platform-api\n      description: \"Unified REST API for Speakeasy SDK platform management.\"\
  \n      resources:\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"List and manage Speakeasy workspaces\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"Get Workspaces for a User\"\n              call: \"speakeasy.get-workspaces\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/workspace/{workspace_id}\n          name: workspace\n          description: \"Get a specific workspace by ID\"\n          operations:\n            - method: GET\n              name: get-workspace\n              description: \"Get Workspace\"\n              call: \"speakeasy.get-workspace\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workspace/{workspace_id}/tokens\n          name: workspace-tokens\n\
  \          description: \"Manage workspace access tokens\"\n          operations:\n            - method: GET\n              name: list-workspace-tokens\n              description: \"Get Tokens for a Particular Workspace\"\n              call: \"speakeasy.get-workspace-tokens\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace-token\n              description: \"Create a Token for a Particular Workspace\"\n              call: \"speakeasy.create-workspace-token\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations\n          name: organizations\n          description: \"List organizations for the authenticated user\"\n          operations:\n    \
  \        - method: GET\n              name: list-organizations\n              description: \"Get Organizations for a User\"\n              call: \"speakeasy.get-organizations\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organizationID}\n          name: organization\n          description: \"Get a specific organization\"\n          operations:\n            - method: GET\n              name: get-organization\n              description: \"Get Organization\"\n              call: \"speakeasy.get-organization\"\n              with:\n                organizationID: \"rest.organizationID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/namespaces\n          name: namespaces\n          description: \"List artifact namespaces in the registry\"\n          operations:\n            - method: GET\n              name: list-namespaces\n\
  \              description: \"List Artifact Namespaces\"\n              call: \"speakeasy.list-namespaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/code-samples\n          name: code-samples\n          description: \"Retrieve SDK code samples for namespaces\"\n          operations:\n            - method: GET\n              name: get-code-samples\n              description: \"Retrieve Usage Snippets\"\n              call: \"speakeasy.get-code-samples\"\n              with:\n                namespace_name: \"rest.namespace_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/validate\n          name: auth\n          description: \"Validate API key and check access\"\n          operations:\n            - method: GET\n              name: validate-api-key\n              description: \"Validate the Current API Key\"\n           \
  \   call: \"speakeasy.validate-api-key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/suggest/openapi\n          name: suggestions\n          description: \"Generate OpenAPI improvement suggestions\"\n          operations:\n            - method: POST\n              name: suggest-openapi\n              description: \"Generate Suggestions for Improving an OpenAPI Document\"\n              call: \"speakeasy.suggest-openapi\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: speakeasy-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Speakeasy SDK platform management.\"\n      tools:\n        - name: validate-api-key\n          description: \"Validate the current Speakeasy API key and retrieve workspace details\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"speakeasy.validate-api-key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-current-user\n          description: \"Get information about the authenticated user including email and workspaces\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"speakeasy.get-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-workspaces\n          description: \"List all workspaces accessible to the authenticated user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"speakeasy.get-workspaces\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-workspace\n          description: \"Get details for a specific workspace by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n  \
  \        call: \"speakeasy.get-workspace\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-workspace\n          description: \"Create a new Speakeasy workspace within an organization\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"speakeasy.create-workspace\"\n          with:\n            name: \"tools.name\"\n            slug: \"tools.slug\"\n            organization_id: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-workspace-tokens\n          description: \"List API tokens for a specific workspace\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"speakeasy.get-workspace-tokens\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n\
  \            - type: array\n              mapping: \"$.\"\n\n        - name: create-workspace-token\n          description: \"Create a new API token for a workspace\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"speakeasy.create-workspace-token\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-organizations\n          description: \"List all organizations the authenticated user belongs to\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"speakeasy.get-organizations\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-organization\n          description: \"Get details for a specific organization by ID\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"speakeasy.get-organization\"\n          with:\n            organizationID: \"tools.organizationID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-organization\n          description: \"Create a new Speakeasy organization\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"speakeasy.create-organization\"\n          with:\n            name: \"tools.name\"\n            slug: \"tools.slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-artifact-namespaces\n          description: \"List artifact namespaces in the Speakeasy registry containing spec revisions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"speakeasy.list-namespaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-code-samples\n\
  \          description: \"Retrieve SDK code samples for a specific namespace and revision\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"speakeasy.get-code-samples\"\n          with:\n            namespace_name: \"tools.namespace_name\"\n            revision_reference: \"tools.revision_reference\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: suggest-openapi-improvements\n          description: \"Generate AI-powered suggestions for improving an OpenAPI document\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"speakeasy.suggest-openapi\"\n          with:\n            schema: \"tools.schema\"\n            diagnostics: \"tools.diagnostics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/speakeasy/refs/heads/main/capabilities/sdk-platform-management.yaml
tags:
- AI
- Code Generation
- MCP
- OpenAPI
- Platform
- SDKs
- Terraform
tools:
- description: Validate the current Speakeasy API key and retrieve workspace details
  hints:
    idempotent: true
    readOnly: true
  name: validate-api-key
- description: Get information about the authenticated user including email and workspaces
  hints:
    idempotent: true
    readOnly: true
  name: get-current-user
- description: List all workspaces accessible to the authenticated user
  hints:
    idempotent: true
    readOnly: true
  name: list-workspaces
- description: Get details for a specific workspace by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-workspace
- description: Create a new Speakeasy workspace within an organization
  hints:
    idempotent: false
    readOnly: false
  name: create-workspace
- description: List API tokens for a specific workspace
  hints:
    idempotent: true
    readOnly: true
  name: list-workspace-tokens
- description: Create a new API token for a workspace
  hints:
    idempotent: false
    readOnly: false
  name: create-workspace-token
- description: List all organizations the authenticated user belongs to
  hints:
    idempotent: true
    readOnly: true
  name: list-organizations
- description: Get details for a specific organization by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-organization
- description: Create a new Speakeasy organization
  hints:
    idempotent: false
    readOnly: false
  name: create-organization
- description: List artifact namespaces in the Speakeasy registry containing spec revisions
  hints:
    idempotent: true
    readOnly: true
  name: list-artifact-namespaces
- description: Retrieve SDK code samples for a specific namespace and revision
  hints:
    idempotent: true
    readOnly: true
  name: get-code-samples
- description: Generate AI-powered suggestions for improving an OpenAPI document
  hints:
    idempotent: false
    readOnly: false
  name: suggest-openapi-improvements
---
