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
- port number in
- mobile
- list all devices and sim cards associated with a subscriber
- subscriber balance management
- mobile network connectivity and subscriber management
- create port order
- mobile or web application developer embedding messaging into consumer apps
- reserve number
- Enterprise Developer
- reserve phone numbers for subscriber assignment
- list subscriber devices
- subscriber device inventory
- number portability
- list portability orders
- get port order status
- subscriber activation and management
- messaging
- phone number reservation
- at&t
- developer building enterprise notification, alerting, or communication systems
- subscriber management
- topup balance
- reserve phone number
- engineer integrating at&t network services with bss/oss systems via tm forum apis
- list devices and sims for subscriber
- sms and mms messaging services for consumer and enterprise applications
- activate a new mvno subscriber on at&t network
- submit number portability order
- sms notifications and in-app messaging for mobile apps and enterprise systems
- Telecom Engineer
- submit a number portability order to bring a subscriber's existing number to at&t mvno
- telecommunications
- subscriber plan profile
- list devices
- retrieve subscriber's service plan, features, and account profile
- get subscriber service plan and profile
- add prepaid data or voice balance to a subscriber's account
- wireless
- get port order
- add balance to subscriber account
- activate subscriber
- port order status
- reserve phone numbers from the at&t number pool prior to subscriber activation
- mobile virtual network operator services on at&t infrastructure
- list number portability orders with optional state filtering
- enterprise
- mvno
- MVNO Operator
- wireline
- activate a new subscriber on the at&t mvno network with a service plan
- list port orders
- mvno business operator managing at&t-powered mobile subscribers and services
- number portability operations
- get subscriber profile
- tm forum
- complete mvno subscriber lifecycle and number portability management
- App Developer
- get portability order status
- broadband
- check the current status of a number portability order
- speech
- topup subscriber balance
slug: mvno-operations
source_filename: mvno-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AT&T MVNO Operations\"\n  description: \"Comprehensive MVNO management capability using AT&T MVNX API for subscriber lifecycle management, number portability, device inventory, and balance management. Used by MVNO operators managing AT&T-powered mobile services.\"\n  tags:\n    - AT&T\n    - MVNO\n    - Subscriber Management\n    - Number Portability\n    - TM Forum\n    - Mobile\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATT_MVNX_CLIENT_ID: ATT_MVNX_CLIENT_ID\n\ncapability:\n  consumes:\n    - import: att-mvnx\n      location: ./shared/mvnx-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: att-mvno-api\n      description: \"Unified REST API for AT&T MVNO subscriber and service management.\"\n      resources:\n        - path: /v1/subscribers\n          name: subscribers\n          description: \"Subscriber activation and management\"\n      \
  \    operations:\n            - method: POST\n              name: activate-subscriber\n              description: \"Activate a new MVNO subscriber on AT&T network\"\n              call: \"att-mvnx.create-product-order\"\n              with:\n                externalId: \"rest.externalId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscribers/{subscriberId}/profile\n          name: subscriber-profile\n          description: \"Subscriber plan profile\"\n          operations:\n            - method: GET\n              name: get-subscriber-profile\n              description: \"Get subscriber service plan and profile\"\n              call: \"att-mvnx.get-subscriber-profile\"\n              with:\n                id: \"rest.subscriberId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscribers/{subscriberId}/devices\n          name: subscriber-devices\n\
  \          description: \"Subscriber device inventory\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List devices and SIMs for subscriber\"\n              call: \"att-mvnx.list-resources\"\n              with:\n                relatedParty.id: \"rest.subscriberId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/numbers/reserve\n          name: number-reservation\n          description: \"Phone number reservation\"\n          operations:\n            - method: POST\n              name: reserve-number\n              description: \"Reserve phone numbers for subscriber assignment\"\n              call: \"att-mvnx.reserve-number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/porting\n          name: porting\n          description: \"Number portability operations\"\n         \
  \ operations:\n            - method: POST\n              name: create-port-order\n              description: \"Submit number portability order\"\n              call: \"att-mvnx.create-portability-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-port-orders\n              description: \"List portability orders\"\n              call: \"att-mvnx.list-portability-orders\"\n              with:\n                state: \"rest.state\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/porting/{orderId}\n          name: port-order-detail\n          description: \"Port order status\"\n          operations:\n            - method: GET\n              name: get-port-order\n              description: \"Get portability order status\"\n              call: \"att-mvnx.get-portability-order\"\
  \n              with:\n                id: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/balance/topup\n          name: balance-management\n          description: \"Subscriber balance management\"\n          operations:\n            - method: POST\n              name: topup-balance\n              description: \"Add balance to subscriber account\"\n              call: \"att-mvnx.topup-balance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: att-mvno-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AT&T MVNO subscriber lifecycle and operations management.\"\n      tools:\n        - name: activate-subscriber\n          description: \"Activate a new subscriber on the AT&T MVNO network with a service plan\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"att-mvnx.create-product-order\"\n          with:\n            externalId: \"tools.externalId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subscriber-profile\n          description: \"Retrieve subscriber's service plan, features, and account profile\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-mvnx.get-subscriber-profile\"\n          with:\n            id: \"tools.subscriberId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriber-devices\n          description: \"List all devices and SIM cards associated with a subscriber\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-mvnx.list-resources\"\n          with:\n            relatedParty.id: \"tools.subscriberId\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: reserve-phone-number\n          description: \"Reserve phone numbers from the AT&T number pool prior to subscriber activation\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-mvnx.reserve-number\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: port-number-in\n          description: \"Submit a number portability order to bring a subscriber's existing number to AT&T MVNO\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-mvnx.create-portability-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-port-order-status\n          description: \"Check the current status of a number portability order\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-mvnx.get-portability-order\"\
  \n          with:\n            id: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-port-orders\n          description: \"List number portability orders with optional state filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-mvnx.list-portability-orders\"\n          with:\n            state: \"tools.state\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: topup-subscriber-balance\n          description: \"Add prepaid data or voice balance to a subscriber's account\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-mvnx.topup-balance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/at-and-t/refs/heads/main/capabilities/mvno-operations.yaml
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
