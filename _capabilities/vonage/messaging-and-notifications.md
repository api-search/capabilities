---
categories: []
consumed_apis:
- vonage-sms
- vonage-messages
description: Unified messaging workflow combining Vonage SMS API and Messages API for sending notifications, alerts, and multi-channel communications to customers. Used by developers building notification systems, customer engagement platforms, and omnichannel messaging applications.
layout: capability
name: Vonage Messaging and Notifications
operations:
- description: Send an SMS message to a recipient.
  method: POST
  name: send-sms
  path: /v1/sms
- description: Send a message via the unified Messages API.
  method: POST
  name: send-message
  path: /v1/messages
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- send messages via any supported channel (whatsapp, messenger, viber, rcs, mms, sms).
- send an sms text message to a phone number.
- vonage
- sms
- send message
- video conferencing
- verification
- send a message via the unified messages api.
- send rcs message
- send whatsapp message
- send an sms message to a recipient.
- telecommunications
- omnichannel
- notifications
- whatsapp
- communication
- send a whatsapp message to a phone number.
- send a viber service message to a phone number.
- send sms messages via legacy sms api.
- voice
- send viber message
- send sms
- messaging
- send an rcs rich message to a phone number.
slug: messaging-and-notifications
source_filename: messaging-and-notifications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vonage Messaging and Notifications\"\n  description: >-\n    Unified messaging workflow combining Vonage SMS API and Messages API for\n    sending notifications, alerts, and multi-channel communications to customers.\n    Used by developers building notification systems, customer engagement platforms,\n    and omnichannel messaging applications.\n  tags:\n    - Communication\n    - Messaging\n    - Notifications\n    - Omnichannel\n    - SMS\n    - WhatsApp\n    - Vonage\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VONAGE_API_KEY: VONAGE_API_KEY\n      VONAGE_API_SECRET: VONAGE_API_SECRET\n      VONAGE_JWT_TOKEN: VONAGE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: vonage-sms\n      location: ./shared/sms-api.yaml\n    - import: vonage-messages\n      location: ./shared/messages-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vonage-messaging-api\n\
  \      description: \"Unified REST API for Vonage messaging and notifications.\"\n      resources:\n        - path: /v1/sms\n          name: sms-messages\n          description: \"Send SMS messages via legacy SMS API.\"\n          operations:\n            - method: POST\n              name: send-sms\n              description: \"Send an SMS message to a recipient.\"\n              call: \"vonage-sms.send-sms\"\n              with:\n                to: \"rest.to\"\n                from: \"rest.from\"\n                text: \"rest.text\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages\n          name: channel-messages\n          description: \"Send messages via any supported channel (WhatsApp, Messenger, Viber, RCS, MMS, SMS).\"\n          operations:\n            - method: POST\n              name: send-message\n              description: \"Send a message via the unified Messages API.\"\n              call:\
  \ \"vonage-messages.send-message\"\n              with:\n                message_type: \"rest.message_type\"\n                to: \"rest.to\"\n                from: \"rest.from\"\n                channel: \"rest.channel\"\n                text: \"rest.text\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vonage-messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted multi-channel messaging with Vonage.\"\n      tools:\n        - name: send-sms\n          description: \"Send an SMS text message to a phone number.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-sms.send-sms\"\n          with:\n            to: \"tools.to\"\n            from: \"tools.from\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: send-whatsapp-message\n          description: \"Send a WhatsApp message to a phone number.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-messages.send-message\"\n          with:\n            message_type: \"text\"\n            channel: \"whatsapp\"\n            to: \"tools.to\"\n            from: \"tools.from\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-rcs-message\n          description: \"Send an RCS rich message to a phone number.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-messages.send-message\"\n          with:\n            message_type: \"text\"\n            channel: \"rcs\"\n            to: \"tools.to\"\n            from: \"tools.from\"\n            text: \"tools.text\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-viber-message\n          description: \"Send a Viber service message to a phone number.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vonage-messages.send-message\"\n          with:\n            message_type: \"text\"\n            channel: \"viber_service\"\n            to: \"tools.to\"\n            from: \"tools.from\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vonage/refs/heads/main/capabilities/messaging-and-notifications.yaml
tags:
- Communication
- Messaging
- Notifications
- Omnichannel
- SMS
- WhatsApp
- Vonage
tools:
- description: Send an SMS text message to a phone number.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-sms
- description: Send a WhatsApp message to a phone number.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-whatsapp-message
- description: Send an RCS rich message to a phone number.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-rcs-message
- description: Send a Viber service message to a phone number.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-viber-message
---
