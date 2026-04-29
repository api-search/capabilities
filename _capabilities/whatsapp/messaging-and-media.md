---
categories:
- messaging
consumed_apis:
- whatsapp-cloud
description: Unified workflow for sending messages, managing media files, and creating QR codes for customer conversations. Combines WhatsApp Cloud API messaging, media management, and QR code capabilities used by customer engagement teams and chatbot developers.
layout: capability
name: WhatsApp Messaging And Media
operations:
- description: Sends a message to a WhatsApp user.
  method: POST
  name: send-message
  path: /v1/messages
- description: Uploads media to WhatsApp servers.
  method: POST
  name: upload-media
  path: /v1/media
- description: Retrieves a temporary download URL for media.
  method: GET
  name: get-media-url
  path: /v1/media/{media_id}
- description: Deletes a media file.
  method: DELETE
  name: delete-media
  path: /v1/media/{media_id}
- description: Lists all QR codes for a phone number.
  method: GET
  name: list-qr-codes
  path: /v1/qr-codes
- description: Creates a QR code for starting conversations.
  method: POST
  name: create-qr-code
  path: /v1/qr-codes
- description: Retrieves a specific QR code.
  method: GET
  name: get-qr-code
  path: /v1/qr-codes/{qr_code_id}
- description: Updates a QR code.
  method: POST
  name: update-qr-code
  path: /v1/qr-codes/{qr_code_id}
- description: Deletes a QR code.
  method: DELETE
  name: delete-qr-code
  path: /v1/qr-codes/{qr_code_id}
