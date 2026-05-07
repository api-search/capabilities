---
categories: []
consumed_apis: []
description: Keystone is the OpenStack Identity service that provides authentication, authorization, and a service catalog for an OpenStack cloud. Tokens issued by Keystone are required to call any other OpenStack service API. The v3 API exposes endpoints for tokens, users, groups, projects, domains, roles, role assignments, services, endpoints, and the service catalog.
layout: capability
name: OpenStack Identity (Keystone) API v3
operations:
- description: Issue an authentication token
  method: POST
  name: issuetoken
  path: /auth/tokens
- description: Validate token
  method: GET
  name: validatetoken
  path: /auth/tokens
- description: Revoke token
  method: DELETE
  name: revoketoken
  path: /auth/tokens
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Create user
  method: POST
  name: createuser
  path: /users
- description: Get user
  method: GET
  name: getuser
  path: /users/{user_id}
- description: Update user
  method: PATCH
  name: updateuser
  path: /users/{user_id}
- description: Delete user
  method: DELETE
  name: deleteuser
  path: /users/{user_id}
- description: List groups
  method: GET
  name: listgroups
  path: /groups
- description: Create group
  method: POST
  name: creategroup
  path: /groups
- description: List projects
  method: GET
  name: listprojects
  path: /projects
- description: Create project
  method: POST
  name: createproject
  path: /projects
- description: Get project
  method: GET
  name: getproject
  path: /projects/{project_id}
- description: Update project
  method: PATCH
  name: updateproject
  path: /projects/{project_id}
- description: Delete project
  method: DELETE
  name: deleteproject
  path: /projects/{project_id}
- description: List domains
  method: GET
  name: listdomains
  path: /domains
- description: Create domain
  method: POST
  name: createdomain
  path: /domains
- description: List roles
  method: GET
  name: listroles
  path: /roles
- description: Create role
  method: POST
  name: createrole
  path: /roles
- description: List role assignments
  method: GET
  name: listroleassignments
  path: /role_assignments
- description: List services in catalog
  method: GET
  name: listservices
  path: /services
- description: Create service
  method: POST
  name: createservice
  path: /services
- description: List service endpoints
  method: GET
  name: listendpoints
  path: /endpoints
- description: Create endpoint
  method: POST
  name: createendpoint
  path: /endpoints
