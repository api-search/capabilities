---
categories: []
consumed_apis: []
description: The Google Chat API enables building Chat apps that integrate with Google Chat. It provides RESTful access to manage spaces, memberships, messages, reactions, media, and custom emojis.
layout: capability
name: Google Chat API
operations:
- description: Google Chat List spaces
  method: GET
  name: listspaces
  path: /v1/spaces
- description: Google Chat Create space
  method: POST
  name: createspace
  path: /v1/spaces
- description: Google Chat Get space
  method: GET
  name: getspace
  path: /v1/{name}
- description: Google Chat Update space
  method: PATCH
  name: updatespace
  path: /v1/{name}
- description: Google Chat Delete space
  method: DELETE
  name: deletespace
  path: /v1/{name}
- description: Google Chat Setup space
  method: POST
  name: setupspace
  path: /v1/spaces:setup
- description: Google Chat List members
  method: GET
  name: listmembers
  path: /v1/{parent}/members
- description: Google Chat Create member
  method: POST
  name: createmember
  path: /v1/{parent}/members
- description: Google Chat List messages
  method: GET
  name: listmessages
  path: /v1/{parent}/messages
- description: Google Chat Create message
  method: POST
  name: createmessage
  path: /v1/{parent}/messages
- description: Google Chat List reactions
  method: GET
  name: listreactions
  path: /v1/{parent}/reactions
- description: Google Chat Create reaction
  method: POST
  name: createreaction
  path: /v1/{parent}/reactions
- description: Google Chat List custom emojis
  method: GET
  name: listcustomemojis
  path: /v1/customEmojis
- description: Google Chat Create custom emoji
  method: POST
  name: createcustomemoji
  path: /v1/customEmojis
