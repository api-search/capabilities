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
- att check sms delivery
- sms and in-app messaging services
- enterprise
- Enterprise Developer
- oauth and network-based authentication
- sms messaging and oauth authentication for consumer and business applications
- check delivery status of a sent at&t sms message
- Identity Developer
- send sms message
- developer building fraud prevention and identity verification using at&t network signals
- wireline service ordering and qualification
- sms inbound messages
- get delivery status
- wireless
- telecommunications
- engineer integrating enterprise wireline services and ebonding systems
- at&t
- sms delivery status
- broadband
- network
- mobile or web developer building consumer applications on at&t apis
- App Developer
- obtain oauth access token
- oauth token management
- developer integrating at&t enterprise connectivity and ebonding apis
- messaging
- fortune 100
- Security Developer
- sms
- oauth
- wireline
- sms outbound messaging
- send an sms message to one or more recipients via at&t network
- developer implementing frictionless mobile authentication via at&t network
- camara network-based fraud prevention using sim swap and number verification
- get sms delivery status
- get inbound sms messages
- att send sms
- mobile virtual network operator managing subscribers on at&t infrastructure
- retrieve inbound sms messages for an at&t registered endpoint
- 5g
- device status, roaming, and qos management
- send sms
- att get inbound sms
- network-based fraud detection and threat intelligence
- get inbound sms
- get token
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
