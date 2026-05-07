---
categories: []
consumed_apis: []
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
- list services
- get upcoming pickup schedule.
- next scheduled garbage and recycling pickup.
- list wm billing invoices, optionally filtered by date range.
- list billing and service contacts.
- get today's planned service schedule.
- get the wm customer account overview including balance due and contact information.
- billing
- account management
- update paperless billing or autopay enrollment.
- get preferences
- get the current amount due on the wm customer account.
- list planned services
- get paperless billing and autopay preferences.
- billing and service contact management.
- get invoice details
- get details for a specific invoice.
- find out when the next garbage and recycling pickup is scheduled.
- check if the wm customer is enrolled in paperless billing or autopay.
- list service fees
- update preferences
- waste management
- get the types of materials (garbage, recycling, yard waste) collected for each service.
- estimated time of arrival for a service.
- get balance
- list contacts
- get next pickup
- get planned services
- update contact name, email, or phone number on the wm customer account.
- get the breakdown of fuel surcharges, environmental fees, and regulatory recovery fees on services.
- recycling
- list all services for the customer.
- get service eta
- get the full breakdown of a specific wm invoice including fees and line items.
- get customer account overview including balance and contact details.
- environmental services
- list all invoices with optional date range.
- current balance due on the account.
- sustainability
- get the current balance due.
- full invoice details with line items and fees.
- update contacts
- get the estimated arrival window for a wm truck on a scheduled service day.
- customer billing and notification preferences.
- list all active waste and recycling collection services for the customer.
- list billing and service contacts on the wm customer account.
- enroll or unenroll the wm customer in paperless billing or automatic payment.
- list invoices
- customer service
- get account overview
- all waste and recycling services for the account.
- fortune 500
- update billing or service contact information.
- service scheduling
- invoice history and billing records.
- list service materials
- customer account overview with balance and profile.
- solid waste
- services scheduled for pickup today.
- check which waste collection services are scheduled for pickup today.
- get eta for today's scheduled pickup.
slug: customer-service
source_filename: customer-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Waste Management Customer Service\n  description: Unified customer service capability for Waste Management accounts. Combines account management, service scheduling,\n    ETA tracking, and billing operations to support residential and commercial customer self-service workflows.\n  tags:\n  - Waste Management\n  - Customer Service\n  - Billing\n  - Service Scheduling\n  - Account Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WM_JWT_TOKEN: WM_JWT_TOKEN\n    WM_CLIENT_ID: WM_CLIENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: wm-customer\n    baseUri: https://api.wm.com/v1\n    description: Waste Management Customer API providing account, service, and billing data.\n    authentication:\n      type: bearer\n      token: '{{WM_JWT_TOKEN}}'\n    resources:\n    - name: customers\n      path: /customers\n      description: Customer account overview including balance and contact\
  \ information.\n      operations:\n      - name: get-customer-overview\n        method: GET\n        description: Retrieve customer account overview including balance due and contact info.\n        inputParameters:\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique identifier for tracking the request.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /customers/{customerId}/services\n      description: Services associated with the customer account.\n      operations:\n      - name: list-services\n        method: GET\n        description: List all services for a customer including materials, equipment, and pricing.\n        inputParameters:\n\
  \        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: line_of_business\n          in: query\n          type: string\n          required: false\n          description: Filter by RESIDENTIAL, COMMERCIAL, or ROLLOFF.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-planned-services\n        method: GET\n        description: Retrieve today's planned service schedule for the customer.\n        inputParameters:\n        - name: customerId\n          in: path\n  \
  \        type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-next-pickup\n        method: GET\n        description: Get upcoming pickup schedule for the customer's waste and recycling services.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n   \
  \       description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service-eta\n        method: GET\n        description: Get estimated arrival time for a specific service.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: Unique service identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in:\
  \ header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-service-materials\n        method: GET\n        description: Retrieve hauling material information for all customer services.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: list-service-invoice-fees\n        method: GET\n        description: Retrieve invoice fees including fuel, environmental, and regulatory surcharges.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /customers/{customerId}/invoices\n      description: Invoice history and details for the customer account.\n      operations:\n      - name: list-invoices\n\
  \        method: GET\n        description: List all invoices with optional date range filtering.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter (YYYY-MM-DD).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter (YYYY-MM-DD).\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: get-invoice-details\n        method: GET\n        description: Retrieve full details for a specific invoice including line items and fees.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Unique invoice identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balance\n      path:\
  \ /customers/{customerId}/balance\n      description: Current account balance information.\n      operations:\n      - name: get-balance\n        method: GET\n        description: Retrieve the current balance due on the customer account.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /customers/{customerId}/contacts\n      description: Billing and service contacts for the customer\
  \ account.\n      operations:\n      - name: list-contacts\n        method: GET\n        description: Retrieve billing and service contacts for the account.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contacts\n        method: PATCH\n        description: Update billing and service contact information.\n        inputParameters:\n        - name: customerId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n    - name: preferences\n      path: /customers/{customerId}/preferences\n      description: Customer preference settings including paperless billing and autopay.\n      operations:\n      - name: list-preferences\n        method: GET\n\
  \        description: Retrieve customer preferences including paperless billing and autopay settings.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-preferences\n        method: PATCH\n        description: Update paperless billing and automatic payment enrollment settings.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n\
  \          description: Unique WM customer identifier.\n        - name: Request-Tracking-Id\n          in: header\n          type: string\n          required: true\n          description: Unique request tracking identifier.\n        - name: ClientId\n          in: header\n          type: string\n          required: true\n          description: Client identifier provided by WM.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            paperlessBilling: '{{tools.paperlessBilling}}'\n            autoPayEnrolled: '{{tools.autoPayEnrolled}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wm-customer-service-api\n    description: Unified REST API for Waste Management customer service workflows.\n    resources:\n    - path: /v1/account\n      name: account\n      description: Customer account overview with balance and profile.\n      operations:\n\
  \      - method: GET\n        name: get-account-overview\n        description: Get customer account overview including balance and contact details.\n        call: wm-customer.get-customer-overview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/balance\n      name: balance\n      description: Current balance due on the account.\n      operations:\n      - method: GET\n        name: get-balance\n        description: Get the current balance due.\n        call: wm-customer.get-balance\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services\n      name: services\n      description: All waste and recycling services for the account.\n      operations:\n      - method: GET\n        name: list-services\n        description: List all services for the customer.\n        call: wm-customer.list-services\n        with:\n          customerId: rest.customerId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/planned\n      name: planned-services\n      description: Services scheduled for pickup today.\n      operations:\n      - method: GET\n        name: list-planned-services\n        description: Get today's planned service schedule.\n        call: wm-customer.list-planned-services\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/next-pickup\n      name: next-pickup\n      description: Next scheduled garbage and recycling pickup.\n      operations:\n      - method: GET\n        name: get-next-pickup\n        description: Get upcoming pickup schedule.\n        call: wm-customer.get-next-pickup\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}/eta\n      name: service-eta\n\
  \      description: Estimated time of arrival for a service.\n      operations:\n      - method: GET\n        name: get-service-eta\n        description: Get ETA for today's scheduled pickup.\n        call: wm-customer.get-service-eta\n        with:\n          customerId: rest.customerId\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice history and billing records.\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List all invoices with optional date range.\n        call: wm-customer.list-invoices\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}\n      name: invoice-detail\n      description: Full invoice details with line items and fees.\n      operations:\n      - method: GET\n        name: get-invoice-details\n\
  \        description: Get details for a specific invoice.\n        call: wm-customer.get-invoice-details\n        with:\n          customerId: rest.customerId\n          invoiceId: rest.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts\n      name: contacts\n      description: Billing and service contact management.\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List billing and service contacts.\n        call: wm-customer.list-contacts\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-contacts\n        description: Update billing or service contact information.\n        call: wm-customer.update-contacts\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/preferences\n  \
  \    name: preferences\n      description: Customer billing and notification preferences.\n      operations:\n      - method: GET\n        name: get-preferences\n        description: Get paperless billing and autopay preferences.\n        call: wm-customer.list-preferences\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-preferences\n        description: Update paperless billing or autopay enrollment.\n        call: wm-customer.update-preferences\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wm-customer-service-mcp\n    transport: http\n    description: MCP server for AI-assisted Waste Management customer service.\n    tools:\n    - name: get-account-overview\n      description: Get the WM customer account overview including balance due\
  \ and contact information.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.get-customer-overview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-balance\n      description: Get the current amount due on the WM customer account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.get-balance\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List all active waste and recycling collection services for the customer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-services\n      with:\n        customerId: tools.customerId\n        line_of_business: tools.line_of_business\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-planned-services\n      description: Check which waste collection services\
  \ are scheduled for pickup today.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-planned-services\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-next-pickup\n      description: Find out when the next garbage and recycling pickup is scheduled.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.get-next-pickup\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-eta\n      description: Get the estimated arrival window for a WM truck on a scheduled service day.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.get-service-eta\n      with:\n        customerId: tools.customerId\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n\
  \      description: List WM billing invoices, optionally filtered by date range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-invoices\n      with:\n        customerId: tools.customerId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice-details\n      description: Get the full breakdown of a specific WM invoice including fees and line items.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.get-invoice-details\n      with:\n        customerId: tools.customerId\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contacts\n      description: List billing and service contacts on the WM customer account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-contacts\n      with:\n        customerId:\
  \ tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-contacts\n      description: Update contact name, email, or phone number on the WM customer account.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: wm-customer.update-contacts\n      with:\n        customerId: tools.customerId\n        firstName: tools.firstName\n        lastName: tools.lastName\n        email: tools.email\n        phone: tools.phone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-preferences\n      description: Check if the WM customer is enrolled in paperless billing or autopay.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-preferences\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-preferences\n      description: Enroll or unenroll the WM customer in paperless\
  \ billing or automatic payment.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: wm-customer.update-preferences\n      with:\n        customerId: tools.customerId\n        paperlessBilling: tools.paperlessBilling\n        autoPayEnrolled: tools.autoPayEnrolled\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-materials\n      description: Get the types of materials (garbage, recycling, yard waste) collected for each service.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-service-materials\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-fees\n      description: Get the breakdown of fuel surcharges, environmental fees, and regulatory recovery fees on services.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wm-customer.list-service-invoice-fees\n \
  \     with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
