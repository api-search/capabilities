---
categories: []
consumed_apis: []
description: The ACC Account Admin API automates the creation and management of projects, assignment and management of project users, and management of member and partner company directories within Autodesk Construction Cloud. It supports bulk operations for enterprise-scale administration.
layout: capability
name: Autodesk ACC Account Admin API
operations:
- description: Autodesk List Projects
  method: GET
  name: getprojects
  path: /construction/admin/v1/accounts/{accountId}/projects
- description: Autodesk Create Project
  method: POST
  name: createproject
  path: /construction/admin/v1/accounts/{accountId}/projects
- description: Autodesk Get Project
  method: GET
  name: getproject
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}
- description: Autodesk Update Project
  method: PATCH
  name: updateproject
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}
- description: Autodesk List Project Users
  method: GET
  name: getprojectusers
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users
- description: Autodesk Add Project User
  method: POST
  name: addprojectuser
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users
- description: Autodesk Update Project User
  method: PATCH
  name: updateprojectuser
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users/{userId}
- description: Autodesk Remove Project User
  method: DELETE
  name: removeprojectuser
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users/{userId}
- description: Autodesk List Account Users
  method: GET
  name: getaccountusers
  path: /construction/admin/v1/accounts/{accountId}/users
- description: Autodesk List Companies
  method: GET
  name: getcompanies
  path: /construction/admin/v1/accounts/{accountId}/companies
- description: Autodesk Create Company
  method: POST
  name: createcompany
  path: /construction/admin/v1/accounts/{accountId}/companies
- description: Autodesk List Industry Roles
  method: GET
  name: getindustryroles
  path: /construction/admin/v1/projects/{projectId}/industryRoles
