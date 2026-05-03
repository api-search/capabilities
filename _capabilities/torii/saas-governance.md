---
categories: []
consumed_apis:
- torii-saas-management
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
- audit
- list apps
- cost optimization
- users
- it management
- update a saas contract with new renewal date, status, or annual cost.
- provision scim user
- list scim users
- update contract details including renewal date and cost.
- list users provisioned via scim 2.0 in torii.
- apps
- retrieve available field metadata for contracts in torii.
- sync custom app data
- contracts
- saas management
- get file upload url
- retrieve available field metadata for saas applications in torii.
- retrieve available field metadata for users in torii.
- discover and manage saas applications.
- provision a new user via scim 2.0.
- torii
- get app metadata
- provision a new user into torii via scim 2.0 protocol.
- workflow automation history.
- user management and visibility.
- get full details of a saas contract including cost and renewal date.
- admin audit logs for compliance.
- discover all saas applications in use across the organization, including shadow it, managed apps, and closed apps.
- list all users and their app access.
- get user metadata
- list workflow action execution history.
- deprovision (delete) a user from torii via scim 2.0.
- get a specific saas contract with renewal details.
- discover apps
- list all users in the organization with their saas app access details.
- list torii workflow automation execution history and status.
- list users
- get contract
- get contract metadata
- compliance
- retrieve admin audit log entries for compliance review — up to 1,000 per request.
- delete scim user
- retrieve admin audit log entries for compliance review.
- sync custom integration
- get a secure temporary s3 url for uploading files to torii.
- governance
- list provisioned users via scim 2.0.
- provision user
- get audit logs
- list all apps discovered in the organization, including shadow it.
- scim 2.0 user provisioning.
- list workflow executions
- update contract
- saas contract management.
- shadow it
- push user and license data from a custom app into torii.
- custom app data ingestion.
- push user and license data from a custom application into torii for visibility.
slug: saas-governance
source_filename: saas-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Torii SaaS Governance\"\n  description: \"Workflow capability for SaaS governance and IT management using Torii — covering shadow IT discovery, user lifecycle management, contract renewals, spend optimization, compliance auditing, and custom integration data sync.\"\n  tags:\n    - Apps\n    - Audit\n    - Compliance\n    - Contracts\n    - Cost Optimization\n    - Governance\n    - IT Management\n    - SaaS Management\n    - Shadow IT\n    - Torii\n    - Users\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TORII_API_KEY: TORII_API_KEY\n\ncapability:\n  consumes:\n    - import: torii-saas-management\n      location: ./shared/torii-saas-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: torii-saas-governance-api\n      description: \"Unified REST API for SaaS governance workflows — discovery, user management, contract tracking, and compliance.\"\
  \n      resources:\n        - path: /v1/apps\n          name: apps\n          description: \"Discover and manage SaaS applications.\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"List all apps discovered in the organization, including shadow IT.\"\n              call: \"torii-saas-management.list-apps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"User management and visibility.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users and their app access.\"\n              call: \"torii-saas-management.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contracts/{idContract}\n          name: contract\n          description: \"SaaS contract\
  \ management.\"\n          operations:\n            - method: GET\n              name: get-contract\n              description: \"Get a specific SaaS contract with renewal details.\"\n              call: \"torii-saas-management.get-contract\"\n              with:\n                idContract: \"rest.idContract\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-contract\n              description: \"Update contract details including renewal date and cost.\"\n              call: \"torii-saas-management.update-contract\"\n              with:\n                idContract: \"rest.idContract\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audit\n          name: audit\n          description: \"Admin audit logs for compliance.\"\n          operations:\n            - method: GET\n              name: get-audit-logs\n\
  \              description: \"Retrieve admin audit log entries for compliance review.\"\n              call: \"torii-saas-management.get-audit-logs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integrations/sync\n          name: custom-integration\n          description: \"Custom app data ingestion.\"\n          operations:\n            - method: POST\n              name: sync-custom-integration\n              description: \"Push user and license data from a custom app into Torii.\"\n              call: \"torii-saas-management.sync-custom-integration\"\n              with:\n                appName: \"rest.appName\"\n                users: \"rest.users\"\n                licenses: \"rest.licenses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/executions\n          name: workflow-executions\n          description: \"Workflow\
  \ automation history.\"\n          operations:\n            - method: GET\n              name: list-workflow-executions\n              description: \"List workflow action execution history.\"\n              call: \"torii-saas-management.list-workflow-executions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scim/users\n          name: scim-users\n          description: \"SCIM 2.0 user provisioning.\"\n          operations:\n            - method: GET\n              name: list-scim-users\n              description: \"List provisioned users via SCIM 2.0.\"\n              call: \"torii-saas-management.list-scim-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: provision-user\n              description: \"Provision a new user via SCIM 2.0.\"\n              call: \"torii-saas-management.create-scim-user\"\n  \
  \            with:\n                userName: \"rest.userName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: torii-saas-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SaaS governance and IT management using Torii.\"\n      tools:\n        - name: discover-apps\n          description: \"Discover all SaaS applications in use across the organization, including shadow IT, managed apps, and closed apps.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.list-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-app-metadata\n          description: \"Retrieve available field metadata for SaaS applications in Torii.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.get-apps-metadata\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all users in the organization with their SaaS app access details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user-metadata\n          description: \"Retrieve available field metadata for users in Torii.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.get-users-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contract\n          description: \"Get full details of a SaaS contract including cost and renewal date.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"\
  torii-saas-management.get-contract\"\n          with:\n            idContract: \"tools.idContract\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-contract\n          description: \"Update a SaaS contract with new renewal date, status, or annual cost.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"torii-saas-management.update-contract\"\n          with:\n            idContract: \"tools.idContract\"\n            renewalDate: \"tools.renewalDate\"\n            annualCost: \"tools.annualCost\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contract-metadata\n          description: \"Retrieve available field metadata for contracts in Torii.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.get-contracts-metadata\"\n          outputParameters:\n  \
  \          - type: object\n              mapping: \"$.\"\n        - name: get-audit-logs\n          description: \"Retrieve admin audit log entries for compliance review — up to 1,000 per request.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.get-audit-logs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sync-custom-app-data\n          description: \"Push user and license data from a custom application into Torii for visibility.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"torii-saas-management.sync-custom-integration\"\n          with:\n            appName: \"tools.appName\"\n            users: \"tools.users\"\n            licenses: \"tools.licenses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflow-executions\n          description:\
  \ \"List Torii workflow automation execution history and status.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.list-workflow-executions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-scim-users\n          description: \"List users provisioned via SCIM 2.0 in Torii.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"torii-saas-management.list-scim-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: provision-scim-user\n          description: \"Provision a new user into Torii via SCIM 2.0 protocol.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"torii-saas-management.create-scim-user\"\n          with:\n            userName: \"tools.userName\"\n            name: \"tools.name\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: delete-scim-user\n          description: \"Deprovision (delete) a user from Torii via SCIM 2.0.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"torii-saas-management.delete-scim-user\"\n          with:\n            idUser: \"tools.idUser\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-upload-url\n          description: \"Get a secure temporary S3 URL for uploading files to Torii.\"\n          hints:\n            readOnly: true\n            idempotent: false\n          call: \"torii-saas-management.get-file-upload-url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
