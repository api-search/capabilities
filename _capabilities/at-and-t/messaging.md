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
- sms short code inbox
- Enterprise Developer
- send an sms short code message to up to 50 recipients
- sms get inbound messages
- list messages from a user's at&t inbox with pagination and unread filtering
- sms short code messaging
- mobile or web application developer embedding messaging into consumer apps
- get inbox delta
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- sms send message
- inbox delta synchronization
- send an mms or sms message on behalf of an authenticated at&t user
- get inbound sms
- at&t
- in app send message
- wireless
- in-app user messaging inbox
- send sms
- developer building enterprise notification, alerting, or communication systems
- telecommunications
- sms and mms messaging services for consumer and enterprise applications
- list user inbox messages
- broadband
- mms
- mobile network connectivity and subscriber management
- delete a message from the user's inbox permanently
- poll for inbound sms messages received on a registered short code
- sms delivery tracking
- get sms delivery status
- in app get message
- mvno business operator managing at&t-powered mobile subscribers and services
- Telecom Engineer
- send message
- check delivery status of a sent sms
- App Developer
- list messages
- in app list messages
- sms notifications and in-app messaging for mobile apps and enterprise systems
- complete mvno subscriber lifecycle and number portability management
- speech
- in app sync inbox delta
- notifications
- enterprise
- mobile
- messaging
- get inbox changes since last synchronization for efficient message management
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- mobile virtual network operator services on at&t infrastructure
- sms
- MVNO Operator
- check the delivery status of a sent sms message
- wireline
- get full details of a specific inbox message including content and metadata
- in app delete message
- poll for inbound sms messages
- sms check delivery status
- get inbox changes since last sync
- send mms or sms on behalf of user
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
