---
categories: []
consumed_apis:
- beyondtrust
description: Unified privileged access management workflow combining Password Safe credential management, access request workflows, and secrets management. Used by security engineers and DevOps teams to manage just-in-time privileged access and secrets retrieval for automated pipelines.
layout: capability
name: BeyondTrust Privileged Access Management
operations:
- description: List managed accounts
  method: GET
  name: list-managed-accounts
  path: /v1/managed-accounts
- description: List managed systems
  method: GET
  name: list-managed-systems
  path: /v1/managed-systems
- description: List access requests
  method: GET
  name: list-requests
  path: /v1/requests
- description: Create an access request
  method: POST
  name: create-request
  path: /v1/requests
- description: Get credentials for approved request
  method: GET
  name: get-request-credentials
  path: /v1/requests/{requestId}/credentials
- description: List secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Create a new secret
  method: POST
  name: create-secret
  path: /v1/secrets
- description: Get a secret value
  method: GET
  name: get-secret
  path: /v1/secrets/{id}
- description: Delete a secret
  method: DELETE
  name: delete-secret
  path: /v1/secrets/{id}
personas:
- description: Security team member managing privileged access policies and requests
  id: security-engineer
  name: Security Engineer
- description: DevOps engineer retrieving secrets and credentials for CI/CD pipelines
  id: devops-engineer
  name: DevOps Engineer
