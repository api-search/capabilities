---
categories: []
consumed_apis: []
description: The Vault HTTP API provides full access to Vault functionality via HTTP. Every aspect of Vault can be controlled via this API including secrets management, authentication, system configuration, identity, and policy management.
layout: capability
name: HashiCorp Vault HTTP API
operations:
- description: Check initialization status
  method: GET
  name: getinitstatus
  path: /sys/init
- description: Initialize Vault
  method: PUT
  name: initialize
  path: /sys/init
- description: Check seal status
  method: GET
  name: getsealstatus
  path: /sys/seal-status
- description: Seal the Vault
  method: PUT
  name: seal
  path: /sys/seal
- description: Submit an unseal key
  method: PUT
  name: unseal
  path: /sys/unseal
- description: Health status
  method: GET
  name: gethealth
  path: /sys/health
- description: List mounted secrets engines
  method: GET
  name: listsecretengines
  path: /sys/mounts
- description: Enable a secrets engine
  method: POST
  name: enablesecretengine
  path: /sys/mounts/{path}
- description: Disable a secrets engine
  method: DELETE
  name: disablesecretengine
  path: /sys/mounts/{path}
- description: List auth methods
  method: GET
  name: listauthmethods
  path: /sys/auth
- description: Enable an auth method
  method: POST
  name: enableauthmethod
  path: /sys/auth/{path}
- description: Disable an auth method
  method: DELETE
  name: disableauthmethod
  path: /sys/auth/{path}
- description: List ACL policies
  method: GET
  name: listaclpolicies
  path: /sys/policies/acl
- description: Read an ACL policy
  method: GET
  name: getaclpolicy
  path: /sys/policies/acl/{name}
- description: Create or update an ACL policy
  method: PUT
  name: createaclpolicy
  path: /sys/policies/acl/{name}
- description: Delete an ACL policy
  method: DELETE
  name: deleteaclpolicy
  path: /sys/policies/acl/{name}
- description: List audit devices
  method: GET
  name: listauditdevices
  path: /sys/audit
- description: Enable an audit device
  method: PUT
  name: enableauditdevice
  path: /sys/audit/{path}
- description: Disable an audit device
  method: DELETE
  name: disableauditdevice
  path: /sys/audit/{path}
- description: Lookup a lease
  method: PUT
  name: lookuplease
  path: /sys/leases/lookup
- description: Renew a lease
  method: PUT
  name: renewlease
  path: /sys/leases/renew
- description: Revoke a lease
  method: PUT
  name: revokelease
  path: /sys/leases/revoke
- description: Create a token
  method: POST
  name: createtoken
  path: /auth/token/create
- description: Lookup a token
  method: POST
  name: lookuptoken
  path: /auth/token/lookup
- description: Lookup own token
  method: GET
  name: lookupselftoken
  path: /auth/token/lookup-self
- description: Renew a token
  method: POST
  name: renewtoken
  path: /auth/token/renew
- description: Renew own token
  method: POST
  name: renewselftoken
  path: /auth/token/renew-self
- description: Revoke a token
  method: POST
  name: revoketoken
  path: /auth/token/revoke
- description: Revoke own token
  method: POST
  name: revokeselftoken
  path: /auth/token/revoke-self
- description: Login with username and password
  method: POST
  name: loginuserpass
  path: /auth/userpass/login/{username}
- description: Login with AppRole
  method: POST
  name: loginapprole
  path: /auth/approle/login
- description: Read KV secret (v2)
  method: GET
  name: readkvsecret
  path: /secret/data/{path}
- description: Create or update KV secret (v2)
  method: POST
  name: createkvsecret
  path: /secret/data/{path}
- description: Delete latest version of KV secret
  method: DELETE
  name: deletekvsecretlatest
  path: /secret/data/{path}
- description: Read KV secret metadata
  method: GET
  name: getkvmetadata
  path: /secret/metadata/{path}
- description: Delete all versions and metadata
  method: DELETE
  name: deletekvmetadata
  path: /secret/metadata/{path}
