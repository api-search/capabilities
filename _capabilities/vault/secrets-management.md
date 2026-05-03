---
categories: []
consumed_apis:
- vault-kv
- vault-sys
description: Unified workflow capability for platform engineers and DevOps teams managing secrets with HashiCorp Vault. Combines KV secrets CRUD, version management, metadata operations, and system configuration into a single AI-accessible interface for secrets lifecycle management.
layout: capability
name: HashiCorp Vault Secrets Management
operations:
- description: Read a secret from Vault KV v2 by path.
  method: GET
  name: read-secret
  path: /v1/secrets/{path}
- description: Write a secret to Vault KV v2.
  method: POST
  name: write-secret
  path: /v1/secrets/{path}
- description: Soft delete the latest version of a secret.
  method: DELETE
  name: delete-secret
  path: /v1/secrets/{path}
- description: Read metadata and version history for a secret.
  method: GET
  name: read-secret-metadata
  path: /v1/secrets/{path}/metadata
- description: List all enabled authentication methods.
  method: GET
  name: list-auth-methods
  path: /v1/auth-methods
- description: List all mounted secrets engines.
  method: GET
  name: list-secrets-mounts
  path: /v1/mounts
- description: List all ACL policies.
  method: GET
  name: list-policies
  path: /v1/policies
- description: Check Vault health status.
  method: GET
  name: get-health
  path: /v1/health
personas: []
provider_name: HashiCorp Vault
provider_slug: vault
search_terms:
- create or update a vault acl policy with hcl rules defining path-based capabilities.
- list policies
- list all secrets engines mounted in vault with their type, path, and configuration.
- kv v2 secret crud with versioning.
- soft delete the latest version of a secret in vault. the data can be recovered with undelete.
- read policy
- security
- vault acl policy management.
- check vault health status.
- list all mounted secrets engines.
- read metadata and version history for a secret.
- read a secret from hashicorp vault kv v2 store by path. returns the secret data and version metadata.
- open source
- list all enabled authentication methods.
- vault secrets engine mount management.
- read a specific vault acl policy by name to view its path-based access rules.
- get vault health
- encryption
- read secret metadata
- check hashicorp vault health status including initialized, sealed, and standby state.
- write a secret to vault kv v2.
- soft delete the latest version of a secret.
- vault authentication method management.
- secrets management
- list all acl policies configured in vault.
- platform engineering
- read metadata and version history for a vault secret including creation time, current version, and all version states.
- write secret
- lookup lease
- list all acl policies.
- write a secret to hashicorp vault kv v2. each write creates a new version.
- list secrets mounts
- look up a vault lease by id to check ttl, expiration time, and renewable status.
- list auth methods
- secret metadata and version history.
- renew lease
- pki
- hashicorp vault
- list all authentication methods enabled in vault including type, path, and configuration.
- renew a vault lease to extend the ttl of dynamic secrets and tokens.
- read secret
- vault health status.
- write policy
- devops
- delete secret
- read a secret from vault kv v2 by path.
- get health
slug: secrets-management
source_filename: secrets-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"HashiCorp Vault Secrets Management\"\n  description: \"Unified workflow capability for platform engineers and DevOps teams managing secrets with HashiCorp Vault. Combines KV secrets CRUD, version management, metadata operations, and system configuration into a single AI-accessible interface for secrets lifecycle management.\"\n  tags:\n    - HashiCorp Vault\n    - Secrets Management\n    - DevOps\n    - Platform Engineering\n    - Security\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VAULT_TOKEN: VAULT_TOKEN\n      VAULT_ADDR: VAULT_ADDR\n\ncapability:\n  consumes:\n    - import: vault-kv\n      location: ./shared/kv-secrets.yaml\n    - import: vault-sys\n      location: ./shared/sys-backend.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vault-secrets-api\n      description: \"Unified REST API for HashiCorp Vault secrets lifecycle management.\"\n\
  \      resources:\n        - path: /v1/secrets/{path}\n          name: secrets\n          description: \"KV v2 secret CRUD with versioning.\"\n          operations:\n            - method: GET\n              name: read-secret\n              description: \"Read a secret from Vault KV v2 by path.\"\n              call: \"vault-kv.read-secret\"\n              with:\n                path: \"rest.path\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: write-secret\n              description: \"Write a secret to Vault KV v2.\"\n              call: \"vault-kv.write-secret\"\n              with:\n                path: \"rest.path\"\n                data: \"rest.data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-secret\n              description:\
  \ \"Soft delete the latest version of a secret.\"\n              call: \"vault-kv.delete-latest-secret-version\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/secrets/{path}/metadata\n          name: secret-metadata\n          description: \"Secret metadata and version history.\"\n          operations:\n            - method: GET\n              name: read-secret-metadata\n              description: \"Read metadata and version history for a secret.\"\n              call: \"vault-kv.read-secret-metadata\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth-methods\n          name: auth-methods\n          description: \"Vault authentication method management.\"\n          operations:\n            - method: GET\n             \
  \ name: list-auth-methods\n              description: \"List all enabled authentication methods.\"\n              call: \"vault-sys.list-auth-methods\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/mounts\n          name: secrets-mounts\n          description: \"Vault secrets engine mount management.\"\n          operations:\n            - method: GET\n              name: list-secrets-mounts\n              description: \"List all mounted secrets engines.\"\n              call: \"vault-sys.list-secrets-mounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies\n          name: policies\n          description: \"Vault ACL policy management.\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List all ACL policies.\"\n              call: \"vault-sys.list-policies\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/health\n          name: health\n          description: \"Vault health status.\"\n          operations:\n            - method: GET\n              name: get-health\n              description: \"Check Vault health status.\"\n              call: \"vault-sys.get-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vault-secrets-mcp\n      transport: http\n      description: \"MCP server for AI-assisted HashiCorp Vault secrets management workflows.\"\n      tools:\n        - name: read-secret\n          description: \"Read a secret from HashiCorp Vault KV v2 store by path. Returns the secret data and version metadata.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-kv.read-secret\"\n          with:\n        \
  \    path: \"tools.path\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: write-secret\n          description: \"Write a secret to HashiCorp Vault KV v2. Each write creates a new version.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"vault-kv.write-secret\"\n          with:\n            path: \"tools.path\"\n            data: \"tools.data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-secret\n          description: \"Soft delete the latest version of a secret in Vault. The data can be recovered with undelete.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"vault-kv.delete-latest-secret-version\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n\n        - name: read-secret-metadata\n          description: \"Read metadata and version history for a Vault secret including creation time, current version, and all version states.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-kv.read-secret-metadata\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-auth-methods\n          description: \"List all authentication methods enabled in Vault including type, path, and configuration.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-sys.list-auth-methods\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-secrets-mounts\n          description: \"List all secrets engines mounted in Vault with their type, path, and\
  \ configuration.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-sys.list-secrets-mounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-policies\n          description: \"List all ACL policies configured in Vault.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-sys.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: read-policy\n          description: \"Read a specific Vault ACL policy by name to view its path-based access rules.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-sys.read-policy\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: write-policy\n          description: \"\
  Create or update a Vault ACL policy with HCL rules defining path-based capabilities.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"vault-sys.write-policy\"\n          with:\n            name: \"tools.name\"\n            policy: \"tools.policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-lease\n          description: \"Look up a Vault lease by ID to check TTL, expiration time, and renewable status.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vault-sys.lookup-lease\"\n          with:\n            lease_id: \"tools.lease_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: renew-lease\n          description: \"Renew a Vault lease to extend the TTL of dynamic secrets and tokens.\"\n          hints:\n            readOnly: false\n            idempotent: false\n\
  \          call: \"vault-sys.renew-lease\"\n          with:\n            lease_id: \"tools.lease_id\"\n            increment: \"tools.increment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-vault-health\n          description: \"Check HashiCorp Vault health status including initialized, sealed, and standby state.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vault-sys.get-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vault/refs/heads/main/capabilities/secrets-management.yaml
