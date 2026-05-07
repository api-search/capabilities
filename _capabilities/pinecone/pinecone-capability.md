---
categories: []
consumed_apis: []
description: Provides an API for managing a Pinecone organization and its resources.
layout: capability
name: Pinecone Admin API
operations:
- description: List projects
  method: GET
  name: list-projects
  path: /admin/projects
- description: Create a new project
  method: POST
  name: create-project
  path: /admin/projects
- description: List organizations
  method: GET
  name: list-organizations
  path: /admin/organizations
- description: Get project details
  method: GET
  name: fetch-project
  path: /admin/projects/{project_id}
- description: Delete a project
  method: DELETE
  name: delete-project
  path: /admin/projects/{project_id}
- description: Update a project
  method: PATCH
  name: update-project
  path: /admin/projects/{project_id}
- description: Get organization details
  method: GET
  name: fetch-organization
  path: /admin/organizations/{organization_id}
- description: Delete an organization
  method: DELETE
  name: delete-organization
  path: /admin/organizations/{organization_id}
- description: Update an organization
  method: PATCH
  name: update-organization
  path: /admin/organizations/{organization_id}
- description: List API keys
  method: GET
  name: list-project-api-keys
  path: /admin/projects/{project_id}/api-keys
- description: Create an API key
  method: POST
  name: create-api-key
  path: /admin/projects/{project_id}/api-keys
- description: Get API key details
  method: GET
  name: fetch-api-key
  path: /admin/api-keys/{api_key_id}
- description: Delete an API key
  method: DELETE
  name: delete-api-key
  path: /admin/api-keys/{api_key_id}
- description: Update an API key
  method: PATCH
  name: update-api-key
  path: /admin/api-keys/{api_key_id}
