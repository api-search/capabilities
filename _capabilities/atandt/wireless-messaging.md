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
- network-based fraud detection and threat intelligence
- wireline service ordering and qualification
- att get inbound sms
- fortune 100
- sms inbound messages
- sms delivery status
- messaging
- get token
- telecommunications
- get delivery status
- att check sms delivery
- developer implementing frictionless mobile authentication via at&t network
- oauth and network-based authentication
- developer building fraud prevention and identity verification using at&t network signals
- wireless
- Security Developer
- sms outbound messaging
- developer integrating at&t enterprise connectivity and ebonding apis
- at&t
- 5g
- check delivery status of a sent at&t sms message
- device status, roaming, and qos management
- get inbound sms
- App Developer
- Enterprise Developer
- broadband
- network
- att send sms
- oauth
- engineer integrating enterprise wireline services and ebonding systems
- mobile or web developer building consumer applications on at&t apis
- Identity Developer
- oauth token management
- mobile virtual network operator managing subscribers on at&t infrastructure
- retrieve inbound sms messages for an at&t registered endpoint
- sms and in-app messaging services
- obtain oauth access token
- enterprise
- wireline
- sms messaging and oauth authentication for consumer and business applications
- sms
- get sms delivery status
- send sms message
- send sms
- camara network-based fraud prevention using sim swap and number verification
- get inbound sms messages
- send an sms message to one or more recipients via at&t network
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
