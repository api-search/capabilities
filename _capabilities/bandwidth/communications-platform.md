---
consumed_apis:
- bandwidth-voice
- bandwidth-messaging
- bandwidth-mfa
- bandwidth-phone-numbers
- bandwidth-emergency
- bandwidth-toll-free
description: Unified communications platform workflow covering voice calls, messaging (SMS/MMS), multi-factor authentication, phone number management, emergency calling (E911), and toll-free verification. Serves developers building communication-enabled applications.
layout: capability
name: Bandwidth Communications Platform
operations:
- description: Initiate an outbound voice call
  method: POST
  name: create-call
  path: /v1/calls
- description: Send an SMS or MMS message
  method: POST
  name: send-message
  path: /v1/messages
- description: Verify an MFA code
  method: POST
  name: verify-mfa
  path: /v1/mfa/verify
personas: []
provider_name: Bandwidth
provider_slug: bandwidth
search_terms:
- create call
- bandwidth
- developer building communication-enabled web or mobile applications
- e911 endpoint registration and management
- get call status
- send message
- multi-factor authentication via voice or sms
- list e911 endpoints
- retrieve the status and details of a voice call
- search available phone numbers
- send an mfa verification code via sms
- voice
- verify an mfa code
- list messages sent or received on the account
- submit a toll-free number for verification
- multi-factor authentication
- initiate an outbound voice call
- verify mfa
- search for available phone numbers to order
- list toll-free number verification requests
- messaging
- telephony
- communications
- list messages
- register an endpoint for e911 emergency calling
- voice call management
- send mfa code sms
- create e911 endpoint
- send sms message
- outbound and inbound voice call management and recording
- order phone numbers
- list toll free verifications
- send an sms or mms message
- sms
- list emergency calling (e911) endpoints for the account
- engineer designing and operating telephony and messaging infrastructure
- create voice call
- sms and mms message delivery and media management
- administrator managing bandwidth account, numbers, and compliance
- place an order for phone numbers
- sms/mms messaging
- verify mfa code
- search, order, and manage telephone numbers
- verify a multi-factor authentication code
- submit toll free verification
- send an sms or mms message via bandwidth messaging
- unified voice, messaging, mfa, phone numbers, e911, and toll-free management
- Application Developer
- Platform Administrator
- mfa
- Communications Engineer
- initiate an outbound voice call through bandwidth
- cpaas
slug: communications-platform
tags:
- Bandwidth
- Voice
- Messaging
- Communications
- Telephony
tools:
- description: Initiate an outbound voice call through Bandwidth
  hints:
    openWorld: false
    readOnly: false
  name: create-voice-call
- description: Retrieve the status and details of a voice call
  hints:
    openWorld: false
    readOnly: true
  name: get-call-status
- description: Send an SMS or MMS message via Bandwidth messaging
  hints:
    openWorld: false
    readOnly: false
  name: send-sms-message
- description: List messages sent or received on the account
  hints:
    openWorld: false
    readOnly: true
  name: list-messages
- description: Send an MFA verification code via SMS
  hints:
    openWorld: false
    readOnly: false
  name: send-mfa-code-sms
- description: Verify a multi-factor authentication code
  hints:
    openWorld: false
    readOnly: false
  name: verify-mfa-code
- description: Search for available phone numbers to order
  hints:
    openWorld: true
    readOnly: true
  name: search-available-phone-numbers
- description: Place an order for phone numbers
  hints:
    openWorld: false
    readOnly: false
  name: order-phone-numbers
- description: List emergency calling (E911) endpoints for the account
  hints:
    openWorld: false
    readOnly: true
  name: list-e911-endpoints
- description: Register an endpoint for E911 emergency calling
  hints:
    openWorld: false
    readOnly: false
  name: create-e911-endpoint
- description: List toll-free number verification requests
  hints:
    openWorld: false
    readOnly: true
  name: list-toll-free-verifications
- description: Submit a toll-free number for verification
  hints:
    openWorld: false
    readOnly: false
  name: submit-toll-free-verification
---
