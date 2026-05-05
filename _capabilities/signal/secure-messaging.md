---
api_specs:
- filename: signal-server-openapi.yml
  format: yaml
  label: signal-server
  slug: signal-server
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/signal/refs/heads/main/openapi/signal-server-openapi.yml
categories: []
consumed_apis:
- signal-server
description: Unified workflow capability for Signal Private Messenger server integration, enabling secure end-to-end encrypted messaging operations. Covers account lifecycle management, linked device provisioning, pre-key bundle distribution for the Signal Protocol key exchange, encrypted message delivery, and user profile management. Designed for self-hosted Signal Server deployments and developers building Signal-compatible secure messaging applications.
layout: capability
name: Signal Secure Messaging
operations:
- description: Get the current Signal account identity
  method: GET
  name: get-account-identity
  path: /v1/accounts/identity
- description: Configure account capabilities and settings
  method: PUT
  name: set-account-attributes
  path: /v1/accounts/attributes
- description: List all devices linked to the account
  method: GET
  name: list-devices
  path: /v1/devices
- description: Send end-to-end encrypted messages to a destination account
  method: PUT
  name: send-message
  path: /v1/messages/{destinationUuid}
- description: Get pre-key bundle for initiating a Signal Protocol session
  method: GET
  name: get-pre-key-bundle
  path: /v2/keys
- description: Get Signal user profile
  method: GET
  name: get-profile
  path: /v1/profile/{uuid}
personas: []
provider_name: Signal
provider_slug: signal
search_terms:
- list linked devices
- send end-to-end encrypted messages to a destination account
- send encrypted message
- register a new signal account with a phone number (for self-hosted deployments)
- security
- get pre-key bundle for initiating a signal protocol session
- send message
- account identity
- open source
- set account attributes
- get pre key bundle
- get profile
- configure account capabilities and settings
- encryption
- cryptography
- list devices
- pre-key bundle management for signal protocol
- list all devices linked to the account
- user profile management
- register account
- end-to-end encryption
- get signal user profile
- configure signal account capabilities such as voice, video, and push notification settings
- list all devices linked to the signal account including device ids and last seen timestamps
- send end-to-end encrypted signal protocol messages to a destination account uuid
- get user profile
- get the signal profile for a user by their account uuid
- encrypted message delivery
- get account identity
- retrieve pre-key bundle for establishing a new signal protocol encrypted session with a contact
- signal protocol
- linked device management
- account configuration
- get the current signal account identity
- get the signal account identity including uuid and phone number for the authenticated user
- messaging
- privacy
slug: secure-messaging
source_filename: secure-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Signal Secure Messaging\"\n  description: >-\n    Unified workflow capability for Signal Private Messenger server integration,\n    enabling secure end-to-end encrypted messaging operations. Covers account\n    lifecycle management, linked device provisioning, pre-key bundle distribution\n    for the Signal Protocol key exchange, encrypted message delivery, and user\n    profile management. Designed for self-hosted Signal Server deployments and\n    developers building Signal-compatible secure messaging applications.\n  tags:\n    - Messaging\n    - Encryption\n    - Privacy\n    - Security\n    - Signal Protocol\n    - Open Source\n    - End-to-End Encryption\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIGNAL_USERNAME: SIGNAL_USERNAME\n      SIGNAL_PASSWORD: SIGNAL_PASSWORD\n\ncapability:\n  consumes:\n    - import: signal-server\n      location: ./shared/signal-server.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: signal-secure-messaging-api\n      description: \"Unified REST API for Signal secure messaging server operations.\"\n      resources:\n        - path: /v1/accounts/identity\n          name: account-identity\n          description: \"Account identity\"\n          operations:\n            - method: GET\n              name: get-account-identity\n              description: \"Get the current Signal account identity\"\n              call: \"signal-server.get-account-identity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/attributes\n          name: account-attributes\n          description: \"Account configuration\"\n          operations:\n            - method: PUT\n              name: set-account-attributes\n              description: \"Configure account capabilities and settings\"\n              call: \"signal-server.set-account-attributes\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices\n          name: devices\n          description: \"Linked device management\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List all devices linked to the account\"\n              call: \"signal-server.list-devices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages/{destinationUuid}\n          name: messages\n          description: \"Encrypted message delivery\"\n          operations:\n            - method: PUT\n              name: send-message\n              description: \"Send end-to-end encrypted messages to a destination account\"\n              call: \"signal-server.send-message\"\n              with:\n                destinationUuid: \"rest.destinationUuid\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n\n        - path: /v2/keys\n          name: pre-keys\n          description: \"Pre-key bundle management for Signal Protocol\"\n          operations:\n            - method: GET\n              name: get-pre-key-bundle\n              description: \"Get pre-key bundle for initiating a Signal Protocol session\"\n              call: \"signal-server.get-pre-key-bundle\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/profile/{uuid}\n          name: profile\n          description: \"User profile management\"\n          operations:\n            - method: GET\n              name: get-profile\n              description: \"Get Signal user profile\"\n              call: \"signal-server.get-profile\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9090\n      namespace: signal-secure-messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Signal secure messaging server management.\"\n      tools:\n        - name: get-account-identity\n          description: \"Get the Signal account identity including UUID and phone number for the authenticated user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"signal-server.get-account-identity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: set-account-attributes\n          description: \"Configure Signal account capabilities such as voice, video, and push notification settings\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"signal-server.set-account-attributes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n  \
  \      - name: list-linked-devices\n          description: \"List all devices linked to the Signal account including device IDs and last seen timestamps\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"signal-server.list-devices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-encrypted-message\n          description: \"Send end-to-end encrypted Signal Protocol messages to a destination account UUID\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"signal-server.send-message\"\n          with:\n            destinationUuid: \"tools.destinationUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pre-key-bundle\n          description: \"Retrieve pre-key bundle for establishing a new Signal Protocol encrypted session with a contact\"\n\
  \          hints:\n            readOnly: true\n            openWorld: false\n          call: \"signal-server.get-pre-key-bundle\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-profile\n          description: \"Get the Signal profile for a user by their account UUID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"signal-server.get-profile\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: register-account\n          description: \"Register a new Signal account with a phone number (for self-hosted deployments)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"signal-server.register-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/signal/refs/heads/main/capabilities/secure-messaging.yaml
tags:
- Messaging
- Encryption
- Privacy
- Security
- Signal Protocol
- Open Source
- End-to-End Encryption
tools:
- description: Get the Signal account identity including UUID and phone number for the authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: get-account-identity
- description: Configure Signal account capabilities such as voice, video, and push notification settings
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-account-attributes
- description: List all devices linked to the Signal account including device IDs and last seen timestamps
  hints:
    openWorld: false
    readOnly: true
  name: list-linked-devices
- description: Send end-to-end encrypted Signal Protocol messages to a destination account UUID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-encrypted-message
- description: Retrieve pre-key bundle for establishing a new Signal Protocol encrypted session with a contact
  hints:
    openWorld: false
    readOnly: true
  name: get-pre-key-bundle
- description: Get the Signal profile for a user by their account UUID
  hints:
    openWorld: false
    readOnly: true
  name: get-user-profile
- description: Register a new Signal account with a phone number (for self-hosted deployments)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: register-account
---