personas: []
provider_name: Autodesk
provider_slug: autodesk
search_terms:
- autodesk create company
- autodesk update project user
- autodesk list industry roles
- engineering
- getproject
- media and entertainment
- autodesk list project users
- autodesk add project user
- autodesk create project
- removeprojectuser
- addprojectuser
- api
- autodesk
- construction
- getprojects
- autodesk list projects
- autodesk update project
- design
- getaccountusers
- architecture
- updateproject
- manufacturing
- autodesk list companies
- updateprojectuser
- getprojectusers
- createcompany
- autodesk list account users
- cad
- 3d modeling
- getcompanies
- sustainability
- autodesk remove project user
- bim
- digital twins
- autodesk get project
- getindustryroles
- createproject
slug: autodesk-capability
source_filename: autodesk-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Autodesk ACC Account Admin API\n  description: The ACC Account Admin API automates the creation and management of projects, assignment and management of project\n    users, and management of member and partner company directories within Autodesk Construction Cloud. It supports bulk operations\n    for enterprise-scale administration.\n  tags:\n  - Autodesk\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: autodesk\n    baseUri: https://developer.api.autodesk.com\n    description: Autodesk ACC Account Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{AUTODESK_TOKEN}}'\n    resources:\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects\n      operations:\n      - name: getprojects\n        method: GET\n        description: Autodesk List Projects\n        inputParameters:\n\
  \        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: filter[status]\n          in: query\n          type: string\n        - name: filter[name]\n          in: query\n          type: string\n        - name: filter[platform]\n          in: query\n          type: string\n        - name: sort\n          in: query\n          type: string\n          description: Sort field and direction (e.g., name asc, startDate desc).\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Autodesk Create Project\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: Autodesk Get Project\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PATCH\n        description: Autodesk Update Project\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users\n      operations:\n      - name: getprojectusers\n        method: GET\n        description: Autodesk List Project Users\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: filter[email]\n          in: query\n          type: string\n        - name: filter[name]\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: addprojectuser\n        method: POST\n        description: Autodesk Add Project User\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users/{userId}\n      operations:\n      - name: updateprojectuser\n        method: PATCH\n        description: Autodesk Update Project User\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name:\
  \ userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeprojectuser\n        method: DELETE\n        description: Autodesk Remove Project User\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-users\n      path: /construction/admin/v1/accounts/{accountId}/users\n      operations:\n      - name: getaccountusers\n        method: GET\n        description: Autodesk List Account Users\n\
  \        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: filter[email]\n          in: query\n          type: string\n        - name: filter[name]\n          in: query\n          type: string\n        - name: filter[status]\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-compani\n      path: /construction/admin/v1/accounts/{accountId}/companies\n      operations:\n      - name: getcompanies\n        method: GET\n        description: Autodesk List Companies\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name:\
  \ filter[name]\n          in: query\n          type: string\n        - name: filter[trade]\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcompany\n        method: POST\n        description: Autodesk Create Company\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-projects-projectid-industr\n      path: /construction/admin/v1/projects/{projectId}/industryRoles\n      operations:\n      - name: getindustryroles\n        method: GET\n        description: Autodesk List Industry Roles\n\
  \        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: autodesk-rest\n    description: REST adapter for Autodesk ACC Account Admin API.\n    resources:\n    - path: /construction/admin/v1/accounts/{accountId}/projects\n      name: getprojects\n      operations:\n      - method: GET\n        name: getprojects\n        description: Autodesk List Projects\n        call: autodesk.getprojects\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Autodesk Create Project\n        call: autodesk.createproject\n\
  \        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Autodesk Get Project\n        call: autodesk.getproject\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}\n      name: updateproject\n      operations:\n      - method: PATCH\n        name: updateproject\n        description: Autodesk Update Project\n        call: autodesk.updateproject\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users\n\
  \      name: getprojectusers\n      operations:\n      - method: GET\n        name: getprojectusers\n        description: Autodesk List Project Users\n        call: autodesk.getprojectusers\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users\n      name: addprojectuser\n      operations:\n      - method: POST\n        name: addprojectuser\n        description: Autodesk Add Project User\n        call: autodesk.addprojectuser\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users/{userId}\n      name: updateprojectuser\n      operations:\n      - method: PATCH\n        name: updateprojectuser\n        description:\
  \ Autodesk Update Project User\n        call: autodesk.updateprojectuser\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users/{userId}\n      name: removeprojectuser\n      operations:\n      - method: DELETE\n        name: removeprojectuser\n        description: Autodesk Remove Project User\n        call: autodesk.removeprojectuser\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/users\n      name: getaccountusers\n      operations:\n      - method: GET\n        name: getaccountusers\n        description: Autodesk List Account Users\n        call: autodesk.getaccountusers\n\
  \        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/companies\n      name: getcompanies\n      operations:\n      - method: GET\n        name: getcompanies\n        description: Autodesk List Companies\n        call: autodesk.getcompanies\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/companies\n      name: createcompany\n      operations:\n      - method: POST\n        name: createcompany\n        description: Autodesk Create Company\n        call: autodesk.createcompany\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/projects/{projectId}/industryRoles\n      name: getindustryroles\n      operations:\n      - method:\
  \ GET\n        name: getindustryroles\n        description: Autodesk List Industry Roles\n        call: autodesk.getindustryroles\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: autodesk-mcp\n    transport: http\n    description: MCP adapter for Autodesk ACC Account Admin API for AI agent use.\n    tools:\n    - name: getprojects\n      description: Autodesk List Projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk.getprojects\n      with:\n        accountId: tools.accountId\n        filter[status]: tools.filter[status]\n        filter[name]: tools.filter[name]\n        filter[platform]: tools.filter[platform]\n        sort: tools.sort\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n\
  \        required: true\n      - name: filter[status]\n        type: string\n        description: filter[status]\n      - name: filter[name]\n        type: string\n        description: filter[name]\n      - name: filter[platform]\n        type: string\n        description: filter[platform]\n      - name: sort\n        type: string\n        description: Sort field and direction (e.g., name asc, startDate desc).\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Autodesk Create Project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: autodesk.createproject\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Autodesk Get Project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk.getproject\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Autodesk Update Project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: autodesk.updateproject\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n      inputParameters:\n      - name: accountId\n        type: string\n\
  \        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprojectusers\n      description: Autodesk List Project Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk.getprojectusers\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n        filter[email]: tools.filter[email]\n        filter[name]: tools.filter[name]\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: filter[email]\n        type: string\n        description: filter[email]\n      - name: filter[name]\n\
  \        type: string\n        description: filter[name]\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addprojectuser\n      description: Autodesk Add Project User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: autodesk.addprojectuser\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateprojectuser\n      description: Autodesk Update Project User\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: autodesk.updateprojectuser\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n        userId: tools.userId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeprojectuser\n      description: Autodesk Remove Project User\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: autodesk.removeprojectuser\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n        userId: tools.userId\n      inputParameters:\n      - name: accountId\n        type: string\n        description:\
  \ accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountusers\n      description: Autodesk List Account Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk.getaccountusers\n      with:\n        accountId: tools.accountId\n        filter[email]: tools.filter[email]\n        filter[name]: tools.filter[name]\n        filter[status]: tools.filter[status]\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: filter[email]\n        type: string\n        description: filter[email]\n      - name: filter[name]\n      \
  \  type: string\n        description: filter[name]\n      - name: filter[status]\n        type: string\n        description: filter[status]\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcompanies\n      description: Autodesk List Companies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk.getcompanies\n      with:\n        accountId: tools.accountId\n        filter[name]: tools.filter[name]\n        filter[trade]: tools.filter[trade]\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: filter[name]\n        type: string\n        description: filter[name]\n      - name: filter[trade]\n        type:\
  \ string\n        description: filter[trade]\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcompany\n      description: Autodesk Create Company\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: autodesk.createcompany\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getindustryroles\n      description: Autodesk List Industry Roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk.getindustryroles\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name:\
  \ projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AUTODESK_TOKEN: AUTODESK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/autodesk/refs/heads/main/capabilities/autodesk-capability.yaml
tags:
- Autodesk
- API
tools:
- description: Autodesk List Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojects
- description: Autodesk Create Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Autodesk Get Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Autodesk Update Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproject
- description: Autodesk List Project Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectusers
- description: Autodesk Add Project User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addprojectuser
- description: Autodesk Update Project User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprojectuser
- description: Autodesk Remove Project User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeprojectuser
- description: Autodesk List Account Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountusers
- description: Autodesk List Companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanies
- description: Autodesk Create Company
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompany
- description: Autodesk List Industry Roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getindustryroles
---
