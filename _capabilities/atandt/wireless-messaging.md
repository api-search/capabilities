---
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
- wireline
- sms outbound messaging
- device status, roaming, and qos management
- obtain oauth access token
- att check sms delivery
- oauth
- get inbound sms messages
- Identity Developer
- broadband
- enterprise
- sms inbound messages
- 5g
- messaging
- att get inbound sms
- send an sms message to one or more recipients via at&t network
- send sms
- get delivery status
- oauth and network-based authentication
- engineer integrating enterprise wireline services and ebonding systems
- network
- retrieve inbound sms messages for an at&t registered endpoint
- mobile or web developer building consumer applications on at&t apis
- developer building fraud prevention and identity verification using at&t network signals
- developer integrating at&t enterprise connectivity and ebonding apis
- Enterprise Developer
- get sms delivery status
- get inbound sms
- sms and in-app messaging services
- wireline service ordering and qualification
- developer implementing frictionless mobile authentication via at&t network
- oauth token management
- wireless
- camara network-based fraud prevention using sim swap and number verification
- check delivery status of a sent at&t sms message
- network-based fraud detection and threat intelligence
- sms delivery status
- at&t
- sms
- get token
- sms messaging and oauth authentication for consumer and business applications
- App Developer
- send sms message
- att send sms
- fortune 100
- telecommunications
- Security Developer
- mobile virtual network operator managing subscribers on at&t infrastructure
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
