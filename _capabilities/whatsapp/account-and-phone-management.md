---
categories: []
consumed_apis: []
description: Unified workflow for managing WhatsApp Business Accounts, phone numbers, business profiles, user assignments, product catalogs, and phone registration. Combines Business Management API and Cloud API capabilities used by platform administrators and business operations teams.
layout: capability
name: WhatsApp Account And Phone Management
operations:
- description: Retrieves information about a WhatsApp Business Account.
  method: GET
  name: get-business-account
  path: /v1/business-accounts/{waba_id}
- description: Lists all phone numbers associated with a WABA.
  method: GET
  name: list-phone-numbers
  path: /v1/phone-numbers
- description: Retrieves information about a registered phone number.
  method: GET
  name: get-phone-number
  path: /v1/phone-numbers/{phone_number_id}
- description: Retrieves the WhatsApp Business profile.
  method: GET
  name: get-business-profile
  path: /v1/business-profiles
- description: Updates the WhatsApp Business profile.
  method: POST
  name: update-business-profile
  path: /v1/business-profiles
- description: Lists assigned users.
  method: GET
  name: list-assigned-users
  path: /v1/assigned-users
- description: Assigns a user to a WABA.
  method: POST
  name: assign-user
  path: /v1/assigned-users
- description: Removes an assigned user.
  method: DELETE
  name: remove-assigned-user
  path: /v1/assigned-users
- description: Lists product catalogs.
  method: GET
  name: list-product-catalogs
  path: /v1/product-catalogs
- description: Connects a product catalog.
  method: POST
  name: connect-product-catalog
  path: /v1/product-catalogs
- description: Disconnects a product catalog.
  method: DELETE
  name: disconnect-product-catalog
  path: /v1/product-catalogs
- description: Sets or updates the two-step verification PIN.
  method: POST
  name: set-two-step-verification
  path: /v1/two-step-verification
- description: Requests a verification code.
  method: POST
  name: request-verification-code
  path: /v1/registrations/request-code
- description: Verifies a phone number.
  method: POST
  name: verify-code
  path: /v1/registrations/verify-code
- description: Registers a phone number for Cloud API.
  method: POST
  name: register-phone-number
  path: /v1/registrations/register
- description: Deregisters a phone number.
  method: POST
  name: deregister-phone-number
  path: /v1/registrations/deregister
