---
categories: []
consumed_apis: []
description: The Google Wallet API enables developers to create and manage digital passes including event tickets, boarding passes, loyalty cards, gift cards, offers, transit passes, and generic passes. It provides REST endpoints for creating pass classes (templates) and pass objects (instances), managing issuers, handling media uploads, and generating JWT tokens for save-to-wallet functionality.
layout: capability
name: Google Wallet API
operations:
- description: Google Wallet Insert Generic Class
  method: POST
  name: insertgenericclass
  path: /genericClass
- description: Google Wallet List Generic Classes
  method: GET
  name: listgenericclasses
  path: /genericClass
- description: Google Wallet Get Generic Class
  method: GET
  name: getgenericclass
  path: /genericClass/{resourceId}
- description: Google Wallet Update Generic Class
  method: PUT
  name: updategenericclass
  path: /genericClass/{resourceId}
- description: Google Wallet Insert Generic Object
  method: POST
  name: insertgenericobject
  path: /genericObject
- description: Google Wallet Get Generic Object
  method: GET
  name: getgenericobject
  path: /genericObject/{resourceId}
- description: Google Wallet Insert Event Ticket Class
  method: POST
  name: inserteventticketclass
  path: /eventTicketClass
- description: Google Wallet Insert Loyalty Class
  method: POST
  name: insertloyaltyclass
  path: /loyaltyClass
- description: Google Wallet List Issuers
  method: GET
  name: listissuers
  path: /issuer
- description: Google Wallet Insert JWT
  method: POST
  name: insertjwt
  path: /jwt
