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
- Enterprise Developer
- get port order
- port number in
- list port orders
- mobile or web application developer embedding messaging into consumer apps
- get portability order status
- subscriber balance management
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- submit number portability order
- list subscriber devices
- list portability orders
- get port order status
- create port order
- at&t
- list all devices and sim cards associated with a subscriber
- activate subscriber
- wireless
- developer building enterprise notification, alerting, or communication systems
- reserve phone numbers from the at&t number pool prior to subscriber activation
- telecommunications
- mvno
- sms and mms messaging services for consumer and enterprise applications
- broadband
- mobile network connectivity and subscriber management
- reserve number
- subscriber management
- topup subscriber balance
- subscriber plan profile
- mvno business operator managing at&t-powered mobile subscribers and services
- list devices
- get subscriber service plan and profile
- number portability operations
- port order status
- get subscriber profile
- reserve phone number
- check the current status of a number portability order
- subscriber activation and management
- activate a new subscriber on the at&t mvno network with a service plan
- App Developer
- Telecom Engineer
- phone number reservation
- topup balance
- number portability
- sms notifications and in-app messaging for mobile apps and enterprise systems
- complete mvno subscriber lifecycle and number portability management
- tm forum
- speech
- reserve phone numbers for subscriber assignment
- retrieve subscriber's service plan, features, and account profile
- mobile
- add prepaid data or voice balance to a subscriber's account
- activate a new mvno subscriber on at&t network
- messaging
- mobile virtual network operator services on at&t infrastructure
- add balance to subscriber account
- list number portability orders with optional state filtering
- submit a number portability order to bring a subscriber's existing number to at&t mvno
- MVNO Operator
- wireline
- list devices and sims for subscriber
- subscriber device inventory
- enterprise
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
