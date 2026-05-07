---
categories:
- messaging
consumed_apis: []
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
- send messages of all types to whatsapp users.
- sends a message to a whatsapp user. supports text, image, video, audio, document, sticker, location, contacts, interactive, template, and reaction message types.
- get qr code
- retrieves a temporary download url for media.
- update qr code
- creates a qr code that customers can scan to start a conversation.
- deletes a media file from whatsapp servers.
- uploads media to whatsapp servers.
- sends a message to a whatsapp user.
- retrieves a specific qr code.
- upload media
- whatsapp
- send message
- creates a qr code for starting conversations.
- retrieve and delete media files.
- qr codes
- individual qr code management.
- qr codes for starting customer conversations.
- updates the prefilled message for a qr code.
- uploads media to whatsapp servers. returns a media id for use when sending media messages.
- deletes a media file.
- list qr codes
- customer engagement
- get media url
- lists all qr codes for a phone number.
- media
- updates a qr code.
- delete media
- delete qr code
- messaging
- create qr code
- retrieves a temporary download url for a media file. url expires after 5 minutes.
- upload media files to whatsapp servers.
- deletes a qr code.
slug: messaging-and-media
source_filename: messaging-and-media.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WhatsApp Messaging And Media\n  description: Unified workflow for sending messages, managing media files, and creating QR codes for customer conversations.\n    Combines WhatsApp Cloud API messaging, media management, and QR code capabilities used by customer engagement teams and\n    chatbot developers.\n  tags:\n  - WhatsApp\n  - Messaging\n  - Media\n  - QR Codes\n  - Customer Engagement\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: whatsapp-cloud\n    baseUri: https://graph.facebook.com/v21.0\n    description: WhatsApp Cloud API for sending messages, managing media, business profiles, phone registration, and QR codes.\n    authentication:\n      type: bearer\n      token: '{{WHATSAPP_ACCESS_TOKEN}}'\n    resources:\n    - name: messages\n      path: /\n      description: Send messages of\
  \ all types to WhatsApp users.\n      operations:\n      - name: send-message\n        method: POST\n        path: /{phone_number_id}/messages\n        description: Sends a message to a WhatsApp user. Also used to mark incoming messages as read.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID from the WhatsApp Business Account\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n            to: '{{tools.to}}'\n            type: '{{tools.type}}'\n            text: '{{tools.text}}'\n            template: '{{tools.template}}'\n            interactive: '{{tools.interactive}}'\n            image: '{{tools.image}}'\n            video: '{{tools.video}}'\n            audio: '{{tools.audio}}'\n            document: '{{tools.document}}'\n            sticker: '{{tools.sticker}}'\n            location: '{{tools.location}}'\n\
  \            contacts: '{{tools.contacts}}'\n            reaction: '{{tools.reaction}}'\n            context: '{{tools.context}}'\n            status: '{{tools.status}}'\n            message_id: '{{tools.message_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media\n      path: /\n      description: Upload, retrieve, and delete media files.\n      operations:\n      - name: upload-media\n        method: POST\n        path: /{phone_number_id}/media\n        description: Uploads media to WhatsApp servers. Returns a media ID for use in messages.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID from the WhatsApp Business Account\n        body:\n          type: json\n          data:\n            file: '{{tools.file}}'\n            type: '{{tools.type}}'\n            messaging_product:\
  \ '{{tools.messaging_product}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media-url\n        method: GET\n        path: /{media_id}\n        description: Retrieves a temporary download URL for a media file. URL expires after 5 minutes.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: Media ID returned from upload or webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-media\n        method: DELETE\n        path: /{media_id}\n        description: Deletes a media file from WhatsApp servers.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: Media ID returned from upload or webhook\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phone-numbers\n      path: /\n      description: Manage and verify phone numbers.\n      operations:\n      - name: get-phone-number\n        method: GET\n        path: /{phone_number_id}\n        description: Retrieves information about a registered phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: two-step-verification\n      path: /\n      description: Manage two-step verification PIN.\n      operations:\n      - name: set-two-step-verification\n\
  \        method: POST\n        path: /{phone_number_id}\n        description: Sets or updates the two-step verification PIN for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            pin: '{{tools.pin}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-profile\n      path: /\n      description: Get and update WhatsApp Business profile information.\n      operations:\n      - name: get-business-profile\n        method: GET\n        path: /{phone_number_id}/whatsapp_business_profile\n        description: Retrieves the WhatsApp Business profile for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n    \
  \      description: Phone Number ID\n        - name: fields\n          in: query\n          type: string\n          required: true\n          description: Comma-separated fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-business-profile\n        method: POST\n        path: /{phone_number_id}/whatsapp_business_profile\n        description: Updates the WhatsApp Business profile for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n            about: '{{tools.about}}'\n            address: '{{tools.address}}'\n            description: '{{tools.description}}'\n            email: '{{tools.email}}'\n            websites: '{{tools.websites}}'\n\
  \            vertical: '{{tools.vertical}}'\n            profile_picture_handle: '{{tools.profile_picture_handle}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: registration\n      path: /\n      description: Register and deregister phone numbers.\n      operations:\n      - name: request-verification-code\n        method: POST\n        path: /{phone_number_id}/request_code\n        description: Requests a verification code via SMS or voice call for phone registration.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            code_method: '{{tools.code_method}}'\n            language: '{{tools.language}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: verify-code\n        method: POST\n        path: /{phone_number_id}/verify_code\n        description: Verifies a phone number using the code received via SMS or voice.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            code: '{{tools.code}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-phone-number\n        method: POST\n        path: /{phone_number_id}/register\n        description: Registers a phone number for use with the Cloud API.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            messaging_product:\
  \ '{{tools.messaging_product}}'\n            pin: '{{tools.pin}}'\n            data_localization_region: '{{tools.data_localization_region}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregister-phone-number\n        method: POST\n        path: /{phone_number_id}/deregister\n        description: Deregisters a phone number from the Cloud API.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: qr-codes\n      path: /\n      description: Create and manage QR codes for customer conversations.\n      operations:\n      - name:\
  \ create-qr-code\n        method: POST\n        path: /{phone_number_id}/message_qrdls\n        description: Creates a QR code that customers can scan to start a conversation.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            prefilled_message: '{{tools.prefilled_message}}'\n            generate_qr_image: '{{tools.generate_qr_image}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-qr-codes\n        method: GET\n        path: /{phone_number_id}/message_qrdls\n        description: Lists all QR codes for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-qr-code\n        method: GET\n        path: /{phone_number_id}/message_qrdls/{qr_code_id}\n        description: Retrieves a specific QR code.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: qr_code_id\n          in: path\n          type: string\n          required: true\n          description: QR code identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-qr-code\n        method: POST\n        path: /{phone_number_id}/message_qrdls/{qr_code_id}\n        description: Updates the prefilled message for a QR code.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Phone Number ID\n        - name: qr_code_id\n          in: path\n          type: string\n          required: true\n          description: QR code identifier\n        body:\n          type: json\n          data:\n            prefilled_message: '{{tools.prefilled_message}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-qr-code\n        method: DELETE\n        path: /{phone_number_id}/message_qrdls/{qr_code_id}\n        description: Deletes a QR code.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: qr_code_id\n          in: path\n          type: string\n          required: true\n          description: QR code identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: whatsapp-messaging-api\n    description: Unified REST API for WhatsApp messaging, media management, and QR codes.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Send messages of all types to WhatsApp users.\n      operations:\n      - method: POST\n        name: send-message\n        description: Sends a message to a WhatsApp user.\n        call: whatsapp-cloud.send-message\n        with:\n          phone_number_id: rest.phone_number_id\n          messaging_product: rest.messaging_product\n          to: rest.to\n          type: rest.type\n          text: rest.text\n          template: rest.template\n          interactive: rest.interactive\n          image: rest.image\n          video: rest.video\n          audio: rest.audio\n          document: rest.document\n          sticker: rest.sticker\n          location: rest.location\n          contacts: rest.contacts\n        \
  \  reaction: rest.reaction\n          context: rest.context\n          status: rest.status\n          message_id: rest.message_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media\n      name: media-upload\n      description: Upload media files to WhatsApp servers.\n      operations:\n      - method: POST\n        name: upload-media\n        description: Uploads media to WhatsApp servers.\n        call: whatsapp-cloud.upload-media\n        with:\n          phone_number_id: rest.phone_number_id\n          file: rest.file\n          type: rest.type\n          messaging_product: rest.messaging_product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media/{media_id}\n      name: media\n      description: Retrieve and delete media files.\n      operations:\n      - method: GET\n        name: get-media-url\n        description: Retrieves a temporary download URL for media.\n        call: whatsapp-cloud.get-media-url\n\
  \        with:\n          media_id: rest.media_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-media\n        description: Deletes a media file.\n        call: whatsapp-cloud.delete-media\n        with:\n          media_id: rest.media_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/qr-codes\n      name: qr-codes\n      description: QR codes for starting customer conversations.\n      operations:\n      - method: GET\n        name: list-qr-codes\n        description: Lists all QR codes for a phone number.\n        call: whatsapp-cloud.list-qr-codes\n        with:\n          phone_number_id: rest.phone_number_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-qr-code\n        description: Creates a QR code for starting conversations.\n        call: whatsapp-cloud.create-qr-code\n        with:\n     \
  \     phone_number_id: rest.phone_number_id\n          prefilled_message: rest.prefilled_message\n          generate_qr_image: rest.generate_qr_image\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/qr-codes/{qr_code_id}\n      name: qr-code\n      description: Individual QR code management.\n      operations:\n      - method: GET\n        name: get-qr-code\n        description: Retrieves a specific QR code.\n        call: whatsapp-cloud.get-qr-code\n        with:\n          phone_number_id: rest.phone_number_id\n          qr_code_id: rest.qr_code_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: update-qr-code\n        description: Updates a QR code.\n        call: whatsapp-cloud.update-qr-code\n        with:\n          phone_number_id: rest.phone_number_id\n          qr_code_id: rest.qr_code_id\n          prefilled_message: rest.prefilled_message\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-qr-code\n        description: Deletes a QR code.\n        call: whatsapp-cloud.delete-qr-code\n        with:\n          phone_number_id: rest.phone_number_id\n          qr_code_id: rest.qr_code_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: whatsapp-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted WhatsApp messaging, media management, and QR code operations.\n    tools:\n    - name: send-message\n      description: Sends a message to a WhatsApp user. Supports text, image, video, audio, document, sticker, location, contacts,\n        interactive, template, and reaction message types.\n      hints:\n        readOnly: false\n        destructive: false\n      call: whatsapp-cloud.send-message\n      with:\n        phone_number_id: tools.phone_number_id\n        messaging_product: tools.messaging_product\n\
  \        to: tools.to\n        type: tools.type\n        text: tools.text\n        template: tools.template\n        interactive: tools.interactive\n        image: tools.image\n        video: tools.video\n        audio: tools.audio\n        document: tools.document\n        sticker: tools.sticker\n        location: tools.location\n        contacts: tools.contacts\n        reaction: tools.reaction\n        context: tools.context\n        status: tools.status\n        message_id: tools.message_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-media\n      description: Uploads media to WhatsApp servers. Returns a media ID for use when sending media messages.\n      hints:\n        readOnly: false\n        destructive: false\n      call: whatsapp-cloud.upload-media\n      with:\n        phone_number_id: tools.phone_number_id\n        file: tools.file\n        type: tools.type\n        messaging_product: tools.messaging_product\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-media-url\n      description: Retrieves a temporary download URL for a media file. URL expires after 5 minutes.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-cloud.get-media-url\n      with:\n        media_id: tools.media_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-media\n      description: Deletes a media file from WhatsApp servers.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: whatsapp-cloud.delete-media\n      with:\n        media_id: tools.media_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-qr-code\n      description: Creates a QR code that customers can scan to start a conversation.\n      hints:\n        readOnly: false\n        destructive: false\n      call: whatsapp-cloud.create-qr-code\n      with:\n        phone_number_id: tools.phone_number_id\n\
  \        prefilled_message: tools.prefilled_message\n        generate_qr_image: tools.generate_qr_image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-qr-codes\n      description: Lists all QR codes for a phone number.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-cloud.list-qr-codes\n      with:\n        phone_number_id: tools.phone_number_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-qr-code\n      description: Retrieves a specific QR code.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-cloud.get-qr-code\n      with:\n        phone_number_id: tools.phone_number_id\n        qr_code_id: tools.qr_code_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-qr-code\n      description: Updates the prefilled message for a QR code.\n      hints:\n        readOnly: false\n        idempotent: true\n \
  \     call: whatsapp-cloud.update-qr-code\n      with:\n        phone_number_id: tools.phone_number_id\n        qr_code_id: tools.qr_code_id\n        prefilled_message: tools.prefilled_message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-qr-code\n      description: Deletes a QR code.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: whatsapp-cloud.delete-qr-code\n      with:\n        phone_number_id: tools.phone_number_id\n        qr_code_id: tools.qr_code_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
