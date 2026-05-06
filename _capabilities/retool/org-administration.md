---
categories: []
consumed_apis: []
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
- permanently remove a user.
- manage retool applications.
- create a new user account in the retool organization.
- list apps
- create app
- remove a specific user from a group.
- list all data source resource connections in the organization.
- update app
- update user profile or admin status.
- list all groups in the organization.
- create a new permission group.
- add a user to a group.
- remove a user from a group.
- create a new permission group for access control.
- delete an application permanently.
- retrieve a specific retool application by id.
- dashboard
- manage group membership.
- retool
- permanently remove a user from the organization.
- add group member
- list folders
- no code
- manage organizational folders.
- retrieve a user by uuid.
- create user
- low code
- list all permission groups in the organization.
- retrieve an application by id.
- list all folders.
- manage users in the retool organization.
- delete app
- list all applications.
- delete user
- list resources
- list all users with pagination support.
- manage permission groups.
- manage a specific application.
- create a new user and add to the organization.
- remove group member
- list all users in the retool organization with pagination.
- list all retool applications in the organization.
- internal tools
- administration
- add a user to a permission group.
- update user
- list all organizational folders for apps, resources, and workflows.
- update an application's metadata.
- get user
- create a new organizational folder.
- list all data source resources.
- admin panel
- update a user's name, admin status, or disable their account.
- list users
- permanently delete a retool application.
- list groups
- create a new retool application.
- create a new application.
- get app
- view data source connections.
- create folder
- create group
- create a new folder.
- manage a specific user.
- user management
- retrieve a specific user by their uuid.
- remove a user from a permission group.
slug: org-administration
source_filename: org-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Retool Organization Administration\n  description: Unified workflow capability for managing a Retool organization through the Management API. Enables IT administrators\n    and platform teams to automate user provisioning, group membership, app lifecycle, and resource management programmatically.\n    Exposes both a REST API and MCP server for AI-assisted administration tasks.\n  tags:\n  - Retool\n  - Administration\n  - User Management\n  - Internal Tools\n  - Low Code\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RETOOL_API_TOKEN: RETOOL_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: retool\n    baseUri: https://api.retool.com/v1\n    description: Retool Management API for organization administration.\n    authentication:\n      type: bearer\n      token: '{{RETOOL_API_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      description: Manage user accounts\
  \ in the Retool organization.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the organization with pagination.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of users per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user in the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n    \
  \        lastName: '{{tools.lastName}}'\n            isAdmin: '{{tools.isAdmin}}'\n            userType: '{{tools.userType}}'\n    - name: user-by-id\n      path: /users/{userId}\n      description: Manage a specific user by their UUID.\n      operations:\n      - name: get-user\n        method: GET\n        description: Retrieve a specific user by their ID.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user's profile and access settings.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the user.\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            isAdmin: '{{tools.isAdmin}}'\n            isDisabled: '{{tools.isDisabled}}'\n      - name: delete-user\n        method: DELETE\n        description: Permanently remove a user from the organization.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Manage groups for permission control.\n      operations:\n      - name: list-groups\n        method: GET\n        description: List all groups in the organization.\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: group-members\n      path: /groups/{groupId}/members\n      description: Manage group membership.\n      operations:\n      - name: add-group-member\n        method: POST\n        description: Add a user to a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: integer\n          required: true\n          description: The numeric group identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userId: '{{tools.userId}}'\n\
  \    - name: group-member-by-id\n      path: /groups/{groupId}/members/{userId}\n      description: Remove a specific member from a group.\n      operations:\n      - name: remove-group-member\n        method: DELETE\n        description: Remove a user from a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: integer\n          required: true\n          description: The numeric group identifier.\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the user to remove.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /apps\n      description: Manage Retool applications.\n      operations:\n      - name: list-apps\n        method: GET\n        description: List all applications in the organization.\n        inputParameters:\n        - name: page\n          in: query\n\
  \          type: integer\n          required: false\n          description: Page number for pagination.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of apps per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-app\n        method: POST\n        description: Create a new Retool application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            folderId: '{{tools.folderId}}'\n    - name: app-by-id\n      path: /apps/{appId}\n      description: Manage a specific Retool application.\n      operations:\n      - name: get-app\n        method: GET\n        description: Retrieve a specific\
  \ application by its ID.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique app identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-app\n        method: PUT\n        description: Update an application's metadata.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique app identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            folderId: '{{tools.folderId}}'\n      - name: delete-app\n        method: DELETE\n        description: Permanently delete an\
  \ application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The unique app identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /resources\n      description: View data source resource connections.\n      operations:\n      - name: list-resources\n        method: GET\n        description: List all data source resources in the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      description: Manage organizational folders.\n      operations:\n      - name: list-folders\n        method: GET\n        description: List all folders in the organization.\n        inputParameters:\n        - name: folderType\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter by folder type (app, resource, workflow).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-folder\n        method: POST\n        description: Create a new organizational folder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            folderType: '{{tools.folderType}}'\n            parentFolderId: '{{tools.parentFolderId}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: retool-org-admin-api\n    description: Unified REST API for Retool organization administration.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Manage users in the Retool organization.\n      operations:\n      - method: GET\n        name: list-users\n\
  \        description: List all users with pagination support.\n        call: retool.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user and add to the organization.\n        call: retool.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}\n      name: user-by-id\n      description: Manage a specific user.\n      operations:\n      - method: GET\n        name: get-user\n        description: Retrieve a user by UUID.\n        call: retool.get-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-user\n        description: Update user profile or admin status.\n        call: retool.update-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Permanently remove a user.\n        call: retool.delete-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Manage permission groups.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List all groups in the organization.\n        call: retool.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a new permission group.\n        call: retool.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}/members\n      name: group-members\n      description: Manage group membership.\n      operations:\n      - method: POST\n        name: add-group-member\n \
  \       description: Add a user to a group.\n        call: retool.add-group-member\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}/members/{userId}\n      name: group-member-by-id\n      description: Remove a specific user from a group.\n      operations:\n      - method: DELETE\n        name: remove-group-member\n        description: Remove a user from a group.\n        call: retool.remove-group-member\n        with:\n          groupId: rest.groupId\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps\n      name: apps\n      description: Manage Retool applications.\n      operations:\n      - method: GET\n        name: list-apps\n        description: List all applications.\n        call: retool.list-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n    \
  \    name: create-app\n        description: Create a new application.\n        call: retool.create-app\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps/{appId}\n      name: app-by-id\n      description: Manage a specific application.\n      operations:\n      - method: GET\n        name: get-app\n        description: Retrieve an application by ID.\n        call: retool.get-app\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-app\n        description: Update an application's metadata.\n        call: retool.update-app\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-app\n        description: Delete an application permanently.\n        call: retool.delete-app\n        with:\n          appId: rest.appId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/resources\n      name: resources\n      description: View data source connections.\n      operations:\n      - method: GET\n        name: list-resources\n        description: List all data source resources.\n        call: retool.list-resources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/folders\n      name: folders\n      description: Manage organizational folders.\n      operations:\n      - method: GET\n        name: list-folders\n        description: List all folders.\n        call: retool.list-folders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-folder\n        description: Create a new folder.\n        call: retool.create-folder\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: retool-org-admin-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted Retool organization administration.\n    tools:\n    - name: list-users\n      description: List all users in the Retool organization with pagination.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Retrieve a specific user by their UUID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user account in the Retool organization.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: retool.create-user\n      with:\n        email: tools.email\n        firstName: tools.firstName\n        lastName: tools.lastName\n        isAdmin: tools.isAdmin\n \
  \       userType: tools.userType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update a user's name, admin status, or disable their account.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: retool.update-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Permanently remove a user from the organization.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: retool.delete-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List all permission groups in the organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.list-groups\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: create-group\n      description: Create a new permission group for access control.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: retool.create-group\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-group-member\n      description: Add a user to a permission group.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: retool.add-group-member\n      with:\n        groupId: tools.groupId\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-group-member\n      description: Remove a user from a permission group.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: retool.remove-group-member\n      with:\n        groupId: tools.groupId\n        userId:\
  \ tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-apps\n      description: List all Retool applications in the organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.list-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app\n      description: Retrieve a specific Retool application by ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.get-app\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-app\n      description: Create a new Retool application.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: retool.create-app\n      with:\n        name: tools.name\n        description: tools.description\n        folderId: tools.folderId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: delete-app\n      description: Permanently delete a Retool application.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: retool.delete-app\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-resources\n      description: List all data source resource connections in the organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.list-resources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-folders\n      description: List all organizational folders for apps, resources, and workflows.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: retool.list-folders\n      with:\n        folderType: tools.folderType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-folder\n      description: Create a new organizational\
  \ folder.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: retool.create-folder\n      with:\n        name: tools.name\n        folderType: tools.folderType\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
