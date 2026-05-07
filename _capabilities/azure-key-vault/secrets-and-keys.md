---
categories:
- security
consumed_apis: []
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
- decrypt data using a key.
- get a certificate.
- verify
- delete a secret.
- delete secret
- list keys.
- get secret
- secrets management
- create a new cryptographic key.
- key management
- list secrets
- set a secret.
- delete certificate
- list certificates.
- delete a key.
- secret management.
- key management.
- list certificates in the vault.
- list keys
- get key
- decrypt
- get certificate
- cloud security
- list certificates
- create a key.
- cryptography
- individual secret management.
- delete a certificate.
- key vault
- certificate management.
- list secrets.
- list cryptographic keys in the vault.
- get key details.
- encrypt
- delete key
- get a secret.
- verify a signature.
- set a secret value.
- create key
- list secrets in the vault.
- certificates
- sign a digest using a key.
- azure
- set secret
- sign
- get a key.
- create a new certificate.
- encrypt data using a key.
- security
- individual key management.
- get a secret value.
- create certificate
slug: secrets-and-keys
source_filename: secrets-and-keys.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Key Vault Secrets and Keys\n  description: Unified workflow for managing cryptographic keys, secrets, and certificates with encryption, signing, and certificate\n    lifecycle operations. Used by security engineers and DevOps teams.\n  tags:\n  - Azure\n  - Key Vault\n  - Security\n  - Secrets Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_KEY_VAULT_TOKEN: AZURE_KEY_VAULT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: key-vault\n    baseUri: https://myvault.vault.azure.net\n    description: Azure Key Vault Data Plane API for key, secret, and certificate operations.\n    authentication:\n      type: bearer\n      token: '{{AZURE_KEY_VAULT_TOKEN}}'\n    resources:\n    - name: keys\n      path: /keys\n      description: Key management.\n      operations:\n      - name: list-keys\n        method: GET\n        description: List keys in the vault.\n        inputParameters:\n\
  \        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-create\n      path: /keys/{key-name}/create\n      description: Key creation.\n      operations:\n      - name: create-key\n        method: POST\n        description: Create a new key.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            kty: '{{tools.keyType}}'\n    - name: key-details\n      path: /keys/{key-name}/{key-version}\n      description: Individual key operations.\n      operations:\n      - name: get-key\n\
  \        method: GET\n        description: Get a key.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        - name: key-version\n          in: path\n          type: string\n          required: true\n          description: Key version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-key\n        method: PATCH\n        description: Update key attributes.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        - name: key-version\n          in: path\n          type: string\n          required: true\n          description: Key version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-delete\n\
  \      path: /keys/{key-name}\n      description: Key deletion.\n      operations:\n      - name: delete-key\n        method: DELETE\n        description: Delete a key.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-encrypt\n      path: /keys/{key-name}/{key-version}/encrypt\n      description: Encryption operations.\n      operations:\n      - name: encrypt\n        method: POST\n        description: Encrypt data using a key.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        - name: key-version\n          in: path\n          type: string\n          required: true\n          description: Key version.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            alg: '{{tools.algorithm}}'\n            value: '{{tools.value}}'\n    - name: key-decrypt\n      path: /keys/{key-name}/{key-version}/decrypt\n      description: Decryption operations.\n      operations:\n      - name: decrypt\n        method: POST\n        description: Decrypt data using a key.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        - name: key-version\n          in: path\n          type: string\n          required: true\n          description: Key version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            alg: '{{tools.algorithm}}'\n            value:\
  \ '{{tools.value}}'\n    - name: key-sign\n      path: /keys/{key-name}/{key-version}/sign\n      description: Signing operations.\n      operations:\n      - name: sign\n        method: POST\n        description: Sign a digest using a key.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        - name: key-version\n          in: path\n          type: string\n          required: true\n          description: Key version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            alg: '{{tools.algorithm}}'\n            value: '{{tools.digest}}'\n    - name: key-verify\n      path: /keys/{key-name}/{key-version}/verify\n      description: Verification operations.\n      operations:\n      - name: verify\n        method: POST\n        description: Verify\
  \ a signature.\n        inputParameters:\n        - name: key-name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        - name: key-version\n          in: path\n          type: string\n          required: true\n          description: Key version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            alg: '{{tools.algorithm}}'\n            digest: '{{tools.digest}}'\n            value: '{{tools.signature}}'\n    - name: secrets\n      path: /secrets\n      description: Secret management.\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List secrets in the vault.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-set\n      path: /secrets/{secret-name}\n  \
  \    description: Secret creation and deletion.\n      operations:\n      - name: set-secret\n        method: PUT\n        description: Set a secret value.\n        inputParameters:\n        - name: secret-name\n          in: path\n          type: string\n          required: true\n          description: Secret name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            value: '{{tools.value}}'\n      - name: delete-secret\n        method: DELETE\n        description: Delete a secret.\n        inputParameters:\n        - name: secret-name\n          in: path\n          type: string\n          required: true\n          description: Secret name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-details\n      path: /secrets/{secret-name}/{secret-version}\n\
  \      description: Individual secret operations.\n      operations:\n      - name: get-secret\n        method: GET\n        description: Get a secret value.\n        inputParameters:\n        - name: secret-name\n          in: path\n          type: string\n          required: true\n          description: Secret name.\n        - name: secret-version\n          in: path\n          type: string\n          required: true\n          description: Secret version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates\n      path: /certificates\n      description: Certificate management.\n      operations:\n      - name: list-certificates\n        method: GET\n        description: List certificates in the vault.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-create\n      path: /certificates/{certificate-name}/create\n\
  \      description: Certificate creation.\n      operations:\n      - name: create-certificate\n        method: POST\n        description: Create a new certificate.\n        inputParameters:\n        - name: certificate-name\n          in: path\n          type: string\n          required: true\n          description: Certificate name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-details\n      path: /certificates/{certificate-name}/{certificate-version}\n      description: Individual certificate operations.\n      operations:\n      - name: get-certificate\n        method: GET\n        description: Get a certificate.\n        inputParameters:\n        - name: certificate-name\n          in: path\n          type: string\n          required: true\n          description: Certificate name.\n        - name: certificate-version\n          in: path\n          type: string\n          required:\
  \ true\n          description: Certificate version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-delete\n      path: /certificates/{certificate-name}\n      description: Certificate deletion.\n      operations:\n      - name: delete-certificate\n        method: DELETE\n        description: Delete a certificate.\n        inputParameters:\n        - name: certificate-name\n          in: path\n          type: string\n          required: true\n          description: Certificate name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: secrets-and-keys-api\n    description: Unified REST API for Azure Key Vault secrets, keys, and certificates.\n    resources:\n    - path: /v1/keys\n      name: keys\n      description: Key management.\n      operations:\n\
  \      - method: GET\n        name: list-keys\n        description: List keys.\n        call: key-vault.list-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-key\n        description: Create a key.\n        call: key-vault.create-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{id}\n      name: key-details\n      description: Individual key management.\n      operations:\n      - method: GET\n        name: get-key\n        description: Get a key.\n        call: key-vault.get-key\n        with:\n          key-name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-key\n        description: Delete a key.\n        call: key-vault.delete-key\n        with:\n          key-name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets\n     \
  \ name: secrets\n      description: Secret management.\n      operations:\n      - method: GET\n        name: list-secrets\n        description: List secrets.\n        call: key-vault.list-secrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets/{id}\n      name: secret-details\n      description: Individual secret management.\n      operations:\n      - method: PUT\n        name: set-secret\n        description: Set a secret.\n        call: key-vault.set-secret\n        with:\n          secret-name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-secret\n        description: Get a secret.\n        call: key-vault.get-secret\n        with:\n          secret-name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-secret\n        description: Delete a secret.\n        call: key-vault.delete-secret\n\
  \        with:\n          secret-name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certificates\n      name: certificates\n      description: Certificate management.\n      operations:\n      - method: GET\n        name: list-certificates\n        description: List certificates.\n        call: key-vault.list-certificates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: secrets-and-keys-mcp\n    transport: http\n    description: MCP server for AI-assisted Key Vault secrets, keys, and certificate management.\n    tools:\n    - name: list-keys\n      description: List cryptographic keys in the vault.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: key-vault.list-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-key\n      description: Create a new cryptographic key.\n      hints:\n        readOnly:\
  \ false\n      call: key-vault.create-key\n      with:\n        key-name: tools.keyName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-key\n      description: Get key details.\n      hints:\n        readOnly: true\n      call: key-vault.get-key\n      with:\n        key-name: tools.keyName\n        key-version: tools.keyVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-key\n      description: Delete a key.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: key-vault.delete-key\n      with:\n        key-name: tools.keyName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: encrypt\n      description: Encrypt data using a key.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: key-vault.encrypt\n      with:\n        key-name: tools.keyName\n        key-version: tools.keyVersion\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: decrypt\n      description: Decrypt data using a key.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: key-vault.decrypt\n      with:\n        key-name: tools.keyName\n        key-version: tools.keyVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sign\n      description: Sign a digest using a key.\n      hints:\n        readOnly: false\n      call: key-vault.sign\n      with:\n        key-name: tools.keyName\n        key-version: tools.keyVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify\n      description: Verify a signature.\n      hints:\n        readOnly: true\n      call: key-vault.verify\n      with:\n        key-name: tools.keyName\n        key-version: tools.keyVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-secrets\n      description: List secrets in the vault.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: key-vault.list-secrets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-secret\n      description: Set a secret value.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: key-vault.set-secret\n      with:\n        secret-name: tools.secretName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-secret\n      description: Get a secret value.\n      hints:\n        readOnly: true\n      call: key-vault.get-secret\n      with:\n        secret-name: tools.secretName\n        secret-version: tools.secretVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-secret\n      description: Delete a secret.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: key-vault.delete-secret\n      with:\n        secret-name: tools.secretName\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-certificates\n      description: List certificates in the vault.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: key-vault.list-certificates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-certificate\n      description: Create a new certificate.\n      hints:\n        readOnly: false\n      call: key-vault.create-certificate\n      with:\n        certificate-name: tools.certificateName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-certificate\n      description: Get a certificate.\n      hints:\n        readOnly: true\n      call: key-vault.get-certificate\n      with:\n        certificate-name: tools.certificateName\n        certificate-version: tools.certificateVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-certificate\n      description: Delete a\
  \ certificate.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: key-vault.delete-certificate\n      with:\n        certificate-name: tools.certificateName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
