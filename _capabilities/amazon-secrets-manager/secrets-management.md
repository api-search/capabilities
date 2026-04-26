---
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
- restore secret
- end-to-end secrets lifecycle management including creation, retrieval, rotation, and deletion
- schedule a secret for deletion
- list all managed secrets
- list all secrets stored in amazon secrets manager
- secret rotation management
- secret value retrieval and update
- retrieve the plaintext value of a secret
- developers who integrate applications with secrets manager to retrieve credentials at runtime
- configuration
- trigger rotation for a secret
- random password generation
- update the value of a secret
- credentials
- get metadata for a secret
- delete secret
- cancel scheduled deletion and restore a secret
- get secret value
- aws
- list secrets
- update the value stored in a secret
- get random password
- engineers who manage application infrastructure and configure secrets rotation and access policies
- get metadata and configuration details of a secret
- create secret
- rotation
- Application Developer
- put secret value
- secret lifecycle management
- generate a cryptographically secure random password
- create and store a new secret
- trigger automatic rotation for a secret
- secure storage and access control for sensitive credentials and configuration
- security
- secrets
- rotate secret
- devops
- create a new secret in amazon secrets manager
- individual secret management
- describe secret
- DevOps Engineer
- lifecycle management of secrets including rotation, versioning, and audit
- retrieve the current value of a secret
- amazon secrets manager
slug: secrets-management
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
