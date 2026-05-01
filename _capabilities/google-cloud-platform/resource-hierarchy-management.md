---
api_specs:
- filename: cloud-resource-manager-openapi.yml
  format: yaml
  label: cloud-resource-manager
  slug: cloud-resource-manager
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/google-cloud-platform/refs/heads/main/openapi/cloud-resource-manager-openapi.yml
categories: []
consumed_apis:
- cloud-resource-manager
description: Workflow for managing the Google Cloud resource hierarchy including projects, folders, organizations, and tags. Used by cloud administrators and platform engineers.
layout: capability
name: Google Cloud Platform Resource Hierarchy Management
operations:
- description: List projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details
  method: GET
  name: get-project
  path: /v1/projects/{name}
- description: Update a project
  method: PATCH
  name: update-project
  path: /v1/projects/{name}
- description: Delete a project
  method: DELETE
  name: delete-project
  path: /v1/projects/{name}
- description: List folders
  method: GET
  name: list-folders
  path: /v1/folders
- description: Create a folder
  method: POST
  name: create-folder
  path: /v1/folders
- description: Get organization details
  method: GET
  name: get-organization
  path: /v1/organizations/{name}
personas: []
provider_name: Google Cloud Platform
provider_slug: google-cloud-platform
search_terms:
- get organization
- search for organizations
- list tag keys for resource tagging
- delete a google cloud project
- single project operations
- list google cloud projects under a parent
- project management
- infrastructure
- get project
- create folder
- get folder details
- resource management
- update project
- organization operations
- delete project
- list folders under a parent
- list folders
- list projects
- get project details
- delete a folder
- delete folder
- delete a project
- create tag key
- cloud computing
- api management
- create a folder
- get organization details
- search for projects matching a query
- create a new tag key
- search projects
- governance
- update a project
- get folder
- list tag keys
- create a new google cloud project
- platform as a service
- google cloud
- create project
- search organizations
- create a project
- folder management
slug: resource-hierarchy-management
source_filename: resource-hierarchy-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Cloud Platform Resource Hierarchy Management\"\n  description: \"Workflow for managing the Google Cloud resource hierarchy including projects, folders, organizations, and tags. Used by cloud administrators and platform engineers.\"\n  tags:\n    - Google Cloud\n    - Resource Management\n    - Governance\n    - Infrastructure\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: cloud-resource-manager\n      location: ./shared/cloud-resource-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gcp-resource-api\n      description: \"Unified REST API for GCP resource hierarchy management.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Project management\"\n          operations:\n            - method: GET\n      \
  \        name: list-projects\n              description: \"List projects\"\n              call: \"cloud-resource-manager.list-projects\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a project\"\n              call: \"cloud-resource-manager.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{name}\n          name: project\n          description: \"Single project operations\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details\"\n              call: \"cloud-resource-manager.get-project\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-project\n              description: \"Update a project\"\n              call: \"cloud-resource-manager.update-project\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete a project\"\n              call: \"cloud-resource-manager.delete-project\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/folders\n          name: folders\n          description: \"Folder management\"\n          operations:\n            - method: GET\n              name: list-folders\n              description: \"List folders\"\n              call: \"cloud-resource-manager.list-folders\"\
  \n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-folder\n              description: \"Create a folder\"\n              call: \"cloud-resource-manager.create-folder\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{name}\n          name: organization\n          description: \"Organization operations\"\n          operations:\n            - method: GET\n              name: get-organization\n              description: \"Get organization details\"\n              call: \"cloud-resource-manager.get-organization\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: gcp-resource-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted GCP resource hierarchy management.\"\n      tools:\n        - name: list-projects\n          description: \"List Google Cloud projects under a parent\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.list-projects\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new Google Cloud project\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cloud-resource-manager.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get project details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.get-project\"\
  \n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-project\n          description: \"Update a project\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloud-resource-manager.update-project\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-project\n          description: \"Delete a Google Cloud project\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"cloud-resource-manager.delete-project\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-projects\n          description: \"Search for projects matching a query\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.search-projects\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-folders\n          description: \"List folders under a parent\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.list-folders\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-folder\n          description: \"Create a folder\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cloud-resource-manager.create-folder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-folder\n          description: \"Get folder details\"\n   \
  \       hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.get-folder\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-folder\n          description: \"Delete a folder\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"cloud-resource-manager.delete-folder\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organization\n          description: \"Get organization details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.get-organization\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: search-organizations\n          description: \"Search for organizations\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.search-organizations\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tag-keys\n          description: \"List tag keys for resource tagging\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-resource-manager.list-tag-keys\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-tag-key\n          description: \"Create a new tag key\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cloud-resource-manager.create-tag-key\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-platform/refs/heads/main/capabilities/resource-hierarchy-management.yaml
tags:
- Google Cloud
- Resource Management
- Governance
- Infrastructure
tools:
- description: List Google Cloud projects under a parent
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new Google Cloud project
  hints:
    idempotent: false
    readOnly: false
  name: create-project
- description: Get project details
  hints:
    idempotent: true
    readOnly: true
  name: get-project
- description: Update a project
  hints:
    idempotent: true
    readOnly: false
  name: update-project
- description: Delete a Google Cloud project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: Search for projects matching a query
  hints:
    idempotent: true
    readOnly: true
  name: search-projects
- description: List folders under a parent
  hints:
    idempotent: true
    readOnly: true
  name: list-folders
- description: Create a folder
  hints:
    idempotent: false
    readOnly: false
  name: create-folder
- description: Get folder details
  hints:
    idempotent: true
    readOnly: true
  name: get-folder
- description: Delete a folder
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-folder
- description: Get organization details
  hints:
    idempotent: true
    readOnly: true
  name: get-organization
- description: Search for organizations
  hints:
    idempotent: true
    readOnly: true
  name: search-organizations
- description: List tag keys for resource tagging
  hints:
    idempotent: true
    readOnly: true
  name: list-tag-keys
- description: Create a new tag key
  hints:
    idempotent: false
    readOnly: false
  name: create-tag-key
---
