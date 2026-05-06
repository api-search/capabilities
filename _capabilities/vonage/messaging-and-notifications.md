---
categories: []
consumed_apis: []
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
- send a viber service message to a phone number.
- send messages via any supported channel (whatsapp, messenger, viber, rcs, mms, sms).
- send rcs message
- omnichannel
- voice
- communication
- send an sms text message to a phone number.
- vonage
- sms
- send sms
- messaging
- send sms messages via legacy sms api.
- whatsapp
- send whatsapp message
- telecommunications
- send message
- video conferencing
- send an sms message to a recipient.
- send viber message
- send an rcs rich message to a phone number.
- notifications
- send a message via the unified messages api.
- send a whatsapp message to a phone number.
- verification
slug: messaging-and-notifications
source_filename: messaging-and-notifications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vonage Messaging and Notifications\n  description: Unified messaging workflow combining Vonage SMS API and Messages API for sending notifications, alerts, and\n    multi-channel communications to customers. Used by developers building notification systems, customer engagement platforms,\n    and omnichannel messaging applications.\n  tags:\n  - Communication\n  - Messaging\n  - Notifications\n  - Omnichannel\n  - SMS\n  - WhatsApp\n  - Vonage\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VONAGE_API_KEY: VONAGE_API_KEY\n    VONAGE_API_SECRET: VONAGE_API_SECRET\n    VONAGE_JWT_TOKEN: VONAGE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vonage-sms\n    baseUri: https://rest.nexmo.com\n    description: Vonage SMS API for sending text messages globally.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{VONAGE_API_KEY}}'\n      placement: body\n  \
  \  resources:\n    - name: sms\n      path: /sms/json\n      description: Send outbound SMS messages.\n      operations:\n      - name: send-sms\n        method: POST\n        description: Send an SMS message to a recipient.\n        inputParameters:\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Recipient phone number in E.164 format.\n        - name: from\n          in: body\n          type: string\n          required: true\n          description: Sender phone number or alphanumeric name.\n        - name: text\n          in: body\n          type: string\n          required: true\n          description: The SMS message body.\n        - name: type\n          in: body\n          type: string\n          required: false\n          description: 'Message type: text, binary, or unicode.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: vonage-messages\n    baseUri: https://api.nexmo.com\n    description: Vonage Messages API for multi-channel messaging.\n    authentication:\n      type: bearer\n      token: '{{VONAGE_JWT_TOKEN}}'\n    resources:\n    - name: messages\n      path: /v1/messages\n      description: Send messages across channels.\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message to a given channel.\n        inputParameters:\n        - name: message_type\n          in: body\n          type: string\n          required: true\n          description: Message type (text, image, audio, video, file, template).\n        - name: to\n          in: body\n          type: string\n          required: true\n          description: Recipient phone number or ID.\n        - name: from\n          in: body\n          type: string\n          required: true\n          description: Sender number or ID.\n        - name: channel\n          in: body\n          type:\
  \ string\n          required: true\n          description: Channel (sms, whatsapp, messenger, viber_service, mms, rcs).\n        - name: text\n          in: body\n          type: string\n          required: false\n          description: Message text for text messages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message\n      path: /v1/messages/{message_uuid}\n      description: Update message status.\n      operations:\n      - name: update-message\n        method: PATCH\n        description: Update the status of a message (e.g., mark as read).\n        inputParameters:\n        - name: message_uuid\n          in: path\n          type: string\n          required: true\n          description: The message UUID.\n        - name: status\n          in: body\n          type: string\n          required: true\n          description: New status (read).\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vonage-messaging-api\n    description: Unified REST API for Vonage messaging and notifications.\n    resources:\n    - path: /v1/sms\n      name: sms-messages\n      description: Send SMS messages via legacy SMS API.\n      operations:\n      - method: POST\n        name: send-sms\n        description: Send an SMS message to a recipient.\n        call: vonage-sms.send-sms\n        with:\n          to: rest.to\n          from: rest.from\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: channel-messages\n      description: Send messages via any supported channel (WhatsApp, Messenger, Viber, RCS, MMS, SMS).\n      operations:\n      - method: POST\n        name: send-message\n        description: Send a message via the unified Messages API.\n        call: vonage-messages.send-message\n\
  \        with:\n          message_type: rest.message_type\n          to: rest.to\n          from: rest.from\n          channel: rest.channel\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vonage-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted multi-channel messaging with Vonage.\n    tools:\n    - name: send-sms\n      description: Send an SMS text message to a phone number.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-sms.send-sms\n      with:\n        to: tools.to\n        from: tools.from\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-whatsapp-message\n      description: Send a WhatsApp message to a phone number.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-messages.send-message\n\
  \      with:\n        message_type: text\n        channel: whatsapp\n        to: tools.to\n        from: tools.from\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-rcs-message\n      description: Send an RCS rich message to a phone number.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-messages.send-message\n      with:\n        message_type: text\n        channel: rcs\n        to: tools.to\n        from: tools.from\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-viber-message\n      description: Send a Viber service message to a phone number.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vonage-messages.send-message\n      with:\n        message_type: text\n        channel: viber_service\n        to: tools.to\n        from: tools.from\n\
  \        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