personas: []
provider_name: Google Chat
provider_slug: google-chat
search_terms:
- google chat delete space
- google chat create space
- google chat get space
- google workspace
- createmember
- google chat list spaces
- listmembers
- google chat list custom emojis
- listreactions
- createcustomemoji
- google chat create custom emoji
- google
- google chat list reactions
- deletespace
- google chat create message
- updatespace
- messaging
- api
- setupspace
- listcustomemojis
- spaces
- google chat create reaction
- getspace
- google chat setup space
- google chat list messages
- listspaces
- createreaction
- listmessages
- chat
- createmessage
- google chat list members
- google chat create member
- collaboration
- createspace
- google chat update space
slug: google-chat-capability
source_filename: google-chat-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Chat API\n  description: The Google Chat API enables building Chat apps that integrate with Google Chat. It provides RESTful access\n    to manage spaces, memberships, messages, reactions, media, and custom emojis.\n  tags:\n  - Google\n  - Chat\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-chat\n    baseUri: https://chat.googleapis.com\n    description: Google Chat API HTTP API.\n    resources:\n    - name: v1-spaces\n      path: /v1/spaces\n      operations:\n      - name: listspaces\n        method: GET\n        description: Google Chat List spaces\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: createspace\n        method: POST\n        description: Google Chat Create space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-name\n      path: /v1/{name}\n      operations:\n      - name: getspace\n        method: GET\n        description: Google Chat Get space\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: 'Format: spaces/{space}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatespace\n        method: PATCH\n        description: Google Chat Update space\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletespace\n        method: DELETE\n        description: Google Chat Delete space\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-spaces-setup\n      path: /v1/spaces:setup\n      operations:\n      - name: setupspace\n        method: POST\n        description: Google Chat Setup space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-members\n      path: /v1/{parent}/members\n      operations:\n      - name: listmembers\n        method: GET\n        description: Google Chat List members\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required:\
  \ true\n          description: 'Format: spaces/{space}'\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmember\n        method: POST\n        description: Google Chat Create member\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-messages\n      path: /v1/{parent}/messages\n      operations:\n      - name: listmessages\n        method: GET\n        description: Google Chat List messages\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: 'Format:\
  \ spaces/{space}'\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmessage\n        method: POST\n        description: Google Chat Create message\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-reactions\n      path: /v1/{parent}/reactions\n      operations:\n      - name: listreactions\n        method: GET\n        description: Google Chat List reactions\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n          description: 'Format: spaces/{space}/messages/{message}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createreaction\n        method: POST\n        description: Google Chat Create reaction\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-customemojis\n      path: /v1/customEmojis\n      operations:\n      - name: listcustomemojis\n        method: GET\n        description: Google Chat List custom emojis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustomemoji\n        method: POST\n        description: Google Chat Create custom emoji\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-chat-rest\n    description: REST adapter for Google Chat API.\n    resources:\n    - path: /v1/spaces\n      name: listspaces\n      operations:\n      - method: GET\n        name: listspaces\n        description: Google Chat List spaces\n        call: google-chat.listspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces\n      name: createspace\n      operations:\n      - method: POST\n        name: createspace\n        description: Google Chat Create space\n        call: google-chat.createspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{name}\n      name: getspace\n      operations:\n      - method: GET\n        name: getspace\n        description: Google Chat Get space\n        call: google-chat.getspace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/{name}\n      name: updatespace\n      operations:\n      - method: PATCH\n        name: updatespace\n        description: Google Chat Update space\n        call: google-chat.updatespace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{name}\n      name: deletespace\n      operations:\n      - method: DELETE\n        name: deletespace\n        description: Google Chat Delete space\n        call: google-chat.deletespace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces:setup\n      name: setupspace\n      operations:\n      - method: POST\n        name: setupspace\n        description: Google Chat Setup space\n        call: google-chat.setupspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/members\n      name: listmembers\n\
  \      operations:\n      - method: GET\n        name: listmembers\n        description: Google Chat List members\n        call: google-chat.listmembers\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/members\n      name: createmember\n      operations:\n      - method: POST\n        name: createmember\n        description: Google Chat Create member\n        call: google-chat.createmember\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/messages\n      name: listmessages\n      operations:\n      - method: GET\n        name: listmessages\n        description: Google Chat List messages\n        call: google-chat.listmessages\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/messages\n      name: createmessage\n\
  \      operations:\n      - method: POST\n        name: createmessage\n        description: Google Chat Create message\n        call: google-chat.createmessage\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/reactions\n      name: listreactions\n      operations:\n      - method: GET\n        name: listreactions\n        description: Google Chat List reactions\n        call: google-chat.listreactions\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/reactions\n      name: createreaction\n      operations:\n      - method: POST\n        name: createreaction\n        description: Google Chat Create reaction\n        call: google-chat.createreaction\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customEmojis\n\
  \      name: listcustomemojis\n      operations:\n      - method: GET\n        name: listcustomemojis\n        description: Google Chat List custom emojis\n        call: google-chat.listcustomemojis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customEmojis\n      name: createcustomemoji\n      operations:\n      - method: POST\n        name: createcustomemoji\n        description: Google Chat Create custom emoji\n        call: google-chat.createcustomemoji\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-chat-mcp\n    transport: http\n    description: MCP adapter for Google Chat API for AI agent use.\n    tools:\n    - name: listspaces\n      description: Google Chat List spaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-chat.listspaces\n      with:\n        pageSize: tools.pageSize\n        pageToken:\
  \ tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspace\n      description: Google Chat Create space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-chat.createspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getspace\n      description: Google Chat Get space\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-chat.getspace\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: 'Format: spaces/{space}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatespace\n   \
  \   description: Google Chat Update space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-chat.updatespace\n      with:\n        name: tools.name\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletespace\n      description: Google Chat Delete space\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-chat.deletespace\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setupspace\n      description: Google Chat Setup\
  \ space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-chat.setupspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmembers\n      description: Google Chat List members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-chat.listmembers\n      with:\n        parent: tools.parent\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: parent\n        type: string\n        description: 'Format: spaces/{space}'\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmember\n      description: Google Chat Create member\n      hints:\n        readOnly: false\n     \
  \   destructive: false\n        idempotent: false\n      call: google-chat.createmember\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmessages\n      description: Google Chat List messages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-chat.listmessages\n      with:\n        parent: tools.parent\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: parent\n        type: string\n        description: 'Format: spaces/{space}'\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: createmessage\n      description: Google Chat Create message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-chat.createmessage\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreactions\n      description: Google Chat List reactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-chat.listreactions\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: 'Format: spaces/{space}/messages/{message}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createreaction\n      description: Google Chat Create reaction\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-chat.createreaction\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomemojis\n      description: Google Chat List custom emojis\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-chat.listcustomemojis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomemoji\n      description: Google Chat Create custom emoji\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-chat.createcustomemoji\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-chat/refs/heads/main/capabilities/google-chat-capability.yaml
tags:
- Google
- Chat
- API
tools:
- description: Google Chat List spaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspaces
- description: Google Chat Create space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspace
- description: Google Chat Get space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspace
- description: Google Chat Update space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatespace
- description: Google Chat Delete space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletespace
- description: Google Chat Setup space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setupspace
- description: Google Chat List members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmembers
- description: Google Chat Create member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmember
- description: Google Chat List messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmessages
- description: Google Chat Create message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
- description: Google Chat List reactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreactions
- description: Google Chat Create reaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreaction
- description: Google Chat List custom emojis
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomemojis
- description: Google Chat Create custom emoji
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomemoji
---