provider_name: BeyondTrust
provider_slug: beyondtrust
search_terms:
- create request
- get a secret value
- cancel and delete an access request
- zero trust
- privileged account discovery
- security
- credential retrieval for approved requests
- delete secret
- secure storage and retrieval of secrets and credentials
- create secret
- get request credentials
- list secrets stored in beyondtrust secrets safe
- secrets
- security team member managing privileged access policies and requests
- privileged access
- privileged access management
- credentials
- delete a secret
- just in time access
- list privileged accounts available for just-in-time access
- list systems registered in password safe
- secrets management
- individual secret operations
- beyondtrust
- list secrets
- managed system discovery
- access management
- delete request
- list managed systems
- create an access request
- get secret
- list managed accounts
- store a new secret in secrets safe
- just-in-time access to privileged accounts on managed systems
- devops engineer retrieving secrets and credentials for ci/cd pipelines
- retrieve credentials for an approved privileged access request
- access
- list access requests
- create a new secret
- compliance
- list requests
- create a just-in-time access request for a privileged account
- list all active privileged access requests
- security engineer
- devops engineer
- access request management
- get credentials for approved request
- retrieve a specific secret value from secrets safe
slug: privileged-access-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: BeyondTrust Privileged Access Management\n  description: >-\n    Unified privileged access management workflow combining Password Safe\n    credential management, access request workflows, and secrets management.\n    Used by security engineers and DevOps teams to manage just-in-time\n    privileged access and secrets retrieval for automated pipelines.\n  tags:\n    - BeyondTrust\n    - Privileged Access Management\n    - Zero Trust\n    - Secrets Management\n    - Just In Time Access\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BEYONDTRUST_HOST: BEYONDTRUST_HOST\n      BEYONDTRUST_APP_ID: BEYONDTRUST_APP_ID\n      BEYONDTRUST_API_KEY: BEYONDTRUST_API_KEY\n\ncapability:\n  consumes:\n    - import: beyondtrust\n      location: ./shared/beyondtrust.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: beyondtrust-pam-api\n      description: Unified REST API\
  \ for BeyondTrust privileged access management.\n      resources:\n        - path: /v1/managed-accounts\n          name: managed-accounts\n          description: Privileged account discovery\n          operations:\n            - method: GET\n              name: list-managed-accounts\n              description: List managed accounts\n              call: \"beyondtrust.list-managed-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/managed-systems\n          name: managed-systems\n          description: Managed system discovery\n          operations:\n            - method: GET\n              name: list-managed-systems\n              description: List managed systems\n              call: \"beyondtrust.list-managed-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requests\n          name: requests\n          description: Access request\
  \ management\n          operations:\n            - method: GET\n              name: list-requests\n              description: List access requests\n              call: \"beyondtrust.list-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-request\n              description: Create an access request\n              call: \"beyondtrust.create-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requests/{requestId}/credentials\n          name: request-credentials\n          description: Credential retrieval for approved requests\n          operations:\n            - method: GET\n              name: get-request-credentials\n              description: Get credentials for approved request\n              call: \"beyondtrust.get-request-credentials\"\n              with:\n                requestId: \"rest.requestId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name: secrets\n          description: Secrets management\n          operations:\n            - method: GET\n              name: list-secrets\n              description: List secrets\n              call: \"beyondtrust.list-secrets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-secret\n              description: Create a new secret\n              call: \"beyondtrust.create-secret\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets/{id}\n          name: secret\n          description: Individual secret operations\n          operations:\n            - method: GET\n              name: get-secret\n              description: Get a secret value\n              call: \"beyondtrust.get-secret\"\
  \n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-secret\n              description: Delete a secret\n              call: \"beyondtrust.delete-secret\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: beyondtrust-pam-mcp\n      transport: http\n      description: MCP server for AI-assisted BeyondTrust PAM and secrets management.\n      tools:\n        - name: list-managed-accounts\n          description: List privileged accounts available for just-in-time access\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"beyondtrust.list-managed-accounts\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-managed-systems\n          description: List systems registered in Password Safe\n          hints:\n            readOnly: true\n          call: \"beyondtrust.list-managed-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-requests\n          description: List all active privileged access requests\n          hints:\n            readOnly: true\n          call: \"beyondtrust.list-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-request\n          description: Create a just-in-time access request for a privileged account\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"beyondtrust.create-request\"\n          with:\n            system_id: \"tools.system_id\"\n            account_id: \"tools.account_id\"\n            duration_minutes: \"tools.duration_minutes\"\
  \n            reason: \"tools.reason\"\n            access_type: \"tools.access_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-request-credentials\n          description: Retrieve credentials for an approved privileged access request\n          hints:\n            readOnly: true\n          call: \"beyondtrust.get-request-credentials\"\n          with:\n            requestId: \"tools.request_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-secrets\n          description: List secrets stored in BeyondTrust Secrets Safe\n          hints:\n            readOnly: true\n          call: \"beyondtrust.list-secrets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-secret\n          description: Retrieve a specific secret value from Secrets Safe\n          hints:\n            readOnly: true\n          call:\
  \ \"beyondtrust.get-secret\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-secret\n          description: Store a new secret in Secrets Safe\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"beyondtrust.create-secret\"\n          with:\n            title: \"tools.title\"\n            type: \"tools.type\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-request\n          description: Cancel and delete an access request\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"beyondtrust.delete-request\"\n          with:\n            requestId: \"tools.request_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/beyondtrust/refs/heads/main/capabilities/privileged-access-management.yaml
tags:
- BeyondTrust
- Privileged Access Management
- Zero Trust
- Secrets Management
- Just In Time Access
tools:
- description: List privileged accounts available for just-in-time access
  hints:
    openWorld: true
    readOnly: true
  name: list-managed-accounts
- description: List systems registered in Password Safe
  hints:
    readOnly: true
  name: list-managed-systems
- description: List all active privileged access requests
  hints:
    readOnly: true
  name: list-requests
- description: Create a just-in-time access request for a privileged account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-request
- description: Retrieve credentials for an approved privileged access request
  hints:
    readOnly: true
  name: get-request-credentials
- description: List secrets stored in BeyondTrust Secrets Safe
  hints:
    readOnly: true
  name: list-secrets
- description: Retrieve a specific secret value from Secrets Safe
  hints:
    readOnly: true
  name: get-secret
- description: Store a new secret in Secrets Safe
  hints:
    destructive: false
    readOnly: false
  name: create-secret
- description: Cancel and delete an access request
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-request
---
