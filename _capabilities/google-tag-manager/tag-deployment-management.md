---
categories:
- analytics
consumed_apis: []
description: Workflow for managing tag deployment lifecycle including accounts, containers, workspaces, tags, triggers, variables, and version publishing. Used by marketing technologists and web analytics engineers.
layout: capability
name: Google Tag Manager Tag Deployment Management
operations:
- description: List all GTM accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List containers in an account
  method: GET
  name: list-containers
  path: /v1/containers
- description: Create a container
  method: POST
  name: create-container
  path: /v1/containers
- description: List tags in a workspace
  method: GET
  name: list-tags
  path: /v1/tags
- description: Create a tag
  method: POST
  name: create-tag
  path: /v1/tags
- description: List triggers in a workspace
  method: GET
  name: list-triggers
  path: /v1/triggers
- description: List variables in a workspace
  method: GET
  name: list-variables
  path: /v1/variables
personas: []
provider_name: Google Tag Manager
provider_slug: google-tag-manager
search_terms:
- analytics
- get account
- list workspaces
- delete a trigger
- delete trigger
- list all google tag manager accounts
- list tags
- trigger management
- delete a variable
- conversion tracking
- list all gtm accounts
- get account details
- publish a container version
- create container
- account management
- update account settings
- list accounts
- list variables in a workspace
- list triggers
- get container details
- delete variable
- container management
- delete workspace
- publish version
- list variables
- create a new container
- create a new variable
- list container version headers
- create workspace
- list versions
- google tag manager
- create a new trigger
- list triggers in a workspace
- delete tag
- variable management
- delete a container
- create trigger
- tag management
- delete container
- get container
- update account
- list workspaces in a container
- create variable
- tracking
- marketing
- create tag
- delete a workspace
- list tags in a workspace
- list containers in an account
- create a new workspace
- create a new tag
- get tag details
- create a tag
- list containers
- get tag
- delete a tag
- create a container
slug: tag-deployment-management
source_filename: tag-deployment-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Tag Manager Tag Deployment Management\n  description: Workflow for managing tag deployment lifecycle including accounts, containers, workspaces, tags, triggers,\n    variables, and version publishing. Used by marketing technologists and web analytics engineers.\n  tags:\n  - Google Tag Manager\n  - Tag Management\n  - Marketing\n  - Analytics\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tag-manager\n    baseUri: https://tagmanager.googleapis.com\n    description: Google Tag Manager API v2 for container and tag configuration management.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_OAUTH_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /tagmanager/v2/accounts\n      description: Account management operations.\n      operations:\n      - name: list-accounts\n \
  \       method: GET\n        description: Lists all GTM accounts.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Gets a GTM account.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The account path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Updates a GTM account.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The account path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n \
  \         type: json\n          data:\n            name: '{{tools.name}}'\n            shareData: '{{tools.shareData}}'\n    - name: containers\n      path: /tagmanager/v2/{parent}/containers\n      description: Container management operations.\n      operations:\n      - name: list-containers\n        method: GET\n        description: Lists containers in an account.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The account path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-container\n        method: POST\n        description: Creates a container.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The account path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            usageContext: '{{tools.usageContext}}'\n      - name: get-container\n        method: GET\n        description: Gets a container.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The container path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-container\n        method: DELETE\n        description: Deletes a container.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The container path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /tagmanager/v2/{parent}/workspaces\n\
  \      description: Workspace management operations.\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: Lists workspaces in a container.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The container path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace\n        method: POST\n        description: Creates a workspace.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The container path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n\
  \      - name: delete-workspace\n        method: DELETE\n        description: Deletes a workspace.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tagmanager/v2/{parent}/tags\n      description: Tag management operations.\n      operations:\n      - name: list-tags\n        method: GET\n        description: Lists tags in a workspace.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tag\n        method: POST\n        description: Creates a tag.\n        inputParameters:\n\
  \        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n      - name: get-tag\n        method: GET\n        description: Gets a tag.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The tag path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-tag\n        method: DELETE\n        description: Deletes a tag.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The tag path.\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: triggers\n      path: /tagmanager/v2/{parent}/triggers\n      description: Trigger management operations.\n      operations:\n      - name: list-triggers\n        method: GET\n        description: Lists triggers in a workspace.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-trigger\n        method: POST\n        description: Creates a trigger.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n      - name: delete-trigger\n        method: DELETE\n        description: Deletes a trigger.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The trigger path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /tagmanager/v2/{parent}/variables\n      description: Variable management operations.\n      operations:\n      - name: list-variables\n        method: GET\n        description: Lists variables in a workspace.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-variable\n        method: POST\n        description: Creates a variable.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The workspace path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n      - name: delete-variable\n        method: DELETE\n        description: Deletes a variable.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The variable path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n\
  \      path: /tagmanager/v2/{parent}/version_headers\n      description: Version management operations.\n      operations:\n      - name: list-versions\n        method: GET\n        description: Lists container version headers.\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: The container path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-version\n        method: POST\n        description: Publishes a container version.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: The container version path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gtm-deploy-api\n \
  \   description: Unified REST API for GTM tag deployment management.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all GTM accounts\n        call: tag-manager.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/containers\n      name: containers\n      description: Container management\n      operations:\n      - method: GET\n        name: list-containers\n        description: List containers in an account\n        call: tag-manager.list-containers\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-container\n        description: Create a container\n        call: tag-manager.create-container\n        with:\n          parent: rest.parent\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: Tag management\n      operations:\n      - method: GET\n        name: list-tags\n        description: List tags in a workspace\n        call: tag-manager.list-tags\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-tag\n        description: Create a tag\n        call: tag-manager.create-tag\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/triggers\n      name: triggers\n      description: Trigger management\n      operations:\n      - method: GET\n        name: list-triggers\n        description: List triggers in a workspace\n        call: tag-manager.list-triggers\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/variables\n      name: variables\n      description: Variable management\n      operations:\n      - method: GET\n        name: list-variables\n        description: List variables in a workspace\n        call: tag-manager.list-variables\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gtm-deploy-mcp\n    transport: http\n    description: MCP server for AI-assisted GTM tag deployment management.\n    tools:\n    - name: list-accounts\n      description: List all Google Tag Manager accounts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get account details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.get-account\n      with:\n        path: tools.path\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-account\n      description: Update account settings\n      hints:\n        readOnly: false\n        idempotent: true\n      call: tag-manager.update-account\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-containers\n      description: List containers in an account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-containers\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-container\n      description: Create a new container\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tag-manager.create-container\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-container\n      description: Get container\
  \ details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.get-container\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container\n      description: Delete a container\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tag-manager.delete-container\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List workspaces in a container\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-workspaces\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace\n      description: Create a new workspace\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tag-manager.create-workspace\n\
  \      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-workspace\n      description: Delete a workspace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tag-manager.delete-workspace\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags\n      description: List tags in a workspace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-tags\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-tag\n      description: Create a new tag\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tag-manager.create-tag\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tag\n    \
  \  description: Get tag details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.get-tag\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-tag\n      description: Delete a tag\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tag-manager.delete-tag\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-triggers\n      description: List triggers in a workspace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-triggers\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-trigger\n      description: Create a new trigger\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tag-manager.create-trigger\n     \
  \ with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-trigger\n      description: Delete a trigger\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tag-manager.delete-trigger\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-variables\n      description: List variables in a workspace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-variables\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-variable\n      description: Create a new variable\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tag-manager.create-variable\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ delete-variable\n      description: Delete a variable\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tag-manager.delete-variable\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-versions\n      description: List container version headers\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tag-manager.list-versions\n      with:\n        parent: tools.parent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-version\n      description: Publish a container version\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tag-manager.publish-version\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-tag-manager/refs/heads/main/capabilities/tag-deployment-management.yaml
