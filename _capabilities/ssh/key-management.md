---
categories: []
consumed_apis:
- ssh-key-management
description: Unified workflow capability for SSH key lifecycle management, certificate authority operations, and access control. Enables security and infrastructure teams to manage SSH keys, sign short-lived certificates, control user access via authorized_keys, and maintain known_hosts integrity.
layout: capability
name: SSH Key Management
operations:
- description: List registered SSH public keys
  method: GET
  name: list-keys
  path: /v1/keys
- description: Register a new SSH public key
  method: POST
  name: add-key
  path: /v1/keys
- description: Generate a new SSH key pair
  method: POST
  name: generate-key-pair
  path: /v1/keys/generate
- description: Get SSH key details
  method: GET
  name: get-key
  path: /v1/keys/{keyId}
- description: Delete an SSH key
  method: DELETE
  name: delete-key
  path: /v1/keys/{keyId}
- description: List issued SSH certificates
  method: GET
  name: list-certificates
  path: /v1/certificates
- description: Sign a public key to create a certificate
  method: POST
  name: sign-certificate
  path: /v1/certificates
- description: Get authorized keys for a user
  method: GET
  name: get-authorized-keys
  path: /v1/authorized-keys/{username}
- description: Add a key to user authorized_keys
  method: POST
  name: add-authorized-key
  path: /v1/authorized-keys/{username}
- description: List known SSH hosts
  method: GET
  name: list-known-hosts
  path: /v1/known-hosts
- description: Add a host to known_hosts
  method: POST
  name: add-known-host
  path: /v1/known-hosts
