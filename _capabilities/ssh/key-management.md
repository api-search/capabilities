---
categories: []
consumed_apis: []
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
- add a host to known_hosts
- get authorized keys
- cryptography
- key management
- system administration
- infrastructure
- list known ssh hosts
- generate key pair
- sign an ssh public key with the ca to create a short-lived certificate
- register a new ssh public key
- ssh certificate management
- delete a registered ssh key
- secure shell
- get key
- sign certificate
- list issued ssh certificates with principals and validity periods
- user authorized keys
- security
- certificate authority
- list issued ssh certificates
- list certificates
- delete key
- ssh
- add authorized key
- known hosts management
- get ssh key details including fingerprint and last use
- delete an ssh key
- generate a new ssh key pair (ed25519 recommended)
- network security
- add a key to user authorized_keys
- remote access
- add a host and its public key to the known_hosts database
- list registered ssh public keys with optional user and type filtering
- sign a public key to create a certificate
- get ssh key details
- list registered ssh public keys
- register a new ssh public key in the system
- generate a new ssh key pair
- access control
- add an ssh public key to a user's authorized_keys
- individual key management
- add known host
- list known hosts
- key pair generation
- get all authorized ssh keys for a user
- list known ssh hosts and their verified public keys
- ssh key registration
- list keys
- add key
- get authorized keys for a user
slug: key-management
source_filename: key-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SSH Key Management\n  description: Unified workflow capability for SSH key lifecycle management, certificate authority operations, and access\n    control. Enables security and infrastructure teams to manage SSH keys, sign short-lived certificates, control user access\n    via authorized_keys, and maintain known_hosts integrity.\n  tags:\n  - SSH\n  - Key Management\n  - Certificate Authority\n  - Access Control\n  - Security\n  - Infrastructure\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SSH_MGMT_API_TOKEN: SSH_MGMT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ssh-key-management\n    baseUri: https://api.openssh.example.com/v1\n    description: SSH Key Management REST API\n    authentication:\n      type: bearer\n      token: '{{SSH_MGMT_API_TOKEN}}'\n    resources:\n    - name: keys\n      path: /keys\n      description: SSH key registration and management\n      operations:\n\
  \      - name: list-keys\n        method: GET\n        description: List registered SSH keys\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n          required: false\n        - name: keyType\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-key\n        method: POST\n        description: Register a new SSH public key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            publicKey: '{{tools.publicKey}}'\n            comment: '{{tools.comment}}'\n    - name: generate-key-pair\n      path: /keys/generate\n      description: SSH key pair generation\n      operations:\n      - name: generate-key-pair\n        method: POST\n        description:\
  \ Generate a new SSH key pair\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-by-id\n      path: /keys/{keyId}\n      description: Individual key management\n      operations:\n      - name: get-key\n        method: GET\n        description: Get SSH key details\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-key\n        method: DELETE\n        description: Delete an SSH key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates\n      path: /certificates\n     \
  \ description: SSH certificate authority operations\n      operations:\n      - name: sign-certificate\n        method: POST\n        description: Sign an SSH public key to create a certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-certificates\n        method: GET\n        description: List issued SSH certificates\n        inputParameters:\n        - name: principal\n          in: query\n          type: string\n          required: false\n        - name: expired\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authorized-keys\n      path: /authorized-keys/{username}\n      description: Authorized keys management\n      operations:\n      - name: get-authorized-keys\n        method: GET\n        description: Get authorized\
  \ keys for a user\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-authorized-key\n        method: POST\n        description: Add a key to user authorized_keys\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: known-hosts\n      path: /known-hosts\n      description: Known hosts management\n      operations:\n      - name: list-known-hosts\n        method: GET\n        description: List known SSH hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-known-host\n    \
  \    method: POST\n        description: Add a host to known_hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ssh-key-management-workflow-api\n    description: Unified REST API for SSH key management and certificate authority operations.\n    resources:\n    - path: /v1/keys\n      name: keys\n      description: SSH key registration\n      operations:\n      - method: GET\n        name: list-keys\n        description: List registered SSH public keys\n        call: ssh-key-management.list-keys\n        with:\n          userId: rest.userId\n          keyType: rest.keyType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-key\n        description: Register a new SSH public key\n        call: ssh-key-management.add-key\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/keys/generate\n      name: key-generation\n      description: Key pair generation\n      operations:\n      - method: POST\n        name: generate-key-pair\n        description: Generate a new SSH key pair\n        call: ssh-key-management.generate-key-pair\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{keyId}\n      name: key-detail\n      description: Individual key management\n      operations:\n      - method: GET\n        name: get-key\n        description: Get SSH key details\n        call: ssh-key-management.get-key\n        with:\n          keyId: rest.keyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-key\n        description: Delete an SSH key\n        call: ssh-key-management.delete-key\n        with:\n          keyId: rest.keyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certificates\n\
  \      name: certificates\n      description: SSH certificate management\n      operations:\n      - method: GET\n        name: list-certificates\n        description: List issued SSH certificates\n        call: ssh-key-management.list-certificates\n        with:\n          principal: rest.principal\n          expired: rest.expired\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: sign-certificate\n        description: Sign a public key to create a certificate\n        call: ssh-key-management.sign-certificate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authorized-keys/{username}\n      name: authorized-keys\n      description: User authorized keys\n      operations:\n      - method: GET\n        name: get-authorized-keys\n        description: Get authorized keys for a user\n        call: ssh-key-management.get-authorized-keys\n        with:\n          username: rest.username\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-authorized-key\n        description: Add a key to user authorized_keys\n        call: ssh-key-management.add-authorized-key\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/known-hosts\n      name: known-hosts\n      description: Known hosts management\n      operations:\n      - method: GET\n        name: list-known-hosts\n        description: List known SSH hosts\n        call: ssh-key-management.list-known-hosts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-known-host\n        description: Add a host to known_hosts\n        call: ssh-key-management.add-known-host\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ssh-key-management-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted SSH key management and certificate operations.\n    tools:\n    - name: list-keys\n      description: List registered SSH public keys with optional user and type filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssh-key-management.list-keys\n      with:\n        userId: tools.userId\n        keyType: tools.keyType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-key\n      description: Register a new SSH public key in the system\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssh-key-management.add-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-key-pair\n      description: Generate a new SSH key pair (ed25519 recommended)\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssh-key-management.generate-key-pair\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: get-key\n      description: Get SSH key details including fingerprint and last use\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssh-key-management.get-key\n      with:\n        keyId: tools.keyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-key\n      description: Delete a registered SSH key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ssh-key-management.delete-key\n      with:\n        keyId: tools.keyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sign-certificate\n      description: Sign an SSH public key with the CA to create a short-lived certificate\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssh-key-management.sign-certificate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-certificates\n      description: List\
  \ issued SSH certificates with principals and validity periods\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssh-key-management.list-certificates\n      with:\n        principal: tools.principal\n        expired: tools.expired\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-authorized-keys\n      description: Get all authorized SSH keys for a user\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssh-key-management.get-authorized-keys\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-authorized-key\n      description: Add an SSH public key to a user's authorized_keys\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssh-key-management.add-authorized-key\n      with:\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-known-hosts\n\
  \      description: List known SSH hosts and their verified public keys\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssh-key-management.list-known-hosts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-known-host\n      description: Add a host and its public key to the known_hosts database\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssh-key-management.add-known-host\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