personas: []
provider_name: OpenStack
provider_slug: openstack
search_terms:
- createendpoint
- create group
- cloud platform
- getproject
- revoke token
- issuetoken
- openstack
- list groups
- creategroup
- api
- update user
- create domain
- createrole
- linux foundation
- open source
- list domains
- listendpoints
- virtualization
- getuser
- delete user
- validatetoken
- updateproject
- listgroups
- deleteuser
- list projects
- list users
- create project
- delete project
- create role
- list service endpoints
- infrastructure as a service
- revoketoken
- updateuser
- list role assignments
- deleteproject
- validate token
- list services in catalog
- get user
- listroleassignments
- createuser
- create user
- get project
- listroles
- listusers
- create endpoint
- create service
- issue an authentication token
- listprojects
- list roles
- listdomains
- createservice
- update project
- createdomain
- listservices
- createproject
slug: openstack-capability
source_filename: openstack-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenStack Identity (Keystone) API v3\n  description: Keystone is the OpenStack Identity service that provides authentication, authorization, and a service catalog\n    for an OpenStack cloud. Tokens issued by Keystone are required to call any other OpenStack service API. The v3 API exposes\n    endpoints for tokens, users, groups, projects, domains, roles, role assignments, services, endpoints, and the service\n    catalog.\n  tags:\n  - Openstack\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openstack\n    baseUri: https://keystone.example.com:5000/v3\n    description: OpenStack Identity (Keystone) API v3 HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Auth-Token\n      value: '{{OPENSTACK_TOKEN}}'\n    resources:\n    - name: auth-tokens\n      path: /auth/tokens\n      operations:\n      - name: issuetoken\n        method: POST\n\
  \        description: Issue an authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validatetoken\n        method: GET\n        description: Validate token\n        inputParameters:\n        - name: X-Subject-Token\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoketoken\n        method: DELETE\n        description: Revoke token\n        inputParameters:\n        - name: X-Subject-Token\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-user-id\n      path: /users/{user_id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Create group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: projects-project-id\n      path: /projects/{project_id}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PATCH\n        description: Update project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Delete project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /domains\n      operations:\n      - name: listdomains\n        method: GET\n        description: List domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createdomain\n        method: POST\n        description: Create domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      operations:\n      - name: listroles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrole\n        method: POST\n        description: Create role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: role-assignments\n      path: /role_assignments\n      operations:\n      - name: listroleassignments\n        method: GET\n        description: List role assignments\n        inputParameters:\n        - name: scope.project.id\n          in: query\n          type: string\n        - name: scope.domain.id\n\
  \          in: query\n          type: string\n        - name: user.id\n          in: query\n          type: string\n        - name: group.id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: List services in catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservice\n        method: POST\n        description: Create service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints\n      path: /endpoints\n      operations:\n      - name: listendpoints\n        method: GET\n        description: List service endpoints\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createendpoint\n        method: POST\n        description: Create endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openstack-rest\n    description: REST adapter for OpenStack Identity (Keystone) API v3.\n    resources:\n    - path: /auth/tokens\n      name: issuetoken\n      operations:\n      - method: POST\n        name: issuetoken\n        description: Issue an authentication token\n        call: openstack.issuetoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/tokens\n      name: validatetoken\n      operations:\n      - method: GET\n        name: validatetoken\n        description: Validate token\n        call: openstack.validatetoken\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /auth/tokens\n      name: revoketoken\n      operations:\n      - method: DELETE\n        name: revoketoken\n        description: Revoke token\n        call: openstack.revoketoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: openstack.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create user\n        call: openstack.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: openstack.getuser\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: updateuser\n      operations:\n      - method: PATCH\n        name: updateuser\n        description: Update user\n        call: openstack.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete user\n        call: openstack.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: List groups\n        call: openstack.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Create group\n        call: openstack.creategroup\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: openstack.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create project\n        call: openstack.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get project\n        call: openstack.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: updateproject\n      operations:\n      - method: PATCH\n        name: updateproject\n\
  \        description: Update project\n        call: openstack.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Delete project\n        call: openstack.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: listdomains\n      operations:\n      - method: GET\n        name: listdomains\n        description: List domains\n        call: openstack.listdomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: createdomain\n      operations:\n      - method: POST\n        name: createdomain\n        description: Create domain\n        call: openstack.createdomain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: listroles\n\
  \      operations:\n      - method: GET\n        name: listroles\n        description: List roles\n        call: openstack.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: createrole\n      operations:\n      - method: POST\n        name: createrole\n        description: Create role\n        call: openstack.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /role_assignments\n      name: listroleassignments\n      operations:\n      - method: GET\n        name: listroleassignments\n        description: List role assignments\n        call: openstack.listroleassignments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List services in catalog\n        call: openstack.listservices\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /services\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: Create service\n        call: openstack.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints\n      name: listendpoints\n      operations:\n      - method: GET\n        name: listendpoints\n        description: List service endpoints\n        call: openstack.listendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints\n      name: createendpoint\n      operations:\n      - method: POST\n        name: createendpoint\n        description: Create endpoint\n        call: openstack.createendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openstack-mcp\n    transport: http\n    description: MCP adapter for OpenStack Identity\
  \ (Keystone) API v3 for AI agent use.\n    tools:\n    - name: issuetoken\n      description: Issue an authentication token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.issuetoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validatetoken\n      description: Validate token\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.validatetoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoketoken\n      description: Revoke token\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openstack.revoketoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.listusers\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openstack.deleteuser\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: Create group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.creategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Create project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.createproject\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Update project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: Delete project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openstack.deleteproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdomains\n      description: List domains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ openstack.listdomains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdomain\n      description: Create domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.createdomain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: List roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.listroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrole\n      description: Create role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.createrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroleassignments\n      description: List role assignments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: openstack.listroleassignments\n      with:\n        scope.project.id: tools.scope.project.id\n        scope.domain.id: tools.scope.domain.id\n        user.id: tools.user.id\n        group.id: tools.group.id\n      inputParameters:\n      - name: scope.project.id\n        type: string\n        description: scope.project.id\n      - name: scope.domain.id\n        type: string\n        description: scope.domain.id\n      - name: user.id\n        type: string\n        description: user.id\n      - name: group.id\n        type: string\n        description: group.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: List services in catalog\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: Create service\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.createservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listendpoints\n      description: List service endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstack.listendpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createendpoint\n      description: Create endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstack.createendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENSTACK_TOKEN: OPENSTACK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openstack/refs/heads/main/capabilities/openstack-capability.yaml
tags:
- Openstack
- API
tools:
- description: Issue an authentication token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: issuetoken
- description: Validate token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validatetoken
- description: Revoke token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoketoken
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Update project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproject
- description: Delete project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: List domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdomains
- description: Create domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdomain
- description: List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Create role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: List role assignments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroleassignments
- description: List services in catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Create service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: List service endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpoints
- description: Create endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createendpoint
---
