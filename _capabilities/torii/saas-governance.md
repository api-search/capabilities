---
categories: []
consumed_apis: []
description: Workflow capability for SaaS governance and IT management using Torii — covering shadow IT discovery, user lifecycle management, contract renewals, spend optimization, compliance auditing, and custom integration data sync.
layout: capability
name: Torii SaaS Governance
operations:
- description: List all apps discovered in the organization, including shadow IT.
  method: GET
  name: list-apps
  path: /v1/apps
- description: List all users and their app access.
  method: GET
  name: list-users
  path: /v1/users
- description: Get a specific SaaS contract with renewal details.
  method: GET
  name: get-contract
  path: /v1/contracts/{idContract}
- description: Update contract details including renewal date and cost.
  method: PUT
  name: update-contract
  path: /v1/contracts/{idContract}
- description: Retrieve admin audit log entries for compliance review.
  method: GET
  name: get-audit-logs
  path: /v1/audit
- description: Push user and license data from a custom app into Torii.
  method: POST
  name: sync-custom-integration
  path: /v1/integrations/sync
- description: List workflow action execution history.
  method: GET
  name: list-workflow-executions
  path: /v1/workflows/executions
- description: List provisioned users via SCIM 2.0.
  method: GET
  name: list-scim-users
  path: /v1/scim/users
- description: Provision a new user via SCIM 2.0.
  method: POST
  name: provision-user
  path: /v1/scim/users
