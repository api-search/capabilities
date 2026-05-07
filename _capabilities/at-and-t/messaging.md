---
categories:
- messaging
consumed_apis: []
description: Unified messaging capability combining AT&T SMS API and In-App Messaging API for customer notifications, two-way messaging, and inbox management. Used by developers building mobile apps and enterprise notification systems.
layout: capability
name: AT&T Messaging
operations:
- description: Send an SMS short code message to up to 50 recipients
  method: POST
  name: send-sms
  path: /v1/sms/messages
- description: Check delivery status of a sent SMS
  method: GET
  name: get-sms-delivery-status
  path: /v1/sms/messages/{messageId}/status
- description: Poll for inbound SMS messages
  method: GET
  name: get-inbound-sms
  path: /v1/sms/inbox/{registrationId}
- description: Send MMS or SMS on behalf of user
  method: POST
  name: send-message
  path: /v1/in-app/messages
- description: List user inbox messages
  method: GET
  name: list-messages
  path: /v1/in-app/messages
- description: Get inbox changes since last sync
  method: GET
  name: get-inbox-delta
  path: /v1/in-app/delta
personas: []
provider_name: AT&T
provider_slug: at-and-t
search_terms:
- sms notifications and in-app messaging for mobile apps and enterprise systems
- in app send message
- notifications
- complete mvno subscriber lifecycle and number portability management
- sms short code inbox
- send mms or sms on behalf of user
- check delivery status of a sent sms
- sms delivery tracking
- send sms
- developer building enterprise notification, alerting, or communication systems
- get inbound sms
- inbox delta synchronization
- Enterprise Developer
- list messages from a user's at&t inbox with pagination and unread filtering
- sms send message
- mobile
- send an sms short code message to up to 50 recipients
- mobile or web application developer embedding messaging into consumer apps
- sms
- broadband
- send message
- poll for inbound sms messages received on a registered short code
- list user inbox messages
- telecommunications
- check the delivery status of a sent sms message
- in-app user messaging inbox
- in app list messages
- MVNO Operator
- get inbox delta
- wireline
- list messages
- get inbox changes since last sync
- poll for inbound sms messages
- App Developer
- mvno business operator managing at&t-powered mobile subscribers and services
- enterprise
- sms check delivery status
- sms short code messaging
- Telecom Engineer
- mms
- get inbox changes since last synchronization for efficient message management
- at&t
- delete a message from the user's inbox permanently
- mobile network connectivity and subscriber management
- sms get inbound messages
- get full details of a specific inbox message including content and metadata
- in app get message
- mobile virtual network operator services on at&t infrastructure
- get sms delivery status
- in app delete message
- messaging
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- sms and mms messaging services for consumer and enterprise applications
- send an mms or sms message on behalf of an authenticated at&t user
- speech
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- in app sync inbox delta
- wireless
slug: messaging
source_filename: messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AT&T Messaging\n  description: Unified messaging capability combining AT&T SMS API and In-App Messaging API for customer notifications, two-way\n    messaging, and inbox management. Used by developers building mobile apps and enterprise notification systems.\n  tags:\n  - AT&T\n  - SMS\n  - MMS\n  - Messaging\n  - Notifications\n  - Mobile\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ATT_SMS_ACCESS_TOKEN: ATT_SMS_ACCESS_TOKEN\n    ATT_IAM_ACCESS_TOKEN: ATT_IAM_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: att-sms\n    baseUri: https://api.att.com\n    description: AT&T SMS API for short code messaging\n    authentication:\n      type: bearer\n      token: '{{ATT_SMS_ACCESS_TOKEN}}'\n    resources:\n    - name: sms-token\n      path: /oauth/v4/token\n      description: OAuth token management\n      operations:\n      - name: get-access-token\n        method: POST\n \
  \       description: Obtain OAuth access token using client credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sms-outbox\n      path: /sms/v3/messaging/outbox\n      description: SMS outbound messaging\n      operations:\n      - name: send-sms\n        method: POST\n        description: Send SMS message to up to 50 recipients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            address: '{{tools.address}}'\n            message: '{{tools.message}}'\n    - name: sms-delivery-status\n      path: /sms/v3/messaging/outbox/{messageId}\n      description: SMS delivery status\n      operations:\n      - name: get-sms-delivery-status\n        method: GET\n        description: Get delivery status of a sent SMS message\n        inputParameters:\n        - name:\
  \ messageId\n          in: path\n          type: string\n          required: true\n          description: Message ID from send SMS response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sms-inbox\n      path: /sms/v3/messaging/inbox/{registrationId}\n      description: SMS inbound messages\n      operations:\n      - name: get-inbound-sms\n        method: GET\n        description: Poll for inbound SMS messages on a short code\n        inputParameters:\n        - name: registrationId\n          in: path\n          type: string\n          required: true\n          description: Short code registration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: att-iam\n    baseUri: https://api.att.com\n    description: AT&T In-App Messaging API for user messaging\n    authentication:\n      type:\
  \ bearer\n      token: '{{ATT_IAM_ACCESS_TOKEN}}'\n    resources:\n    - name: messages\n      path: /myMessages/v2/messages\n      description: Message send and list operations\n      operations:\n      - name: send-message\n        method: POST\n        description: Send MMS or SMS message on behalf of user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            addresses: '{{tools.addresses}}'\n            text: '{{tools.text}}'\n      - name: list-messages\n        method: GET\n        description: List messages from user inbox\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max messages to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name:\
  \ isUnread\n          in: query\n          type: boolean\n          required: false\n          description: Filter unread messages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message-detail\n      path: /myMessages/v2/messages/{messageId}\n      description: Individual message operations\n      operations:\n      - name: get-message\n        method: GET\n        description: Get message details by ID\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required: true\n          description: Message ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message\n        method: DELETE\n        description: Delete a message from inbox\n        inputParameters:\n        - name: messageId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Message ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message-index\n      path: /myMessages/v2/messages/index\n      description: Message index cache management\n      operations:\n      - name: create-message-index\n        method: POST\n        description: Create inbox index cache for delta sync\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inbox-delta\n      path: /myMessages/v2/delta\n      description: Inbox delta synchronization\n      operations:\n      - name: get-inbox-delta\n        method: GET\n        description: Get inbox changes since last sync\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: true\n          description: State token from previous sync\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: att-messaging-api\n    description: Unified REST API for AT&T SMS and in-app messaging operations.\n    resources:\n    - path: /v1/sms/messages\n      name: sms-outbox\n      description: SMS short code messaging\n      operations:\n      - method: POST\n        name: send-sms\n        description: Send an SMS short code message to up to 50 recipients\n        call: att-sms.send-sms\n        with:\n          address: rest.address\n          message: rest.message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sms/messages/{messageId}/status\n      name: sms-delivery-status\n      description: SMS delivery tracking\n      operations:\n      - method: GET\n        name: get-sms-delivery-status\n        description: Check delivery status of a sent SMS\n        call: att-sms.get-sms-delivery-status\n\
  \        with:\n          messageId: rest.messageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sms/inbox/{registrationId}\n      name: sms-inbox\n      description: SMS short code inbox\n      operations:\n      - method: GET\n        name: get-inbound-sms\n        description: Poll for inbound SMS messages\n        call: att-sms.get-inbound-sms\n        with:\n          registrationId: rest.registrationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/in-app/messages\n      name: in-app-messages\n      description: In-app user messaging inbox\n      operations:\n      - method: POST\n        name: send-message\n        description: Send MMS or SMS on behalf of user\n        call: att-iam.send-message\n        with:\n          addresses: rest.addresses\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-messages\n\
  \        description: List user inbox messages\n        call: att-iam.list-messages\n        with:\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/in-app/delta\n      name: inbox-delta\n      description: Inbox delta synchronization\n      operations:\n      - method: GET\n        name: get-inbox-delta\n        description: Get inbox changes since last sync\n        call: att-iam.get-inbox-delta\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: att-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted AT&T messaging operations including SMS notifications and in-app messaging.\n    tools:\n    - name: sms-send-message\n      description: Send an SMS short code message to AT&T subscribers for notifications, alerts, or marketing\n      hints:\n    \
  \    readOnly: false\n        destructive: false\n      call: att-sms.send-sms\n      with:\n        address: tools.address\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sms-check-delivery-status\n      description: Check the delivery status of a sent SMS message\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-sms.get-sms-delivery-status\n      with:\n        messageId: tools.messageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sms-get-inbound-messages\n      description: Poll for inbound SMS messages received on a registered short code\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-sms.get-inbound-sms\n      with:\n        registrationId: tools.registrationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: in-app-send-message\n      description: Send an MMS or SMS message on behalf of\
  \ an authenticated AT&T user\n      hints:\n        readOnly: false\n        destructive: false\n      call: att-iam.send-message\n      with:\n        addresses: tools.addresses\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: in-app-list-messages\n      description: List messages from a user's AT&T inbox with pagination and unread filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-iam.list-messages\n      with:\n        limit: tools.limit\n        offset: tools.offset\n        isUnread: tools.isUnread\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: in-app-get-message\n      description: Get full details of a specific inbox message including content and metadata\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-iam.get-message\n      with:\n        messageId: tools.messageId\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: in-app-delete-message\n      description: Delete a message from the user's inbox permanently\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: att-iam.delete-message\n      with:\n        messageId: tools.messageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: in-app-sync-inbox-delta\n      description: Get inbox changes since last synchronization for efficient message management\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-iam.get-inbox-delta\n      with:\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/at-and-t/refs/heads/main/capabilities/messaging.yaml
tags:
- AT&T
- SMS
- MMS
- Messaging
- Notifications
- Mobile
tools:
- description: Send an SMS short code message to AT&T subscribers for notifications, alerts, or marketing
  hints:
    destructive: false
    readOnly: false
  name: sms-send-message
- description: Check the delivery status of a sent SMS message
  hints:
    idempotent: true
    readOnly: true
  name: sms-check-delivery-status
- description: Poll for inbound SMS messages received on a registered short code
  hints:
    idempotent: true
    readOnly: true
  name: sms-get-inbound-messages
- description: Send an MMS or SMS message on behalf of an authenticated AT&T user
  hints:
    destructive: false
    readOnly: false
  name: in-app-send-message
- description: List messages from a user's AT&T inbox with pagination and unread filtering
  hints:
    idempotent: true
    readOnly: true
  name: in-app-list-messages
- description: Get full details of a specific inbox message including content and metadata
  hints:
    idempotent: true
    readOnly: true
  name: in-app-get-message
- description: Delete a message from the user's inbox permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: in-app-delete-message
- description: Get inbox changes since last synchronization for efficient message management
  hints:
    idempotent: true
    readOnly: true
  name: in-app-sync-inbox-delta
---
