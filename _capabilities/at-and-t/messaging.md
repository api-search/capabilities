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
- App Developer
- send sms
- mobile network connectivity and subscriber management
- sms short code messaging
- sms get inbound messages
- in app get message
- send an mms or sms message on behalf of an authenticated at&t user
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- in app sync inbox delta
- list messages
- Enterprise Developer
- developer building enterprise notification, alerting, or communication systems
- sms delivery tracking
- list messages from a user's at&t inbox with pagination and unread filtering
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- in app delete message
- sms notifications and in-app messaging for mobile apps and enterprise systems
- mobile or web application developer embedding messaging into consumer apps
- sms and mms messaging services for consumer and enterprise applications
- complete mvno subscriber lifecycle and number portability management
- get inbox delta
- sms send message
- get inbox changes since last sync
- get sms delivery status
- notifications
- in-app user messaging inbox
- enterprise
- send an sms short code message to up to 50 recipients
- in app list messages
- send message
- check the delivery status of a sent sms message
- delete a message from the user's inbox permanently
- speech
- check delivery status of a sent sms
- inbox delta synchronization
- send mms or sms on behalf of user
- Telecom Engineer
- broadband
- sms short code inbox
- get inbound sms
- sms check delivery status
- messaging
- list user inbox messages
- mvno business operator managing at&t-powered mobile subscribers and services
- mms
- get full details of a specific inbox message including content and metadata
- mobile virtual network operator services on at&t infrastructure
- telecommunications
- get inbox changes since last synchronization for efficient message management
- wireless
- sms
- poll for inbound sms messages
- mobile
- wireline
- MVNO Operator
- poll for inbound sms messages received on a registered short code
- in app send message
- at&t
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
