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
- get delivery status
- att check sms delivery
- App Developer
- sms and in-app messaging services
- wireline service ordering and qualification
- Identity Developer
- oauth
- send an sms message to one or more recipients via at&t network
- att send sms
- sms
- retrieve inbound sms messages for an at&t registered endpoint
- send sms message
- obtain oauth access token
- broadband
- send sms
- enterprise
- sms outbound messaging
- developer implementing frictionless mobile authentication via at&t network
- camara network-based fraud prevention using sim swap and number verification
- oauth token management
- get token
- sms inbound messages
- developer integrating at&t enterprise connectivity and ebonding apis
- device status, roaming, and qos management
- 5g
- messaging
- developer building fraud prevention and identity verification using at&t network signals
- mobile virtual network operator managing subscribers on at&t infrastructure
- telecommunications
- att get inbound sms
- sms delivery status
- mobile or web developer building consumer applications on at&t apis
- get sms delivery status
- fortune 100
- network
- get inbound sms messages
- check delivery status of a sent at&t sms message
- wireless
- sms messaging and oauth authentication for consumer and business applications
- at&t
- network-based fraud detection and threat intelligence
- engineer integrating enterprise wireline services and ebonding systems
- oauth and network-based authentication
- Security Developer
- get inbound sms
- Enterprise Developer
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