- description: Delete specific versions of KV secret
  method: POST
  name: deletekvsecretversions
  path: /secret/delete/{path}
- description: Undelete versions of KV secret
  method: POST
  name: undeletekvsecretversions
  path: /secret/undelete/{path}
- description: Permanently destroy versions
  method: POST
  name: destroykvsecretversions
  path: /secret/destroy/{path}
- description: Encrypt data
  method: POST
  name: transitencrypt
  path: /transit/encrypt/{name}
- description: Decrypt data
  method: POST
  name: transitdecrypt
  path: /transit/decrypt/{name}
- description: Create an encryption key
  method: POST
  name: createtransitkey
  path: /transit/keys/{name}
- description: Read an encryption key
  method: GET
  name: gettransitkey
  path: /transit/keys/{name}
- description: Delete an encryption key
  method: DELETE
  name: deletetransitkey
  path: /transit/keys/{name}
- description: Create an identity entity
  method: POST
  name: createentity
  path: /identity/entity
- description: Read an entity by ID
  method: GET
  name: getentity
  path: /identity/entity/id/{id}
- description: Update an entity
  method: POST
  name: updateentity
  path: /identity/entity/id/{id}
- description: Delete an entity
  method: DELETE
  name: deleteentity
  path: /identity/entity/id/{id}
- description: Read root generation progress
  method: GET
  name: getrootgenerationprogress
  path: /sys/generate-root/attempt
- description: Start root token generation
  method: PUT
  name: startrootgeneration
  path: /sys/generate-root/attempt
- description: Cancel root token generation
  method: DELETE
  name: cancelrootgeneration
  path: /sys/generate-root/attempt
- description: Get leader information
  method: GET
  name: getleader
  path: /sys/leader
- description: Wrap data
  method: POST
  name: wrap
  path: /sys/wrapping/wrap
- description: Unwrap data
  method: POST
  name: unwrap
  path: /sys/wrapping/unwrap
