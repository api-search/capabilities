---
consumed_apis:
- att-sms
- att-iam
description: Unified messaging capability combining AT&T SMS API and In-App Messaging API for customer notifications, two-way messaging, and inbox management. Used by developers building mobile apps and enterprise notification systems.
layout: capability
name: AT&T Messaging
operations:
- description: Send an SMS short code message to up to 50 recipients
  method: POST
  name: send-sms
  path: /v1/sms/messages
- description: Check delivery status of a sent SMS
  method: GET
  name: get-sms-delivery-status
  path: /v1/sms/messages/{messageId}/status
- description: Poll for inbound SMS messages
  method: GET
  name: get-inbound-sms
  path: /v1/sms/inbox/{registrationId}
- description: Send MMS or SMS on behalf of user
  method: POST
  name: send-message
  path: /v1/in-app/messages
- description: List user inbox messages
  method: GET
  name: list-messages
  path: /v1/in-app/messages
- description: Get inbox changes since last sync
  method: GET
  name: get-inbox-delta
  path: /v1/in-app/delta
personas: []
provider_name: AT&T
provider_slug: at-and-t
search_terms:
- get inbox delta
- Telecom Engineer
- list messages
- delete a message from the user's inbox permanently
- sms
- mobile network connectivity and subscriber management
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- poll for inbound sms messages
- sms get inbound messages
- App Developer
- send an mms or sms message on behalf of an authenticated at&t user
- list messages from a user's at&t inbox with pagination and unread filtering
- complete mvno subscriber lifecycle and number portability management
- check delivery status of a sent sms
- poll for inbound sms messages received on a registered short code
- telecommunications
- send message
- wireline
- get full details of a specific inbox message including content and metadata
- developer building enterprise notification, alerting, or communication systems
- mobile or web application developer embedding messaging into consumer apps
- mvno business operator managing at&t-powered mobile subscribers and services
- wireless
- in app sync inbox delta
- sms notifications and in-app messaging for mobile apps and enterprise systems
- sms check delivery status
- mobile virtual network operator services on at&t infrastructure
- speech
- messaging
- in app get message
- notifications
- at&t
- mms
- sms and mms messaging services for consumer and enterprise applications
- check the delivery status of a sent sms message
- mobile
- sms send message
- sms short code inbox
- in app send message
- MVNO Operator
- broadband
- enterprise
- send an sms short code message to up to 50 recipients
- get sms delivery status
- in-app user messaging inbox
- Enterprise Developer
- in app list messages
- list user inbox messages
- send sms
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- sms short code messaging
- get inbox changes since last synchronization for efficient message management
- get inbox changes since last sync
- get inbound sms
- inbox delta synchronization
- sms delivery tracking
- send mms or sms on behalf of user
- in app delete message
slug: messaging
tags:
- AT&T
- SMS
- MMS
- Messaging
- Notifications
- Mobile
tools:
- description: Send an SMS short code message to AT&T subscribers for notifications, alerts, or marketing
  hints:
    destructive: false
    readOnly: false
  name: sms-send-message
- description: Check the delivery status of a sent SMS message
  hints:
    idempotent: true
    readOnly: true
  name: sms-check-delivery-status
- description: Poll for inbound SMS messages received on a registered short code
  hints:
    idempotent: true
    readOnly: true
  name: sms-get-inbound-messages
- description: Send an MMS or SMS message on behalf of an authenticated AT&T user
  hints:
    destructive: false
    readOnly: false
  name: in-app-send-message
- description: List messages from a user's AT&T inbox with pagination and unread filtering
  hints:
    idempotent: true
    readOnly: true
  name: in-app-list-messages
- description: Get full details of a specific inbox message including content and metadata
  hints:
    idempotent: true
    readOnly: true
  name: in-app-get-message
- description: Delete a message from the user's inbox permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: in-app-delete-message
- description: Get inbox changes since last synchronization for efficient message management
  hints:
    idempotent: true
    readOnly: true
  name: in-app-sync-inbox-delta
---
