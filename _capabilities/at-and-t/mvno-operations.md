---
consumed_apis:
- att-mvnx
description: Comprehensive MVNO management capability using AT&T MVNX API for subscriber lifecycle management, number portability, device inventory, and balance management. Used by MVNO operators managing AT&T-powered mobile services.
layout: capability
name: AT&T MVNO Operations
operations:
- description: Activate a new MVNO subscriber on AT&T network
  method: POST
  name: activate-subscriber
  path: /v1/subscribers
- description: Get subscriber service plan and profile
  method: GET
  name: get-subscriber-profile
  path: /v1/subscribers/{subscriberId}/profile
- description: List devices and SIMs for subscriber
  method: GET
  name: list-devices
  path: /v1/subscribers/{subscriberId}/devices
- description: Reserve phone numbers for subscriber assignment
  method: POST
  name: reserve-number
  path: /v1/numbers/reserve
- description: Submit number portability order
  method: POST
  name: create-port-order
  path: /v1/porting
- description: List portability orders
  method: GET
  name: list-port-orders
  path: /v1/porting
- description: Get portability order status
  method: GET
  name: get-port-order
  path: /v1/porting/{orderId}
- description: Add balance to subscriber account
  method: POST
  name: topup-balance
  path: /v1/balance/topup
personas: []
provider_name: AT&T
provider_slug: at-and-t
search_terms:
- get subscriber service plan and profile
- mobile network connectivity and subscriber management
- reserve phone number
- wireline
- speech
- subscriber activation and management
- complete mvno subscriber lifecycle and number portability management
- list subscriber devices
- subscriber balance management
- broadband
- activate subscriber
- number portability operations
- add balance to subscriber account
- mvno business operator managing at&t-powered mobile subscribers and services
- enterprise
- get port order status
- messaging
- MVNO Operator
- sms notifications and in-app messaging for mobile apps and enterprise systems
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- port number in
- subscriber device inventory
- mvno
- create port order
- Enterprise Developer
- tm forum
- get subscriber profile
- reserve number
- port order status
- list devices and sims for subscriber
- list number portability orders with optional state filtering
- list devices
- number portability
- list all devices and sim cards associated with a subscriber
- mobile or web application developer embedding messaging into consumer apps
- check the current status of a number portability order
- wireless
- mobile virtual network operator services on at&t infrastructure
- at&t
- developer building enterprise notification, alerting, or communication systems
- mobile
- activate a new mvno subscriber on at&t network
- retrieve subscriber's service plan, features, and account profile
- subscriber plan profile
- list port orders
- topup balance
- reserve phone numbers from the at&t number pool prior to subscriber activation
- App Developer
- Telecom Engineer
- subscriber management
- list portability orders
- add prepaid data or voice balance to a subscriber's account
- get portability order status
- submit a number portability order to bring a subscriber's existing number to at&t mvno
- get port order
- phone number reservation
- telecommunications
- activate a new subscriber on the at&t mvno network with a service plan
- topup subscriber balance
- sms and mms messaging services for consumer and enterprise applications
- submit number portability order
- reserve phone numbers for subscriber assignment
slug: mvno-operations
tags:
- AT&T
- MVNO
- Subscriber Management
- Number Portability
- TM Forum
- Mobile
tools:
- description: Activate a new subscriber on the AT&T MVNO network with a service plan
  hints:
    destructive: false
    readOnly: false
  name: activate-subscriber
- description: Retrieve subscriber's service plan, features, and account profile
  hints:
    idempotent: true
    readOnly: true
  name: get-subscriber-profile
- description: List all devices and SIM cards associated with a subscriber
  hints:
    idempotent: true
    readOnly: true
  name: list-subscriber-devices
- description: Reserve phone numbers from the AT&T number pool prior to subscriber activation
  hints:
    destructive: false
    readOnly: false
  name: reserve-phone-number
- description: Submit a number portability order to bring a subscriber's existing number to AT&T MVNO
  hints:
    destructive: false
    readOnly: false
  name: port-number-in
- description: Check the current status of a number portability order
  hints:
    idempotent: true
    readOnly: true
  name: get-port-order-status
- description: List number portability orders with optional state filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-port-orders
- description: Add prepaid data or voice balance to a subscriber's account
  hints:
    destructive: false
    readOnly: false
  name: topup-subscriber-balance
---
