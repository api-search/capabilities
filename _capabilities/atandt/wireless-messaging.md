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
- Enterprise Developer
- sms delivery status
- developer integrating at&t enterprise connectivity and ebonding apis
- network-based fraud detection and threat intelligence
- check delivery status of a sent at&t sms message
- device status, roaming, and qos management
- get delivery status
- get inbound sms
- at&t
- wireless
- developer implementing frictionless mobile authentication via at&t network
- fortune 100
- send sms
- mobile or web developer building consumer applications on at&t apis
- oauth and network-based authentication
- telecommunications
- 5g
- wireline service ordering and qualification
- Identity Developer
- broadband
- retrieve inbound sms messages for an at&t registered endpoint
- sms outbound messaging
- obtain oauth access token
- sms messaging and oauth authentication for consumer and business applications
- get sms delivery status
- send an sms message to one or more recipients via at&t network
- get token
- oauth
- App Developer
- developer building fraud prevention and identity verification using at&t network signals
- Security Developer
- network
- send sms message
- messaging
- oauth token management
- sms
- engineer integrating enterprise wireline services and ebonding systems
- att send sms
- sms and in-app messaging services
- wireline
- mobile virtual network operator managing subscribers on at&t infrastructure
- att check sms delivery
- att get inbound sms
- camara network-based fraud prevention using sim swap and number verification
- sms inbound messages
- get inbound sms messages
- enterprise
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
