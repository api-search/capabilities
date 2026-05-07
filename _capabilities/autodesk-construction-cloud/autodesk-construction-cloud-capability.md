---
categories: []
consumed_apis: []
description: The Autodesk Construction Cloud (ACC) Admin API provides programmatic management of ACC accounts, projects, users, and company settings. REST APIs enable automation of project provisioning, user access control, and account-level administration across ACC and BIM 360 deployments.
layout: capability
name: Autodesk Construction Cloud Admin API
operations:
- description: Get account projects
  method: GET
  name: getaccountprojects
  path: /construction/admin/v1/accounts/{accountId}/projects
- description: Create a new project
  method: POST
  name: createproject
  path: /construction/admin/v1/accounts/{accountId}/projects
- description: Get project by ID
  method: GET
  name: getproject
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}
- description: Update project
  method: PATCH
  name: updateproject
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}
- description: Get project users
  method: GET
  name: getprojectusers
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users
- description: Add user to project
  method: POST
  name: addprojectuser
  path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users
- description: Get account users
  method: GET
  name: getaccountusers
  path: /construction/admin/v1/accounts/{accountId}/users
- description: Get account companies
  method: GET
  name: getaccountcompanies
  path: /construction/admin/v1/accounts/{accountId}/companies
personas: []
provider_name: Autodesk Construction Cloud
provider_slug: autodesk-construction-cloud
search_terms:
- engineering
- get project by id
- getproject
- addprojectuser
- api
- autodesk
- construction
- get account companies
- project management
- getaccountusers
- get account projects
- architecture
- field management
- updateproject
- add user to project
- create a new project
- getprojectusers
- get project users
- cloud
- cad
- getaccountprojects
- aec
- get account users
- bim
- update project
- getaccountcompanies
- createproject
slug: autodesk-construction-cloud-capability
source_filename: autodesk-construction-cloud-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Autodesk Construction Cloud Admin API\n  description: The Autodesk Construction Cloud (ACC) Admin API provides programmatic management of ACC accounts, projects,\n    users, and company settings. REST APIs enable automation of project provisioning, user access control, and account-level\n    administration across ACC and BIM 360 deployments.\n  tags:\n  - Autodesk\n  - Construction\n  - Cloud\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: autodesk-construction-cloud\n    baseUri: https://developer.api.autodesk.com\n    description: Autodesk Construction Cloud Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{AUTODESK_CONSTRUCTION_CLOUD_TOKEN}}'\n    resources:\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects\n      operations:\n      - name: getaccountprojects\n\
  \        method: GET\n        description: Get account projects\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the ACC account\n        - name: filter[status]\n          in: query\n          type: string\n          description: Filter by project status\n        - name: filter[name]\n          in: query\n          type: string\n          description: Filter projects by name (partial match)\n        - name: include\n          in: query\n          type: string\n          description: Include related resources\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a new project\n \
  \       inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get project by ID\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PATCH\n        description: Update project\n        inputParameters:\n        - name: accountId\n          in: path\n\
  \          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-project\n      path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users\n      operations:\n      - name: getprojectusers\n        method: GET\n        description: Get project users\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: addprojectuser\n        method: POST\n        description: Add user to project\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-users\n      path: /construction/admin/v1/accounts/{accountId}/users\n      operations:\n      - name: getaccountusers\n        method: GET\n        description: Get account users\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: filter[status]\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in:\
  \ query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: construction-admin-v1-accounts-accountid-compani\n      path: /construction/admin/v1/accounts/{accountId}/companies\n      operations:\n      - name: getaccountcompanies\n        method: GET\n        description: Get account companies\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: autodesk-construction-cloud-rest\n    description: REST adapter for Autodesk Construction Cloud Admin API.\n    resources:\n    - path: /construction/admin/v1/accounts/{accountId}/projects\n      name: getaccountprojects\n      operations:\n      - method: GET\n        name: getaccountprojects\n\
  \        description: Get account projects\n        call: autodesk-construction-cloud.getaccountprojects\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create a new project\n        call: autodesk-construction-cloud.createproject\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get project by ID\n        call: autodesk-construction-cloud.getproject\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}\n      name: updateproject\n      operations:\n      - method: PATCH\n        name: updateproject\n        description: Update project\n        call: autodesk-construction-cloud.updateproject\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users\n      name: getprojectusers\n      operations:\n      - method: GET\n        name: getprojectusers\n        description: Get project users\n        call: autodesk-construction-cloud.getprojectusers\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/projects/{projectId}/users\n\
  \      name: addprojectuser\n      operations:\n      - method: POST\n        name: addprojectuser\n        description: Add user to project\n        call: autodesk-construction-cloud.addprojectuser\n        with:\n          accountId: rest.accountId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/users\n      name: getaccountusers\n      operations:\n      - method: GET\n        name: getaccountusers\n        description: Get account users\n        call: autodesk-construction-cloud.getaccountusers\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /construction/admin/v1/accounts/{accountId}/companies\n      name: getaccountcompanies\n      operations:\n      - method: GET\n        name: getaccountcompanies\n        description: Get account companies\n        call: autodesk-construction-cloud.getaccountcompanies\n\
  \        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: autodesk-construction-cloud-mcp\n    transport: http\n    description: MCP adapter for Autodesk Construction Cloud Admin API for AI agent use.\n    tools:\n    - name: getaccountprojects\n      description: Get account projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk-construction-cloud.getaccountprojects\n      with:\n        accountId: tools.accountId\n        filter[status]: tools.filter[status]\n        filter[name]: tools.filter[name]\n        include: tools.include\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: The unique identifier of the ACC account\n        required: true\n      - name: filter[status]\n        type: string\n        description:\
  \ Filter by project status\n      - name: filter[name]\n        type: string\n        description: Filter projects by name (partial match)\n      - name: include\n        type: string\n        description: Include related resources\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Create a new project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: autodesk-construction-cloud.createproject\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get project by ID\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: autodesk-construction-cloud.getproject\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Update project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: autodesk-construction-cloud.updateproject\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprojectusers\n      description: Get project users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk-construction-cloud.getprojectusers\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addprojectuser\n      description: Add user to project\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: autodesk-construction-cloud.addprojectuser\n      with:\n        accountId: tools.accountId\n        projectId: tools.projectId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountusers\n      description: Get account users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk-construction-cloud.getaccountusers\n      with:\n        accountId: tools.accountId\n        filter[status]: tools.filter[status]\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name:\
  \ filter[status]\n        type: string\n        description: filter[status]\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountcompanies\n      description: Get account companies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: autodesk-construction-cloud.getaccountcompanies\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AUTODESK_CONSTRUCTION_CLOUD_TOKEN: AUTODESK_CONSTRUCTION_CLOUD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/autodesk-construction-cloud/refs/heads/main/capabilities/autodesk-construction-cloud-capability.yaml
tags:
- Autodesk
- Construction
- Cloud
- API
tools:
- description: Get account projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountprojects
- description: Create a new project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get project by ID
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
- description: Get project users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectusers
- description: Add user to project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addprojectuser
- description: Get account users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountusers
- description: Get account companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountcompanies
---