personas: []
provider_name: HashiCorp Vault
provider_slug: hashicorp-vault
search_terms:
- transitdecrypt
- renewtoken
- renewselftoken
- getentity
- start root token generation
- delete an acl policy
- revokelease
- read kv secret (v2)
- renew a lease
- update an entity
- disableauthmethod
- security
- transitencrypt
- create or update an acl policy
- revoke own token
- list auth methods
- api
- cancelrootgeneration
- enablesecretengine
- list audit devices
- lookuptoken
- delete all versions and metadata
- wrap
- create an identity entity
- loginapprole
- deletekvsecretlatest
- enable an audit device
- renewlease
- undelete versions of kv secret
- infrastructure
- lookup a token
- wrap data
- login with approle
- revoke a lease
- seal
- encryption
- cancel root token generation
- deleteaclpolicy
- readkvsecret
- secrets management
- lookupselftoken
- login with username and password
- read kv secret metadata
- enableauthmethod
- renew own token
- revoketoken
- unseal
- getinitstatus
- lookuplease
- getleader
- lookup a lease
- deletekvsecretversions
- createentity
- create an encryption key
- delete an entity
- list mounted secrets engines
- unwrap
- enable an auth method
- encrypt data
- devops
- renew a token
- revokeselftoken
- undeletekvsecretversions
- delete latest version of kv secret
- createtoken
- createaclpolicy
- hashicorp
- disable an auth method
- disable a secrets engine
- read an acl policy
- check initialization status
- read an entity by id
- seal the vault
- list acl policies
- listaclpolicies
- createkvsecret
- getaclpolicy
- create or update kv secret (v2)
- check seal status
- listauthmethods
- createtransitkey
- disable an audit device
- enableauditdevice
- listauditdevices
- create a token
- permanently destroy versions
- getrootgenerationprogress
- submit an unseal key
- getkvmetadata
- deletekvmetadata
- getsealstatus
- read root generation progress
- startrootgeneration
- initialize vault
- initialize
- disableauditdevice
- disablesecretengine
- unwrap data
- gethealth
- gettransitkey
- updateentity
- health status
- delete an encryption key
- destroykvsecretversions
- decrypt data
- lookup own token
- read an encryption key
- vault
- get leader information
- delete specific versions of kv secret
- listsecretengines
- deleteentity
- revoke a token
- deletetransitkey
- enable a secrets engine
- loginuserpass
slug: hashicorp-vault-capability
source_filename: hashicorp-vault-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Vault HTTP API\n  description: The Vault HTTP API provides full access to Vault functionality via HTTP. Every aspect of Vault can be controlled\n    via this API including secrets management, authentication, system configuration, identity, and policy management.\n  tags:\n  - Hashicorp\n  - Vault\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hashicorp-vault\n    baseUri: https://127.0.0.1:8200/v1\n    description: HashiCorp Vault HTTP API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Vault-Token\n      value: '{{HASHICORP_VAULT_TOKEN}}'\n    resources:\n    - name: sys-init\n      path: /sys/init\n      operations:\n      - name: getinitstatus\n        method: GET\n        description: Check initialization status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: initialize\n        method: PUT\n        description: Initialize Vault\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-seal-status\n      path: /sys/seal-status\n      operations:\n      - name: getsealstatus\n        method: GET\n        description: Check seal status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-seal\n      path: /sys/seal\n      operations:\n      - name: seal\n        method: PUT\n        description: Seal the Vault\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-unseal\n      path: /sys/unseal\n      operations:\n      - name: unseal\n        method: PUT\n        description: Submit an unseal key\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: sys-health\n      path: /sys/health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Health status\n        inputParameters:\n        - name: standbyok\n          in: query\n          type: boolean\n          description: Return 200 for standby nodes too\n        - name: activecode\n          in: query\n          type: integer\n          description: Custom status code for active node\n        - name: standbycode\n          in: query\n          type: integer\n          description: Custom status code for standby node\n        - name: sealedcode\n          in: query\n          type: integer\n          description: Custom status code for sealed node\n        - name: uninitcode\n          in: query\n          type: integer\n          description: Custom status code for uninitialized node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: sys-mounts\n      path: /sys/mounts\n      operations:\n      - name: listsecretengines\n        method: GET\n        description: List mounted secrets engines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-mounts-path\n      path: /sys/mounts/{path}\n      operations:\n      - name: enablesecretengine\n        method: POST\n        description: Enable a secrets engine\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disablesecretengine\n        method: DELETE\n        description: Disable a secrets engine\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-auth\n      path: /sys/auth\n      operations:\n      - name: listauthmethods\n        method: GET\n        description: List auth methods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-auth-path\n      path: /sys/auth/{path}\n      operations:\n      - name: enableauthmethod\n        method: POST\n        description: Enable an auth method\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disableauthmethod\n        method: DELETE\n        description: Disable an auth method\n        inputParameters:\n        - name: path\n          in: path\n \
  \         type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-policies-acl\n      path: /sys/policies/acl\n      operations:\n      - name: listaclpolicies\n        method: GET\n        description: List ACL policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-policies-acl-name\n      path: /sys/policies/acl/{name}\n      operations:\n      - name: getaclpolicy\n        method: GET\n        description: Read an ACL policy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaclpolicy\n        method: PUT\n        description: Create or update an ACL\
  \ policy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaclpolicy\n        method: DELETE\n        description: Delete an ACL policy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-audit\n      path: /sys/audit\n      operations:\n      - name: listauditdevices\n        method: GET\n        description: List audit devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-audit-path\n      path: /sys/audit/{path}\n      operations:\n      - name: enableauditdevice\n   \
  \     method: PUT\n        description: Enable an audit device\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disableauditdevice\n        method: DELETE\n        description: Disable an audit device\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-leases-lookup\n      path: /sys/leases/lookup\n      operations:\n      - name: lookuplease\n        method: PUT\n        description: Lookup a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-leases-renew\n      path: /sys/leases/renew\n\
  \      operations:\n      - name: renewlease\n        method: PUT\n        description: Renew a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-leases-revoke\n      path: /sys/leases/revoke\n      operations:\n      - name: revokelease\n        method: PUT\n        description: Revoke a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-create\n      path: /auth/token/create\n      operations:\n      - name: createtoken\n        method: POST\n        description: Create a token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup\n      path: /auth/token/lookup\n      operations:\n      - name: lookuptoken\n        method: POST\n        description: Lookup a token\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup-self\n      path: /auth/token/lookup-self\n      operations:\n      - name: lookupselftoken\n        method: GET\n        description: Lookup own token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew\n      path: /auth/token/renew\n      operations:\n      - name: renewtoken\n        method: POST\n        description: Renew a token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew-self\n      path: /auth/token/renew-self\n      operations:\n      - name: renewselftoken\n        method: POST\n        description: Renew own token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: auth-token-revoke\n      path: /auth/token/revoke\n      operations:\n      - name: revoketoken\n        method: POST\n        description: Revoke a token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke-self\n      path: /auth/token/revoke-self\n      operations:\n      - name: revokeselftoken\n        method: POST\n        description: Revoke own token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-userpass-login-username\n      path: /auth/userpass/login/{username}\n      operations:\n      - name: loginuserpass\n        method: POST\n        description: Login with username and password\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: auth-approle-login\n      path: /auth/approle/login\n      operations:\n      - name: loginapprole\n        method: POST\n        description: Login with AppRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-data-path\n      path: /secret/data/{path}\n      operations:\n      - name: readkvsecret\n        method: GET\n        description: Read KV secret (v2)\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: integer\n          description: Specific version to read\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createkvsecret\n        method: POST\n        description: Create or update\
  \ KV secret (v2)\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletekvsecretlatest\n        method: DELETE\n        description: Delete latest version of KV secret\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-metadata-path\n      path: /secret/metadata/{path}\n      operations:\n      - name: getkvmetadata\n        method: GET\n        description: Read KV secret metadata\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deletekvmetadata\n        method: DELETE\n        description: Delete all versions and metadata\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-delete-path\n      path: /secret/delete/{path}\n      operations:\n      - name: deletekvsecretversions\n        method: POST\n        description: Delete specific versions of KV secret\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-undelete-path\n      path: /secret/undelete/{path}\n      operations:\n      - name: undeletekvsecretversions\n       \
  \ method: POST\n        description: Undelete versions of KV secret\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secret-destroy-path\n      path: /secret/destroy/{path}\n      operations:\n      - name: destroykvsecretversions\n        method: POST\n        description: Permanently destroy versions\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transit-encrypt-name\n      path: /transit/encrypt/{name}\n      operations:\n      - name: transitencrypt\n        method: POST\n        description: Encrypt data\n        inputParameters:\n        - name: name\n          in: path\n\
  \          type: string\n          required: true\n          description: Name of the encryption key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transit-decrypt-name\n      path: /transit/decrypt/{name}\n      operations:\n      - name: transitdecrypt\n        method: POST\n        description: Decrypt data\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transit-keys-name\n      path: /transit/keys/{name}\n      operations:\n      - name: createtransitkey\n        method: POST\n        description: Create an encryption key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: gettransitkey\n        method: GET\n        description: Read an encryption key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetransitkey\n        method: DELETE\n        description: Delete an encryption key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity\n      path: /identity/entity\n      operations:\n      - name: createentity\n        method: POST\n        description: Create an identity entity\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: identity-entity-id-id\n      path: /identity/entity/id/{id}\n      operations:\n      - name: getentity\n        method: GET\n        description: Read an entity by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateentity\n        method: POST\n        description: Update an entity\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteentity\n        method: DELETE\n        description: Delete an entity\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-generate-root-attempt\n      path: /sys/generate-root/attempt\n      operations:\n      - name: getrootgenerationprogress\n        method: GET\n        description: Read root generation progress\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startrootgeneration\n        method: PUT\n        description: Start root token generation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelrootgeneration\n        method: DELETE\n        description: Cancel root token generation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-leader\n      path:\
  \ /sys/leader\n      operations:\n      - name: getleader\n        method: GET\n        description: Get leader information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-wrapping-wrap\n      path: /sys/wrapping/wrap\n      operations:\n      - name: wrap\n        method: POST\n        description: Wrap data\n        inputParameters:\n        - name: X-Vault-Wrap-TTL\n          in: header\n          type: string\n          required: true\n          description: TTL for the wrapping token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sys-wrapping-unwrap\n      path: /sys/wrapping/unwrap\n      operations:\n      - name: unwrap\n        method: POST\n        description: Unwrap data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hashicorp-vault-rest\n    description: REST adapter for HashiCorp Vault HTTP API.\n    resources:\n    - path: /sys/init\n      name: getinitstatus\n      operations:\n      - method: GET\n        name: getinitstatus\n        description: Check initialization status\n        call: hashicorp-vault.getinitstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/init\n      name: initialize\n      operations:\n      - method: PUT\n        name: initialize\n        description: Initialize Vault\n        call: hashicorp-vault.initialize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/seal-status\n      name: getsealstatus\n      operations:\n      - method: GET\n        name: getsealstatus\n        description: Check seal status\n        call: hashicorp-vault.getsealstatus\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /sys/seal\n      name: seal\n      operations:\n      - method: PUT\n        name: seal\n        description: Seal the Vault\n        call: hashicorp-vault.seal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/unseal\n      name: unseal\n      operations:\n      - method: PUT\n        name: unseal\n        description: Submit an unseal key\n        call: hashicorp-vault.unseal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Health status\n        call: hashicorp-vault.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/mounts\n      name: listsecretengines\n      operations:\n      - method: GET\n        name: listsecretengines\n        description: List mounted secrets engines\n        call: hashicorp-vault.listsecretengines\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/mounts/{path}\n      name: enablesecretengine\n      operations:\n      - method: POST\n        name: enablesecretengine\n        description: Enable a secrets engine\n        call: hashicorp-vault.enablesecretengine\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/mounts/{path}\n      name: disablesecretengine\n      operations:\n      - method: DELETE\n        name: disablesecretengine\n        description: Disable a secrets engine\n        call: hashicorp-vault.disablesecretengine\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/auth\n      name: listauthmethods\n      operations:\n      - method: GET\n        name: listauthmethods\n        description: List auth methods\n        call: hashicorp-vault.listauthmethods\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/auth/{path}\n      name: enableauthmethod\n      operations:\n      - method: POST\n        name: enableauthmethod\n        description: Enable an auth method\n        call: hashicorp-vault.enableauthmethod\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/auth/{path}\n      name: disableauthmethod\n      operations:\n      - method: DELETE\n        name: disableauthmethod\n        description: Disable an auth method\n        call: hashicorp-vault.disableauthmethod\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/policies/acl\n      name: listaclpolicies\n      operations:\n      - method: GET\n        name: listaclpolicies\n        description: List ACL policies\n        call: hashicorp-vault.listaclpolicies\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /sys/policies/acl/{name}\n      name: getaclpolicy\n      operations:\n      - method: GET\n        name: getaclpolicy\n        description: Read an ACL policy\n        call: hashicorp-vault.getaclpolicy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/policies/acl/{name}\n      name: createaclpolicy\n      operations:\n      - method: PUT\n        name: createaclpolicy\n        description: Create or update an ACL policy\n        call: hashicorp-vault.createaclpolicy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/policies/acl/{name}\n      name: deleteaclpolicy\n      operations:\n      - method: DELETE\n        name: deleteaclpolicy\n        description: Delete an ACL policy\n        call: hashicorp-vault.deleteaclpolicy\n        with:\n          name: rest.name\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/audit\n      name: listauditdevices\n      operations:\n      - method: GET\n        name: listauditdevices\n        description: List audit devices\n        call: hashicorp-vault.listauditdevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/audit/{path}\n      name: enableauditdevice\n      operations:\n      - method: PUT\n        name: enableauditdevice\n        description: Enable an audit device\n        call: hashicorp-vault.enableauditdevice\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/audit/{path}\n      name: disableauditdevice\n      operations:\n      - method: DELETE\n        name: disableauditdevice\n        description: Disable an audit device\n        call: hashicorp-vault.disableauditdevice\n        with:\n          path: rest.path\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /sys/leases/lookup\n      name: lookuplease\n      operations:\n      - method: PUT\n        name: lookuplease\n        description: Lookup a lease\n        call: hashicorp-vault.lookuplease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/leases/renew\n      name: renewlease\n      operations:\n      - method: PUT\n        name: renewlease\n        description: Renew a lease\n        call: hashicorp-vault.renewlease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sys/leases/revoke\n      name: revokelease\n      operations:\n      - method: PUT\n        name: revokelease\n        description: Revoke a lease\n        call: hashicorp-vault.revokelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/create\n      name: createtoken\n      operations:\n      - method: POST\n        name: createtoken\n\
  \        description: Create a token\n        call: hashicorp-vault.createtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup\n      name: lookuptoken\n      operations:\n      - method: POST\n        name: lookuptoken\n        description: Lookup a token\n        call: hashicorp-vault.lookuptoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup-self\n      name: lookupselftoken\n      operations:\n      - method: GET\n        name: lookupselftoken\n        description: Lookup own token\n        call: hashicorp-vault.lookupselftoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/renew\n      name: renewtoken\n      operations:\n      - method: POST\n        name: renewtoken\n        description: Renew a token\n        call: hashicorp-vault.renewtoken\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /auth/token/renew-self\n      name: renewselftoken\n      operations:\n      - method: POST\n        name: renewselftoken\n        description: Renew own token\n        call: hashicorp-vault.renewselftoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke\n      name: revoketoken\n      operations:\n      - method: POST\n        name: revoketoken\n        description: Revoke a token\n        call: hashicorp-vault.revoketoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke-self\n      name: revokeselftoken\n      operations:\n      - method: POST\n        name: revokeselftoken\n        description: Revoke own token\n        call: hashicorp-vault.revokeselftoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/userpass/login/{username}\n      name: loginuserpass\n      operations:\n      - method: POST\n        name:\
  \ loginuserpass\n        description: Login with username and password\n        call: hashicorp-vault.loginuserpass\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/approle/login\n      name: loginapprole\n      operations:\n      - method: POST\n        name: loginapprole\n        description: Login with AppRole\n        call: hashicorp-vault.loginapprole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/data/{path}\n      name: readkvsecret\n      operations:\n      - method: GET\n        name: readkvsecret\n        description: Read KV secret (v2)\n        call: hashicorp-vault.readkvsecret\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/data/{path}\n      name: createkvsecret\n      operations:\n      - method: POST\n        name: createkvsecret\n        description:\
  \ Create or update KV secret (v2)\n        call: hashicorp-vault.createkvsecret\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/data/{path}\n      name: deletekvsecretlatest\n      operations:\n      - method: DELETE\n        name: deletekvsecretlatest\n        description: Delete latest version of KV secret\n        call: hashicorp-vault.deletekvsecretlatest\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/metadata/{path}\n      name: getkvmetadata\n      operations:\n      - method: GET\n        name: getkvmetadata\n        description: Read KV secret metadata\n        call: hashicorp-vault.getkvmetadata\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/metadata/{path}\n      name: deletekvmetadata\n      operations:\n     \
  \ - method: DELETE\n        name: deletekvmetadata\n        description: Delete all versions and metadata\n        call: hashicorp-vault.deletekvmetadata\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/delete/{path}\n      name: deletekvsecretversions\n      operations:\n      - method: POST\n        name: deletekvsecretversions\n        description: Delete specific versions of KV secret\n        call: hashicorp-vault.deletekvsecretversions\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secret/undelete/{path}\n      name: undeletekvsecretversions\n      operations:\n      - method: POST\n        name: undeletekvsecretversions\n        description: Undelete versions of KV secret\n        call: hashicorp-vault.undeletekvsecretversions\n        with:\n          path: rest.path\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /secret/destroy/{path}\n      name: destroykvsecretversions\n      operations:\n      - method: POST\n        name: destroykvsecretversions\n        description: Permanently destroy versions\n        call: hashicorp-vault.destroykvsecretversions\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transit/encrypt/{name}\n      name: transitencrypt\n      operations:\n      - method: POST\n        name: transitencrypt\n        description: Encrypt data\n        call: hashicorp-vault.transitencrypt\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transit/decrypt/{name}\n      name: transitdecrypt\n      operations:\n      - method: POST\n        name: transitdecrypt\n        description: Decrypt data\n        call: hashicorp-vault.transitdecrypt\n        with:\n          name: rest.name\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transit/keys/{name}\n      name: createtransitkey\n      operations:\n      - method: POST\n        name: createtransitkey\n        description: Create an encryption key\n        call: hashicorp-vault.createtransitkey\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transit/keys/{name}\n      name: gettransitkey\n      operations:\n      - method: GET\n        name: gettransitkey\n        description: Read an encryption key\n        call: hashicorp-vault.gettransitkey\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transit/keys/{name}\n      name: deletetransitkey\n      operations:\n      - method: DELETE\n        name: deletetransitkey\n        description: Delete an\n\n# --- truncated at 32 KB (53 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hashicorp-vault/refs/heads/main/capabilities/hashicorp-vault-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hashicorp-vault/refs/heads/main/capabilities/hashicorp-vault-capability.yaml
