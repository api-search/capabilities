---
categories: []
consumed_apis:
- whatsapp-business-mgmt
- whatsapp-cloud
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
- request verification codes for registration.
- disconnects a product catalog from a waba.
- registers a phone number for use with the cloud api.
- disconnects a product catalog.
- connects a product catalog to a waba.
- update business profile
- requests a verification code via sms or voice call for phone registration.
- list assigned users
- verify phone numbers.
- user management
- lists assigned users.
- deregister phone numbers.
- whatsapp business account information.
- assigns a user with specific tasks to a waba.
- retrieves the whatsapp business profile.
- retrieves information about a registered phone number.
- register phone number
- lists product catalogs connected to a waba.
- user assignments for a waba.
- removes a user from a waba.
- list phone numbers
- set two step verification
- assigns a user to a waba.
- deregisters a phone number from the cloud api.
- individual phone number information.
- product catalog management.
- register phone numbers.
- updates the whatsapp business profile for a phone number.
- lists product catalogs.
- deregisters a phone number.
- remove assigned user
- updates the whatsapp business profile.
- connects a product catalog.
- request verification code
- get business account
- whatsapp
- list product catalogs
- removes an assigned user.
- get phone number
- two-step verification pin management.
- retrieves the whatsapp business profile for a phone number.
- verifies a phone number using a verification code.
- get business profile
- lists all users assigned to a waba.
- deregister phone number
- retrieves information about a whatsapp business account.
- verify code
- assign user
- registration
- registers a phone number for cloud api.
- whatsapp business profile management.
- product catalogs
- verifies a phone number.
- phone numbers associated with a waba.
- disconnect product catalog
- requests a verification code.
- phone numbers
- business profile
- connect product catalog
- sets or updates the two-step verification pin for a phone number.
- lists all phone numbers associated with a waba.
- account management
- sets or updates the two-step verification pin.
slug: account-and-phone-management
source_filename: account-and-phone-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WhatsApp Account And Phone Management\"\n  description: \"Unified workflow for managing WhatsApp Business Accounts, phone numbers, business profiles, user assignments, product catalogs, and phone registration. Combines Business Management API and Cloud API capabilities used by platform administrators and business operations teams.\"\n  tags:\n    - WhatsApp\n    - Account Management\n    - Phone Numbers\n    - Business Profile\n    - Registration\n    - User Management\n    - Product Catalogs\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: whatsapp-business-mgmt\n      location: ./shared/business-management.yaml\n    - import: whatsapp-cloud\n      location: ./shared/cloud-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: whatsapp-account-api\n      description:\
  \ \"Unified REST API for WhatsApp account management, phone numbers, profiles, users, catalogs, and registration.\"\n      resources:\n        - path: /v1/business-accounts/{waba_id}\n          name: business-accounts\n          description: \"WhatsApp Business Account information.\"\n          operations:\n            - method: GET\n              name: get-business-account\n              description: \"Retrieves information about a WhatsApp Business Account.\"\n              call: \"whatsapp-business-mgmt.get-whatsapp-business-account\"\n              with:\n                waba_id: \"rest.waba_id\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/phone-numbers\n          name: waba-phone-numbers\n          description: \"Phone numbers associated with a WABA.\"\n          operations:\n            - method: GET\n              name: list-phone-numbers\n              description:\
  \ \"Lists all phone numbers associated with a WABA.\"\n              call: \"whatsapp-business-mgmt.list-phone-numbers\"\n              with:\n                waba_id: \"rest.waba_id\"\n                fields: \"rest.fields\"\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n                before: \"rest.before\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/phone-numbers/{phone_number_id}\n          name: phone-number-detail\n          description: \"Individual phone number information.\"\n          operations:\n            - method: GET\n              name: get-phone-number\n              description: \"Retrieves information about a registered phone number.\"\n              call: \"whatsapp-cloud.get-phone-number\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                fields: \"rest.fields\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/business-profiles\n          name: business-profiles\n          description: \"WhatsApp Business profile management.\"\n          operations:\n            - method: GET\n              name: get-business-profile\n              description: \"Retrieves the WhatsApp Business profile.\"\n              call: \"whatsapp-cloud.get-business-profile\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: update-business-profile\n              description: \"Updates the WhatsApp Business profile.\"\n              call: \"whatsapp-cloud.update-business-profile\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                messaging_product: \"rest.messaging_product\"\n \
  \               about: \"rest.about\"\n                address: \"rest.address\"\n                description: \"rest.description\"\n                email: \"rest.email\"\n                websites: \"rest.websites\"\n                vertical: \"rest.vertical\"\n                profile_picture_handle: \"rest.profile_picture_handle\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assigned-users\n          name: assigned-users\n          description: \"User assignments for a WABA.\"\n          operations:\n            - method: GET\n              name: list-assigned-users\n              description: \"Lists assigned users.\"\n              call: \"whatsapp-business-mgmt.list-assigned-users\"\n              with:\n                waba_id: \"rest.waba_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: assign-user\n\
  \              description: \"Assigns a user to a WABA.\"\n              call: \"whatsapp-business-mgmt.assign-user\"\n              with:\n                waba_id: \"rest.waba_id\"\n                user: \"rest.user\"\n                tasks: \"rest.tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-assigned-user\n              description: \"Removes an assigned user.\"\n              call: \"whatsapp-business-mgmt.remove-assigned-user\"\n              with:\n                waba_id: \"rest.waba_id\"\n                user: \"rest.user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/product-catalogs\n          name: product-catalogs\n          description: \"Product catalog management.\"\n          operations:\n            - method: GET\n              name: list-product-catalogs\n              description:\
  \ \"Lists product catalogs.\"\n              call: \"whatsapp-business-mgmt.list-product-catalogs\"\n              with:\n                waba_id: \"rest.waba_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: connect-product-catalog\n              description: \"Connects a product catalog.\"\n              call: \"whatsapp-business-mgmt.connect-product-catalog\"\n              with:\n                waba_id: \"rest.waba_id\"\n                catalog_id: \"rest.catalog_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: disconnect-product-catalog\n              description: \"Disconnects a product catalog.\"\n              call: \"whatsapp-business-mgmt.disconnect-product-catalog\"\n              with:\n                waba_id: \"rest.waba_id\"\n                catalog_id: \"rest.catalog_id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/two-step-verification\n          name: two-step-verification\n          description: \"Two-step verification PIN management.\"\n          operations:\n            - method: POST\n              name: set-two-step-verification\n              description: \"Sets or updates the two-step verification PIN.\"\n              call: \"whatsapp-cloud.set-two-step-verification\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                pin: \"rest.pin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/registrations/request-code\n          name: registration-request-code\n          description: \"Request verification codes for registration.\"\n          operations:\n            - method: POST\n              name: request-verification-code\n              description:\
  \ \"Requests a verification code.\"\n              call: \"whatsapp-cloud.request-verification-code\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                code_method: \"rest.code_method\"\n                language: \"rest.language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/registrations/verify-code\n          name: registration-verify-code\n          description: \"Verify phone numbers.\"\n          operations:\n            - method: POST\n              name: verify-code\n              description: \"Verifies a phone number.\"\n              call: \"whatsapp-cloud.verify-code\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                code: \"rest.code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/registrations/register\n          name: registration-register\n\
  \          description: \"Register phone numbers.\"\n          operations:\n            - method: POST\n              name: register-phone-number\n              description: \"Registers a phone number for Cloud API.\"\n              call: \"whatsapp-cloud.register-phone-number\"\n              with:\n                phone_number_id: \"rest.phone_number_id\"\n                messaging_product: \"rest.messaging_product\"\n                pin: \"rest.pin\"\n                data_localization_region: \"rest.data_localization_region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/registrations/deregister\n          name: registration-deregister\n          description: \"Deregister phone numbers.\"\n          operations:\n            - method: POST\n              name: deregister-phone-number\n              description: \"Deregisters a phone number.\"\n              call: \"whatsapp-cloud.deregister-phone-number\"\n\
  \              with:\n                phone_number_id: \"rest.phone_number_id\"\n                messaging_product: \"rest.messaging_product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: whatsapp-account-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WhatsApp account management, phone numbers, profiles, users, catalogs, and registration.\"\n      tools:\n        - name: get-business-account\n          description: \"Retrieves information about a WhatsApp Business Account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.get-whatsapp-business-account\"\n          with:\n            waba_id: \"tools.waba_id\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-phone-numbers\n        \
  \  description: \"Lists all phone numbers associated with a WABA.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.list-phone-numbers\"\n          with:\n            waba_id: \"tools.waba_id\"\n            fields: \"tools.fields\"\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n            before: \"tools.before\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-phone-number\n          description: \"Retrieves information about a registered phone number.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-cloud.get-phone-number\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-business-profile\n          description:\
  \ \"Retrieves the WhatsApp Business profile for a phone number.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-cloud.get-business-profile\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-business-profile\n          description: \"Updates the WhatsApp Business profile for a phone number.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"whatsapp-cloud.update-business-profile\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            messaging_product: \"tools.messaging_product\"\n            about: \"tools.about\"\n            address: \"tools.address\"\n            description: \"tools.description\"\n            email: \"tools.email\"\n            websites: \"tools.websites\"\n\
  \            vertical: \"tools.vertical\"\n            profile_picture_handle: \"tools.profile_picture_handle\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-assigned-users\n          description: \"Lists all users assigned to a WABA.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.list-assigned-users\"\n          with:\n            waba_id: \"tools.waba_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: assign-user\n          description: \"Assigns a user with specific tasks to a WABA.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-business-mgmt.assign-user\"\n          with:\n            waba_id: \"tools.waba_id\"\n            user: \"tools.user\"\n            tasks: \"tools.tasks\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: remove-assigned-user\n          description: \"Removes a user from a WABA.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.remove-assigned-user\"\n          with:\n            waba_id: \"tools.waba_id\"\n            user: \"tools.user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-product-catalogs\n          description: \"Lists product catalogs connected to a WABA.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.list-product-catalogs\"\n          with:\n            waba_id: \"tools.waba_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: connect-product-catalog\n          description: \"Connects a product catalog to a WABA.\"\n \
  \         hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-business-mgmt.connect-product-catalog\"\n          with:\n            waba_id: \"tools.waba_id\"\n            catalog_id: \"tools.catalog_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: disconnect-product-catalog\n          description: \"Disconnects a product catalog from a WABA.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.disconnect-product-catalog\"\n          with:\n            waba_id: \"tools.waba_id\"\n            catalog_id: \"tools.catalog_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: set-two-step-verification\n          description: \"Sets or updates the two-step verification PIN for a phone number.\"\n          hints:\n            readOnly:\
  \ false\n            idempotent: true\n          call: \"whatsapp-cloud.set-two-step-verification\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            pin: \"tools.pin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: request-verification-code\n          description: \"Requests a verification code via SMS or voice call for phone registration.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-cloud.request-verification-code\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            code_method: \"tools.code_method\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: verify-code\n          description: \"Verifies a phone number using a verification code.\"\n          hints:\n            readOnly: false\n        \
  \    destructive: false\n          call: \"whatsapp-cloud.verify-code\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            code: \"tools.code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: register-phone-number\n          description: \"Registers a phone number for use with the Cloud API.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-cloud.register-phone-number\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            messaging_product: \"tools.messaging_product\"\n            pin: \"tools.pin\"\n            data_localization_region: \"tools.data_localization_region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deregister-phone-number\n          description: \"Deregisters a phone number from the Cloud API.\"\n          hints:\n         \
  \   readOnly: false\n            destructive: true\n          call: \"whatsapp-cloud.deregister-phone-number\"\n          with:\n            phone_number_id: \"tools.phone_number_id\"\n            messaging_product: \"tools.messaging_product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