personas: []
provider_name: Google Wallet
provider_slug: google-wallet
search_terms:
- google wallet insert generic class
- google wallet insert generic object
- google wallet insert event ticket class
- google wallet list generic classes
- google wallet list issuers
- passes
- updategenericclass
- insertgenericclass
- google wallet get generic object
- google
- loyalty cards
- inserteventticketclass
- listgenericclasses
- getgenericclass
- api
- mobile payments
- google wallet update generic class
- wallet
- google wallet insert loyalty class
- digital wallet
- getgenericobject
- google wallet insert jwt
- insertgenericobject
- insertloyaltyclass
- insertjwt
- google wallet get generic class
- listissuers
- tickets
- google wallet
slug: google-wallet-capability
source_filename: google-wallet-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Wallet API\n  description: The Google Wallet API enables developers to create and manage digital passes including event tickets, boarding\n    passes, loyalty cards, gift cards, offers, transit passes, and generic passes. It provides REST endpoints for creating\n    pass classes (templates) and pass objects (instances), managing issuers, handling media uploads, and generating JWT tokens\n    for save-to-wallet functionality.\n  tags:\n  - Google\n  - Wallet\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-wallet\n    baseUri: https://walletobjects.googleapis.com/walletobjects/v1\n    description: Google Wallet API HTTP API.\n    resources:\n    - name: genericclass\n      path: /genericClass\n      operations:\n      - name: insertgenericclass\n        method: POST\n        description: Google Wallet Insert Generic Class\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listgenericclasses\n        method: GET\n        description: Google Wallet List Generic Classes\n        inputParameters:\n        - name: issuerId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: genericclass-resourceid\n      path: /genericClass/{resourceId}\n      operations:\n      - name: getgenericclass\n        method: GET\n        description: Google Wallet Get Generic Class\n        inputParameters:\n        - name: resourceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategenericclass\n        method: PUT\n        description: Google Wallet\
  \ Update Generic Class\n        inputParameters:\n        - name: resourceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: genericobject\n      path: /genericObject\n      operations:\n      - name: insertgenericobject\n        method: POST\n        description: Google Wallet Insert Generic Object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: genericobject-resourceid\n      path: /genericObject/{resourceId}\n      operations:\n      - name: getgenericobject\n        method: GET\n        description: Google Wallet Get Generic Object\n        inputParameters:\n        - name: resourceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: eventticketclass\n      path: /eventTicketClass\n      operations:\n      - name: inserteventticketclass\n        method: POST\n        description: Google Wallet Insert Event Ticket Class\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyaltyclass\n      path: /loyaltyClass\n      operations:\n      - name: insertloyaltyclass\n        method: POST\n        description: Google Wallet Insert Loyalty Class\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issuer\n      path: /issuer\n      operations:\n      - name: listissuers\n        method: GET\n        description: Google Wallet List Issuers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jwt\n      path:\
  \ /jwt\n      operations:\n      - name: insertjwt\n        method: POST\n        description: Google Wallet Insert JWT\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-wallet-rest\n    description: REST adapter for Google Wallet API.\n    resources:\n    - path: /genericClass\n      name: insertgenericclass\n      operations:\n      - method: POST\n        name: insertgenericclass\n        description: Google Wallet Insert Generic Class\n        call: google-wallet.insertgenericclass\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /genericClass\n      name: listgenericclasses\n      operations:\n      - method: GET\n        name: listgenericclasses\n        description: Google Wallet List Generic Classes\n        call: google-wallet.listgenericclasses\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /genericClass/{resourceId}\n      name: getgenericclass\n      operations:\n      - method: GET\n        name: getgenericclass\n        description: Google Wallet Get Generic Class\n        call: google-wallet.getgenericclass\n        with:\n          resourceId: rest.resourceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /genericClass/{resourceId}\n      name: updategenericclass\n      operations:\n      - method: PUT\n        name: updategenericclass\n        description: Google Wallet Update Generic Class\n        call: google-wallet.updategenericclass\n        with:\n          resourceId: rest.resourceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /genericObject\n      name: insertgenericobject\n      operations:\n      - method: POST\n        name: insertgenericobject\n        description: Google Wallet Insert Generic Object\n        call: google-wallet.insertgenericobject\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /genericObject/{resourceId}\n      name: getgenericobject\n      operations:\n      - method: GET\n        name: getgenericobject\n        description: Google Wallet Get Generic Object\n        call: google-wallet.getgenericobject\n        with:\n          resourceId: rest.resourceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /eventTicketClass\n      name: inserteventticketclass\n      operations:\n      - method: POST\n        name: inserteventticketclass\n        description: Google Wallet Insert Event Ticket Class\n        call: google-wallet.inserteventticketclass\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loyaltyClass\n      name: insertloyaltyclass\n      operations:\n      - method: POST\n        name: insertloyaltyclass\n        description: Google Wallet Insert Loyalty Class\n        call: google-wallet.insertloyaltyclass\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /issuer\n      name: listissuers\n      operations:\n      - method: GET\n        name: listissuers\n        description: Google Wallet List Issuers\n        call: google-wallet.listissuers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jwt\n      name: insertjwt\n      operations:\n      - method: POST\n        name: insertjwt\n        description: Google Wallet Insert JWT\n        call: google-wallet.insertjwt\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-wallet-mcp\n    transport: http\n    description: MCP adapter for Google Wallet API for AI agent use.\n    tools:\n    - name: insertgenericclass\n      description: Google Wallet Insert Generic Class\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-wallet.insertgenericclass\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgenericclasses\n      description: Google Wallet List Generic Classes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-wallet.listgenericclasses\n      with:\n        issuerId: tools.issuerId\n      inputParameters:\n      - name: issuerId\n        type: string\n        description: issuerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgenericclass\n      description: Google Wallet Get Generic Class\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-wallet.getgenericclass\n      with:\n        resourceId: tools.resourceId\n      inputParameters:\n      - name: resourceId\n        type: string\n        description: resourceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: updategenericclass\n      description: Google Wallet Update Generic Class\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-wallet.updategenericclass\n      with:\n        resourceId: tools.resourceId\n      inputParameters:\n      - name: resourceId\n        type: string\n        description: resourceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertgenericobject\n      description: Google Wallet Insert Generic Object\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-wallet.insertgenericobject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgenericobject\n      description: Google Wallet Get Generic Object\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-wallet.getgenericobject\n      with:\n\
  \        resourceId: tools.resourceId\n      inputParameters:\n      - name: resourceId\n        type: string\n        description: resourceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inserteventticketclass\n      description: Google Wallet Insert Event Ticket Class\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-wallet.inserteventticketclass\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertloyaltyclass\n      description: Google Wallet Insert Loyalty Class\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-wallet.insertloyaltyclass\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listissuers\n      description: Google Wallet List Issuers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: google-wallet.listissuers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertjwt\n      description: Google Wallet Insert JWT\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-wallet.insertjwt\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-wallet/refs/heads/main/capabilities/google-wallet-capability.yaml
tags:
- Google
- Wallet
- API
tools:
- description: Google Wallet Insert Generic Class
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertgenericclass
- description: Google Wallet List Generic Classes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgenericclasses
- description: Google Wallet Get Generic Class
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgenericclass
- description: Google Wallet Update Generic Class
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategenericclass
- description: Google Wallet Insert Generic Object
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertgenericobject
- description: Google Wallet Get Generic Object
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgenericobject
- description: Google Wallet Insert Event Ticket Class
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: inserteventticketclass
- description: Google Wallet Insert Loyalty Class
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertloyaltyclass
- description: Google Wallet List Issuers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listissuers
- description: Google Wallet Insert JWT
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertjwt
---
