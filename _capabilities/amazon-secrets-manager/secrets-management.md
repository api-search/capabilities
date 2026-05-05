---
api_specs:
- filename: amazon-secrets-manager-openapi.yml
  format: yaml
  label: amazon-secrets-manager
  slug: amazon-secrets-manager
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-secrets-manager/refs/heads/main/openapi/amazon-secrets-manager-openapi.yml
categories:
- security
consumed_apis:
- amazon-secrets-manager
description: Unified capability for managing application secrets lifecycle including creation, retrieval, rotation, and deletion. Used by DevOps Engineers and Application Developers.
layout: capability
name: Amazon Secrets Manager Secrets Management
operations:
- description: List all managed secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Create and store a new secret
  method: POST
  name: create-secret
  path: /v1/secrets
- description: Get metadata for a secret
  method: GET
  name: describe-secret
  path: /v1/secrets/{name}
- description: Retrieve the current value of a secret
  method: GET
  name: get-secret-value
  path: /v1/secrets/{name}/value
- description: Update the value of a secret
  method: PUT
  name: put-secret-value
  path: /v1/secrets/{name}/value
- description: Trigger rotation for a secret
  method: POST
  name: rotate-secret
  path: /v1/secrets/{name}/rotate
- description: Generate a cryptographically secure random password
  method: POST
  name: get-random-password
  path: /v1/passwords/random
personas: []
provider_name: Amazon Secrets Manager
provider_slug: amazon-secrets-manager
search_terms:
- get random password
- list secrets
- engineers who manage application infrastructure and configure secrets rotation and access policies
- amazon secrets manager
- list all managed secrets
- describe secret
- security
- put secret value
- restore secret
- create secret
- secure storage and access control for sensitive credentials and configuration
- generate a cryptographically secure random password
- schedule a secret for deletion
- secret rotation management
- delete secret
- retrieve the plaintext value of a secret
- get metadata and configuration details of a secret
- individual secret management
- get secret value
- rotation
- trigger automatic rotation for a secret
- DevOps Engineer
- cancel scheduled deletion and restore a secret
- end-to-end secrets lifecycle management including creation, retrieval, rotation, and deletion
- update the value stored in a secret
- devops
- retrieve the current value of a secret
- credentials
- lifecycle management of secrets including rotation, versioning, and audit
- secret value retrieval and update
- create a new secret in amazon secrets manager
- configuration
- trigger rotation for a secret
- create and store a new secret
- list all secrets stored in amazon secrets manager
- Application Developer
- secret lifecycle management
- secrets
- get metadata for a secret
- update the value of a secret
- random password generation
- developers who integrate applications with secrets manager to retrieve credentials at runtime
- rotate secret
slug: secrets-management
source_filename: secrets-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Secrets Manager Secrets Management\"\n  description: \"Unified capability for managing application secrets lifecycle including creation, retrieval, rotation, and deletion. Used by DevOps Engineers and Application Developers.\"\n  tags:\n    - Amazon Secrets Manager\n    - Security\n    - Secrets\n    - DevOps\n    - Credentials\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-secrets-manager\n      location: ./shared/amazon-secrets-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: secrets-management-api\n      description: \"Unified REST API for Amazon Secrets Manager secrets lifecycle management.\"\n      resources:\n        - path: /v1/secrets\n          name: secrets\n\
  \          description: \"Secret lifecycle management\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List all managed secrets\"\n              call: \"amazon-secrets-manager.list-secrets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-secret\n              description: \"Create and store a new secret\"\n              call: \"amazon-secrets-manager.create-secret\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets/{name}\n          name: secret\n          description: \"Individual secret management\"\n          operations:\n            - method: GET\n              name: describe-secret\n              description: \"Get metadata for a secret\"\n              call: \"amazon-secrets-manager.describe-secret\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets/{name}/value\n          name: secret-value\n          description: \"Secret value retrieval and update\"\n          operations:\n            - method: GET\n              name: get-secret-value\n              description: \"Retrieve the current value of a secret\"\n              call: \"amazon-secrets-manager.get-secret-value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: put-secret-value\n              description: \"Update the value of a secret\"\n              call: \"amazon-secrets-manager.put-secret-value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets/{name}/rotate\n          name: secret-rotation\n          description: \"Secret rotation management\"\n          operations:\n            - method: POST\n\
  \              name: rotate-secret\n              description: \"Trigger rotation for a secret\"\n              call: \"amazon-secrets-manager.rotate-secret\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/passwords/random\n          name: random-password\n          description: \"Random password generation\"\n          operations:\n            - method: POST\n              name: get-random-password\n              description: \"Generate a cryptographically secure random password\"\n              call: \"amazon-secrets-manager.get-random-password\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: secrets-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Secrets Manager secrets lifecycle management.\"\n      tools:\n        - name: list-secrets\n          description:\
  \ \"List all secrets stored in Amazon Secrets Manager\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-secrets-manager.list-secrets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-secret\n          description: \"Create a new secret in Amazon Secrets Manager\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-secrets-manager.create-secret\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-secret-value\n          description: \"Retrieve the plaintext value of a secret\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-secrets-manager.get-secret-value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-secret-value\n          description: \"Update\
  \ the value stored in a secret\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-secrets-manager.put-secret-value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-secret\n          description: \"Get metadata and configuration details of a secret\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-secrets-manager.describe-secret\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rotate-secret\n          description: \"Trigger automatic rotation for a secret\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-secrets-manager.rotate-secret\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-secret\n          description: \"Schedule a secret for deletion\"\
  \n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"amazon-secrets-manager.delete-secret\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restore-secret\n          description: \"Cancel scheduled deletion and restore a secret\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"amazon-secrets-manager.restore-secret\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-random-password\n          description: \"Generate a cryptographically secure random password\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-secrets-manager.get-random-password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-secrets-manager/refs/heads/main/capabilities/secrets-management.yaml
tags:
- Amazon Secrets Manager
- Security
- Secrets
- DevOps
- Credentials
tools:
- description: List all secrets stored in Amazon Secrets Manager
  hints:
    idempotent: true
    readOnly: true
  name: list-secrets
- description: Create a new secret in Amazon Secrets Manager
  hints:
    idempotent: false
    readOnly: false
  name: create-secret
- description: Retrieve the plaintext value of a secret
  hints:
    idempotent: true
    readOnly: true
  name: get-secret-value
- description: Update the value stored in a secret
  hints:
    idempotent: false
    readOnly: false
  name: put-secret-value
- description: Get metadata and configuration details of a secret
  hints:
    idempotent: true
    readOnly: true
  name: describe-secret
- description: Trigger automatic rotation for a secret
  hints:
    idempotent: false
    readOnly: false
  name: rotate-secret
- description: Schedule a secret for deletion
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-secret
- description: Cancel scheduled deletion and restore a secret
  hints:
    idempotent: true
    readOnly: false
  name: restore-secret
- description: Generate a cryptographically secure random password
  hints:
    idempotent: false
    readOnly: false
  name: get-random-password
---
