---
api_specs:
- filename: retool-management-api-openapi.yml
  format: yaml
  label: retool
  slug: retool
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/retool/refs/heads/main/openapi/retool-management-api-openapi.yml
categories: []
consumed_apis:
- retool
description: Unified workflow capability for managing a Retool organization through the Management API. Enables IT administrators and platform teams to automate user provisioning, group membership, app lifecycle, and resource management programmatically. Exposes both a REST API and MCP server for AI-assisted administration tasks.
layout: capability
name: Retool Organization Administration
operations:
- description: List all users with pagination support.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user and add to the organization.
  method: POST
  name: create-user
  path: /v1/users
- description: Retrieve a user by UUID.
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: Update user profile or admin status.
  method: PUT
  name: update-user
  path: /v1/users/{userId}
- description: Permanently remove a user.
  method: DELETE
  name: delete-user
  path: /v1/users/{userId}
- description: List all groups in the organization.
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a new permission group.
  method: POST
  name: create-group
  path: /v1/groups
- description: Add a user to a group.
  method: POST
  name: add-group-member
  path: /v1/groups/{groupId}/members
- description: Remove a user from a group.
  method: DELETE
  name: remove-group-member
  path: /v1/groups/{groupId}/members/{userId}
- description: List all applications.
  method: GET
  name: list-apps
  path: /v1/apps
- description: Create a new application.
  method: POST
  name: create-app
  path: /v1/apps
- description: Retrieve an application by ID.
  method: GET
  name: get-app
  path: /v1/apps/{appId}
- description: Update an application's metadata.
  method: PUT
  name: update-app
  path: /v1/apps/{appId}
- description: Delete an application permanently.
  method: DELETE
  name: delete-app
  path: /v1/apps/{appId}
- description: List all data source resources.
  method: GET
  name: list-resources
  path: /v1/resources
- description: List all folders.
  method: GET
  name: list-folders
  path: /v1/folders
- description: Create a new folder.
  method: POST
  name: create-folder
  path: /v1/folders
