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
- search, order, and manage telephone numbers
- register an endpoint for e911 emergency calling
- administrator managing bandwidth account, numbers, and compliance
- send an sms or mms message via bandwidth messaging
- search available phone numbers
- submit toll free verification
- list toll free verifications
- multi-factor authentication
- sms
- developer building communication-enabled web or mobile applications
- create call
- send sms message
- engineer designing and operating telephony and messaging infrastructure
- retrieve the status and details of a voice call
- order phone numbers
- list e911 endpoints
- unified voice, messaging, mfa, phone numbers, e911, and toll-free management
- verify mfa code
- cpaas
- search for available phone numbers to order
- bandwidth
- verify a multi-factor authentication code
- Communications Engineer
- sms and mms message delivery and media management
- initiate an outbound voice call through bandwidth
- voice
- messaging
- list toll-free number verification requests
- communications
- Platform Administrator
- send an mfa verification code via sms
- create voice call
- Application Developer
- outbound and inbound voice call management and recording
- initiate an outbound voice call
- list emergency calling (e911) endpoints for the account
- submit a toll-free number for verification
- send message
- voice call management
- verify mfa
- place an order for phone numbers
- mfa
- send mfa code sms
- multi-factor authentication via voice or sms
- verify an mfa code
- sms/mms messaging
- get call status
- send an sms or mms message
- e911 endpoint registration and management
- list messages
- list messages sent or received on the account
- telephony
- create e911 endpoint
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