tags:
- HashiCorp Vault
- Secrets Management
- DevOps
- Platform Engineering
- Security
tools:
- description: Read a secret from HashiCorp Vault KV v2 store by path. Returns the secret data and version metadata.
  hints:
    openWorld: false
    readOnly: true
  name: read-secret
- description: Write a secret to HashiCorp Vault KV v2. Each write creates a new version.
  hints:
    idempotent: false
    readOnly: false
  name: write-secret
- description: Soft delete the latest version of a secret in Vault. The data can be recovered with undelete.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: delete-secret
- description: Read metadata and version history for a Vault secret including creation time, current version, and all version states.
  hints:
    openWorld: false
    readOnly: true
  name: read-secret-metadata
- description: List all authentication methods enabled in Vault including type, path, and configuration.
  hints:
    openWorld: false
    readOnly: true
  name: list-auth-methods
- description: List all secrets engines mounted in Vault with their type, path, and configuration.
  hints:
    openWorld: false
    readOnly: true
  name: list-secrets-mounts
- description: List all ACL policies configured in Vault.
  hints:
    openWorld: false
    readOnly: true
  name: list-policies
- description: Read a specific Vault ACL policy by name to view its path-based access rules.
  hints:
    openWorld: false
    readOnly: true
  name: read-policy
- description: Create or update a Vault ACL policy with HCL rules defining path-based capabilities.
  hints:
    idempotent: true
    readOnly: false
  name: write-policy
- description: Look up a Vault lease by ID to check TTL, expiration time, and renewable status.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-lease
- description: Renew a Vault lease to extend the TTL of dynamic secrets and tokens.
  hints:
    idempotent: false
    readOnly: false
  name: renew-lease
- description: Check HashiCorp Vault health status including initialized, sealed, and standby state.
  hints:
    openWorld: true
    readOnly: true
  name: get-vault-health
---
