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
- device status, roaming, and qos management
- App Developer
- send sms
- oauth token management
- Enterprise Developer
- broadband
- sms delivery status
- camara network-based fraud prevention using sim swap and number verification
- oauth and network-based authentication
- att send sms
- att get inbound sms
- 5g
- att check sms delivery
- at&t
- mobile or web developer building consumer applications on at&t apis
- get sms delivery status
- mobile virtual network operator managing subscribers on at&t infrastructure
- Security Developer
- developer implementing frictionless mobile authentication via at&t network
- network
- enterprise
- obtain oauth access token
- check delivery status of a sent at&t sms message
- send an sms message to one or more recipients via at&t network
- sms and in-app messaging services
- send sms message
- get token
- get inbound sms messages
- get inbound sms
- fortune 100
- messaging
- wireline service ordering and qualification
- retrieve inbound sms messages for an at&t registered endpoint
- telecommunications
- wireless
- sms inbound messages
- developer integrating at&t enterprise connectivity and ebonding apis
- sms messaging and oauth authentication for consumer and business applications
- sms
- oauth
- Identity Developer
- wireline
- engineer integrating enterprise wireline services and ebonding systems
- network-based fraud detection and threat intelligence
- sms outbound messaging
- developer building fraud prevention and identity verification using at&t network signals
- get delivery status
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
