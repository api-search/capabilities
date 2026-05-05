---
categories: []
consumed_apis:
- wm-customer
description: Unified customer service capability for Waste Management accounts. Combines account management, service scheduling, ETA tracking, and billing operations to support residential and commercial customer self-service workflows.
layout: capability
name: Waste Management Customer Service
operations:
- description: Get customer account overview including balance and contact details.
  method: GET
  name: get-account-overview
  path: /v1/account
- description: Get the current balance due.
  method: GET
  name: get-balance
  path: /v1/balance
- description: List all services for the customer.
  method: GET
  name: list-services
  path: /v1/services
- description: Get today's planned service schedule.
  method: GET
  name: list-planned-services
  path: /v1/services/planned
- description: Get upcoming pickup schedule.
  method: GET
  name: get-next-pickup
  path: /v1/services/next-pickup
- description: Get ETA for today's scheduled pickup.
  method: GET
  name: get-service-eta
  path: /v1/services/{serviceId}/eta
- description: List all invoices with optional date range.
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Get details for a specific invoice.
  method: GET
  name: get-invoice-details
  path: /v1/invoices/{invoiceId}
- description: List billing and service contacts.
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Update billing or service contact information.
  method: PATCH
  name: update-contacts
  path: /v1/contacts
- description: Get paperless billing and autopay preferences.
  method: GET
  name: get-preferences
  path: /v1/preferences
- description: Update paperless billing or autopay enrollment.
  method: PATCH
  name: update-preferences
  path: /v1/preferences
personas: []
provider_name: Waste Management
provider_slug: waste-management
search_terms:
- list service fees
- account management
- update paperless billing or autopay enrollment.
- recycling
- get next pickup
- update billing or service contact information.
- get planned services
- billing
- get invoice details
- customer service
- current balance due on the account.
- get eta for today's scheduled pickup.
- update contact name, email, or phone number on the wm customer account.
- check if the wm customer is enrolled in paperless billing or autopay.
- environmental services
- list invoices
- get today's planned service schedule.
- full invoice details with line items and fees.
- customer account overview with balance and profile.
- list all invoices with optional date range.
- list billing and service contacts.
- get the current amount due on the wm customer account.
- get balance
- fortune 500
- solid waste
- get preferences
- waste management
- list all services for the customer.
- list services
- billing and service contact management.
- customer billing and notification preferences.
- list wm billing invoices, optionally filtered by date range.
- list billing and service contacts on the wm customer account.
- list planned services
- get the current balance due.
- services scheduled for pickup today.
- update preferences
- get service eta
- get customer account overview including balance and contact details.
- estimated time of arrival for a service.
- get the types of materials (garbage, recycling, yard waste) collected for each service.
- get the wm customer account overview including balance due and contact information.
- list contacts
- list all active waste and recycling collection services for the customer.
- all waste and recycling services for the account.
- find out when the next garbage and recycling pickup is scheduled.
- get paperless billing and autopay preferences.
- update contacts
- sustainability
- enroll or unenroll the wm customer in paperless billing or automatic payment.
- get details for a specific invoice.
- get the full breakdown of a specific wm invoice including fees and line items.
- check which waste collection services are scheduled for pickup today.
- get account overview
- get the breakdown of fuel surcharges, environmental fees, and regulatory recovery fees on services.
- get upcoming pickup schedule.
- invoice history and billing records.
- get the estimated arrival window for a wm truck on a scheduled service day.
- list service materials
- service scheduling
- next scheduled garbage and recycling pickup.
slug: customer-service
source_filename: customer-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Waste Management Customer Service\"\n  description: >-\n    Unified customer service capability for Waste Management accounts. Combines\n    account management, service scheduling, ETA tracking, and billing operations\n    to support residential and commercial customer self-service workflows.\n  tags:\n    - Waste Management\n    - Customer Service\n    - Billing\n    - Service Scheduling\n    - Account Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WM_JWT_TOKEN: WM_JWT_TOKEN\n      WM_CLIENT_ID: WM_CLIENT_ID\n\ncapability:\n  consumes:\n    - import: wm-customer\n      location: ./shared/customer-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wm-customer-service-api\n      description: \"Unified REST API for Waste Management customer service workflows.\"\n      resources:\n        - path: /v1/account\n          name: account\n    \
  \      description: \"Customer account overview with balance and profile.\"\n          operations:\n            - method: GET\n              name: get-account-overview\n              description: \"Get customer account overview including balance and contact details.\"\n              call: \"wm-customer.get-customer-overview\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/balance\n          name: balance\n          description: \"Current balance due on the account.\"\n          operations:\n            - method: GET\n              name: get-balance\n              description: \"Get the current balance due.\"\n              call: \"wm-customer.get-balance\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services\n          name: services\n          description: \"All waste\
  \ and recycling services for the account.\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List all services for the customer.\"\n              call: \"wm-customer.list-services\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/planned\n          name: planned-services\n          description: \"Services scheduled for pickup today.\"\n          operations:\n            - method: GET\n              name: list-planned-services\n              description: \"Get today's planned service schedule.\"\n              call: \"wm-customer.list-planned-services\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/next-pickup\n     \
  \     name: next-pickup\n          description: \"Next scheduled garbage and recycling pickup.\"\n          operations:\n            - method: GET\n              name: get-next-pickup\n              description: \"Get upcoming pickup schedule.\"\n              call: \"wm-customer.get-next-pickup\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}/eta\n          name: service-eta\n          description: \"Estimated time of arrival for a service.\"\n          operations:\n            - method: GET\n              name: get-service-eta\n              description: \"Get ETA for today's scheduled pickup.\"\n              call: \"wm-customer.get-service-eta\"\n              with:\n                customerId: \"rest.customerId\"\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice history and billing records.\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List all invoices with optional date range.\"\n              call: \"wm-customer.list-invoices\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices/{invoiceId}\n          name: invoice-detail\n          description: \"Full invoice details with line items and fees.\"\n          operations:\n            - method: GET\n              name: get-invoice-details\n              description: \"Get details for a specific invoice.\"\n              call: \"wm-customer.get-invoice-details\"\n              with:\n                customerId: \"rest.customerId\"\n            \
  \    invoiceId: \"rest.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts\n          name: contacts\n          description: \"Billing and service contact management.\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List billing and service contacts.\"\n              call: \"wm-customer.list-contacts\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-contacts\n              description: \"Update billing or service contact information.\"\n              call: \"wm-customer.update-contacts\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n        - path: /v1/preferences\n          name: preferences\n          description: \"Customer billing and notification preferences.\"\n          operations:\n            - method: GET\n              name: get-preferences\n              description: \"Get paperless billing and autopay preferences.\"\n              call: \"wm-customer.list-preferences\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-preferences\n              description: \"Update paperless billing or autopay enrollment.\"\n              call: \"wm-customer.update-preferences\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wm-customer-service-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted Waste Management customer service.\"\n      tools:\n        - name: get-account-overview\n          description: \"Get the WM customer account overview including balance due and contact information.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.get-customer-overview\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-balance\n          description: \"Get the current amount due on the WM customer account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.get-balance\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-services\n          description: \"List all active waste and recycling collection services for the customer.\"\n   \
  \       hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-services\"\n          with:\n            customerId: \"tools.customerId\"\n            line_of_business: \"tools.line_of_business\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-planned-services\n          description: \"Check which waste collection services are scheduled for pickup today.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-planned-services\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-next-pickup\n          description: \"Find out when the next garbage and recycling pickup is scheduled.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.get-next-pickup\"\n\
  \          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-service-eta\n          description: \"Get the estimated arrival window for a WM truck on a scheduled service day.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.get-service-eta\"\n          with:\n            customerId: \"tools.customerId\"\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-invoices\n          description: \"List WM billing invoices, optionally filtered by date range.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-invoices\"\n          with:\n            customerId: \"tools.customerId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-invoice-details\n          description: \"Get the full breakdown of a specific WM invoice including fees and line items.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.get-invoice-details\"\n          with:\n            customerId: \"tools.customerId\"\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-contacts\n          description: \"List billing and service contacts on the WM customer account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-contacts\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-contacts\n          description:\
  \ \"Update contact name, email, or phone number on the WM customer account.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wm-customer.update-contacts\"\n          with:\n            customerId: \"tools.customerId\"\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            email: \"tools.email\"\n            phone: \"tools.phone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-preferences\n          description: \"Check if the WM customer is enrolled in paperless billing or autopay.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-preferences\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-preferences\n          description: \"Enroll or unenroll\
  \ the WM customer in paperless billing or automatic payment.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wm-customer.update-preferences\"\n          with:\n            customerId: \"tools.customerId\"\n            paperlessBilling: \"tools.paperlessBilling\"\n            autoPayEnrolled: \"tools.autoPayEnrolled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-service-materials\n          description: \"Get the types of materials (garbage, recycling, yard waste) collected for each service.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-service-materials\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-service-fees\n          description: \"Get the breakdown of fuel surcharges, environmental\
  \ fees, and regulatory recovery fees on services.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wm-customer.list-service-invoice-fees\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/waste-management/refs/heads/main/capabilities/customer-service.yaml