tags:
- Hashicorp
- Vault
- API
tools:
- description: Check initialization status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinitstatus
- description: Initialize Vault
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: initialize
- description: Check seal status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsealstatus
- description: Seal the Vault
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: seal
- description: Submit an unseal key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unseal
- description: Health status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: List mounted secrets engines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecretengines
- description: Enable a secrets engine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: enablesecretengine
- description: Disable a secrets engine
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disablesecretengine
- description: List auth methods
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthmethods
- description: Enable an auth method
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: enableauthmethod
- description: Disable an auth method
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disableauthmethod
- description: List ACL policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaclpolicies
- description: Read an ACL policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaclpolicy
- description: Create or update an ACL policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createaclpolicy
- description: Delete an ACL policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaclpolicy
- description: List audit devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauditdevices
- description: Enable an audit device
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: enableauditdevice
- description: Disable an audit device
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disableauditdevice
- description: Lookup a lease
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: lookuplease
- description: Renew a lease
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: renewlease
- description: Revoke a lease
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: revokelease
- description: Create a token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtoken
- description: Lookup a token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lookuptoken
- description: Lookup own token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lookupselftoken
- description: Renew a token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewtoken
- description: Renew own token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewselftoken
- description: Revoke a token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revoketoken
- description: Revoke own token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeselftoken
- description: Login with username and password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginuserpass
- description: Login with AppRole
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginapprole
- description: Read KV secret (v2)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readkvsecret
- description: Create or update KV secret (v2)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkvsecret
- description: Delete latest version of KV secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekvsecretlatest
- description: Read KV secret metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkvmetadata
- description: Delete all versions and metadata
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekvmetadata
- description: Delete specific versions of KV secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletekvsecretversions
- description: Undelete versions of KV secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: undeletekvsecretversions
- description: Permanently destroy versions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: destroykvsecretversions
- description: Encrypt data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: transitencrypt
- description: Decrypt data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: transitdecrypt
- description: Create an encryption key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransitkey
- description: Read an encryption key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransitkey
- description: Delete an encryption key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetransitkey
- description: Create an identity entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentity
- description: Read an entity by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentity
- description: Update an entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateentity
- description: Delete an entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteentity
- description: Read root generation progress
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrootgenerationprogress
- description: Start root token generation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: startrootgeneration
- description: Cancel root token generation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelrootgeneration
- description: Get leader information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getleader
- description: Wrap data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: wrap
- description: Unwrap data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unwrap
---
