---
categories:
- messaging
consumed_apis:
- att-sms
- att-iam
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
- broadband
- inbox delta synchronization
- developer building enterprise notification, alerting, or communication systems
- sms short code inbox
- get inbox delta
- complete mvno subscriber lifecycle and number portability management
- at&t
- mobile virtual network operator services on at&t infrastructure
- check the delivery status of a sent sms message
- poll for inbound sms messages received on a registered short code
- poll for inbound sms messages
- in app list messages
- get inbound sms
- send mms or sms on behalf of user
- send message
- sms notifications and in-app messaging for mobile apps and enterprise systems
- sms send message
- speech
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- list messages
- get inbox changes since last synchronization for efficient message management
- in app get message
- send an mms or sms message on behalf of an authenticated at&t user
- in app send message
- telecommunications
- in app sync inbox delta
- wireless
- mms
- mobile
- notifications
- sms and mms messaging services for consumer and enterprise applications
- delete a message from the user's inbox permanently
- App Developer
- send an sms short code message to up to 50 recipients
- sms short code messaging
- get inbox changes since last sync
- sms check delivery status
- Telecom Engineer
- sms
- check delivery status of a sent sms
- wireline
- messaging
- mobile or web application developer embedding messaging into consumer apps
- mobile network connectivity and subscriber management
- list messages from a user's at&t inbox with pagination and unread filtering
- Enterprise Developer
- enterprise
- mvno business operator managing at&t-powered mobile subscribers and services
- list user inbox messages
- MVNO Operator
- get sms delivery status
- get full details of a specific inbox message including content and metadata
- in app delete message
- send sms
- sms delivery tracking
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- sms get inbound messages
- in-app user messaging inbox
slug: messaging
source_filename: messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AT&T Messaging\"\n  description: \"Unified messaging capability combining AT&T SMS API and In-App Messaging API for customer notifications, two-way messaging, and inbox management. Used by developers building mobile apps and enterprise notification systems.\"\n  tags:\n    - AT&T\n    - SMS\n    - MMS\n    - Messaging\n    - Notifications\n    - Mobile\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATT_SMS_ACCESS_TOKEN: ATT_SMS_ACCESS_TOKEN\n      ATT_IAM_ACCESS_TOKEN: ATT_IAM_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: att-sms\n      location: ./shared/sms-api.yaml\n    - import: att-iam\n      location: ./shared/in-app-messaging-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: att-messaging-api\n      description: \"Unified REST API for AT&T SMS and in-app messaging operations.\"\n      resources:\n        - path: /v1/sms/messages\n\
  \          name: sms-outbox\n          description: \"SMS short code messaging\"\n          operations:\n            - method: POST\n              name: send-sms\n              description: \"Send an SMS short code message to up to 50 recipients\"\n              call: \"att-sms.send-sms\"\n              with:\n                address: \"rest.address\"\n                message: \"rest.message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sms/messages/{messageId}/status\n          name: sms-delivery-status\n          description: \"SMS delivery tracking\"\n          operations:\n            - method: GET\n              name: get-sms-delivery-status\n              description: \"Check delivery status of a sent SMS\"\n              call: \"att-sms.get-sms-delivery-status\"\n              with:\n                messageId: \"rest.messageId\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n        - path: /v1/sms/inbox/{registrationId}\n          name: sms-inbox\n          description: \"SMS short code inbox\"\n          operations:\n            - method: GET\n              name: get-inbound-sms\n              description: \"Poll for inbound SMS messages\"\n              call: \"att-sms.get-inbound-sms\"\n              with:\n                registrationId: \"rest.registrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/in-app/messages\n          name: in-app-messages\n          description: \"In-app user messaging inbox\"\n          operations:\n            - method: POST\n              name: send-message\n              description: \"Send MMS or SMS on behalf of user\"\n              call: \"att-iam.send-message\"\n              with:\n                addresses: \"rest.addresses\"\n                text: \"rest.text\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-messages\n              description: \"List user inbox messages\"\n              call: \"att-iam.list-messages\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/in-app/delta\n          name: inbox-delta\n          description: \"Inbox delta synchronization\"\n          operations:\n            - method: GET\n              name: get-inbox-delta\n              description: \"Get inbox changes since last sync\"\n              call: \"att-iam.get-inbox-delta\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: att-messaging-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted AT&T messaging operations including SMS notifications and in-app messaging.\"\n      tools:\n        - name: sms-send-message\n          description: \"Send an SMS short code message to AT&T subscribers for notifications, alerts, or marketing\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-sms.send-sms\"\n          with:\n            address: \"tools.address\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sms-check-delivery-status\n          description: \"Check the delivery status of a sent SMS message\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-sms.get-sms-delivery-status\"\n          with:\n            messageId: \"tools.messageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: sms-get-inbound-messages\n          description: \"Poll for inbound SMS messages received on a registered short code\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-sms.get-inbound-sms\"\n          with:\n            registrationId: \"tools.registrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: in-app-send-message\n          description: \"Send an MMS or SMS message on behalf of an authenticated AT&T user\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-iam.send-message\"\n          with:\n            addresses: \"tools.addresses\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: in-app-list-messages\n          description: \"List messages from a user's AT&T inbox with pagination and unread filtering\"\n         \
  \ hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-iam.list-messages\"\n          with:\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n            isUnread: \"tools.isUnread\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: in-app-get-message\n          description: \"Get full details of a specific inbox message including content and metadata\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-iam.get-message\"\n          with:\n            messageId: \"tools.messageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: in-app-delete-message\n          description: \"Delete a message from the user's inbox permanently\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"att-iam.delete-message\"\
  \n          with:\n            messageId: \"tools.messageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: in-app-sync-inbox-delta\n          description: \"Get inbox changes since last synchronization for efficient message management\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-iam.get-inbox-delta\"\n          with:\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
