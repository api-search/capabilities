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
- complete mvno subscriber lifecycle and number portability management
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- in app get message
- mobile virtual network operator services on at&t infrastructure
- App Developer
- inbox delta synchronization
- get inbox changes since last synchronization for efficient message management
- sms delivery tracking
- at&t
- send sms
- sms notifications and in-app messaging for mobile apps and enterprise systems
- Enterprise Developer
- send message
- mms
- wireline
- MVNO Operator
- mobile network connectivity and subscriber management
- get inbox changes since last sync
- check the delivery status of a sent sms message
- poll for inbound sms messages received on a registered short code
- wireless
- in app list messages
- list user inbox messages
- sms send message
- enterprise
- mobile
- sms and mms messaging services for consumer and enterprise applications
- list messages
- sms get inbound messages
- telecommunications
- in app delete message
- get inbound sms
- list messages from a user's at&t inbox with pagination and unread filtering
- sms
- notifications
- in-app user messaging inbox
- check delivery status of a sent sms
- send an sms short code message to at&t subscribers for notifications, alerts, or marketing
- send an mms or sms message on behalf of an authenticated at&t user
- poll for inbound sms messages
- in app sync inbox delta
- mvno business operator managing at&t-powered mobile subscribers and services
- get full details of a specific inbox message including content and metadata
- sms check delivery status
- sms short code messaging
- messaging
- send an sms short code message to up to 50 recipients
- sms short code inbox
- send mms or sms on behalf of user
- Telecom Engineer
- get sms delivery status
- speech
- mobile or web application developer embedding messaging into consumer apps
- developer building enterprise notification, alerting, or communication systems
- delete a message from the user's inbox permanently
- broadband
- in app send message
- get inbox delta
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