tags:
- Google Tag Manager
- Tag Management
- Marketing
- Analytics
tools:
- description: List all Google Tag Manager accounts
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: Get account details
  hints:
    idempotent: true
    readOnly: true
  name: get-account
- description: Update account settings
  hints:
    idempotent: true
    readOnly: false
  name: update-account
- description: List containers in an account
  hints:
    idempotent: true
    readOnly: true
  name: list-containers
- description: Create a new container
  hints:
    idempotent: false
    readOnly: false
  name: create-container
- description: Get container details
  hints:
    idempotent: true
    readOnly: true
  name: get-container
- description: Delete a container
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-container
- description: List workspaces in a container
  hints:
    idempotent: true
    readOnly: true
  name: list-workspaces
- description: Create a new workspace
  hints:
    idempotent: false
    readOnly: false
  name: create-workspace
- description: Delete a workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-workspace
- description: List tags in a workspace
  hints:
    idempotent: true
    readOnly: true
  name: list-tags
- description: Create a new tag
  hints:
    idempotent: false
    readOnly: false
  name: create-tag
- description: Get tag details
  hints:
    idempotent: true
    readOnly: true
  name: get-tag
- description: Delete a tag
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-tag
- description: List triggers in a workspace
  hints:
    idempotent: true
    readOnly: true
  name: list-triggers
- description: Create a new trigger
  hints:
    idempotent: false
    readOnly: false
  name: create-trigger
- description: Delete a trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-trigger
- description: List variables in a workspace
  hints:
    idempotent: true
    readOnly: true
  name: list-variables
- description: Create a new variable
  hints:
    idempotent: false
    readOnly: false
  name: create-variable
- description: Delete a variable
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-variable
- description: List container version headers
  hints:
    idempotent: true
    readOnly: true
  name: list-versions
- description: Publish a container version
  hints:
    idempotent: false
    readOnly: false
  name: publish-version
---
