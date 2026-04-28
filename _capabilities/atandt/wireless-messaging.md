---
categories:
- messaging
consumed_apis:
- att-wireless-apis
description: Workflow capability combining AT&T Wireless APIs for SMS messaging and OAuth authentication. Used by developers building consumer and business messaging applications on the AT&T network.
layout: capability
name: AT&T Wireless Messaging
operations:
- description: Obtain OAuth access token
  method: POST
  name: get-token
  path: /v1/auth/token
- description: Send SMS message
  method: POST
  name: send-sms
  path: /v1/sms/outbox
- description: Get SMS delivery status
  method: GET
  name: get-delivery-status
  path: /v1/sms/outbox/{messageId}
- description: Get inbound SMS messages
  method: GET
  name: get-inbound-sms
  path: /v1/sms/inbox/{registrationId}
personas: []
provider_name: AT&T
provider_slug: atandt
search_terms:
- att send sms
- send sms message
- get inbound sms
- fortune 100
- engineer integrating enterprise wireline services and ebonding systems
- att check sms delivery
- get sms delivery status
- Security Developer
- obtain oauth access token
- wireline service ordering and qualification
- developer integrating at&t enterprise connectivity and ebonding apis
- at&t
- sms messaging and oauth authentication for consumer and business applications
- Identity Developer
- device status, roaming, and qos management
- send sms
- check delivery status of a sent at&t sms message
- oauth
- mobile or web developer building consumer applications on at&t apis
- telecommunications
- developer building fraud prevention and identity verification using at&t network signals
- sms
- Enterprise Developer
- get inbound sms messages
- enterprise
- mobile virtual network operator managing subscribers on at&t infrastructure
- network-based fraud detection and threat intelligence
- retrieve inbound sms messages for an at&t registered endpoint
- sms delivery status
- 5g
- sms inbound messages
- network
- sms outbound messaging
- send an sms message to one or more recipients via at&t network
- messaging
- developer implementing frictionless mobile authentication via at&t network
- broadband
- App Developer
- camara network-based fraud prevention using sim swap and number verification
- get delivery status
- oauth token management
- get token
- oauth and network-based authentication
- att get inbound sms
- wireline
- sms and in-app messaging services
- wireless
slug: wireless-messaging
tags:
- AT&T
- SMS
- Messaging
- Wireless
- OAuth
tools:
- description: Send an SMS message to one or more recipients via AT&T network
  hints:
    destructive: false
    readOnly: false
  name: att-send-sms
- description: Check delivery status of a sent AT&T SMS message
  hints:
    idempotent: true
    readOnly: true
  name: att-check-sms-delivery
- description: Retrieve inbound SMS messages for an AT&T registered endpoint
  hints:
    idempotent: true
    readOnly: true
  name: att-get-inbound-sms
---
