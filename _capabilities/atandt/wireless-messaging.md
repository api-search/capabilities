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
- developer integrating at&t enterprise connectivity and ebonding apis
- Identity Developer
- sms
- sms outbound messaging
- network-based fraud detection and threat intelligence
- 5g
- App Developer
- check delivery status of a sent at&t sms message
- engineer integrating enterprise wireline services and ebonding systems
- telecommunications
- sms messaging and oauth authentication for consumer and business applications
- wireline
- oauth token management
- get delivery status
- att check sms delivery
- wireless
- camara network-based fraud prevention using sim swap and number verification
- oauth and network-based authentication
- get inbound sms messages
- sms inbound messages
- messaging
- mobile virtual network operator managing subscribers on at&t infrastructure
- network
- get token
- developer building fraud prevention and identity verification using at&t network signals
- device status, roaming, and qos management
- at&t
- sms delivery status
- att get inbound sms
- sms and in-app messaging services
- obtain oauth access token
- att send sms
- wireline service ordering and qualification
- enterprise
- broadband
- retrieve inbound sms messages for an at&t registered endpoint
- Security Developer
- Enterprise Developer
- get sms delivery status
- developer implementing frictionless mobile authentication via at&t network
- fortune 100
- send an sms message to one or more recipients via at&t network
- send sms
- send sms message
- get inbound sms
- mobile or web developer building consumer applications on at&t apis
- oauth
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
