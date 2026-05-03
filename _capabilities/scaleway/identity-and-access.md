---
categories: []
consumed_apis:
- scaleway-iam
- scaleway-secrets
description: Unified workflow capability for managing Scaleway identity and access management, combining IAM policies, API keys, users, groups, applications, and secret storage. Used by platform administrators and security teams to control access to Scaleway resources and manage credentials securely.
layout: capability
name: Scaleway Identity and Access
operations:
- description: List IAM API keys
  method: GET
  name: list-api-keys
  path: /v1/api-keys
- description: Create an IAM API key
  method: POST
  name: create-api-key
  path: /v1/api-keys
- description: Get API key details
  method: GET
  name: get-api-key
  path: /v1/api-keys/{access_key}
- description: Delete an API key
  method: DELETE
  name: delete-api-key
  path: /v1/api-keys/{access_key}
- description: List IAM users
  method: GET
  name: list-users
  path: /v1/users
- description: List IAM groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create an IAM group
  method: POST
  name: create-group
  path: /v1/groups
- description: List IAM policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create an IAM policy
  method: POST
  name: create-policy
  path: /v1/policies
- description: List secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Create a secret
  method: POST
  name: create-secret
  path: /v1/secrets
- description: Get secret details
  method: GET
  name: get-secret
  path: /v1/secrets/{id}
- description: Delete a secret
  method: DELETE
  name: delete-secret
  path: /v1/secrets/{id}
personas: []
provider_name: Scaleway
provider_slug: scaleway
search_terms:
- list policies
- list api keys
- security
- storage
- access control
- create secret
- european cloud
- list iam groups
- policies
- create an iam policy
- delete an iam api key
- list scaleway iam api keys
- access policy management
- delete a secret from secret manager
- create group
- list iam policies
- delete a secret
- kubernetes
- group management
- get secret details
- list secrets
- get api key details
- secret management
- create an iam api key
- list users
- create policy
- api key management
- create api key
- delete an api key
- create a secret
- user management
- identity
- manage a specific secret
- list secrets in secret manager
- database
- containers
- get api key
- list iam users
- get secret
- list iam api keys
- list iam users in the organization
- create a new secret in secret manager
- delete api key
- scaleway
- ai
- iam
- list groups
- manage a specific api key
- get a secret from secret manager
- create an iam group
- permissions
- serverless
- delete secret
- infrastructure
- cloud computing
- api keys
- create a new iam api key
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Scaleway Identity and Access\"\n  description: >-\n    Unified workflow capability for managing Scaleway identity and access management,\n    combining IAM policies, API keys, users, groups, applications, and secret storage.\n    Used by platform administrators and security teams to control access to Scaleway\n    resources and manage credentials securely.\n  tags:\n    - Access Control\n    - API Keys\n    - IAM\n    - Identity\n    - Permissions\n    - Policies\n    - Scaleway\n    - Security\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCALEWAY_API_KEY: SCALEWAY_API_KEY\n\ncapability:\n  consumes:\n    - import: scaleway-iam\n      location: ./shared/iam.yaml\n    - import: scaleway-secrets\n      location: ./shared/secret-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: scaleway-identity-api\n      description: \"Unified REST API for Scaleway\
  \ identity, access management, and secret storage.\"\n      resources:\n        - path: /v1/api-keys\n          name: api-keys\n          description: \"API key management\"\n          operations:\n            - method: GET\n              name: list-api-keys\n              description: \"List IAM API keys\"\n              call: \"scaleway-iam.list-api-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-key\n              description: \"Create an IAM API key\"\n              call: \"scaleway-iam.create-api-key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-keys/{access_key}\n          name: api-key\n          description: \"Manage a specific API key\"\n          operations:\n            - method: GET\n              name: get-api-key\n              description: \"Get API key details\"\n         \
  \     call: \"scaleway-iam.get-api-key\"\n              with:\n                access_key: \"rest.access_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-api-key\n              description: \"Delete an API key\"\n              call: \"scaleway-iam.delete-api-key\"\n              with:\n                access_key: \"rest.access_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List IAM users\"\n              call: \"scaleway-iam.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"\
  Group management\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List IAM groups\"\n              call: \"scaleway-iam.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create an IAM group\"\n              call: \"scaleway-iam.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: \"Access policy management\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List IAM policies\"\n              call: \"scaleway-iam.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n         \
  \     name: create-policy\n              description: \"Create an IAM policy\"\n              call: \"scaleway-iam.create-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name: secrets\n          description: \"Secret management\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List secrets\"\n              call: \"scaleway-secrets.list-secrets\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-secret\n              description: \"Create a secret\"\n              call: \"scaleway-secrets.create-secret\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n        - path: /v1/secrets/{id}\n          name: secret\n          description: \"Manage a specific secret\"\n          operations:\n            - method: GET\n              name: get-secret\n              description: \"Get secret details\"\n              call: \"scaleway-secrets.get-secret\"\n              with:\n                region: \"rest.region\"\n                secret_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-secret\n              description: \"Delete a secret\"\n              call: \"scaleway-secrets.delete-secret\"\n              with:\n                region: \"rest.region\"\n                secret_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: scaleway-identity-mcp\n      transport: http\n      description: \"MCP\
  \ server for AI-assisted Scaleway identity, access, and secrets management.\"\n      tools:\n        - name: list-api-keys\n          description: \"List Scaleway IAM API keys\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-iam.list-api-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-key\n          description: \"Create a new IAM API key\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-iam.create-api-key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-api-key\n          description: \"Delete an IAM API key\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-iam.delete-api-key\"\n          with:\n            access_key:\
  \ \"tools.access_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List IAM users in the organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-iam.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List IAM groups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-iam.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-policies\n          description: \"List IAM policies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-iam.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-secrets\n\
  \          description: \"List secrets in Secret Manager\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-secrets.list-secrets\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-secret\n          description: \"Create a new secret in Secret Manager\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-secrets.create-secret\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-secret\n          description: \"Get a secret from Secret Manager\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-secrets.get-secret\"\n          with:\n            region: \"tools.region\"\n\
  \            secret_id: \"tools.secret_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-secret\n          description: \"Delete a secret from Secret Manager\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-secrets.delete-secret\"\n          with:\n            region: \"tools.region\"\n            secret_id: \"tools.secret_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scaleway/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Access Control
- API Keys
- IAM
- Identity
- Permissions
- Policies
- Scaleway
- Security
tools:
- description: List Scaleway IAM API keys
  hints:
    openWorld: true
    readOnly: true
  name: list-api-keys
- description: Create a new IAM API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-key
- description: Delete an IAM API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-key
- description: List IAM users in the organization
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: List IAM groups
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: List IAM policies
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: List secrets in Secret Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-secrets
- description: Create a new secret in Secret Manager
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-secret
- description: Get a secret from Secret Manager
  hints:
    openWorld: false
    readOnly: true
  name: get-secret
- description: Delete a secret from Secret Manager
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-secret
---
