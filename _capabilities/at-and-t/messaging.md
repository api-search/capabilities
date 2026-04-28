---
categories:
- messaging
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
- in app get message
- sms check delivery status
- in app list messages
- get inbound sms
- sms delivery tracking
- get inbox changes since last sync
- get sms delivery status
- sms short code inbox
- poll for inbound sms messages
- developer building enterprise notification, alerting, or communication systems
- sms short code messaging
- poll for inbound sms messages received on a registered short code
- at&t
- send an mms or sms message on behalf of an authenticated at&t user
- sms notifications and in-app messaging for mobile apps and enterprise systems
- send sms
- mms
- complete mvno subscriber lifecycle and number portability management
- MVNO Operator
- sms send message
- telecommunications
- enterprise
- sms
- sms get inbound messages
- send an sms short code message to up to 50 recipients
- Enterprise Developer
- mobile network connectivity and subscriber management
- mobile virtual network operator services on at&t infrastructure
- list messages from a user's at&t inbox with pagination and unread filtering
- check delivery status of a sent sms
- wireline
- notifications
- send mms or sms on behalf of user
- mobile or web application developer embedding messaging into consumer apps
- in-app user messaging inbox
- send message
- get inbox delta
- sms and mms messaging services for consumer and enterprise applications
- messaging
- broadband
- inbox delta synchronization
- App Developer
- check the delivery status of a sent sms message
- delete a message from the user's inbox permanently
- list messages
- speech
- get inbox changes since last synchronization for efficient message management
- in app sync inbox delta
- list user inbox messages
- mvno business operator managing at&t-powered mobile subscribers and services
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- in app send message
- mobile
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- Telecom Engineer
- get full details of a specific inbox message including content and metadata
- wireless
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