personas: []
provider_name: WhatsApp
provider_slug: whatsapp
search_terms:
- retrieves a temporary download url for media.
- delete media
- individual qr code management.
- messaging
- qr codes for starting customer conversations.
- list qr codes
- media
- updates the prefilled message for a qr code.
- sends a message to a whatsapp user.
- uploads media to whatsapp servers.
- send message
- creates a qr code for starting conversations.
- lists all qr codes for a phone number.
- qr codes
- retrieve and delete media files.
- whatsapp
- retrieves a specific qr code.
- upload media
- retrieves a temporary download url for a media file. url expires after 5 minutes.
- creates a qr code that customers can scan to start a conversation.
- sends a message to a whatsapp user. supports text, image, video, audio, document, sticker, location, contacts, interactive, template, and reaction message types.
- updates a qr code.
- deletes a qr code.
- deletes a media file from whatsapp servers.
- upload media files to whatsapp servers.
- update qr code
- get media url
- deletes a media file.
- create qr code
- uploads media to whatsapp servers. returns a media id for use when sending media messages.
- customer engagement
- send messages of all types to whatsapp users.
- get qr code
- delete qr code
slug: messaging-and-media
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WhatsApp Messaging And Media\"\n  description: \"Unified workflow for sending messages, managing media files, and creating QR codes for customer conversations. Combines WhatsApp Cloud API messaging, media management, and QR code capabilities used by customer engagement teams and chatbot developers.\"\n  tags:\n    - WhatsApp\n    - Messaging\n    - Media\n    - QR Codes\n    - Customer Engagement\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: whatsapp-cloud\n      location: ./shared/cloud-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: whatsapp-messaging-api\n      description: \"Unified REST API for WhatsApp messaging, media management, and QR codes.\"\n      resources:\n        - path: /v1/messages\n          name: messages\n          description: \"Send messages\
  \ of all types to WhatsApp users.\"\n          operations:\n            - method: POST\n              name: send-message\n              description: \"Sends a message to a WhatsApp user.\"\n              call: \"whatsapp-cloud.send-message\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                messaging_product: \"rest.messaging_product\"\n                to: \"rest.to\"\n                type: \"rest.type\"\n                text: \"rest.text\"\n                template: \"rest.template\"\n                interactive: \"rest.interactive\"\n                image: \"rest.image\"\n                video: \"rest.video\"\n                audio: \"rest.audio\"\n                document: \"rest.document\"\n                sticker: \"rest.sticker\"\n                location: \"rest.location\"\n                contacts: \"rest.contacts\"\n                reaction: \"rest.reaction\"\n                context: \"rest.context\"\n                status: \"rest.status\"\
  \n                message_id: \"rest.message_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/media\n          name: media-upload\n          description: \"Upload media files to WhatsApp servers.\"\n          operations:\n            - method: POST\n              name: upload-media\n              description: \"Uploads media to WhatsApp servers.\"\n              call: \"whatsapp-cloud.upload-media\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                file: \"rest.file\"\n                type: \"rest.type\"\n                messaging_product: \"rest.messaging_product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/media/{media_id}\n          name: media\n          description: \"Retrieve and delete media files.\"\n          operations:\n            - method: GET\n              name: get-media-url\n\
  \              description: \"Retrieves a temporary download URL for media.\"\n              call: \"whatsapp-cloud.get-media-url\"\n              with:\n                media_id: \"rest.media_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-media\n              description: \"Deletes a media file.\"\n              call: \"whatsapp-cloud.delete-media\"\n              with:\n                media_id: \"rest.media_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/qr-codes\n          name: qr-codes\n          description: \"QR codes for starting customer conversations.\"\n          operations:\n            - method: GET\n              name: list-qr-codes\n              description: \"Lists all QR codes for a phone number.\"\n              call: \"whatsapp-cloud.list-qr-codes\"\n              with:\n\
  \                phone_number_id: \"rest.phone_number_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-qr-code\n              description: \"Creates a QR code for starting conversations.\"\n              call: \"whatsapp-cloud.create-qr-code\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                prefilled_message: \"rest.prefilled_message\"\n                generate_qr_image: \"rest.generate_qr_image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/qr-codes/{qr_code_id}\n          name: qr-code\n          description: \"Individual QR code management.\"\n          operations:\n            - method: GET\n              name: get-qr-code\n              description: \"Retrieves a specific QR code.\"\n              call: \"whatsapp-cloud.get-qr-code\"\n          \
  \    with:\n                phone_number_id: \"rest.phone_number_id\"\n                qr_code_id: \"rest.qr_code_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: update-qr-code\n              description: \"Updates a QR code.\"\n              call: \"whatsapp-cloud.update-qr-code\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                qr_code_id: \"rest.qr_code_id\"\n                prefilled_message: \"rest.prefilled_message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-qr-code\n              description: \"Deletes a QR code.\"\n              call: \"whatsapp-cloud.delete-qr-code\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                qr_code_id: \"rest.qr_code_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: whatsapp-messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WhatsApp messaging, media management, and QR code operations.\"\n      tools:\n        - name: send-message\n          description: \"Sends a message to a WhatsApp user. Supports text, image, video, audio, document, sticker, location, contacts, interactive, template, and reaction message types.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-cloud.send-message\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            messaging_product: \"tools.messaging_product\"\n            to: \"tools.to\"\n            type: \"tools.type\"\n            text: \"tools.text\"\n            template: \"tools.template\"\n            interactive: \"tools.interactive\"\n            image: \"tools.image\"\n\
  \            video: \"tools.video\"\n            audio: \"tools.audio\"\n            document: \"tools.document\"\n            sticker: \"tools.sticker\"\n            location: \"tools.location\"\n            contacts: \"tools.contacts\"\n            reaction: \"tools.reaction\"\n            context: \"tools.context\"\n            status: \"tools.status\"\n            message_id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upload-media\n          description: \"Uploads media to WhatsApp servers. Returns a media ID for use when sending media messages.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-cloud.upload-media\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            file: \"tools.file\"\n            type: \"tools.type\"\n            messaging_product: \"tools.messaging_product\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-media-url\n          description: \"Retrieves a temporary download URL for a media file. URL expires after 5 minutes.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-cloud.get-media-url\"\n          with:\n            media_id: \"tools.media_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-media\n          description: \"Deletes a media file from WhatsApp servers.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-cloud.delete-media\"\n          with:\n            media_id: \"tools.media_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-qr-code\n          description: \"Creates a QR code that customers can scan to start a conversation.\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-cloud.create-qr-code\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            prefilled_message: \"tools.prefilled_message\"\n            generate_qr_image: \"tools.generate_qr_image\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-qr-codes\n          description: \"Lists all QR codes for a phone number.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-cloud.list-qr-codes\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-qr-code\n          description: \"Retrieves a specific QR code.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-cloud.get-qr-code\"\
  \n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            qr_code_id: \"tools.qr_code_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-qr-code\n          description: \"Updates the prefilled message for a QR code.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"whatsapp-cloud.update-qr-code\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            qr_code_id: \"tools.qr_code_id\"\n            prefilled_message: \"tools.prefilled_message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-qr-code\n          description: \"Deletes a QR code.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-cloud.delete-qr-code\"\n          with:\n            phone_number_id: \"\
  tools.phone_number_id\"\n            qr_code_id: \"tools.qr_code_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whatsapp/refs/heads/main/capabilities/messaging-and-media.yaml
tags:
- WhatsApp
- Messaging
- Media
- QR Codes
- Customer Engagement
tools:
- description: Sends a message to a WhatsApp user. Supports text, image, video, audio, document, sticker, location, contacts, interactive, template, and reaction message types.
  hints:
    destructive: false
    readOnly: false
  name: send-message
- description: Uploads media to WhatsApp servers. Returns a media ID for use when sending media messages.
  hints:
    destructive: false
    readOnly: false
  name: upload-media
- description: Retrieves a temporary download URL for a media file. URL expires after 5 minutes.
  hints:
    idempotent: true
    readOnly: true
  name: get-media-url
- description: Deletes a media file from WhatsApp servers.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-media
- description: Creates a QR code that customers can scan to start a conversation.
  hints:
    destructive: false
    readOnly: false
  name: create-qr-code
- description: Lists all QR codes for a phone number.
  hints:
    idempotent: true
    readOnly: true
  name: list-qr-codes
- description: Retrieves a specific QR code.
  hints:
    idempotent: true
    readOnly: true
  name: get-qr-code
- description: Updates the prefilled message for a QR code.
  hints:
    idempotent: true
    readOnly: false
  name: update-qr-code
- description: Deletes a QR code.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-qr-code
---