personas: []
provider_name: Torii
provider_slug: torii
search_terms:
- retrieve available field metadata for saas applications in torii.
- provision scim user
- list apps
- sync custom integration
- push user and license data from a custom application into torii for visibility.
- list torii workflow automation execution history and status.
- provision a new user into torii via scim 2.0 protocol.
- deprovision (delete) a user from torii via scim 2.0.
- discover and manage saas applications.
- list all users in the organization with their saas app access details.
- torii
- sync custom app data
- users
- list all users and their app access.
- get contract metadata
- list provisioned users via scim 2.0.
- get contract
- update contract
- delete scim user
- it management
- provision user
- update a saas contract with new renewal date, status, or annual cost.
- get file upload url
- list scim users
- update contract details including renewal date and cost.
- retrieve admin audit log entries for compliance review.
- saas management
- compliance
- list workflow executions
- admin audit logs for compliance.
- list workflow action execution history.
- list all apps discovered in the organization, including shadow it.
- cost optimization
- saas contract management.
- apps
- retrieve available field metadata for contracts in torii.
- custom app data ingestion.
- push user and license data from a custom app into torii.
- retrieve available field metadata for users in torii.
- get full details of a saas contract including cost and renewal date.
- retrieve admin audit log entries for compliance review — up to 1,000 per request.
- user management and visibility.
- audit
- get app metadata
- list users provisioned via scim 2.0 in torii.
- get user metadata
- discover apps
- list users
- workflow automation history.
- discover all saas applications in use across the organization, including shadow it, managed apps, and closed apps.
- get audit logs
- governance
- get a secure temporary s3 url for uploading files to torii.
- scim 2.0 user provisioning.
- shadow it
- get a specific saas contract with renewal details.
- provision a new user via scim 2.0.
- contracts
slug: saas-governance
source_filename: saas-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Torii SaaS Governance\n  description: Workflow capability for SaaS governance and IT management using Torii — covering shadow IT discovery, user\n    lifecycle management, contract renewals, spend optimization, compliance auditing, and custom integration data sync.\n  tags:\n  - Apps\n  - Audit\n  - Compliance\n  - Contracts\n  - Cost Optimization\n  - Governance\n  - IT Management\n  - SaaS Management\n  - Shadow IT\n  - Torii\n  - Users\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TORII_API_KEY: TORII_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: torii-saas-management\n    baseUri: https://api.toriihq.com/v1.0\n    description: Torii SaaS Management Platform API for apps, users, contracts, and more.\n    authentication:\n      type: bearer\n      token: '{{TORII_API_KEY}}'\n    resources:\n    - name: apps\n      path: /apps\n      description: Manage applications discovered\
  \ and tracked in the organization.\n      operations:\n      - name: list-apps\n        method: GET\n        description: List all applications in the organization with optional filtering.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to include.\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by app state (discovered, managed, closed).\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-metadata\n      path: /apps/metadata\n      description:\
  \ Retrieve app field metadata.\n      operations:\n      - name: get-apps-metadata\n        method: GET\n        description: List app fields (predefined and custom).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Manage organization users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the organization.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to include.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: users-metadata\n      path: /users/metadata\n      description: Retrieve user field metadata.\n      operations:\n      - name: get-users-metadata\n        method: GET\n        description: List user fields (predefined and custom).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts\n      path: /contracts/{idContract}\n      description: Manage SaaS contracts and renewal information.\n      operations:\n      - name: get-contract\n        method: GET\n        description: Get details of a specific contract.\n        inputParameters:\n        - name: idContract\n          in: path\n          type: string\n          required: true\n          description: Contract unique identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: update-contract\n        method: PUT\n        description: Update an existing contract.\n        inputParameters:\n        - name: idContract\n          in: path\n          type: string\n          required: true\n          description: Contract unique identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            status: '{{tools.status}}'\n            renewalDate: '{{tools.renewalDate}}'\n            annualCost: '{{tools.annualCost}}'\n    - name: contracts-metadata\n      path: /contracts/metadata\n      description: Retrieve contract field metadata.\n      operations:\n      - name: get-contracts-metadata\n        method: GET\n        description: List contract fields (predefined and custom).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: audit\n      path: /audit\n      description: Retrieve admin audit log entries.\n      operations:\n      - name: get-audit-logs\n        method: GET\n        description: Retrieve up to 1,000 admin audit log entries per request.\n        inputParameters:\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Number of results (max 1000).\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-upload\n      path: /files/upload\n      description: Upload files to Torii (up to 3MB).\n      operations:\n      - name: upload-file\n        method: POST\n        description: Upload a small file (up to 3MB) as multipart form data.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: file-url\n      path: /files/url\n      description: Get a secure S3 upload URL for large files.\n      operations:\n      - name: get-file-upload-url\n        method: GET\n        description: Get a temporary S3 URL for uploading larger files.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-integration\n      path: /services/sync/custom\n      description: Sync custom integration data.\n      operations:\n      - name: sync-custom-integration\n        method: POST\n        description: Push user and license data from a custom integration into Torii.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            appName: '{{tools.appName}}'\n            users: '{{tools.users}}'\n\
  \            licenses: '{{tools.licenses}}'\n    - name: workflow-executions\n      path: /workflows/actionExecutions\n      description: Monitor workflow action executions.\n      operations:\n      - name: list-workflow-executions\n        method: GET\n        description: List workflow action execution history.\n        inputParameters:\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scim-users\n      path: /scim/v2/Users\n      description: SCIM 2.0 user provisioning.\n      operations:\n      - name: list-scim-users\n        method: GET\n        description: List users via SCIM 2.0 (up to 200 per page).\n        inputParameters:\n\
  \        - name: startIndex\n          in: query\n          type: integer\n          required: false\n          description: 1-based start index.\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 200).\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM filter expression.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-scim-user\n        method: POST\n        description: Create a new user via SCIM 2.0.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userName: '{{tools.userName}}'\n            name: '{{tools.name}}'\n            emails: '{{tools.emails}}'\n            active: '{{tools.active}}'\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: torii-saas-governance-api\n    description: Unified REST API for SaaS governance workflows — discovery, user management, contract tracking, and compliance.\n    resources:\n    - path: /v1/apps\n      name: apps\n      description: Discover and manage SaaS applications.\n      operations:\n      - method: GET\n        name: list-apps\n        description: List all apps discovered in the organization, including shadow IT.\n        call: torii-saas-management.list-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management and visibility.\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users and their app access.\n        call: torii-saas-management.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contracts/{idContract}\n      name:\
  \ contract\n      description: SaaS contract management.\n      operations:\n      - method: GET\n        name: get-contract\n        description: Get a specific SaaS contract with renewal details.\n        call: torii-saas-management.get-contract\n        with:\n          idContract: rest.idContract\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-contract\n        description: Update contract details including renewal date and cost.\n        call: torii-saas-management.update-contract\n        with:\n          idContract: rest.idContract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit\n      name: audit\n      description: Admin audit logs for compliance.\n      operations:\n      - method: GET\n        name: get-audit-logs\n        description: Retrieve admin audit log entries for compliance review.\n        call: torii-saas-management.get-audit-logs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/integrations/sync\n      name: custom-integration\n      description: Custom app data ingestion.\n      operations:\n      - method: POST\n        name: sync-custom-integration\n        description: Push user and license data from a custom app into Torii.\n        call: torii-saas-management.sync-custom-integration\n        with:\n          appName: rest.appName\n          users: rest.users\n          licenses: rest.licenses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/executions\n      name: workflow-executions\n      description: Workflow automation history.\n      operations:\n      - method: GET\n        name: list-workflow-executions\n        description: List workflow action execution history.\n        call: torii-saas-management.list-workflow-executions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scim/users\n     \
  \ name: scim-users\n      description: SCIM 2.0 user provisioning.\n      operations:\n      - method: GET\n        name: list-scim-users\n        description: List provisioned users via SCIM 2.0.\n        call: torii-saas-management.list-scim-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: provision-user\n        description: Provision a new user via SCIM 2.0.\n        call: torii-saas-management.create-scim-user\n        with:\n          userName: rest.userName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: torii-saas-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS governance and IT management using Torii.\n    tools:\n    - name: discover-apps\n      description: Discover all SaaS applications in use across the organization, including shadow IT, managed apps, and closed\n        apps.\n      hints:\n    \
  \    readOnly: true\n        idempotent: true\n      call: torii-saas-management.list-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app-metadata\n      description: Retrieve available field metadata for SaaS applications in Torii.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: torii-saas-management.get-apps-metadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the organization with their SaaS app access details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: torii-saas-management.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-metadata\n      description: Retrieve available field metadata for users in Torii.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: torii-saas-management.get-users-metadata\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-contract\n      description: Get full details of a SaaS contract including cost and renewal date.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: torii-saas-management.get-contract\n      with:\n        idContract: tools.idContract\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-contract\n      description: Update a SaaS contract with new renewal date, status, or annual cost.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: torii-saas-management.update-contract\n      with:\n        idContract: tools.idContract\n        renewalDate: tools.renewalDate\n        annualCost: tools.annualCost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contract-metadata\n      description: Retrieve available field metadata for contracts in Torii.\n      hints:\n        readOnly: true\n        idempotent: true\n\
  \      call: torii-saas-management.get-contracts-metadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-audit-logs\n      description: Retrieve admin audit log entries for compliance review — up to 1,000 per request.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: torii-saas-management.get-audit-logs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-custom-app-data\n      description: Push user and license data from a custom application into Torii for visibility.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: torii-saas-management.sync-custom-integration\n      with:\n        appName: tools.appName\n        users: tools.users\n        licenses: tools.licenses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflow-executions\n      description: List Torii workflow automation execution history and status.\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: torii-saas-management.list-workflow-executions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scim-users\n      description: List users provisioned via SCIM 2.0 in Torii.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: torii-saas-management.list-scim-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provision-scim-user\n      description: Provision a new user into Torii via SCIM 2.0 protocol.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: torii-saas-management.create-scim-user\n      with:\n        userName: tools.userName\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-scim-user\n      description: Deprovision (delete) a user from Torii via SCIM 2.0.\n      hints:\n        readOnly: false\n        destructive: true\n      \
  \  idempotent: true\n      call: torii-saas-management.delete-scim-user\n      with:\n        idUser: tools.idUser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-file-upload-url\n      description: Get a secure temporary S3 URL for uploading files to Torii.\n      hints:\n        readOnly: true\n        idempotent: false\n      call: torii-saas-management.get-file-upload-url\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/torii/refs/heads/main/capabilities/saas-governance.yaml