personas: []
provider_name: SSH
provider_slug: ssh
search_terms:
- register a new ssh public key
- list registered ssh public keys with optional user and type filtering
- certificate authority
- get ssh key details
- security
- register a new ssh public key in the system
- access control
- get authorized keys
- list keys
- list known ssh hosts and their verified public keys
- known hosts management
- remote access
- list issued ssh certificates
- add a key to user authorized_keys
- sign a public key to create a certificate
- ssh certificate management
- sign certificate
- cryptography
- get key
- add key
- ssh
- network security
- generate key pair
- key management
- get ssh key details including fingerprint and last use
- delete a registered ssh key
- add an ssh public key to a user's authorized_keys
- ssh key registration
- add a host to known_hosts
- secure shell
- list known ssh hosts
- sign an ssh public key with the ca to create a short-lived certificate
- individual key management
- generate a new ssh key pair
- delete an ssh key
- list certificates
- add authorized key
- generate a new ssh key pair (ed25519 recommended)
- get all authorized ssh keys for a user
- system administration
- delete key
- user authorized keys
- add known host
- infrastructure
- list issued ssh certificates with principals and validity periods
- list registered ssh public keys
- get authorized keys for a user
- key pair generation
- add a host and its public key to the known_hosts database
- list known hosts
slug: key-management
source_filename: key-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SSH Key Management\"\n  description: >-\n    Unified workflow capability for SSH key lifecycle management, certificate\n    authority operations, and access control. Enables security and infrastructure\n    teams to manage SSH keys, sign short-lived certificates, control user access\n    via authorized_keys, and maintain known_hosts integrity.\n  tags:\n    - SSH\n    - Key Management\n    - Certificate Authority\n    - Access Control\n    - Security\n    - Infrastructure\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SSH_MGMT_API_TOKEN: SSH_MGMT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: ssh-key-management\n      location: ./shared/key-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ssh-key-management-workflow-api\n      description: \"Unified REST API for SSH key management and certificate authority operations.\"\n      resources:\n\
  \        - path: /v1/keys\n          name: keys\n          description: \"SSH key registration\"\n          operations:\n            - method: GET\n              name: list-keys\n              description: \"List registered SSH public keys\"\n              call: \"ssh-key-management.list-keys\"\n              with:\n                userId: \"rest.userId\"\n                keyType: \"rest.keyType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-key\n              description: \"Register a new SSH public key\"\n              call: \"ssh-key-management.add-key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/keys/generate\n          name: key-generation\n          description: \"Key pair generation\"\n          operations:\n            - method: POST\n              name: generate-key-pair\n              description:\
  \ \"Generate a new SSH key pair\"\n              call: \"ssh-key-management.generate-key-pair\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/keys/{keyId}\n          name: key-detail\n          description: \"Individual key management\"\n          operations:\n            - method: GET\n              name: get-key\n              description: \"Get SSH key details\"\n              call: \"ssh-key-management.get-key\"\n              with:\n                keyId: \"rest.keyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-key\n              description: \"Delete an SSH key\"\n              call: \"ssh-key-management.delete-key\"\n              with:\n                keyId: \"rest.keyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certificates\n\
  \          name: certificates\n          description: \"SSH certificate management\"\n          operations:\n            - method: GET\n              name: list-certificates\n              description: \"List issued SSH certificates\"\n              call: \"ssh-key-management.list-certificates\"\n              with:\n                principal: \"rest.principal\"\n                expired: \"rest.expired\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: sign-certificate\n              description: \"Sign a public key to create a certificate\"\n              call: \"ssh-key-management.sign-certificate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/authorized-keys/{username}\n          name: authorized-keys\n          description: \"User authorized keys\"\n          operations:\n            - method: GET\n         \
  \     name: get-authorized-keys\n              description: \"Get authorized keys for a user\"\n              call: \"ssh-key-management.get-authorized-keys\"\n              with:\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-authorized-key\n              description: \"Add a key to user authorized_keys\"\n              call: \"ssh-key-management.add-authorized-key\"\n              with:\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/known-hosts\n          name: known-hosts\n          description: \"Known hosts management\"\n          operations:\n            - method: GET\n              name: list-known-hosts\n              description: \"List known SSH hosts\"\n              call: \"ssh-key-management.list-known-hosts\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-known-host\n              description: \"Add a host to known_hosts\"\n              call: \"ssh-key-management.add-known-host\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ssh-key-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SSH key management and certificate operations.\"\n      tools:\n        - name: list-keys\n          description: \"List registered SSH public keys with optional user and type filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssh-key-management.list-keys\"\n          with:\n            userId: \"tools.userId\"\n            keyType: \"tools.keyType\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: add-key\n          description: \"Register a new SSH public key in the system\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssh-key-management.add-key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-key-pair\n          description: \"Generate a new SSH key pair (ed25519 recommended)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssh-key-management.generate-key-pair\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-key\n          description: \"Get SSH key details including fingerprint and last use\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssh-key-management.get-key\"\n          with:\n            keyId: \"tools.keyId\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: delete-key\n          description: \"Delete a registered SSH key\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ssh-key-management.delete-key\"\n          with:\n            keyId: \"tools.keyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sign-certificate\n          description: \"Sign an SSH public key with the CA to create a short-lived certificate\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssh-key-management.sign-certificate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-certificates\n          description: \"List issued SSH certificates with principals and validity periods\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"ssh-key-management.list-certificates\"\n          with:\n            principal: \"tools.principal\"\n            expired: \"tools.expired\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-authorized-keys\n          description: \"Get all authorized SSH keys for a user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssh-key-management.get-authorized-keys\"\n          with:\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-authorized-key\n          description: \"Add an SSH public key to a user's authorized_keys\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssh-key-management.add-authorized-key\"\n          with:\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-known-hosts\n          description: \"List known SSH hosts and their verified public keys\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssh-key-management.list-known-hosts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-known-host\n          description: \"Add a host and its public key to the known_hosts database\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssh-key-management.add-known-host\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ssh/refs/heads/main/capabilities/key-management.yaml
tags:
- SSH
- Key Management
- Certificate Authority
- Access Control
- Security
- Infrastructure
tools:
- description: List registered SSH public keys with optional user and type filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-keys
- description: Register a new SSH public key in the system
  hints:
    idempotent: false
    readOnly: false
  name: add-key
- description: Generate a new SSH key pair (ed25519 recommended)
  hints:
    idempotent: false
    readOnly: false
  name: generate-key-pair
- description: Get SSH key details including fingerprint and last use
  hints:
    idempotent: true
    readOnly: true
  name: get-key
- description: Delete a registered SSH key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-key
- description: Sign an SSH public key with the CA to create a short-lived certificate
  hints:
    idempotent: false
    readOnly: false
  name: sign-certificate
- description: List issued SSH certificates with principals and validity periods
  hints:
    idempotent: true
    readOnly: true
  name: list-certificates
- description: Get all authorized SSH keys for a user
  hints:
    idempotent: true
    readOnly: true
  name: get-authorized-keys
- description: Add an SSH public key to a user's authorized_keys
  hints:
    idempotent: false
    readOnly: false
  name: add-authorized-key
- description: List known SSH hosts and their verified public keys
  hints:
    idempotent: true
    readOnly: true
  name: list-known-hosts
- description: Add a host and its public key to the known_hosts database
  hints:
    idempotent: false
    readOnly: false
  name: add-known-host
---