personas: []
provider_name: Pinecone
provider_slug: pinecone
search_terms:
- delete api key
- ai
- fetch project
- api
- fetch api key
- update an api key
- rag
- fetch organization
- update an organization
- delete project
- create project
- pinecone
- list projects
- delete an api key
- embeddings
- create an api key
- create a new project
- get organization details
- list organizations
- list api keys
- get project details
- update a project
- create api key
- list project api keys
- update organization
- update api key
- delete organization
- vector databases
- delete a project
- update project
- delete an organization
- get api key details
slug: pinecone-capability
source_filename: pinecone-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pinecone Admin API\n  description: Provides an API for managing a Pinecone organization and its resources.\n  tags:\n  - Pinecone\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pinecone\n    baseUri: https://api.pinecone.io\n    description: Pinecone Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PINECONE_TOKEN}}'\n    resources:\n    - name: admin-projects\n      path: /admin/projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: List projects\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n\
  \        method: POST\n        description: Create a new project\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-organizations\n      path: /admin/organizations\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List organizations\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-projects-project-id\n      path: /admin/projects/{project_id}\n      operations:\n   \
  \   - name: fetch-project\n        method: GET\n        description: Get project details\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete a project\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-project\n        method: PATCH\n        description: Update a project\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-organizations-organization-id\n      path: /admin/organizations/{organization_id}\n      operations:\n      - name: fetch-organization\n        method: GET\n        description: Get organization details\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required:\
  \ true\n          description: Required date-based version header\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organization\n        method: DELETE\n        description: Delete an organization\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-organization\n        method: PATCH\n        description: Update an organization\n\
  \        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-projects-project-id-api-keys\n      path: /admin/projects/{project_id}/api-keys\n      operations:\n      - name: list-project-api-keys\n        method: GET\n        description: List API keys\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create an API key\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-api-keys-api-key-id\n      path: /admin/api-keys/{api_key_id}\n      operations:\n      - name: fetch-api-key\n        method: GET\n        description: Get API key details\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required:\
  \ true\n          description: Required date-based version header\n        - name: api_key_id\n          in: path\n          type: string\n          required: true\n          description: API key ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-key\n        method: DELETE\n        description: Delete an API key\n        inputParameters:\n        - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: api_key_id\n          in: path\n          type: string\n          required: true\n          description: API key ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-api-key\n        method: PATCH\n        description: Update an API key\n        inputParameters:\n  \
  \      - name: X-Pinecone-Api-Version\n          in: header\n          type: string\n          required: true\n          description: Required date-based version header\n        - name: api_key_id\n          in: path\n          type: string\n          required: true\n          description: API key ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pinecone-rest\n    description: REST adapter for Pinecone Admin API.\n    resources:\n    - path: /admin/projects\n      name: list-projects\n      operations:\n      - method: GET\n        name: list-projects\n        description: List projects\n        call: pinecone.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/projects\n      name: create-project\n      operations:\n      - method: POST\n        name: create-project\n        description: Create\
  \ a new project\n        call: pinecone.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/organizations\n      name: list-organizations\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List organizations\n        call: pinecone.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/projects/{project_id}\n      name: fetch-project\n      operations:\n      - method: GET\n        name: fetch-project\n        description: Get project details\n        call: pinecone.fetch-project\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/projects/{project_id}\n      name: delete-project\n      operations:\n      - method: DELETE\n        name: delete-project\n        description: Delete a project\n        call: pinecone.delete-project\n    \
  \    with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/projects/{project_id}\n      name: update-project\n      operations:\n      - method: PATCH\n        name: update-project\n        description: Update a project\n        call: pinecone.update-project\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/organizations/{organization_id}\n      name: fetch-organization\n      operations:\n      - method: GET\n        name: fetch-organization\n        description: Get organization details\n        call: pinecone.fetch-organization\n        with:\n          organization_id: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/organizations/{organization_id}\n      name: delete-organization\n      operations:\n      - method: DELETE\n        name:\
  \ delete-organization\n        description: Delete an organization\n        call: pinecone.delete-organization\n        with:\n          organization_id: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/organizations/{organization_id}\n      name: update-organization\n      operations:\n      - method: PATCH\n        name: update-organization\n        description: Update an organization\n        call: pinecone.update-organization\n        with:\n          organization_id: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/projects/{project_id}/api-keys\n      name: list-project-api-keys\n      operations:\n      - method: GET\n        name: list-project-api-keys\n        description: List API keys\n        call: pinecone.list-project-api-keys\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /admin/projects/{project_id}/api-keys\n      name: create-api-key\n      operations:\n      - method: POST\n        name: create-api-key\n        description: Create an API key\n        call: pinecone.create-api-key\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/api-keys/{api_key_id}\n      name: fetch-api-key\n      operations:\n      - method: GET\n        name: fetch-api-key\n        description: Get API key details\n        call: pinecone.fetch-api-key\n        with:\n          api_key_id: rest.api_key_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/api-keys/{api_key_id}\n      name: delete-api-key\n      operations:\n      - method: DELETE\n        name: delete-api-key\n        description: Delete an API key\n        call: pinecone.delete-api-key\n        with:\n          api_key_id: rest.api_key_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /admin/api-keys/{api_key_id}\n      name: update-api-key\n      operations:\n      - method: PATCH\n        name: update-api-key\n        description: Update an API key\n        call: pinecone.update-api-key\n        with:\n          api_key_id: rest.api_key_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pinecone-mcp\n    transport: http\n    description: MCP adapter for Pinecone Admin API for AI agent use.\n    tools:\n    - name: list-projects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pinecone.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pinecone.create-project\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-organizations\n      description: List organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pinecone.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-project\n      description: Get project details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pinecone.fetch-project\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Delete a project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pinecone.delete-project\n      with:\n        project_id:\
  \ tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-project\n      description: Update a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pinecone.update-project\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-organization\n      description: Get organization details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pinecone.fetch-organization\n      with:\n        organization_id: tools.organization_id\n      inputParameters:\n      - name: organization_id\n        type:\
  \ string\n        description: Organization ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-organization\n      description: Delete an organization\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pinecone.delete-organization\n      with:\n        organization_id: tools.organization_id\n      inputParameters:\n      - name: organization_id\n        type: string\n        description: Organization ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-organization\n      description: Update an organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pinecone.update-organization\n      with:\n        organization_id: tools.organization_id\n      inputParameters:\n      - name: organization_id\n        type: string\n        description: Organization\
  \ ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-project-api-keys\n      description: List API keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pinecone.list-project-api-keys\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create an API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pinecone.create-api-key\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: fetch-api-key\n      description: Get API key details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pinecone.fetch-api-key\n      with:\n        api_key_id: tools.api_key_id\n      inputParameters:\n      - name: api_key_id\n        type: string\n        description: API key ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-key\n      description: Delete an API key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pinecone.delete-api-key\n      with:\n        api_key_id: tools.api_key_id\n      inputParameters:\n      - name: api_key_id\n        type: string\n        description: API key ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-api-key\n      description: Update an API key\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: pinecone.update-api-key\n      with:\n        api_key_id: tools.api_key_id\n      inputParameters:\n      - name: api_key_id\n        type: string\n        description: API key ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PINECONE_TOKEN: PINECONE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pinecone/refs/heads/main/capabilities/pinecone-capability.yaml
tags:
- Pinecone
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-project
- description: List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-organizations
- description: Get project details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-project
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: Update a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-project
- description: Get organization details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-organization
- description: Delete an organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-organization
- description: Update an organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-organization
- description: List API keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-project-api-keys
- description: Create an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-key
- description: Get API key details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-api-key
- description: Delete an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-key
- description: Update an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-api-key
---
