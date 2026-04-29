---
categories:
- messaging
consumed_apis:
- att-wireless-apis
description: Workflow capability combining AT&T Wireless APIs for SMS messaging and OAuth authentication. Used by developers building consumer and business messaging applications on the AT&T network.
layout: capability
name: AT&T Wireless Messaging
operations:
- description: Obtain OAuth access token
  method: POST
  name: get-token
  path: /v1/auth/token
- description: Send SMS message
  method: POST
  name: send-sms
  path: /v1/sms/outbox
- description: Get SMS delivery status
  method: GET
  name: get-delivery-status
  path: /v1/sms/outbox/{messageId}
- description: Get inbound SMS messages
  method: GET
  name: get-inbound-sms
  path: /v1/sms/inbox/{registrationId}
personas: []
provider_name: AT&T
provider_slug: atandt
search_terms:
- get inbound sms
- sms inbound messages
- developer integrating at&t enterprise connectivity and ebonding apis
- engineer integrating enterprise wireline services and ebonding systems
- sms messaging and oauth authentication for consumer and business applications
- oauth and network-based authentication
- messaging
- send sms message
- get delivery status
- check delivery status of a sent at&t sms message
- camara network-based fraud prevention using sim swap and number verification
- sms
- Identity Developer
- wireline service ordering and qualification
- sms delivery status
- enterprise
- broadband
- oauth token management
- Security Developer
- wireline
- att send sms
- mobile or web developer building consumer applications on at&t apis
- network
- wireless
- network-based fraud detection and threat intelligence
- telecommunications
- device status, roaming, and qos management
- send an sms message to one or more recipients via at&t network
- sms and in-app messaging services
- 5g
- developer implementing frictionless mobile authentication via at&t network
- send sms
- fortune 100
- retrieve inbound sms messages for an at&t registered endpoint
- oauth
- get inbound sms messages
- obtain oauth access token
- sms outbound messaging
- att check sms delivery
- att get inbound sms
- developer building fraud prevention and identity verification using at&t network signals
- App Developer
- mobile virtual network operator managing subscribers on at&t infrastructure
- at&t
- get token
- get sms delivery status
- Enterprise Developer
slug: wireless-messaging
source_filename: wireless-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AT&T Wireless Messaging\"\n  description: \"Workflow capability combining AT&T Wireless APIs for SMS messaging and OAuth authentication. Used by developers building consumer and business messaging applications on the AT&T network.\"\n  tags:\n    - AT&T\n    - SMS\n    - Messaging\n    - Wireless\n    - OAuth\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATT_ACCESS_TOKEN: ATT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: att-wireless-apis\n      location: ./shared/wireless-apis.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: att-wireless-messaging-api\n      description: \"Unified REST API for AT&T wireless SMS messaging.\"\n      resources:\n        - path: /v1/auth/token\n          name: auth-token\n          description: \"OAuth token management\"\n          operations:\n            - method: POST\n              name: get-token\n    \
  \          description: \"Obtain OAuth access token\"\n              call: \"att-wireless-apis.get-access-token\"\n              with:\n                grant_type: \"rest.grant_type\"\n                client_id: \"rest.client_id\"\n                client_secret: \"rest.client_secret\"\n                scope: \"rest.scope\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sms/outbox\n          name: sms-outbox\n          description: \"SMS outbound messaging\"\n          operations:\n            - method: POST\n              name: send-sms\n              description: \"Send SMS message\"\n              call: \"att-wireless-apis.send-sms\"\n              with:\n                address: \"rest.address\"\n                message: \"rest.message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sms/outbox/{messageId}\n          name: sms-status\n \
  \         description: \"SMS delivery status\"\n          operations:\n            - method: GET\n              name: get-delivery-status\n              description: \"Get SMS delivery status\"\n              call: \"att-wireless-apis.get-sms-delivery-status\"\n              with:\n                messageId: \"rest.messageId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sms/inbox/{registrationId}\n          name: sms-inbox\n          description: \"SMS inbound messages\"\n          operations:\n            - method: GET\n              name: get-inbound-sms\n              description: \"Get inbound SMS messages\"\n              call: \"att-wireless-apis.get-inbound-sms\"\n              with:\n                registrationId: \"rest.registrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: att-wireless-messaging-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted AT&T SMS messaging operations.\"\n      tools:\n        - name: att-send-sms\n          description: \"Send an SMS message to one or more recipients via AT&T network\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-wireless-apis.send-sms\"\n          with:\n            address: \"tools.address\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: att-check-sms-delivery\n          description: \"Check delivery status of a sent AT&T SMS message\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-wireless-apis.get-sms-delivery-status\"\n          with:\n            messageId: \"tools.messageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: att-get-inbound-sms\n    \
  \      description: \"Retrieve inbound SMS messages for an AT&T registered endpoint\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-wireless-apis.get-inbound-sms\"\n          with:\n            registrationId: \"tools.registrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atandt/refs/heads/main/capabilities/wireless-messaging.yaml
tags:
- AT&T
- SMS
- Messaging
- Wireless
- OAuth
tools:
- description: Send an SMS message to one or more recipients via AT&T network
  hints:
    destructive: false
    readOnly: false
  name: att-send-sms
- description: Check delivery status of a sent AT&T SMS message
  hints:
    idempotent: true
    readOnly: true
  name: att-check-sms-delivery
- description: Retrieve inbound SMS messages for an AT&T registered endpoint
  hints:
    idempotent: true
    readOnly: true
  name: att-get-inbound-sms
---
