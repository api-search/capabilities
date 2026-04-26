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
- submit a number portability order to bring a subscriber's existing number to at&t mvno
- get subscriber profile
- Telecom Engineer
- subscriber plan profile
- create port order
- activate a new subscriber on the at&t mvno network with a service plan
- get port order
- add prepaid data or voice balance to a subscriber's account
- reserve number
- mobile network connectivity and subscriber management
- list all devices and sim cards associated with a subscriber
- list number portability orders with optional state filtering
- phone number reservation
- App Developer
- subscriber balance management
- number portability
- port number in
- list devices and sims for subscriber
- complete mvno subscriber lifecycle and number portability management
- topup subscriber balance
- telecommunications
- get port order status
- mvno
- wireline
- get subscriber service plan and profile
- submit number portability order
- mobile or web application developer embedding messaging into consumer apps
- developer building enterprise notification, alerting, or communication systems
- port order status
- mvno business operator managing at&t-powered mobile subscribers and services
- activate a new mvno subscriber on at&t network
- wireless
- sms notifications and in-app messaging for mobile apps and enterprise systems
- mobile virtual network operator services on at&t infrastructure
- get portability order status
- speech
- messaging
- at&t
- subscriber device inventory
- tm forum
- list port orders
- topup balance
- mobile
- MVNO Operator
- enterprise
- broadband
- list devices
- subscriber activation and management
- add balance to subscriber account
- Enterprise Developer
- subscriber management
- list portability orders
- list subscriber devices
- check the current status of a number portability order
- retrieve subscriber's service plan, features, and account profile
- number portability operations
- reserve phone number
- reserve phone numbers for subscriber assignment
- reserve phone numbers from the at&t number pool prior to subscriber activation
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- activate subscriber
- sms and mms messaging services for consumer and enterprise applications
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