personas: []
provider_name: WhatsApp
provider_slug: whatsapp
search_terms:
- registers a phone number for cloud api.
- deregisters a phone number.
- lists all users assigned to a waba.
- updates the whatsapp business profile for a phone number.
- removes a user from a waba.
- verifies a phone number using a verification code.
- retrieves information about a registered phone number.
- get business profile
- request verification code
- request verification codes for registration.
- business profile
- set two step verification
- deregister phone number
- disconnects a product catalog.
- account management
- list assigned users
- verify phone numbers.
- disconnects a product catalog from a waba.
- requests a verification code via sms or voice call for phone registration.
- deregister phone numbers.
- connect product catalog
- sets or updates the two-step verification pin for a phone number.
- phone numbers associated with a waba.
- get business account
- verify code
- registration
- whatsapp
- sets or updates the two-step verification pin.
- get phone number
- disconnect product catalog
- update business profile
- lists all phone numbers associated with a waba.
- product catalogs
- deregisters a phone number from the cloud api.
- removes an assigned user.
- product catalog management.
- assigns a user with specific tasks to a waba.
- whatsapp business account information.
- two-step verification pin management.
- verifies a phone number.
- individual phone number information.
- connects a product catalog to a waba.
- retrieves the whatsapp business profile for a phone number.
- user assignments for a waba.
- user management
- lists product catalogs.
- retrieves information about a whatsapp business account.
- register phone numbers.
- updates the whatsapp business profile.
- connects a product catalog.
- registers a phone number for use with the cloud api.
- list product catalogs
- whatsapp business profile management.
- list phone numbers
- retrieves the whatsapp business profile.
- lists product catalogs connected to a waba.
- assigns a user to a waba.
- assign user
- lists assigned users.
- requests a verification code.
- remove assigned user
- register phone number
- phone numbers
slug: account-and-phone-management
source_filename: account-and-phone-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WhatsApp Account And Phone Management\n  description: Unified workflow for managing WhatsApp Business Accounts, phone numbers, business profiles, user assignments,\n    product catalogs, and phone registration. Combines Business Management API and Cloud API capabilities used by platform\n    administrators and business operations teams.\n  tags:\n  - WhatsApp\n  - Account Management\n  - Phone Numbers\n  - Business Profile\n  - Registration\n  - User Management\n  - Product Catalogs\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: whatsapp-business-mgmt\n    baseUri: https://graph.facebook.com/v21.0\n    description: WhatsApp Business Management API for managing WABAs, phone numbers, templates, analytics, users, catalogs,\n      and webhooks.\n    authentication:\n      type: bearer\n      token:\
  \ '{{WHATSAPP_ACCESS_TOKEN}}'\n    resources:\n    - name: business-accounts\n      path: /\n      description: Manage WhatsApp Business Account information.\n      operations:\n      - name: get-whatsapp-business-account\n        method: GET\n        path: /{waba_id}\n        description: Retrieves information about a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phone-numbers\n      path: /\n      description: List and manage phone numbers on a WABA.\n      operations:\n      - name: list-phone-numbers\n        method: GET\n        path:\
  \ /{waba_id}/phone_numbers\n        description: Lists all phone numbers associated with a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Pagination limit\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for forward pagination\n        - name: before\n          in: query\n          type: string\n          required: false\n          description: Cursor for backward pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: message-templates\n      path: /\n      description: Create, update, and delete message templates.\n      operations:\n      - name: list-message-templates\n        method: GET\n        path: /{waba_id}/message_templates\n        description: Lists all message templates for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Pagination limit\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for forward pagination\n        - name: before\n          in: query\n          type: string\n\
  \          required: false\n          description: Cursor for backward pagination\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by template name\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Filter by language code\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by approval status (APPROVED, PENDING, REJECTED, PAUSED, DISABLED)\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by template category (AUTHENTICATION, MARKETING, UTILITY)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-message-template\n        method: POST\n        path: /{waba_id}/message_templates\n        description:\
  \ Creates a new message template for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            language: '{{tools.language}}'\n            category: '{{tools.category}}'\n            components: '{{tools.components}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-message-template\n        method: POST\n        path: /{message_template_id}\n        description: Updates an existing message template. Only APPROVED or PAUSED templates can be edited.\n        inputParameters:\n        - name: message_template_id\n          in: path\n          type: string\n          required: true\n          description: Message template ID\n        body:\n     \
  \     type: json\n          data:\n            components: '{{tools.components}}'\n            category: '{{tools.category}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message-template\n        method: DELETE\n        path: /{waba_id}/message_templates\n        description: Deletes a message template. Deleting by name removes all language variants.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Template name to delete\n        - name: hsm_id\n          in: query\n          type: string\n          required: false\n          description: Specific template ID to delete a single language variant\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /\n      description: Retrieve conversation and template analytics.\n      operations:\n      - name: get-conversation-analytics\n        method: GET\n        path: /{waba_id}/conversation_analytics\n        description: Retrieves conversation analytics for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start time (Unix timestamp or YYYY-MM-DD)\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End time (Unix timestamp or YYYY-MM-DD)\n        - name: granularity\n          in: query\n          type: string\n          required: true\n          description:\
  \ Time granularity (HALF_HOUR, DAILY, MONTHLY)\n        - name: phone_numbers\n          in: query\n          type: array\n          required: false\n          description: Filter by phone number IDs\n        - name: metric_types\n          in: query\n          type: array\n          required: false\n          description: Metric types (CONVERSATION, COST)\n        - name: conversation_categories\n          in: query\n          type: array\n          required: false\n          description: Conversation categories filter\n        - name: dimensions\n          in: query\n          type: array\n          required: false\n          description: Dimensions for breakdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-template-analytics\n        method: GET\n        path: /{waba_id}/template_analytics\n        description: Retrieves analytics for specific message templates.\n        inputParameters:\n\
  \        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start time\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End time\n        - name: granularity\n          in: query\n          type: string\n          required: true\n          description: Time granularity (DAILY)\n        - name: template_ids\n          in: query\n          type: array\n          required: true\n          description: Template IDs to analyze (max 10)\n        - name: metric_types\n          in: query\n          type: array\n          required: false\n          description: Metric types (SENT, DELIVERED, READ, CLICKED, COST)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: subscribed-apps\n      path: /\n      description: Manage webhook subscriptions for a WABA.\n      operations:\n      - name: list-subscribed-apps\n        method: GET\n        path: /{waba_id}/subscribed_apps\n        description: Lists all apps subscribed to webhook events for this WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: subscribe-app\n        method: POST\n        path: /{waba_id}/subscribed_apps\n        description: Subscribes the current app to receive webhook events for this WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unsubscribe-app\n        method: DELETE\n        path: /{waba_id}/subscribed_apps\n        description: Unsubscribes the current app from webhook events.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assigned-users\n      path: /\n      description: Manage user access to a WABA.\n      operations:\n      - name: list-assigned-users\n        method: GET\n        path: /{waba_id}/assigned_users\n        description: Lists all users assigned to a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assign-user\n        method: POST\n        path: /{waba_id}/assigned_users\n        description: Assigns a user with specific tasks to a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            user: '{{tools.user}}'\n            tasks: '{{tools.tasks}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-assigned-user\n        method: DELETE\n        path: /{waba_id}/assigned_users\n        description: Removes a user from a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n         \
  \ in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            user: '{{tools.user}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product-catalogs\n      path: /\n      description: Connect and manage product catalogs.\n      operations:\n      - name: list-product-catalogs\n        method: GET\n        path: /{waba_id}/product_catalogs\n        description: Lists product catalogs connected to a WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: connect-product-catalog\n        method: POST\n        path: /{waba_id}/product_catalogs\n\
  \        description: Connects a product catalog to a WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            catalog_id: '{{tools.catalog_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disconnect-product-catalog\n        method: DELETE\n        path: /{waba_id}/product_catalogs\n        description: Disconnects a product catalog from a WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            catalog_id: '{{tools.catalog_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n  - type: http\n    namespace: whatsapp-cloud\n    baseUri: https://graph.facebook.com/v21.0\n    description: WhatsApp Cloud API for sending messages, managing media, business profiles, phone registration, and QR codes.\n    authentication:\n      type: bearer\n      token: '{{WHATSAPP_ACCESS_TOKEN}}'\n    resources:\n    - name: messages\n      path: /\n      description: Send messages of all types to WhatsApp users.\n      operations:\n      - name: send-message\n        method: POST\n        path: /{phone_number_id}/messages\n        description: Sends a message to a WhatsApp user. Also used to mark incoming messages as read.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID from the WhatsApp Business Account\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n\
  \            to: '{{tools.to}}'\n            type: '{{tools.type}}'\n            text: '{{tools.text}}'\n            template: '{{tools.template}}'\n            interactive: '{{tools.interactive}}'\n            image: '{{tools.image}}'\n            video: '{{tools.video}}'\n            audio: '{{tools.audio}}'\n            document: '{{tools.document}}'\n            sticker: '{{tools.sticker}}'\n            location: '{{tools.location}}'\n            contacts: '{{tools.contacts}}'\n            reaction: '{{tools.reaction}}'\n            context: '{{tools.context}}'\n            status: '{{tools.status}}'\n            message_id: '{{tools.message_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media\n      path: /\n      description: Upload, retrieve, and delete media files.\n      operations:\n      - name: upload-media\n        method: POST\n        path: /{phone_number_id}/media\n      \
  \  description: Uploads media to WhatsApp servers. Returns a media ID for use in messages.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID from the WhatsApp Business Account\n        body:\n          type: json\n          data:\n            file: '{{tools.file}}'\n            type: '{{tools.type}}'\n            messaging_product: '{{tools.messaging_product}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media-url\n        method: GET\n        path: /{media_id}\n        description: Retrieves a temporary download URL for a media file. URL expires after 5 minutes.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: Media ID returned from upload or webhook\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-media\n        method: DELETE\n        path: /{media_id}\n        description: Deletes a media file from WhatsApp servers.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: Media ID returned from upload or webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phone-numbers\n      path: /\n      description: Manage and verify phone numbers.\n      operations:\n      - name: get-phone-number\n        method: GET\n        path: /{phone_number_id}\n        description: Retrieves information about a registered phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number\
  \ ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: two-step-verification\n      path: /\n      description: Manage two-step verification PIN.\n      operations:\n      - name: set-two-step-verification\n        method: POST\n        path: /{phone_number_id}\n        description: Sets or updates the two-step verification PIN for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            pin: '{{tools.pin}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-profile\n\
  \      path: /\n      description: Get and update WhatsApp Business profile information.\n      operations:\n      - name: get-business-profile\n        method: GET\n        path: /{phone_number_id}/whatsapp_business_profile\n        description: Retrieves the WhatsApp Business profile for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: fields\n          in: query\n          type: string\n          required: true\n          description: Comma-separated fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-business-profile\n        method: POST\n        path: /{phone_number_id}/whatsapp_business_profile\n        description: Updates the WhatsApp Business profile for a phone number.\n        inputParameters:\n        - name: phone_number_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n            about: '{{tools.about}}'\n            address: '{{tools.address}}'\n            description: '{{tools.description}}'\n            email: '{{tools.email}}'\n            websites: '{{tools.websites}}'\n            vertical: '{{tools.vertical}}'\n            profile_picture_handle: '{{tools.profile_picture_handle}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: registration\n      path: /\n      description: Register and deregister phone numbers.\n      operations:\n      - name: request-verification-code\n        method: POST\n        path: /{phone_number_id}/request_code\n        description: Requests a verification code via SMS or voice call for phone registration.\n\
  \        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            code_method: '{{tools.code_method}}'\n            language: '{{tools.language}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: verify-code\n        method: POST\n        path: /{phone_number_id}/verify_code\n        description: Verifies a phone number using the code received via SMS or voice.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            code: '{{tools.code}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: register-phone-number\n        method: POST\n        path: /{phone_number_id}/register\n        description: Registers a phone number for use with the Cloud API.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n            pin: '{{tools.pin}}'\n            data_localization_region: '{{tools.data_localization_region}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregister-phone-number\n        method: POST\n        path: /{phone_number_id}/deregister\n        description: Deregisters a phone number from the Cloud API.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n      \
  \    required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            messaging_product: '{{tools.messaging_product}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: qr-codes\n      path: /\n      description: Create and manage QR codes for customer conversations.\n      operations:\n      - name: create-qr-code\n        method: POST\n        path: /{phone_number_id}/message_qrdls\n        description: Creates a QR code that customers can scan to start a conversation.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        body:\n          type: json\n          data:\n            prefilled_message: '{{tools.prefilled_message}}'\n            generate_qr_image: '{{tools.generate_qr_image}}'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-qr-codes\n        method: GET\n        path: /{phone_number_id}/message_qrdls\n        description: Lists all QR codes for a phone number.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-qr-code\n        method: GET\n        path: /{phone_number_id}/message_qrdls/{qr_code_id}\n        description: Retrieves a specific QR code.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: qr_code_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ QR code identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-qr-code\n        method: POST\n        path: /{phone_number_id}/message_qrdls/{qr_code_id}\n        description: Updates the prefilled message for a QR code.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: qr_code_id\n          in: path\n          type: string\n          required: true\n          description: QR code identifier\n        body:\n          type: json\n          data:\n            prefilled_message: '{{tools.prefilled_message}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-qr-code\n        method: DELETE\n        path: /{phone_number_id}/message_qrdls/{qr_code_id}\n  \
  \      description: Deletes a QR code.\n        inputParameters:\n        - name: phone_number_id\n          in: path\n          type: string\n          required: true\n          description: Phone Number ID\n        - name: qr_code_id\n          in: path\n          type: string\n          required: true\n          description: QR code identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: whatsapp-account-api\n    description: Unified REST API for WhatsApp account management, phone numbers, profiles, users, catalogs, and registration.\n    resources:\n    - path: /v1/business-accounts/{waba_id}\n      name: business-accounts\n      description: WhatsApp Business Account information.\n      operations:\n      - method: GET\n        name: get-business-account\n        description: Retrieves information about a WhatsApp Business Account.\n       \
  \ call: whatsapp-business-mgmt.get-whatsapp-business-account\n        with:\n          waba_id: rest.waba_id\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/phone-numbers\n      name: waba-phone-numbers\n      description: Phone numbers associated with a WABA.\n      operations:\n      - method: GET\n        name: list-phone-numbers\n        description: Lists all phone numbers associated with a WABA.\n        call: whatsapp-business-mgmt.list-phone-numbers\n        with:\n          waba_id: rest.waba_id\n          fields: rest.fields\n          limit: rest.limit\n          after: rest.after\n          before: rest.before\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/phone-numbers/{phone_number_id}\n      name: phone-number-detail\n      description: Individual phone number information.\n      operations:\n      - method: GET\n        name: get-phone-number\n        description:\
  \ Retrieves information about a registered phone number.\n        call: whatsapp-cloud.get-phone-number\n        with:\n          phone_number_id: rest.phone_number_id\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/business-profiles\n      name: business-profiles\n      description: WhatsApp Business profile management.\n      operations:\n      - method: GET\n        name: get-business-profile\n        description: Retrieves the WhatsApp Business profile.\n        call: whatsapp-cloud.get-business-profile\n        with:\n          phone_number_id: rest.phone_number_id\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: update-business-profile\n        description: Updates the WhatsApp Business profile.\n        call: whatsapp-cloud.update-business-profile\n        with:\n          phone_number_id: rest.phone_number_id\n  \
  \        messaging_product: rest.messaging_product\n          about: rest.about\n          address: rest.address\n          description: rest.description\n          email: rest.email\n          websites: rest.websites\n          vertical: rest.vertical\n          profile_picture_handle: rest.profile_picture_handle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assigned-users\n      name: assigned-users\n      description: User assignments for a WABA.\n      operations:\n      - method: GET\n        name: list-assigned-users\n        description: Lists assigned users.\n        call: whatsapp-business-mgmt.list-assigned-users\n        with:\n          waba_id: rest.waba_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: assign-user\n        description: Assigns a user to a WABA.\n        call: whatsapp-business-mgmt.assign-user\n        with:\n          waba_id: rest.waba_id\n     \
  \     user: rest.user\n          tasks: rest.tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-assigned-user\n        description: Removes an assigned user.\n        call: whatsapp-business-mgmt.remove-assigned-user\n        with:\n          waba_id: rest.waba_id\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/product-catalogs\n      name: product-catalogs\n      description: Product catalog management.\n      operations:\n      - method: GET\n        name: list-product-catalogs\n        description: Lists product catalogs.\n        call: whatsapp-business-mgmt.list-product-catalogs\n        with:\n          waba_id: rest.waba_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: connect-product-catalog\n        description: Connects a product catalog.\n        call: whatsapp-business-mgmt.connect-product-catalog\n\
  \        with:\n          waba_id: rest.waba_id\n          catalog_id: rest.catalog_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: disconnect-product-catalog\n        description: Disconnects a product catalog.\n        call: whatsapp-business-mgmt.disconnect-product-catalog\n        with:\n          waba_id: rest.waba_id\n          catalog_id: rest.catalog_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/two-step-verification\n      name: two-step-verification\n      description: Two-step verification PIN management.\n      operations:\n      - method: POST\n        name: set-two-step-verification\n        description: Sets or updates the two-step verification PIN.\n        call: whatsapp-cloud.set-two-step-verification\n        with:\n          phone_number_id: rest.phone_number_id\n          pin: rest.pin\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/registrations/request-code\n      name: registration-request-code\n      description: Request verification codes for registration.\n      operations:\n      - method: POST\n        name: request-verification-code\n        description: Requests a verification code.\n        call: whatsapp-cloud.request-verification-code\n        with:\n          phone_number_id: rest.phone_number_id\n          code_method: rest.code_method\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/registrations/verify-code\n      name: registration-verify-code\n      description: Verify phone numbers.\n      operations:\n\n\n# --- truncated at 32 KB (39 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/whatsapp/refs/heads/main/capabilities/account-and-phone-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whatsapp/refs/heads/main/capabilities/account-and-phone-management.yaml
tags:
- WhatsApp
- Account Management
- Phone Numbers
- Business Profile
- Registration
- User Management
- Product Catalogs
tools:
- description: Retrieves information about a WhatsApp Business Account.
  hints:
    idempotent: true
    readOnly: true
  name: get-business-account
- description: Lists all phone numbers associated with a WABA.
  hints:
    idempotent: true
    readOnly: true
  name: list-phone-numbers
- description: Retrieves information about a registered phone number.
  hints:
    idempotent: true
    readOnly: true
  name: get-phone-number
- description: Retrieves the WhatsApp Business profile for a phone number.
  hints:
    idempotent: true
    readOnly: true
  name: get-business-profile
- description: Updates the WhatsApp Business profile for a phone number.
  hints:
    idempotent: true
    readOnly: false
  name: update-business-profile
- description: Lists all users assigned to a WABA.
  hints:
    idempotent: true
    readOnly: true
  name: list-assigned-users
- description: Assigns a user with specific tasks to a WABA.
  hints:
    destructive: false
    readOnly: false
  name: assign-user
- description: Removes a user from a WABA.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-assigned-user
- description: Lists product catalogs connected to a WABA.
  hints:
    idempotent: true
    readOnly: true
  name: list-product-catalogs
- description: Connects a product catalog to a WABA.
  hints:
    destructive: false
    readOnly: false
  name: connect-product-catalog
- description: Disconnects a product catalog from a WABA.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disconnect-product-catalog
- description: Sets or updates the two-step verification PIN for a phone number.
  hints:
    idempotent: true
    readOnly: false
  name: set-two-step-verification
- description: Requests a verification code via SMS or voice call for phone registration.
  hints:
    destructive: false
    readOnly: false
  name: request-verification-code
- description: Verifies a phone number using a verification code.
  hints:
    destructive: false
    readOnly: false
  name: verify-code
- description: Registers a phone number for use with the Cloud API.
  hints:
    destructive: false
    readOnly: false
  name: register-phone-number
- description: Deregisters a phone number from the Cloud API.
  hints:
    destructive: true
    readOnly: false
  name: deregister-phone-number
---
