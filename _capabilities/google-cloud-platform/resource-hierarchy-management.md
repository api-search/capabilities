---
categories: []
consumed_apis: []
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
- governance
- resource management
- delete a google cloud project
- delete folder
- create a folder
- get folder
- list tag keys for resource tagging
- list google cloud projects under a parent
- create a project
- list folders
- api management
- organization operations
- project management
- list folders under a parent
- cloud computing
- infrastructure
- search for organizations
- delete project
- create project
- list projects
- create a new google cloud project
- get organization details
- search projects
- folder management
- search for projects matching a query
- get project details
- get folder details
- delete a folder
- single project operations
- search organizations
- update a project
- list tag keys
- get project
- create a new tag key
- google cloud
- create tag key
- get organization
- delete a project
- update project
- platform as a service
- create folder
slug: resource-hierarchy-management
source_filename: resource-hierarchy-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Platform Resource Hierarchy Management\n  description: Workflow for managing the Google Cloud resource hierarchy including projects, folders, organizations, and tags.\n    Used by cloud administrators and platform engineers.\n  tags:\n  - Google Cloud\n  - Resource Management\n  - Governance\n  - Infrastructure\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-resource-manager\n    baseUri: https://cloudresourcemanager.googleapis.com\n    description: Google Cloud Resource Manager API for managing projects, folders, and organizations.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_OAUTH_TOKEN}}'\n    resources:\n    - name: projects\n      path: /v3/projects\n      description: Project management operations.\n      operations:\n      - name: list-projects\n      \
  \  method: GET\n        description: Lists projects under a parent resource.\n        inputParameters:\n        - name: parent\n          in: query\n          type: string\n          required: true\n          description: The parent resource.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Creates a new project.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            projectId: '{{tools.projectId}}'\n            displayName: '{{tools.displayName}}'\n            parent: '{{tools.parent}}'\n      - name: get-project\n        method:\
  \ GET\n        description: Gets a project by name.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The project name (projects/{projectId}).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-project\n        method: PATCH\n        description: Updates a project.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The project name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n      - name: delete-project\n        method: DELETE\n        description: Marks a project for deletion.\n        inputParameters:\n        - name: name\n\
  \          in: path\n          type: string\n          required: true\n          description: The project name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-projects\n        method: GET\n        description: Search for projects matching a query.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /v3/folders\n      description: Folder management operations.\n      operations:\n      - name: list-folders\n        method: GET\n        description: Lists folders under a parent resource.\n        inputParameters:\n        - name: parent\n          in: query\n          type: string\n          required: true\n        \
  \  description: The parent resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-folder\n        method: POST\n        description: Creates a folder.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            parent: '{{tools.parent}}'\n      - name: get-folder\n        method: GET\n        description: Gets a folder.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The folder name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-folder\n        method: DELETE\n        description:\
  \ Marks a folder for deletion.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The folder name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /v3/organizations\n      description: Organization operations.\n      operations:\n      - name: get-organization\n        method: GET\n        description: Gets an organization.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The organization name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-organizations\n        method: GET\n        description: Search for organizations.\n        inputParameters:\n        - name: query\n          in: query\n\
  \          type: string\n          required: false\n          description: Search query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tag-keys\n      path: /v3/tagKeys\n      description: Tag key operations.\n      operations:\n      - name: list-tag-keys\n        method: GET\n        description: Lists tag keys.\n        inputParameters:\n        - name: parent\n          in: query\n          type: string\n          required: true\n          description: The parent resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tag-key\n        method: POST\n        description: Creates a tag key.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n         \
  \ data:\n            shortName: '{{tools.shortName}}'\n            parent: '{{tools.parent}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gcp-resource-api\n    description: Unified REST API for GCP resource hierarchy management.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List projects\n        call: cloud-resource-manager.list-projects\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a project\n        call: cloud-resource-manager.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{name}\n      name: project\n      description: Single project operations\n      operations:\n      - method: GET\n        name: get-project\n\
  \        description: Get project details\n        call: cloud-resource-manager.get-project\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-project\n        description: Update a project\n        call: cloud-resource-manager.update-project\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete a project\n        call: cloud-resource-manager.delete-project\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/folders\n      name: folders\n      description: Folder management\n      operations:\n      - method: GET\n        name: list-folders\n        description: List folders\n        call: cloud-resource-manager.list-folders\n        with:\n          parent:\
  \ rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-folder\n        description: Create a folder\n        call: cloud-resource-manager.create-folder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{name}\n      name: organization\n      description: Organization operations\n      operations:\n      - method: GET\n        name: get-organization\n        description: Get organization details\n        call: cloud-resource-manager.get-organization\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gcp-resource-mcp\n    transport: http\n    description: MCP server for AI-assisted GCP resource hierarchy management.\n    tools:\n    - name: list-projects\n      description: List Google Cloud projects under a parent\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: cloud-resource-manager.list-projects\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Google Cloud project\n      hints:\n        readOnly: false\n        idempotent: false\n      call: cloud-resource-manager.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get project details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.get-project\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-project\n      description: Update a project\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloud-resource-manager.update-project\n      with:\n        name: tools.name\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: delete-project\n      description: Delete a Google Cloud project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cloud-resource-manager.delete-project\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-projects\n      description: Search for projects matching a query\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.search-projects\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-folders\n      description: List folders under a parent\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.list-folders\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-folder\n    \
  \  description: Create a folder\n      hints:\n        readOnly: false\n        idempotent: false\n      call: cloud-resource-manager.create-folder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-folder\n      description: Get folder details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.get-folder\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-folder\n      description: Delete a folder\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cloud-resource-manager.delete-folder\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization\n      description: Get organization details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.get-organization\n\
  \      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-organizations\n      description: Search for organizations\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.search-organizations\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tag-keys\n      description: List tag keys for resource tagging\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-resource-manager.list-tag-keys\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-tag-key\n      description: Create a new tag key\n      hints:\n        readOnly: false\n        idempotent: false\n      call: cloud-resource-manager.create-tag-key\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
