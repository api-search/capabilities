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
- list user inbox messages
- in app get message
- send an sms short code message to up to 50 recipients
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- telecommunications
- notifications
- messaging
- sms delivery tracking
- mobile virtual network operator services on at&t infrastructure
- check the delivery status of a sent sms message
- sms check delivery status
- MVNO Operator
- mobile
- in-app user messaging inbox
- send message
- poll for inbound sms messages received on a registered short code
- mobile network connectivity and subscriber management
- wireless
- get inbox delta
- poll for inbound sms messages
- speech
- send an mms or sms message on behalf of an authenticated at&t user
- at&t
- get inbox changes since last sync
- in app sync inbox delta
- check delivery status of a sent sms
- sms get inbound messages
- sms notifications and in-app messaging for mobile apps and enterprise systems
- get full details of a specific inbox message including content and metadata
- in app send message
- in app delete message
- list messages from a user's at&t inbox with pagination and unread filtering
- get inbound sms
- App Developer
- Enterprise Developer
- complete mvno subscriber lifecycle and number portability management
- sms short code inbox
- list messages
- broadband
- delete a message from the user's inbox permanently
- sms send message
- Telecom Engineer
- developer building enterprise notification, alerting, or communication systems
- sms and mms messaging services for consumer and enterprise applications
- inbox delta synchronization
- sms short code messaging
- send mms or sms on behalf of user
- mms
- in app list messages
- get inbox changes since last synchronization for efficient message management
- wireline
- sms
- enterprise
- get sms delivery status
- mobile or web application developer embedding messaging into consumer apps
- send sms
- mvno business operator managing at&t-powered mobile subscribers and services
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