personas: []
provider_name: Retool
provider_slug: retool
search_terms:
- create group
- update an application's metadata.
- update app
- create a new user account in the retool organization.
- list all users in the retool organization with pagination.
- manage a specific user.
- list all organizational folders for apps, resources, and workflows.
- create folder
- list apps
- manage users in the retool organization.
- delete an application permanently.
- manage group membership.
- delete app
- update user profile or admin status.
- add group member
- low code
- list folders
- list resources
- permanently remove a user.
- list all groups in the organization.
- manage retool applications.
- retrieve a user by uuid.
- retrieve an application by id.
- retrieve a specific user by their uuid.
- permanently remove a user from the organization.
- permanently delete a retool application.
- create user
- create a new permission group.
- list all data source resource connections in the organization.
- update a user's name, admin status, or disable their account.
- add a user to a permission group.
- remove a user from a group.
- create a new folder.
- create a new user and add to the organization.
- get app
- list all permission groups in the organization.
- list all folders.
- create a new organizational folder.
- delete user
- retrieve a specific retool application by id.
- administration
- remove a user from a permission group.
- create app
- list all retool applications in the organization.
- create a new application.
- list users
- manage permission groups.
- list groups
- add a user to a group.
- remove a specific user from a group.
- internal tools
- remove group member
- view data source connections.
- create a new retool application.
- list all applications.
- manage a specific application.
- get user
- admin panel
- user management
- update user
- retool
- list all data source resources.
- manage organizational folders.
- dashboard
- no code
- create a new permission group for access control.
- list all users with pagination support.
slug: org-administration
source_filename: org-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Retool Organization Administration\"\n  description: >-\n    Unified workflow capability for managing a Retool organization through\n    the Management API. Enables IT administrators and platform teams to\n    automate user provisioning, group membership, app lifecycle, and resource\n    management programmatically. Exposes both a REST API and MCP server for\n    AI-assisted administration tasks.\n  tags:\n    - Retool\n    - Administration\n    - User Management\n    - Internal Tools\n    - Low Code\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RETOOL_API_TOKEN: RETOOL_API_TOKEN\n\ncapability:\n  consumes:\n    - import: retool\n      location: ./shared/retool-management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: retool-org-admin-api\n      description: \"Unified REST API for Retool organization administration.\"\n      resources:\n    \
  \    - path: /v1/users\n          name: users\n          description: \"Manage users in the Retool organization.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users with pagination support.\"\n              call: \"retool.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user and add to the organization.\"\n              call: \"retool.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{userId}\n          name: user-by-id\n          description: \"Manage a specific user.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Retrieve a user by UUID.\"\n              call: \"retool.get-user\"\n        \
  \      with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-user\n              description: \"Update user profile or admin status.\"\n              call: \"retool.update-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Permanently remove a user.\"\n              call: \"retool.delete-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Manage permission groups.\"\n          operations:\n            - method: GET\n              name: list-groups\n\
  \              description: \"List all groups in the organization.\"\n              call: \"retool.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create a new permission group.\"\n              call: \"retool.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}/members\n          name: group-members\n          description: \"Manage group membership.\"\n          operations:\n            - method: POST\n              name: add-group-member\n              description: \"Add a user to a group.\"\n              call: \"retool.add-group-member\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}/members/{userId}\n\
  \          name: group-member-by-id\n          description: \"Remove a specific user from a group.\"\n          operations:\n            - method: DELETE\n              name: remove-group-member\n              description: \"Remove a user from a group.\"\n              call: \"retool.remove-group-member\"\n              with:\n                groupId: \"rest.groupId\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps\n          name: apps\n          description: \"Manage Retool applications.\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"List all applications.\"\n              call: \"retool.list-apps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-app\n              description: \"Create a new application.\"\
  \n              call: \"retool.create-app\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}\n          name: app-by-id\n          description: \"Manage a specific application.\"\n          operations:\n            - method: GET\n              name: get-app\n              description: \"Retrieve an application by ID.\"\n              call: \"retool.get-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-app\n              description: \"Update an application's metadata.\"\n              call: \"retool.update-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-app\n  \
  \            description: \"Delete an application permanently.\"\n              call: \"retool.delete-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resources\n          name: resources\n          description: \"View data source connections.\"\n          operations:\n            - method: GET\n              name: list-resources\n              description: \"List all data source resources.\"\n              call: \"retool.list-resources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/folders\n          name: folders\n          description: \"Manage organizational folders.\"\n          operations:\n            - method: GET\n              name: list-folders\n              description: \"List all folders.\"\n              call: \"retool.list-folders\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-folder\n              description: \"Create a new folder.\"\n              call: \"retool.create-folder\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: retool-org-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Retool organization administration.\"\n      tools:\n        - name: list-users\n          description: \"List all users in the Retool organization with pagination.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retool.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Retrieve a specific user by their UUID.\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: false\n          call: \"retool.get-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user account in the Retool organization.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"retool.create-user\"\n          with:\n            email: \"tools.email\"\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            isAdmin: \"tools.isAdmin\"\n            userType: \"tools.userType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: \"Update a user's name, admin status, or disable their account.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n \
  \         call: \"retool.update-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Permanently remove a user from the organization.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"retool.delete-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List all permission groups in the organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retool.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: \"Create a new permission group for access control.\"\n  \
  \        hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"retool.create-group\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-group-member\n          description: \"Add a user to a permission group.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"retool.add-group-member\"\n          with:\n            groupId: \"tools.groupId\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-group-member\n          description: \"Remove a user from a permission group.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"retool.remove-group-member\"\n          with:\n\
  \            groupId: \"tools.groupId\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-apps\n          description: \"List all Retool applications in the organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retool.list-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-app\n          description: \"Retrieve a specific Retool application by ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retool.get-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-app\n          description: \"Create a new Retool application.\"\n          hints:\n            readOnly: false\n            destructive: false\n     \
  \       idempotent: false\n          call: \"retool.create-app\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            folderId: \"tools.folderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-app\n          description: \"Permanently delete a Retool application.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"retool.delete-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-resources\n          description: \"List all data source resource connections in the organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retool.list-resources\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-folders\n          description: \"List all organizational folders for apps, resources, and workflows.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"retool.list-folders\"\n          with:\n            folderType: \"tools.folderType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-folder\n          description: \"Create a new organizational folder.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"retool.create-folder\"\n          with:\n            name: \"tools.name\"\n            folderType: \"tools.folderType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/retool/refs/heads/main/capabilities/org-administration.yaml
tags:
- Retool
- Administration
- User Management
- Internal Tools
- Low Code
tools:
- description: List all users in the Retool organization with pagination.
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Retrieve a specific user by their UUID.
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: Create a new user account in the Retool organization.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: Update a user's name, admin status, or disable their account.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-user
- description: Permanently remove a user from the organization.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List all permission groups in the organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-groups
- description: Create a new permission group for access control.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-group
- description: Add a user to a permission group.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-group-member
- description: Remove a user from a permission group.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-group-member
- description: List all Retool applications in the organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-apps
- description: Retrieve a specific Retool application by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-app
- description: Create a new Retool application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-app
- description: Permanently delete a Retool application.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-app
- description: List all data source resource connections in the organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-resources
- description: List all organizational folders for apps, resources, and workflows.
  hints:
    openWorld: false
    readOnly: true
  name: list-folders
- description: Create a new organizational folder.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-folder
---