tags:
- Waste Management
- Customer Service
- Billing
- Service Scheduling
- Account Management
tools:
- description: Get the WM customer account overview including balance due and contact information.
  hints:
    openWorld: true
    readOnly: true
  name: get-account-overview
- description: Get the current amount due on the WM customer account.
  hints:
    openWorld: true
    readOnly: true
  name: get-balance
- description: List all active waste and recycling collection services for the customer.
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Check which waste collection services are scheduled for pickup today.
  hints:
    openWorld: true
    readOnly: true
  name: get-planned-services
- description: Find out when the next garbage and recycling pickup is scheduled.
  hints:
    openWorld: true
    readOnly: true
  name: get-next-pickup
- description: Get the estimated arrival window for a WM truck on a scheduled service day.
  hints:
    openWorld: true
    readOnly: true
  name: get-service-eta
- description: List WM billing invoices, optionally filtered by date range.
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Get the full breakdown of a specific WM invoice including fees and line items.
  hints:
    openWorld: true
    readOnly: true
  name: get-invoice-details
- description: List billing and service contacts on the WM customer account.
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Update contact name, email, or phone number on the WM customer account.
  hints:
    idempotent: true
    readOnly: false
  name: update-contacts
- description: Check if the WM customer is enrolled in paperless billing or autopay.
  hints:
    openWorld: true
    readOnly: true
  name: get-preferences
- description: Enroll or unenroll the WM customer in paperless billing or automatic payment.
  hints:
    idempotent: true
    readOnly: false
  name: update-preferences
- description: Get the types of materials (garbage, recycling, yard waste) collected for each service.
  hints:
    openWorld: true
    readOnly: true
  name: list-service-materials
- description: Get the breakdown of fuel surcharges, environmental fees, and regulatory recovery fees on services.
  hints:
    openWorld: true
    readOnly: true
  name: list-service-fees
---
