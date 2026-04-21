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
- Enterprise Developer
- in app send message
- sms send message
- sms check delivery status
- send mms or sms on behalf of user
- poll for inbound sms messages received on a registered short code
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- sms notifications and in-app messaging for mobile apps and enterprise systems
- mobile or web application developer embedding messaging into consumer apps
- send message
- in app delete message
- broadband
- enterprise
- notifications
- MVNO Operator
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- list user inbox messages
- Telecom Engineer
- check delivery status of a sent sms
- send an mms or sms message on behalf of an authenticated at&t user
- in app sync inbox delta
- messaging
- mvno business operator managing at&t-powered mobile subscribers and services
- list messages
- get inbound sms
- get full details of a specific inbox message including content and metadata
- sms
- poll for inbound sms messages
- telecommunications
- mobile network connectivity and subscriber management
- in app get message
- mms
- at&t
- wireless
- send sms
- developer building enterprise notification, alerting, or communication systems
- speech
- sms short code messaging
- get sms delivery status
- App Developer
- get inbox changes since last synchronization for efficient message management
- wireline
- sms delivery tracking
- sms short code inbox
- send an sms short code message to up to 50 recipients
- get inbox delta
- in-app user messaging inbox
- get inbox changes since last sync
- inbox delta synchronization
- sms and mms messaging services for consumer and enterprise applications
- delete a message from the user's inbox permanently
- check the delivery status of a sent sms message
- sms get inbound messages
- mobile
- complete mvno subscriber lifecycle and number portability management
- mobile virtual network operator services on at&t infrastructure
- list messages from a user's at&t inbox with pagination and unread filtering
- in app list messages
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
