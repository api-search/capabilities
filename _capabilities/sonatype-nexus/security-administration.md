---
categories: []
consumed_apis: []
description: Workflow capability for managing Nexus Repository security including users, roles, privileges, LDAP, SAML, content selectors, and authentication realms. Used by platform administrators and security teams.
layout: capability
name: Sonatype Nexus Security Administration
operations:
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: Delete a user
  method: DELETE
  name: delete-user
  path: /v1/users
- description: List all roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a new role
  method: POST
  name: create-role
  path: /v1/roles
- description: Check system health status
  method: GET
  name: get-status
  path: /v1/system-status
- description: List all tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Get a task by ID
  method: GET
  name: get-task
  path: /v1/tasks
- description: Run a task by ID
  method: POST
  name: run-task
  path: /v1/tasks
personas: []
provider_name: Sonatype Nexus
provider_slug: sonatype-nexus
search_terms:
- devops
- create a new role
- list all background tasks in nexus
- users
- get a task by id
- system health and status
- delete a user
- npm
- get task
- list all users
- roles
- check system status
- access control
- list tasks
- delete a nexus user by id
- delete user
- maven
- software supply chain
- list all tasks
- get status
- list users
- create role
- administration
- check system health status
- list all nexus roles
- background task management
- execute a nexus background task by id
- repository
- create a new nexus user account
- artifact management
- create user
- create a new user
- sonatype nexus
- create a new nexus role with privileges
- run task
- list all roles
- role and permission management
- list roles
- list all nexus users
- security
- docker
- user account management
- package management
- run a task by id
- check nexus system health and status
slug: security-administration
source_filename: security-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sonatype Nexus Security Administration\n  description: Workflow capability for managing Nexus Repository security including users, roles, privileges, LDAP, SAML,\n    content selectors, and authentication realms. Used by platform administrators and security teams.\n  tags:\n  - Sonatype Nexus\n  - Security\n  - Access Control\n  - Users\n  - Roles\n  - Administration\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NEXUS_USERNAME: NEXUS_USERNAME\n    NEXUS_PASSWORD: NEXUS_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: nexus\n    baseUri: https://{nexus-host}/service/rest\n    description: Sonatype Nexus Repository Manager REST API v3\n    authentication:\n      type: basic\n      username: '{{NEXUS_USERNAME}}'\n      password: '{{NEXUS_PASSWORD}}'\n    resources:\n    - name: repositories\n      path: /v1/repositories\n      description: Manage artifact repositories across all\
  \ supported formats\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List repositories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-repository\n        method: DELETE\n        description: Delete repository of any format\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Name of the repository to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-repository\n        method: GET\n        description: Get repository details\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Name of the repository\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: invalidate-repository-cache\n        method: POST\n        description: Invalidate repository cache (proxy or group repositories)\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Name of the repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components\n      path: /v1/components\n      description: Manage software components in repositories\n      operations:\n      - name: list-components\n        method: GET\n        description: List components\n        inputParameters:\n        - name: repository\n          in: query\n          type: string\n          required: true\n          description: Repository name to list components from\n        - name: continuationToken\n          in: query\n          type:\
  \ string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-component\n        method: GET\n        description: Get a single component\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Component ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-component\n        method: DELETE\n        description: Delete a single component\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Component ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path:\
  \ /v1/assets\n      description: Manage binary assets in repositories\n      operations:\n      - name: list-assets\n        method: GET\n        description: List assets\n        inputParameters:\n        - name: repository\n          in: query\n          type: string\n          required: true\n          description: Repository name\n        - name: continuationToken\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-asset\n        method: GET\n        description: Get a single asset\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-asset\n\
  \        method: DELETE\n        description: Delete a single asset\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /v1/search\n      description: Search for components and assets across repositories\n      operations:\n      - name: search-components\n        method: GET\n        description: Search components\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query string\n        - name: repository\n          in: query\n          type: string\n          required: false\n          description: Repository name filter\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Format\
  \ filter (maven2, npm, docker, etc)\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Component name filter\n        - name: version\n          in: query\n          type: string\n          required: false\n          description: Component version filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-assets\n        method: GET\n        description: Search assets\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query string\n        - name: repository\n          in: query\n          type: string\n          required: false\n          description: Repository name filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-users\n      path:\
  \ /v1/security/users\n      description: Manage Nexus users and authentication\n      operations:\n      - name: list-users\n        method: GET\n        description: Retrieve a list of users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user in the default source\n        body:\n          type: json\n          data:\n            userId: '{{tools.userId}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            emailAddress: '{{tools.emailAddress}}'\n            password: '{{tools.password}}'\n            status: '{{tools.status}}'\n            roles: '{{tools.roles}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n\
  \        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-roles\n      path: /v1/security/roles\n      description: Manage Nexus roles and permissions\n      operations:\n      - name: list-roles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-role\n        method: POST\n        description: Create role\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            privileges: '{{tools.privileges}}'\n            roles: '{{tools.roles}}'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /v1/tasks\n      description: Manage and execute background tasks\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-task\n        method: GET\n        description: Get a single task by id\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-task\n        method: POST\n        description: Run task\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Task ID to run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /v1/status\n      description: System health and status checks\n      operations:\n      - name: get-status\n        method: GET\n        description: Health check endpoint that validates server can respond to read requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-status\n        method: GET\n        description: Health check endpoint that returns the results of the system status checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blob-stores\n      path: /v1/blobstores\n      description: Manage blob storage backends\n      operations:\n      - name: list-blob-stores\n        method: GET\n        description: List\
  \ the blob stores\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-blob-store\n        method: DELETE\n        description: Delete a blob store by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Blob store name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: nexus-security-api\n    description: Unified REST API for Nexus security administration.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User account management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: nexus.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \     - method: POST\n        name: create-user\n        description: Create a new user\n        call: nexus.create-user\n        with:\n          userId: rest.userId\n          firstName: rest.firstName\n          lastName: rest.lastName\n          emailAddress: rest.emailAddress\n          password: rest.password\n          status: rest.status\n          roles: rest.roles\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Delete a user\n        call: nexus.delete-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles\n      name: roles\n      description: Role and permission management\n      operations:\n      - method: GET\n        name: list-roles\n        description: List all roles\n        call: nexus.list-roles\n        outputParameters:\n        - type: object\n          mapping: $.\n     \
  \ - method: POST\n        name: create-role\n        description: Create a new role\n        call: nexus.create-role\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/system-status\n      name: system-status\n      description: System health and status\n      operations:\n      - method: GET\n        name: get-status\n        description: Check system health status\n        call: nexus.get-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Background task management\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List all tasks\n        call: nexus.list-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-task\n        description: Get a task by ID\n        call: nexus.get-task\n        with:\n          id: rest.id\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n      - method: POST\n        name: run-task\n        description: Run a task by ID\n        call: nexus.run-task\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: nexus-security-mcp\n    transport: http\n    description: MCP server for AI-assisted Nexus security administration.\n    tools:\n    - name: list-users\n      description: List all Nexus users\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new Nexus user account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nexus.create-user\n      with:\n        userId: tools.userId\n        firstName: tools.firstName\n        lastName: tools.lastName\n        emailAddress:\
  \ tools.emailAddress\n        password: tools.password\n        status: tools.status\n        roles: tools.roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a Nexus user by ID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nexus.delete-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List all Nexus roles\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.list-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-role\n      description: Create a new Nexus role with privileges\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nexus.create-role\n      with:\n        id: tools.id\n        name: tools.name\n        description:\
  \ tools.description\n        privileges: tools.privileges\n        roles: tools.roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-system-status\n      description: Check Nexus system health and status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.get-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List all background tasks in Nexus\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nexus.list-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-task\n      description: Execute a Nexus background task by ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nexus.run-task\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sonatype-nexus/refs/heads/main/capabilities/security-administration.yaml
tags:
- Sonatype Nexus
- Security
- Access Control
- Users
- Roles
- Administration
tools:
- description: List all Nexus users
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Create a new Nexus user account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: Delete a Nexus user by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List all Nexus roles
  hints:
    idempotent: true
    readOnly: true
  name: list-roles
- description: Create a new Nexus role with privileges
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-role
- description: Check Nexus system health and status
  hints:
    idempotent: true
    readOnly: true
  name: check-system-status
- description: List all background tasks in Nexus
  hints:
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Execute a Nexus background task by ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: run-task
---
