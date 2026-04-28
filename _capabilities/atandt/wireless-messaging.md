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
- oauth
- att check sms delivery
- get token
- sms outbound messaging
- developer building fraud prevention and identity verification using at&t network signals
- mobile virtual network operator managing subscribers on at&t infrastructure
- fortune 100
- send sms message
- network-based fraud detection and threat intelligence
- sms messaging and oauth authentication for consumer and business applications
- App Developer
- sms inbound messages
- get delivery status
- camara network-based fraud prevention using sim swap and number verification
- mobile or web developer building consumer applications on at&t apis
- oauth and network-based authentication
- at&t
- send sms
- Enterprise Developer
- wireline
- Identity Developer
- wireline service ordering and qualification
- get inbound sms messages
- sms delivery status
- wireless
- broadband
- 5g
- enterprise
- att send sms
- send an sms message to one or more recipients via at&t network
- engineer integrating enterprise wireline services and ebonding systems
- telecommunications
- developer integrating at&t enterprise connectivity and ebonding apis
- get inbound sms
- sms
- Security Developer
- obtain oauth access token
- att get inbound sms
- check delivery status of a sent at&t sms message
- device status, roaming, and qos management
- developer implementing frictionless mobile authentication via at&t network
- messaging
- get sms delivery status
- network
- oauth token management
- sms and in-app messaging services
- retrieve inbound sms messages for an at&t registered endpoint
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