tags:
- Apps
- Audit
- Compliance
- Contracts
- Cost Optimization
- Governance
- IT Management
- SaaS Management
- Shadow IT
- Torii
- Users
tools:
- description: Discover all SaaS applications in use across the organization, including shadow IT, managed apps, and closed apps.
  hints:
    idempotent: true
    readOnly: true
  name: discover-apps
- description: Retrieve available field metadata for SaaS applications in Torii.
  hints:
    idempotent: true
    readOnly: true
  name: get-app-metadata
- description: List all users in the organization with their SaaS app access details.
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Retrieve available field metadata for users in Torii.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-metadata
- description: Get full details of a SaaS contract including cost and renewal date.
  hints:
    idempotent: true
    readOnly: true
  name: get-contract
- description: Update a SaaS contract with new renewal date, status, or annual cost.
  hints:
    idempotent: true
    readOnly: false
  name: update-contract
- description: Retrieve available field metadata for contracts in Torii.
  hints:
    idempotent: true
    readOnly: true
  name: get-contract-metadata
- description: Retrieve admin audit log entries for compliance review — up to 1,000 per request.
  hints:
    idempotent: true
    readOnly: true
  name: get-audit-logs
- description: Push user and license data from a custom application into Torii for visibility.
  hints:
    idempotent: false
    readOnly: false
  name: sync-custom-app-data
- description: List Torii workflow automation execution history and status.
  hints:
    idempotent: true
    readOnly: true
  name: list-workflow-executions
- description: List users provisioned via SCIM 2.0 in Torii.
  hints:
    idempotent: true
    readOnly: true
  name: list-scim-users
- description: Provision a new user into Torii via SCIM 2.0 protocol.
  hints:
    idempotent: false
    readOnly: false
  name: provision-scim-user
- description: Deprovision (delete) a user from Torii via SCIM 2.0.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-scim-user
- description: Get a secure temporary S3 URL for uploading files to Torii.
  hints:
    idempotent: false
    readOnly: true
  name: get-file-upload-url
---
