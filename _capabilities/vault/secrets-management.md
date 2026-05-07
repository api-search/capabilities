---
categories: []
consumed_apis: []
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
- check hashicorp vault health status including initialized, sealed, and standby state.
- devops
- create or update a vault acl policy with hcl rules defining path-based capabilities.
- delete secret
- renew lease
- vault authentication method management.
- get health
- read metadata and version history for a vault secret including creation time, current version, and all version states.
- pki
- write a secret to hashicorp vault kv v2. each write creates a new version.
- list all mounted secrets engines.
- read a specific vault acl policy by name to view its path-based access rules.
- secrets management
- secret metadata and version history.
- kv v2 secret crud with versioning.
- read secret
- read secret metadata
- hashicorp vault
- soft delete the latest version of a secret in vault. the data can be recovered with undelete.
- list all enabled authentication methods.
- vault secrets engine mount management.
- list auth methods
- vault health status.
- check vault health status.
- read a secret from hashicorp vault kv v2 store by path. returns the secret data and version metadata.
- look up a vault lease by id to check ttl, expiration time, and renewable status.
- write policy
- encryption
- list all acl policies configured in vault.
- list all acl policies.
- vault acl policy management.
- list secrets mounts
- soft delete the latest version of a secret.
- renew a vault lease to extend the ttl of dynamic secrets and tokens.
- list all authentication methods enabled in vault including type, path, and configuration.
- list policies
- write a secret to vault kv v2.
- get vault health
- read metadata and version history for a secret.
- read a secret from vault kv v2 by path.
- open source
- list all secrets engines mounted in vault with their type, path, and configuration.
- security
- lookup lease
- write secret
- read policy
- platform engineering
slug: secrets-management
source_filename: secrets-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Vault Secrets Management\n  description: Unified workflow capability for platform engineers and DevOps teams managing secrets with HashiCorp Vault.\n    Combines KV secrets CRUD, version management, metadata operations, and system configuration into a single AI-accessible\n    interface for secrets lifecycle management.\n  tags:\n  - HashiCorp Vault\n  - Secrets Management\n  - DevOps\n  - Platform Engineering\n  - Security\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VAULT_TOKEN: VAULT_TOKEN\n    VAULT_ADDR: VAULT_ADDR\ncapability:\n  consumes:\n  - type: http\n    namespace: vault-kv\n    baseUri: '{{VAULT_ADDR}}/v1'\n    description: HashiCorp Vault KV v2 secrets engine REST API.\n    authentication:\n      type: apikey\n      key: X-Vault-Token\n      value: '{{VAULT_TOKEN}}'\n      placement: header\n    resources:\n    - name: kv-config\n      path: /secret/config\n      description:\
  \ KV v2 engine configuration.\n      operations:\n      - name: get-kv-config\n        method: GET\n        description: Retrieve KV engine configuration including max versions and CAS settings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-kv-config\n        method: POST\n        description: Configure KV engine settings such as max versions and CAS required.\n        inputParameters:\n        - name: max_versions\n          in: body\n          type: integer\n          required: false\n          description: Maximum number of versions to keep per secret.\n        - name: cas_required\n          in: body\n          type: boolean\n          required: false\n          description: Require CAS for all write operations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n        \
  \  data:\n            max_versions: '{{tools.max_versions}}'\n            cas_required: '{{tools.cas_required}}'\n    - name: kv-data\n      path: /secret/data/{path}\n      description: Secret data CRUD operations with versioning.\n      operations:\n      - name: read-secret\n        method: GET\n        description: Read secret data and metadata for a given path. Returns latest version by default.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the secret.\n        - name: version\n          in: query\n          type: integer\n          required: false\n          description: Specific version to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: object\n          value: $.data.data\n        - name: metadata\n          type: object\n          value: $.data.metadata\n      - name: write-secret\n        method: POST\n        description:\
  \ Create or update a secret. Each write creates a new version.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the secret.\n        - name: data\n          in: body\n          type: object\n          required: true\n          description: Key-value pairs to store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: delete-latest-secret-version\n        method: DELETE\n        description: Soft delete the latest version of a secret.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: kv-metadata\n      path: /secret/metadata/{path}\n      description: Secret metadata and version history management.\n      operations:\n      - name: read-secret-metadata\n        method: GET\n        description: Read metadata and version history for a secret.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-secret-metadata\n        method: DELETE\n        description: Permanently delete all metadata and versions for a secret.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  - type: http\n    namespace: vault-sys\n    baseUri: '{{VAULT_ADDR}}/v1'\n    description: HashiCorp Vault system backend REST API.\n    authentication:\n      type: apikey\n      key: X-Vault-Token\n      value: '{{VAULT_TOKEN}}'\n      placement: header\n    resources:\n    - name: health\n      path: /sys/health\n      description: Vault health and status monitoring.\n      operations:\n      - name: get-health\n        method: GET\n        description: Check Vault health status including initialized, sealed, and standby state.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-methods\n      path: /sys/auth\n      description: Authentication method management.\n      operations:\n      - name: list-auth-methods\n        method: GET\n        description: List all currently enabled authentication methods.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: enable-auth-method\n        method: POST\n        description: Enable a new authentication method at the specified path.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Mount path for the auth method.\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: Auth method type (approle, kubernetes, ldap, etc.).\n        - name: description\n          in: body\n          type: string\n          required: false\n          description: Human-friendly description.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            description: '{{tools.description}}'\n      - name: disable-auth-method\n        method: DELETE\n\
  \        description: Disable an authentication method and revoke all associated tokens.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Mount path of the auth method to disable.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets-mounts\n      path: /sys/mounts\n      description: Secrets engine mount management.\n      operations:\n      - name: list-secrets-mounts\n        method: GET\n        description: List all mounted secrets engines.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enable-secrets-engine\n        method: POST\n        description: Mount a new secrets engine at the specified path.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required:\
  \ true\n          description: Mount path for the secrets engine.\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: Secrets engine type (kv, aws, database, pki, transit, etc.).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            description: '{{tools.description}}'\n      - name: disable-secrets-engine\n        method: DELETE\n        description: Unmount a secrets engine and revoke all associated secrets.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Mount path of the secrets engine to disable.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path:\
  \ /sys/policies/acl\n      description: ACL policy management.\n      operations:\n      - name: list-policies\n        method: GET\n        description: List all ACL policies.\n        outputRawFormat: json\n        outputParameters:\n        - name: policies\n          type: array\n          value: $.data.policies\n      - name: read-policy\n        method: GET\n        description: Read an ACL policy by name.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Policy name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: write-policy\n        method: POST\n        description: Create or update an ACL policy.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Policy name.\n        - name: policy\n          in: body\n\
  \          type: string\n          required: true\n          description: HCL policy document.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policy: '{{tools.policy}}'\n      - name: delete-policy\n        method: DELETE\n        description: Delete an ACL policy.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Policy name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leases\n      path: /sys/leases\n      description: Lease lifecycle management.\n      operations:\n      - name: lookup-lease\n        method: PUT\n        description: Look up a lease by ID to get TTL and expiration information.\n        inputParameters:\n        - name: lease_id\n       \
  \   in: body\n          type: string\n          required: true\n          description: Lease identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lease_id: '{{tools.lease_id}}'\n      - name: renew-lease\n        method: PUT\n        description: Renew a lease to extend its TTL.\n        inputParameters:\n        - name: lease_id\n          in: body\n          type: string\n          required: true\n          description: Lease identifier.\n        - name: increment\n          in: body\n          type: integer\n          required: false\n          description: Requested renewal duration in seconds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lease_id: '{{tools.lease_id}}'\n            increment:\
  \ '{{tools.increment}}'\n      - name: revoke-lease\n        method: PUT\n        description: Revoke a lease and the associated dynamic secret.\n        inputParameters:\n        - name: lease_id\n          in: body\n          type: string\n          required: true\n          description: Lease identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lease_id: '{{tools.lease_id}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vault-secrets-api\n    description: Unified REST API for HashiCorp Vault secrets lifecycle management.\n    resources:\n    - path: /v1/secrets/{path}\n      name: secrets\n      description: KV v2 secret CRUD with versioning.\n      operations:\n      - method: GET\n        name: read-secret\n        description: Read a secret from Vault KV v2 by path.\n        call: vault-kv.read-secret\n        with:\n\
  \          path: rest.path\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: write-secret\n        description: Write a secret to Vault KV v2.\n        call: vault-kv.write-secret\n        with:\n          path: rest.path\n          data: rest.data\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-secret\n        description: Soft delete the latest version of a secret.\n        call: vault-kv.delete-latest-secret-version\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets/{path}/metadata\n      name: secret-metadata\n      description: Secret metadata and version history.\n      operations:\n      - method: GET\n        name: read-secret-metadata\n        description: Read metadata and version history for a secret.\n        call: vault-kv.read-secret-metadata\n\
  \        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth-methods\n      name: auth-methods\n      description: Vault authentication method management.\n      operations:\n      - method: GET\n        name: list-auth-methods\n        description: List all enabled authentication methods.\n        call: vault-sys.list-auth-methods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mounts\n      name: secrets-mounts\n      description: Vault secrets engine mount management.\n      operations:\n      - method: GET\n        name: list-secrets-mounts\n        description: List all mounted secrets engines.\n        call: vault-sys.list-secrets-mounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Vault ACL policy management.\n      operations:\n      - method: GET\n        name: list-policies\n\
  \        description: List all ACL policies.\n        call: vault-sys.list-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Vault health status.\n      operations:\n      - method: GET\n        name: get-health\n        description: Check Vault health status.\n        call: vault-sys.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vault-secrets-mcp\n    transport: http\n    description: MCP server for AI-assisted HashiCorp Vault secrets management workflows.\n    tools:\n    - name: read-secret\n      description: Read a secret from HashiCorp Vault KV v2 store by path. Returns the secret data and version metadata.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-kv.read-secret\n      with:\n        path: tools.path\n        version: tools.version\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: write-secret\n      description: Write a secret to HashiCorp Vault KV v2. Each write creates a new version.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vault-kv.write-secret\n      with:\n        path: tools.path\n        data: tools.data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-secret\n      description: Soft delete the latest version of a secret in Vault. The data can be recovered with undelete.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vault-kv.delete-latest-secret-version\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-secret-metadata\n      description: Read metadata and version history for a Vault secret including creation time, current version, and all\n        version states.\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: vault-kv.read-secret-metadata\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-auth-methods\n      description: List all authentication methods enabled in Vault including type, path, and configuration.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-sys.list-auth-methods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-secrets-mounts\n      description: List all secrets engines mounted in Vault with their type, path, and configuration.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-sys.list-secrets-mounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List all ACL policies configured in Vault.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-sys.list-policies\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-policy\n      description: Read a specific Vault ACL policy by name to view its path-based access rules.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-sys.read-policy\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: write-policy\n      description: Create or update a Vault ACL policy with HCL rules defining path-based capabilities.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: vault-sys.write-policy\n      with:\n        name: tools.name\n        policy: tools.policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-lease\n      description: Look up a Vault lease by ID to check TTL, expiration time, and renewable status.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vault-sys.lookup-lease\n     \
  \ with:\n        lease_id: tools.lease_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renew-lease\n      description: Renew a Vault lease to extend the TTL of dynamic secrets and tokens.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vault-sys.renew-lease\n      with:\n        lease_id: tools.lease_id\n        increment: tools.increment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vault-health\n      description: Check HashiCorp Vault health status including initialized, sealed, and standby state.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vault-sys.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
