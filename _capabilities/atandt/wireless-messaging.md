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
- sms and in-app messaging services
- send sms message
- mobile virtual network operator managing subscribers on at&t infrastructure
- Enterprise Developer
- 5g
- get token
- broadband
- check delivery status of a sent at&t sms message
- oauth
- enterprise
- developer building fraud prevention and identity verification using at&t network signals
- send an sms message to one or more recipients via at&t network
- sms messaging and oauth authentication for consumer and business applications
- messaging
- get inbound sms
- Identity Developer
- sms
- telecommunications
- oauth and network-based authentication
- wireline service ordering and qualification
- mobile or web developer building consumer applications on at&t apis
- wireless
- at&t
- Security Developer
- oauth token management
- obtain oauth access token
- send sms
- sms inbound messages
- get delivery status
- att check sms delivery
- sms delivery status
- camara network-based fraud prevention using sim swap and number verification
- get sms delivery status
- App Developer
- engineer integrating enterprise wireline services and ebonding systems
- wireline
- sms outbound messaging
- retrieve inbound sms messages for an at&t registered endpoint
- get inbound sms messages
- att send sms
- network
- att get inbound sms
- fortune 100
- network-based fraud detection and threat intelligence
- device status, roaming, and qos management
- developer integrating at&t enterprise connectivity and ebonding apis
- developer implementing frictionless mobile authentication via at&t network
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
