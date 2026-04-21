---
consumed_apis:
- key-vault
description: Unified workflow for managing cryptographic keys, secrets, and certificates with encryption, signing, and certificate lifecycle operations. Used by security engineers and DevOps teams.
layout: capability
name: Azure Key Vault Secrets and Keys
operations:
- description: List keys.
  method: GET
  name: list-keys
  path: /v1/keys
- description: Create a key.
  method: POST
  name: create-key
  path: /v1/keys
- description: Get a key.
  method: GET
  name: get-key
  path: /v1/keys/{id}
- description: Delete a key.
  method: DELETE
  name: delete-key
  path: /v1/keys/{id}
- description: List secrets.
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Set a secret.
  method: PUT
  name: set-secret
  path: /v1/secrets/{id}
- description: Get a secret.
  method: GET
  name: get-secret
  path: /v1/secrets/{id}
- description: Delete a secret.
  method: DELETE
  name: delete-secret
  path: /v1/secrets/{id}
- description: List certificates.
  method: GET
  name: list-certificates
  path: /v1/certificates
personas: []
provider_name: Azure Key Vault
provider_slug: azure-key-vault
search_terms:
- verify
- list keys
- get secret
- create a new certificate.
- cryptography
- list certificates in the vault.
- get key
- individual secret management.
- create a key.
- set a secret.
- certificate management.
- delete certificate
- list secrets.
- list certificates.
- set a secret value.
- encrypt data using a key.
- get key details.
- certificates
- azure
- delete a secret.
- decrypt
- delete key
- sign a digest using a key.
- get a key.
- delete a key.
- get a secret value.
- create key
- key management
- sign
- get a secret.
- key vault
- secrets management
- get a certificate.
- create a new cryptographic key.
- list cryptographic keys in the vault.
- delete a certificate.
- security
- get certificate
- list certificates
- list secrets
- list secrets in the vault.
- individual key management.
- delete secret
- decrypt data using a key.
- encrypt
- create certificate
- list keys.
- secret management.
- verify a signature.
- key management.
- set secret
- cloud security
slug: secrets-and-keys
tags:
- Azure
- Key Vault
- Security
- Secrets Management
tools:
- description: List cryptographic keys in the vault.
  hints:
    openWorld: true
    readOnly: true
  name: list-keys
- description: Create a new cryptographic key.
  hints:
    readOnly: false
  name: create-key
- description: Get key details.
  hints:
    readOnly: true
  name: get-key
- description: Delete a key.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-key
- description: Encrypt data using a key.
  hints:
    idempotent: true
    readOnly: false
  name: encrypt
- description: Decrypt data using a key.
  hints:
    idempotent: true
    readOnly: false
  name: decrypt
- description: Sign a digest using a key.
  hints:
    readOnly: false
  name: sign
- description: Verify a signature.
  hints:
    readOnly: true
  name: verify
- description: List secrets in the vault.
  hints:
    openWorld: true
    readOnly: true
  name: list-secrets
- description: Set a secret value.
  hints:
    idempotent: true
    readOnly: false
  name: set-secret
- description: Get a secret value.
  hints:
    readOnly: true
  name: get-secret
- description: Delete a secret.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-secret
- description: List certificates in the vault.
  hints:
    openWorld: true
    readOnly: true
  name: list-certificates
- description: Create a new certificate.
  hints:
    readOnly: false
  name: create-certificate
- description: Get a certificate.
  hints:
    readOnly: true
  name: get-certificate
- description: Delete a certificate.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-certificate
---
