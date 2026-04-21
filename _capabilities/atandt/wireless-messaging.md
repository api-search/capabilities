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
- get inbound sms
- att get inbound sms
- camara network-based fraud prevention using sim swap and number verification
- send an sms message to one or more recipients via at&t network
- at&t
- network-based fraud detection and threat intelligence
- developer building fraud prevention and identity verification using at&t network signals
- get inbound sms messages
- Identity Developer
- sms delivery status
- sms messaging and oauth authentication for consumer and business applications
- engineer integrating enterprise wireline services and ebonding systems
- Security Developer
- oauth token management
- enterprise
- send sms
- messaging
- sms and in-app messaging services
- retrieve inbound sms messages for an at&t registered endpoint
- wireline service ordering and qualification
- network
- mobile or web developer building consumer applications on at&t apis
- send sms message
- App Developer
- oauth
- att check sms delivery
- device status, roaming, and qos management
- fortune 100
- sms
- oauth and network-based authentication
- wireline
- wireless
- sms outbound messaging
- get delivery status
- 5g
- get sms delivery status
- get token
- sms inbound messages
- att send sms
- telecommunications
- developer integrating at&t enterprise connectivity and ebonding apis
- check delivery status of a sent at&t sms message
- broadband
- obtain oauth access token
- developer implementing frictionless mobile authentication via at&t network
- mobile virtual network operator managing subscribers on at&t infrastructure
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
