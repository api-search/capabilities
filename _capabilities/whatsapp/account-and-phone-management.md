---
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
- set two step verification
- phone numbers
- lists product catalogs.
- user assignments for a waba.
- product catalog management.
- lists product catalogs connected to a waba.
- lists all phone numbers associated with a waba.
- verify code
- verify phone numbers.
- remove assigned user
- registration
- request verification code
- individual phone number information.
- register phone number
- list assigned users
- update business profile
- verifies a phone number.
- verifies a phone number using a verification code.
- removes a user from a waba.
- assign user
- registers a phone number for cloud api.
- whatsapp business profile management.
- account management
- requests a verification code.
- sets or updates the two-step verification pin for a phone number.
- registers a phone number for use with the cloud api.
- updates the whatsapp business profile.
- connects a product catalog to a waba.
- list product catalogs
- assigns a user with specific tasks to a waba.
- updates the whatsapp business profile for a phone number.
- business profile
- deregisters a phone number from the cloud api.
- list phone numbers
- retrieves information about a registered phone number.
- request verification codes for registration.
- retrieves information about a whatsapp business account.
- deregister phone number
- disconnects a product catalog.
- retrieves the whatsapp business profile for a phone number.
- product catalogs
- requests a verification code via sms or voice call for phone registration.
- lists assigned users.
- connects a product catalog.
- deregisters a phone number.
- removes an assigned user.
- lists all users assigned to a waba.
- get business profile
- retrieves the whatsapp business profile.
- whatsapp
- phone numbers associated with a waba.
- register phone numbers.
- whatsapp business account information.
- sets or updates the two-step verification pin.
- assigns a user to a waba.
- disconnects a product catalog from a waba.
- user management
- get phone number
- connect product catalog
- disconnect product catalog
- get business account
- deregister phone numbers.
- two-step verification pin management.
slug: account-and-phone-management
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
