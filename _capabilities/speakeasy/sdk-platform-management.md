---
categories: []
consumed_apis: []
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
- create workspace
- get workspaces for a user
- create workspace token
- validate the current speakeasy api key and retrieve workspace details
- list artifact namespaces in the speakeasy registry containing spec revisions
- list and manage speakeasy workspaces
- create a new speakeasy organization
- code generation
- sdks
- list organizations
- retrieve sdk code samples for namespaces
- get a specific organization
- list organizations for the authenticated user
- list all workspaces accessible to the authenticated user
- retrieve usage snippets
- generate suggestions for improving an openapi document
- get a specific workspace by id
- get workspace
- create a new api token for a workspace
- validate api key
- suggest openapi
- generate openapi improvement suggestions
- ai
- get organization
- mcp
- documentation
- openapi
- list api tokens for a specific workspace
- list artifact namespaces in the registry
- list artifact namespaces
- create organization
- manage workspace access tokens
- validate api key and check access
- get details for a specific organization by id
- list namespaces
- suggest openapi improvements
- generate ai-powered suggestions for improving an openapi document
- create a new speakeasy workspace within an organization
- list workspaces
- get information about the authenticated user including email and workspaces
- get current user
- retrieve sdk code samples for a specific namespace and revision
- validate the current api key
- platform
- get details for a specific workspace by id
- get tokens for a particular workspace
- list all organizations the authenticated user belongs to
- testing
- list workspace tokens
- terraform
- get organizations for a user
- create a token for a particular workspace
- get code samples
slug: sdk-platform-management
source_filename: sdk-platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Speakeasy SDK Platform Management\n  description: Unified workflow capability for managing the Speakeasy SDK generation platform. Combines workspace management,\n    organization administration, artifact registry, code sample retrieval, and OpenAPI improvement suggestions into a single\n    workflow interface. Used by platform administrators, API producers, and DevOps engineers managing SDK pipelines.\n  tags:\n  - AI\n  - Code Generation\n  - MCP\n  - OpenAPI\n  - Platform\n  - SDKs\n  - Terraform\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPEAKEASY_API_KEY: SPEAKEASY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: speakeasy\n    baseUri: https://api.prod.speakeasy.com\n    description: Speakeasy platform API for SDK generation, workspace management, and artifact registry\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{SPEAKEASY_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: auth\n      path: /v1/auth\n      description: Authentication and access token management\n      operations:\n      - name: validate-api-key\n        method: GET\n        description: Validate the Current API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-access-token\n        method: GET\n        description: Get or Refresh an Access Token for the Current Workspace\n        inputParameters:\n        - name: workspace_id\n          in: query\n          type: string\n          required: true\n          description: The workspace ID to get an access token for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /v1/user\n      description: Current user information\n      operations:\n      - name: get-user\n        method: GET\n \
  \       description: Get Information About the Current User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /v1/workspaces\n      description: Workspace listing and management\n      operations:\n      - name: get-workspaces\n        method: GET\n        description: Get Workspaces for a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: workspace\n      path: /v1/workspace\n      description: Individual workspace operations\n      operations:\n      - name: get-workspace-by-context\n        method: GET\n        description: Get Workspace by Context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace\n        method: POST\n        description: Create a Workspace\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            slug: '{{tools.slug}}'\n            organization_id: '{{tools.organization_id}}'\n    - name: workspace-detail\n      path: /v1/workspace/{workspace_id}\n      description: Operations on a specific workspace\n      operations:\n      - name: get-workspace\n        method: GET\n        description: Get Workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: The workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspace-tokens\n      path: /v1/workspace/{workspace_id}/tokens\n      description: Workspace token management\n      operations:\n      - name: get-workspace-tokens\n    \
  \    method: GET\n        description: Get Tokens for a Particular Workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: The workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-workspace-token\n        method: POST\n        description: Create a Token for a Particular Workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: The workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            alg: '{{tools.alg}}'\n    - name: organizations\n      path: /v1/organizations\n      description: Organization\
  \ listing\n      operations:\n      - name: get-organizations\n        method: GET\n        description: Get Organizations for a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: organization\n      path: /v1/organization\n      description: Organization creation\n      operations:\n      - name: create-organization\n        method: POST\n        description: Create an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            slug: '{{tools.slug}}'\n            telemetry_disabled: '{{tools.telemetry_disabled}}'\n    - name: organization-detail\n      path: /v1/organization/{organizationID}\n      description: Operations on a specific organization\n      operations:\n      - name: get-organization\n        method:\
  \ GET\n        description: Get Organization\n        inputParameters:\n        - name: organizationID\n          in: path\n          type: string\n          required: true\n          description: The organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: code-samples\n      path: /v1/code_sample\n      description: Code sample retrieval and generation\n      operations:\n      - name: get-code-samples\n        method: GET\n        description: Retrieve Usage Snippets\n        inputParameters:\n        - name: namespace_name\n          in: query\n          type: string\n          required: true\n          description: The namespace name\n        - name: revision_reference\n          in: query\n          type: string\n          required: false\n          description: The revision reference\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: artifacts\n      path: /v1/artifacts/namespaces\n      description: Artifact namespace management\n      operations:\n      - name: list-namespaces\n        method: GET\n        description: Each Namespace Contains Many Revisions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /v1/reports\n      description: Report management\n      operations:\n      - name: upload-report\n        method: POST\n        description: Upload a Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n    - name: suggest\n      path: /v1/suggest/openapi\n      description: OpenAPI improvement suggestions\n      operations:\n      - name: suggest-openapi\n        method: POST\n        description:\
  \ Generate Suggestions for Improving an OpenAPI Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            schema: '{{tools.schema}}'\n            diagnostics: '{{tools.diagnostics}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: speakeasy-platform-api\n    description: Unified REST API for Speakeasy SDK platform management.\n    resources:\n    - path: /v1/workspaces\n      name: workspaces\n      description: List and manage Speakeasy workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: Get Workspaces for a User\n        call: speakeasy.get-workspaces\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/workspace/{workspace_id}\n      name: workspace\n      description: Get a specific workspace by ID\n      operations:\n      - method: GET\n\
  \        name: get-workspace\n        description: Get Workspace\n        call: speakeasy.get-workspace\n        with:\n          workspace_id: rest.workspace_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspace/{workspace_id}/tokens\n      name: workspace-tokens\n      description: Manage workspace access tokens\n      operations:\n      - method: GET\n        name: list-workspace-tokens\n        description: Get Tokens for a Particular Workspace\n        call: speakeasy.get-workspace-tokens\n        with:\n          workspace_id: rest.workspace_id\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-workspace-token\n        description: Create a Token for a Particular Workspace\n        call: speakeasy.create-workspace-token\n        with:\n          workspace_id: rest.workspace_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n\
  \      name: organizations\n      description: List organizations for the authenticated user\n      operations:\n      - method: GET\n        name: list-organizations\n        description: Get Organizations for a User\n        call: speakeasy.get-organizations\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/organizations/{organizationID}\n      name: organization\n      description: Get a specific organization\n      operations:\n      - method: GET\n        name: get-organization\n        description: Get Organization\n        call: speakeasy.get-organization\n        with:\n          organizationID: rest.organizationID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces\n      name: namespaces\n      description: List artifact namespaces in the registry\n      operations:\n      - method: GET\n        name: list-namespaces\n        description: List Artifact Namespaces\n        call: speakeasy.list-namespaces\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/code-samples\n      name: code-samples\n      description: Retrieve SDK code samples for namespaces\n      operations:\n      - method: GET\n        name: get-code-samples\n        description: Retrieve Usage Snippets\n        call: speakeasy.get-code-samples\n        with:\n          namespace_name: rest.namespace_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/validate\n      name: auth\n      description: Validate API key and check access\n      operations:\n      - method: GET\n        name: validate-api-key\n        description: Validate the Current API Key\n        call: speakeasy.validate-api-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/suggest/openapi\n      name: suggestions\n      description: Generate OpenAPI improvement suggestions\n      operations:\n      - method: POST\n        name:\
  \ suggest-openapi\n        description: Generate Suggestions for Improving an OpenAPI Document\n        call: speakeasy.suggest-openapi\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: speakeasy-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted Speakeasy SDK platform management.\n    tools:\n    - name: validate-api-key\n      description: Validate the current Speakeasy API key and retrieve workspace details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.validate-api-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-user\n      description: Get information about the authenticated user including email and workspaces\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.get-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n\
  \      description: List all workspaces accessible to the authenticated user\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.get-workspaces\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-workspace\n      description: Get details for a specific workspace by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.get-workspace\n      with:\n        workspace_id: tools.workspace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace\n      description: Create a new Speakeasy workspace within an organization\n      hints:\n        readOnly: false\n        idempotent: false\n      call: speakeasy.create-workspace\n      with:\n        name: tools.name\n        slug: tools.slug\n        organization_id: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspace-tokens\n      description:\
  \ List API tokens for a specific workspace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.get-workspace-tokens\n      with:\n        workspace_id: tools.workspace_id\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-workspace-token\n      description: Create a new API token for a workspace\n      hints:\n        readOnly: false\n        idempotent: false\n      call: speakeasy.create-workspace-token\n      with:\n        workspace_id: tools.workspace_id\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-organizations\n      description: List all organizations the authenticated user belongs to\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.get-organizations\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-organization\n      description: Get details for a specific organization\
  \ by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.get-organization\n      with:\n        organizationID: tools.organizationID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-organization\n      description: Create a new Speakeasy organization\n      hints:\n        readOnly: false\n        idempotent: false\n      call: speakeasy.create-organization\n      with:\n        name: tools.name\n        slug: tools.slug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-artifact-namespaces\n      description: List artifact namespaces in the Speakeasy registry containing spec revisions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: speakeasy.list-namespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-code-samples\n      description: Retrieve SDK code samples for a specific namespace and revision\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: speakeasy.get-code-samples\n      with:\n        namespace_name: tools.namespace_name\n        revision_reference: tools.revision_reference\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suggest-openapi-improvements\n      description: Generate AI-powered suggestions for improving an OpenAPI document\n      hints:\n        readOnly: false\n        idempotent: false\n      call: speakeasy.suggest-openapi\n      with:\n        schema: tools.schema\n        diagnostics: tools.diagnostics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
