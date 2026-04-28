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
- delete qr code
- retrieves a temporary download url for media.
- qr codes for starting customer conversations.
- messaging
- creates a qr code that customers can scan to start a conversation.
- updates the prefilled message for a qr code.
- update qr code
- deletes a media file from whatsapp servers.
- sends a message to a whatsapp user. supports text, image, video, audio, document, sticker, location, contacts, interactive, template, and reaction message types.
- send message
- retrieves a temporary download url for a media file. url expires after 5 minutes.
- whatsapp
- retrieves a specific qr code.
- upload media
- updates a qr code.
- get media url
- deletes a qr code.
- get qr code
- lists all qr codes for a phone number.
- create qr code
- delete media
- deletes a media file.
- individual qr code management.
- customer engagement
- uploads media to whatsapp servers. returns a media id for use when sending media messages.
- list qr codes
- upload media files to whatsapp servers.
- uploads media to whatsapp servers.
- media
- qr codes
- send messages of all types to whatsapp users.
- sends a message to a whatsapp user.
- retrieve and delete media files.
- creates a qr code for starting conversations.
slug: messaging-and-media
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
