---
categories:
- analytics
consumed_apis:
- tag-manager
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
- account management
- create a container
- create a new trigger
- publish a container version
- update account settings
- get tag
- conversion tracking
- analytics
- delete a container
- variable management
- get tag details
- tracking
- tag management
- create workspace
- delete a tag
- list triggers in a workspace
- list versions
- list workspaces in a container
- list workspaces
- list all google tag manager accounts
- marketing
- list containers in an account
- create container
- delete container
- create variable
- update account
- trigger management
- container management
- delete a variable
- delete workspace
- delete a workspace
- get container details
- list tags in a workspace
- list container version headers
- list accounts
- list tags
- delete a trigger
- get account details
- create trigger
- delete trigger
- create a new variable
- list containers
- list variables
- list variables in a workspace
- delete variable
- create a new container
- get container
- delete tag
- create a new workspace
- publish version
- create a tag
- google tag manager
- get account
- create a new tag
- list triggers
- list all gtm accounts
- create tag
slug: tag-deployment-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Tag Manager Tag Deployment Management\"\n  description: \"Workflow for managing tag deployment lifecycle including accounts, containers, workspaces, tags, triggers, variables, and version publishing. Used by marketing technologists and web analytics engineers.\"\n  tags:\n    - Google Tag Manager\n    - Tag Management\n    - Marketing\n    - Analytics\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: tag-manager\n      location: ./shared/tag-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gtm-deploy-api\n      description: \"Unified REST API for GTM tag deployment management.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Account management\"\n          operations:\n            - method: GET\n        \
  \      name: list-accounts\n              description: \"List all GTM accounts\"\n              call: \"tag-manager.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/containers\n          name: containers\n          description: \"Container management\"\n          operations:\n            - method: GET\n              name: list-containers\n              description: \"List containers in an account\"\n              call: \"tag-manager.list-containers\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-container\n              description: \"Create a container\"\n              call: \"tag-manager.create-container\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/tags\n          name: tags\n          description: \"Tag management\"\n          operations:\n            - method: GET\n              name: list-tags\n              description: \"List tags in a workspace\"\n              call: \"tag-manager.list-tags\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tag\n              description: \"Create a tag\"\n              call: \"tag-manager.create-tag\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/triggers\n          name: triggers\n          description: \"Trigger management\"\n          operations:\n            - method: GET\n              name: list-triggers\n              description:\
  \ \"List triggers in a workspace\"\n              call: \"tag-manager.list-triggers\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/variables\n          name: variables\n          description: \"Variable management\"\n          operations:\n            - method: GET\n              name: list-variables\n              description: \"List variables in a workspace\"\n              call: \"tag-manager.list-variables\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: gtm-deploy-mcp\n      transport: http\n      description: \"MCP server for AI-assisted GTM tag deployment management.\"\n      tools:\n        - name: list-accounts\n          description: \"List all Google Tag Manager accounts\"\
  \n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: \"Get account details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.get-account\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-account\n          description: \"Update account settings\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tag-manager.update-account\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-containers\n          description: \"List containers in an account\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"tag-manager.list-containers\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-container\n          description: \"Create a new container\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tag-manager.create-container\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-container\n          description: \"Get container details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.get-container\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-container\n          description:\
  \ \"Delete a container\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tag-manager.delete-container\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List workspaces in a container\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.list-workspaces\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace\n          description: \"Create a new workspace\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tag-manager.create-workspace\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: delete-workspace\n          description: \"Delete a workspace\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tag-manager.delete-workspace\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tags\n          description: \"List tags in a workspace\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.list-tags\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-tag\n          description: \"Create a new tag\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tag-manager.create-tag\"\n          with:\n            parent: \"tools.parent\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tag\n          description: \"Get tag details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.get-tag\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-tag\n          description: \"Delete a tag\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tag-manager.delete-tag\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-triggers\n          description: \"List triggers in a workspace\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.list-triggers\"\n          with:\n\
  \            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-trigger\n          description: \"Create a new trigger\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tag-manager.create-trigger\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-trigger\n          description: \"Delete a trigger\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tag-manager.delete-trigger\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-variables\n          description: \"List variables in a workspace\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"tag-manager.list-variables\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-variable\n          description: \"Create a new variable\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tag-manager.create-variable\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-variable\n          description: \"Delete a variable\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tag-manager.delete-variable\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-versions\n          description: \"List container version\
  \ headers\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tag-manager.list-versions\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-version\n          description: \"Publish a container version\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tag-manager.publish-version\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
