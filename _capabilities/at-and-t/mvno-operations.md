---
categories: []
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
- phone number reservation
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- get subscriber service plan and profile
- telecommunications
- add balance to subscriber account
- messaging
- list portability orders
- activate a new subscriber on the at&t mvno network with a service plan
- mvno
- list devices
- add prepaid data or voice balance to a subscriber's account
- reserve number
- mobile virtual network operator services on at&t infrastructure
- retrieve subscriber's service plan, features, and account profile
- subscriber management
- MVNO Operator
- mobile
- create port order
- reserve phone number
- mobile network connectivity and subscriber management
- list devices and sims for subscriber
- wireless
- submit number portability order
- topup balance
- number portability
- topup subscriber balance
- activate subscriber
- subscriber activation and management
- port number in
- speech
- list all devices and sim cards associated with a subscriber
- at&t
- sms notifications and in-app messaging for mobile apps and enterprise systems
- reserve phone numbers for subscriber assignment
- get port order
- complete mvno subscriber lifecycle and number portability management
- get subscriber profile
- App Developer
- Enterprise Developer
- submit a number portability order to bring a subscriber's existing number to at&t mvno
- broadband
- activate a new mvno subscriber on at&t network
- get portability order status
- list number portability orders with optional state filtering
- subscriber balance management
- reserve phone numbers from the at&t number pool prior to subscriber activation
- tm forum
- check the current status of a number portability order
- number portability operations
- Telecom Engineer
- developer building enterprise notification, alerting, or communication systems
- sms and mms messaging services for consumer and enterprise applications
- enterprise
- wireline
- port order status
- list subscriber devices
- get port order status
- mobile or web application developer embedding messaging into consumer apps
- list port orders
- subscriber device inventory
- subscriber plan profile
- mvno business operator managing at&t-powered mobile subscribers and services
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
