---
categories:
- security
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
- key management
- list secrets
- encrypt
- cryptography
- delete certificate
- get secret
- cloud security
- get a secret.
- get key details.
- azure
- encrypt data using a key.
- delete a secret.
- create a new certificate.
- list certificates
- set secret
- create certificate
- secrets management
- list secrets.
- list keys.
- list secrets in the vault.
- get key
- list certificates.
- set a secret value.
- get a certificate.
- get certificate
- create key
- delete key
- individual secret management.
- list certificates in the vault.
- verify
- decrypt
- list keys
- verify a signature.
- security
- sign
- secret management.
- set a secret.
- certificate management.
- individual key management.
- get a key.
- key management.
- get a secret value.
- key vault
- decrypt data using a key.
- sign a digest using a key.
- list cryptographic keys in the vault.
- create a key.
- delete a key.
- create a new cryptographic key.
- certificates
- delete a certificate.
- delete secret
slug: secrets-and-keys
source_filename: secrets-and-keys.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Key Vault Secrets and Keys\"\n  description: \"Unified workflow for managing cryptographic keys, secrets, and certificates with encryption, signing, and certificate lifecycle operations. Used by security engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Key Vault\n    - Security\n    - Secrets Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_KEY_VAULT_TOKEN: AZURE_KEY_VAULT_TOKEN\n\ncapability:\n  consumes:\n    - import: key-vault\n      location: ./shared/key-vault-data-plane.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: secrets-and-keys-api\n      description: \"Unified REST API for Azure Key Vault secrets, keys, and certificates.\"\n      resources:\n        - path: /v1/keys\n          name: keys\n          description: \"Key management.\"\n          operations:\n            - method: GET\n              name: list-keys\n\
  \              description: \"List keys.\"\n              call: \"key-vault.list-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-key\n              description: \"Create a key.\"\n              call: \"key-vault.create-key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/keys/{id}\n          name: key-details\n          description: \"Individual key management.\"\n          operations:\n            - method: GET\n              name: get-key\n              description: \"Get a key.\"\n              call: \"key-vault.get-key\"\n              with:\n                key-name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-key\n              description: \"Delete a key.\"\n          \
  \    call: \"key-vault.delete-key\"\n              with:\n                key-name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name: secrets\n          description: \"Secret management.\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List secrets.\"\n              call: \"key-vault.list-secrets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets/{id}\n          name: secret-details\n          description: \"Individual secret management.\"\n          operations:\n            - method: PUT\n              name: set-secret\n              description: \"Set a secret.\"\n              call: \"key-vault.set-secret\"\n              with:\n                secret-name: \"rest.id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: GET\n              name: get-secret\n              description: \"Get a secret.\"\n              call: \"key-vault.get-secret\"\n              with:\n                secret-name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-secret\n              description: \"Delete a secret.\"\n              call: \"key-vault.delete-secret\"\n              with:\n                secret-name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certificates\n          name: certificates\n          description: \"Certificate management.\"\n          operations:\n            - method: GET\n              name: list-certificates\n              description: \"List certificates.\"\n              call: \"key-vault.list-certificates\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: secrets-and-keys-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Key Vault secrets, keys, and certificate management.\"\n      tools:\n        - name: list-keys\n          description: \"List cryptographic keys in the vault.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"key-vault.list-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-key\n          description: \"Create a new cryptographic key.\"\n          hints:\n            readOnly: false\n          call: \"key-vault.create-key\"\n          with:\n            key-name: \"tools.keyName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-key\n          description: \"Get key details.\"\n          hints:\n      \
  \      readOnly: true\n          call: \"key-vault.get-key\"\n          with:\n            key-name: \"tools.keyName\"\n            key-version: \"tools.keyVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-key\n          description: \"Delete a key.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"key-vault.delete-key\"\n          with:\n            key-name: \"tools.keyName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: encrypt\n          description: \"Encrypt data using a key.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"key-vault.encrypt\"\n          with:\n            key-name: \"tools.keyName\"\n            key-version: \"tools.keyVersion\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: decrypt\n          description: \"Decrypt data using a key.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"key-vault.decrypt\"\n          with:\n            key-name: \"tools.keyName\"\n            key-version: \"tools.keyVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sign\n          description: \"Sign a digest using a key.\"\n          hints:\n            readOnly: false\n          call: \"key-vault.sign\"\n          with:\n            key-name: \"tools.keyName\"\n            key-version: \"tools.keyVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify\n          description: \"Verify a signature.\"\n          hints:\n            readOnly: true\n          call: \"key-vault.verify\"\n          with:\n            key-name: \"tools.keyName\"\n            key-version: \"tools.keyVersion\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-secrets\n          description: \"List secrets in the vault.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"key-vault.list-secrets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-secret\n          description: \"Set a secret value.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"key-vault.set-secret\"\n          with:\n            secret-name: \"tools.secretName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-secret\n          description: \"Get a secret value.\"\n          hints:\n            readOnly: true\n          call: \"key-vault.get-secret\"\n          with:\n            secret-name: \"tools.secretName\"\n            secret-version: \"tools.secretVersion\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-secret\n          description: \"Delete a secret.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"key-vault.delete-secret\"\n          with:\n            secret-name: \"tools.secretName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-certificates\n          description: \"List certificates in the vault.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"key-vault.list-certificates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-certificate\n          description: \"Create a new certificate.\"\n          hints:\n            readOnly: false\n          call: \"key-vault.create-certificate\"\n          with:\n            certificate-name:\
  \ \"tools.certificateName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-certificate\n          description: \"Get a certificate.\"\n          hints:\n            readOnly: true\n          call: \"key-vault.get-certificate\"\n          with:\n            certificate-name: \"tools.certificateName\"\n            certificate-version: \"tools.certificateVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-certificate\n          description: \"Delete a certificate.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"key-vault.delete-certificate\"\n          with:\n            certificate-name: \"tools.certificateName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-key-vault/refs/heads/main/capabilities/secrets-and-keys.yaml
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
