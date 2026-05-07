---
categories: []
consumed_apis: []
description: Lago API allows your application to push customer information and metrics (events) from your application to the billing application.
layout: capability
name: Lago API documentation
operations:
- description: Lago Create an add-on
  method: POST
  name: createaddon
  path: /add_ons
- description: Lago List all add-ons
  method: GET
  name: findalladdons
  path: /add_ons
- description: Lago Update an add-on
  method: PUT
  name: updateaddon
  path: /add_ons/{code}
- description: Lago Retrieve an add-on
  method: GET
  name: findaddon
  path: /add_ons/{code}
- description: Lago Delete an add-on
  method: DELETE
  name: destroyaddon
  path: /add_ons/{code}
- description: Lago List gross revenue
  method: GET
  name: findallgrossrevenues
  path: /analytics/gross_revenue
- description: Lago List of finalized invoices
  method: GET
  name: findallinvoicecollections
  path: /analytics/invoice_collection
- description: Lago List usage revenue
  method: GET
  name: findallinvoicedusages
  path: /analytics/invoiced_usage
- description: Lago List MRR
  method: GET
  name: findallmrrs
  path: /analytics/mrr
- description: Lago List overdue balance
  method: GET
  name: findalloverduebalances
  path: /analytics/overdue_balance
- description: Lago Apply a coupon to a customer
  method: POST
  name: applycoupon
  path: /applied_coupons
- description: Lago List all applied coupons
  method: GET
  name: findallappliedcoupons
  path: /applied_coupons
- description: Lago Create a billable metric
  method: POST
  name: createbillablemetric
  path: /billable_metrics
- description: Lago List all billable metrics
  method: GET
  name: findallbillablemetrics
  path: /billable_metrics
- description: Lago Evaluate an expression for a billable metric
  method: POST
  name: evaluatebillablemetricexpression
  path: /billable_metrics/evaluate_expression
- description: Lago Update a billable metric
  method: PUT
  name: updatebillablemetric
  path: /billable_metrics/{code}
- description: Lago Delete a billable metric
  method: DELETE
  name: destroybillablemetric
  path: /billable_metrics/{code}
- description: Lago Retrieve a billable metric
  method: GET
  name: findbillablemetric
  path: /billable_metrics/{code}
- description: Lago Create a coupon
  method: POST
  name: createcoupon
  path: /coupons
- description: Lago List all coupons
  method: GET
  name: findallcoupons
  path: /coupons
- description: Lago Update a coupon
  method: PUT
  name: updatecoupon
  path: /coupons/{code}
- description: Lago Retrieve a coupon
  method: GET
  name: findcoupon
  path: /coupons/{code}
- description: Lago Delete a coupon
  method: DELETE
  name: destroycoupon
  path: /coupons/{code}
- description: Lago Create a credit note
  method: POST
  name: createcreditnote
  path: /credit_notes
- description: Lago List all credit notes
  method: GET
  name: findallcreditnotes
  path: /credit_notes
- description: Lago Update a credit note
  method: PUT
  name: updatecreditnote
  path: /credit_notes/{lago_id}
- description: Lago Retrieve a credit note
  method: GET
  name: findcreditnote
  path: /credit_notes/{lago_id}
- description: Lago Download a credit note PDF
  method: POST
  name: downloadcreditnote
  path: /credit_notes/{lago_id}/download
- description: Lago Estimate amounts for a new credit note
  method: POST
  name: estimatecreditnote
  path: /credit_notes/estimate
- description: Lago Void available credit
  method: PUT
  name: voidcreditnote
  path: /credit_notes/{lago_id}/void
- description: Lago Create a customer
  method: POST
  name: createcustomer
  path: /customers
- description: Lago List all customers
  method: GET
  name: findallcustomers
  path: /customers
- description: Lago Retrieve a customer
  method: GET
  name: findcustomer
  path: /customers/{external_id}
- description: Lago Delete a customer
  method: DELETE
  name: destroycustomer
  path: /customers/{external_id}
- description: Lago Delete an applied coupon
  method: DELETE
  name: deleteappliedcoupon
  path: /customers/{external_customer_id}/applied_coupons/{applied_coupon_id}
- description: Lago Get a customer portal URL
  method: GET
  name: getcustomerportalurl
  path: /customers/{external_customer_id}/portal_url
- description: Lago Retrieve customer current usage
  method: GET
  name: findcustomercurrentusage
  path: /customers/{external_customer_id}/current_usage
- description: Lago Retrieve customer past usage
  method: GET
  name: findallcustomerpastusage
  path: /customers/{external_customer_id}/past_usage
- description: Lago Generate a Customer Payment Provider Checkout URL
  method: POST
  name: generatecustomercheckouturl
  path: /customers/{external_customer_id}/checkout_url
- description: Lago Send usage events
  method: POST
  name: createevent
  path: /events
- description: Lago List all events
  method: GET
  name: findallevents
  path: /events
- description: Lago Batch multiple events
  method: POST
  name: createbatchevents
  path: /events/batch
- description: Lago Estimate fees for a pay in advance charge
  method: POST
  name: eventestimatefees
  path: /events/estimate_fees
- description: Lago Retrieve a specific event
  method: GET
  name: findevent
  path: /events/{transaction_id}
- description: Lago List all fees
  method: GET
  name: findallfees
  path: /fees
- description: Lago Retrieve a specific fee
  method: GET
  name: findfee
  path: /fees/{lago_id}
- description: Lago Update a fee
  method: PUT
  name: updatefee
  path: /fees/{lago_id}
- description: Lago Delete a fee
  method: DELETE
  name: deletefee
  path: /fees/{lago_id}
- description: Lago Create a one-off invoice
  method: POST
  name: createinvoice
  path: /invoices
- description: Lago List all invoices
  method: GET
  name: findallinvoices
  path: /invoices
- description: Lago Update an invoice
  method: PUT
  name: updateinvoice
  path: /invoices/{lago_id}
- description: Lago Retrieve an invoice
  method: GET
  name: findinvoice
  path: /invoices/{lago_id}
- description: Lago Download an invoice PDF
  method: POST
  name: downloadinvoice
  path: /invoices/{lago_id}/download
- description: Lago Finalize a draft invoice
  method: PUT
  name: finalizeinvoice
  path: /invoices/{lago_id}/finalize
- description: Lago Mark an invoice payment dispute as lost
  method: POST
  name: losedisputeinvoice
  path: /invoices/{lago_id}/lose_dispute
- description: Lago Refresh a draft invoice
  method: PUT
  name: refreshinvoice
  path: /invoices/{lago_id}/refresh
- description: Lago Retry generation of a failed invoice
  method: POST
  name: retryinvoice
  path: /invoices/{lago_id}/retry
- description: Lago Generate a payment URL
  method: POST
  name: invoicepaymenturl
  path: /invoices/{lago_id}/payment_url
- description: Lago Retry an invoice payment
  method: POST
  name: retrypayment
  path: /invoices/{lago_id}/retry_payment
- description: Lago Void an invoice
  method: POST
  name: voidinvoice
  path: /invoices/{lago_id}/void
personas: []
provider_name: Lago
provider_slug: lago
search_terms:
- voidcreditnote
- updatecoupon
- lago list all events
- findevent
- finalizeinvoice
- updatecreditnote
- estimatecreditnote
- api
- lago list all coupons
- downloadcreditnote
- usage-based
- evaluatebillablemetricexpression
- lago update a billable metric
- lago retrieve a billable metric
- destroyaddon
- lago list all billable metrics
- lago delete a customer
- lago delete an add-on
- lago list all credit notes
- eventestimatefees
- lago retry an invoice payment
- lago retrieve a customer
- findcreditnote
- createaddon
- createcoupon
- deleteappliedcoupon
- findcoupon
- lago download a credit note pdf
- lago get a customer portal url
- findalloverduebalances
- lago create a credit note
- deletefee
- getcustomerportalurl
- lago list all applied coupons
- createevent
- createcreditnote
- lago generate a customer payment provider checkout url
- findallmrrs
- lago generate a payment url
- updatefee
- lago delete a fee
- applycoupon
- lago retrieve an invoice
- findallfees
- downloadinvoice
- lago retry generation of a failed invoice
- findallcustomerpastusage
- destroycoupon
- lago void an invoice
- lago create a coupon
- createbatchevents
- destroybillablemetric
- retryinvoice
- findallcustomers
- lago void available credit
- metering
- updatebillablemetric
- lago list usage revenue
- lago refresh a draft invoice
- lago send usage events
- lago delete a coupon
- lago create a one-off invoice
- findallappliedcoupons
- lago list overdue balance
- lago estimate fees for a pay in advance charge
- destroycustomer
- findinvoice
- lago delete an applied coupon
- lago finalize a draft invoice
- lago list all customers
- findallcreditnotes
- updateaddon
- lago retrieve customer current usage
- billing
- lago update an invoice
- lago retrieve a specific event
- lago list of finalized invoices
- findallgrossrevenues
- findfee
- invoicepaymenturl
- lago create a customer
- lago delete a billable metric
- lago retrieve a specific fee
- refreshinvoice
- retrypayment
- lago list all fees
- lago retrieve a coupon
- lago update a credit note
- createcustomer
- voidinvoice
- lago apply a coupon to a customer
- findallevents
- lago update an add-on
- lago retrieve customer past usage
- createinvoice
- losedisputeinvoice
- lago create an add-on
- findallbillablemetrics
- lago mark an invoice payment dispute as lost
- findallinvoices
- findallinvoicedusages
- lago retrieve a credit note
- lago create a billable metric
- findallcoupons
- generatecustomercheckouturl
- createbillablemetric
- open source
- findallinvoicecollections
- lago list all invoices
- updateinvoice
- lago list all add-ons
- findcustomer
- lago download an invoice pdf
- lago list mrr
- lago batch multiple events
- lago update a fee
- findcustomercurrentusage
- lago evaluate an expression for a billable metric
- lago
- lago list gross revenue
- findaddon
- findbillablemetric
- lago update a coupon
- findalladdons
- lago retrieve an add-on
- lago estimate amounts for a new credit note
slug: lago-capability
source_filename: lago-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lago API documentation\n  description: Lago API allows your application to push customer information and metrics (events) from your application to\n    the billing application.\n  tags:\n  - Lago\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lago\n    baseUri: https://api.getlago.com/api/v1\n    description: Lago API documentation HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LAGO_TOKEN}}'\n    resources:\n    - name: add-ons\n      path: /add_ons\n      operations:\n      - name: createaddon\n        method: POST\n        description: Lago Create an add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findalladdons\n        method: GET\n        description: Lago List all add-ons\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: add-ons-code\n      path: /add_ons/{code}\n      operations:\n      - name: updateaddon\n        method: PUT\n        description: Lago Update an add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findaddon\n        method: GET\n        description: Lago Retrieve an add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: destroyaddon\n        method: DELETE\n        description: Lago Delete an add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-gross-revenue\n      path: /analytics/gross_revenue\n      operations:\n      - name: findallgrossrevenues\n        method: GET\n        description: Lago List gross revenue\n        inputParameters:\n\
  \        - name: currency\n          in: query\n          type: string\n          description: Currency of revenue analytics. Format must be ISO 4217.\n        - name: external_customer_id\n          in: query\n          type: string\n          description: The customer external unique identifier (provided by your own application). Use it to filter revenue\n            analytics at the customer level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-invoice-collection\n      path: /analytics/invoice_collection\n      operations:\n      - name: findallinvoicecollections\n        method: GET\n        description: Lago List of finalized invoices\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: The currency of revenue analytics. Format must be ISO 4217.\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: analytics-invoiced-usage\n      path: /analytics/invoiced_usage\n      operations:\n      - name: findallinvoicedusages\n        method: GET\n        description: Lago List usage revenue\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: The currency of invoiced usage analytics. Format must be ISO 4217.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-mrr\n      path: /analytics/mrr\n      operations:\n      - name: findallmrrs\n        method: GET\n        description: Lago List MRR\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Quantifies the revenue generated from `subscription` fees on a monthly basis. This figure is calculated\n            post-application of applicable\
  \ taxes and deduction of an\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-overdue-balance\n      path: /analytics/overdue_balance\n      operations:\n      - name: findalloverduebalances\n        method: GET\n        description: Lago List overdue balance\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Currency of revenue analytics. Format must be ISO 4217.\n        - name: external_customer_id\n          in: query\n          type: string\n          description: The customer external unique identifier (provided by your own application). Use it to filter revenue\n            analytics at the customer level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applied-coupons\n      path: /applied_coupons\n      operations:\n  \
  \    - name: applycoupon\n        method: POST\n        description: Lago Apply a coupon to a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallappliedcoupons\n        method: GET\n        description: Lago List all applied coupons\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: The status of the coupon. Can be either `active` or `terminated`.\n        - name: external_customer_id\n          in: query\n          type: string\n          description: The customer external unique identifier (provided by your own application)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billable-metrics\n      path: /billable_metrics\n      operations:\n      - name: createbillablemetric\n        method: POST\n        description: Lago Create\
  \ a billable metric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallbillablemetrics\n        method: GET\n        description: Lago List all billable metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billable-metrics-evaluate-expression\n      path: /billable_metrics/evaluate_expression\n      operations:\n      - name: evaluatebillablemetricexpression\n        method: POST\n        description: Lago Evaluate an expression for a billable metric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billable-metrics-code\n      path: /billable_metrics/{code}\n      operations:\n      - name: updatebillablemetric\n        method: PUT\n        description: Lago Update a billable metric\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: destroybillablemetric\n        method: DELETE\n        description: Lago Delete a billable metric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findbillablemetric\n        method: GET\n        description: Lago Retrieve a billable metric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coupons\n      path: /coupons\n      operations:\n      - name: createcoupon\n        method: POST\n        description: Lago Create a coupon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallcoupons\n        method: GET\n        description: Lago List all coupons\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: coupons-code\n      path: /coupons/{code}\n      operations:\n      - name: updatecoupon\n        method: PUT\n        description: Lago Update a coupon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findcoupon\n        method: GET\n        description: Lago Retrieve a coupon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: destroycoupon\n        method: DELETE\n        description: Lago Delete a coupon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credit-notes\n      path: /credit_notes\n      operations:\n      - name: createcreditnote\n        method: POST\n        description: Lago Create a credit note\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallcreditnotes\n        method: GET\n        description: Lago List all credit notes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credit-notes-lago-id\n      path: /credit_notes/{lago_id}\n      operations:\n      - name: updatecreditnote\n        method: PUT\n        description: Lago Update a credit note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findcreditnote\n        method: GET\n        description: Lago Retrieve a credit note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credit-notes-lago-id-download\n      path: /credit_notes/{lago_id}/download\n      operations:\n      - name:\
  \ downloadcreditnote\n        method: POST\n        description: Lago Download a credit note PDF\n        inputParameters:\n        - name: lago_id\n          in: path\n          type: string\n          required: true\n          description: The credit note unique identifier, created by Lago.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credit-notes-estimate\n      path: /credit_notes/estimate\n      operations:\n      - name: estimatecreditnote\n        method: POST\n        description: Lago Estimate amounts for a new credit note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credit-notes-lago-id-void\n      path: /credit_notes/{lago_id}/void\n      operations:\n      - name: voidcreditnote\n        method: PUT\n        description: Lago Void available credit\n        inputParameters:\n        - name:\
  \ lago_id\n          in: path\n          type: string\n          required: true\n          description: The credit note unique identifier, created by Lago.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      operations:\n      - name: createcustomer\n        method: POST\n        description: Lago Create a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallcustomers\n        method: GET\n        description: Lago List all customers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-external-id\n      path: /customers/{external_id}\n      operations:\n      - name: findcustomer\n        method: GET\n        description: Lago Retrieve a customer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: destroycustomer\n        method: DELETE\n        description: Lago Delete a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-external-customer-id-applied-coupons-a\n      path: /customers/{external_customer_id}/applied_coupons/{applied_coupon_id}\n      operations:\n      - name: deleteappliedcoupon\n        method: DELETE\n        description: Lago Delete an applied coupon\n        inputParameters:\n        - name: external_customer_id\n          in: path\n          type: string\n          required: true\n          description: The customer external unique identifier (provided by your own application)\n        - name: applied_coupon_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the applied\
  \ coupon, created by Lago.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-external-customer-id-portal-url\n      path: /customers/{external_customer_id}/portal_url\n      operations:\n      - name: getcustomerportalurl\n        method: GET\n        description: Lago Get a customer portal URL\n        inputParameters:\n        - name: external_customer_id\n          in: path\n          type: string\n          required: true\n          description: External ID of the existing customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-external-customer-id-current-usage\n      path: /customers/{external_customer_id}/current_usage\n      operations:\n      - name: findcustomercurrentusage\n        method: GET\n        description: Lago Retrieve customer current usage\n        inputParameters:\n\
  \        - name: external_customer_id\n          in: path\n          type: string\n          required: true\n          description: The customer external unique identifier (provided by your own application).\n        - name: external_subscription_id\n          in: query\n          type: string\n          required: true\n          description: The unique identifier of the subscription within your application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-external-customer-id-past-usage\n      path: /customers/{external_customer_id}/past_usage\n      operations:\n      - name: findallcustomerpastusage\n        method: GET\n        description: Lago Retrieve customer past usage\n        inputParameters:\n        - name: external_customer_id\n          in: path\n          type: string\n          required: true\n          description: The customer external unique identifier (provided by your\
  \ own application).\n        - name: external_subscription_id\n          in: query\n          type: string\n          required: true\n          description: The unique identifier of the subscription within your application.\n        - name: billable_metric_code\n          in: query\n          type: string\n          description: Billable metric code filter to apply to the charge usage\n        - name: periods_count\n          in: query\n          type: integer\n          description: Number of past billing period to returns in the result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-external-customer-id-checkout-url\n      path: /customers/{external_customer_id}/checkout_url\n      operations:\n      - name: generatecustomercheckouturl\n        method: POST\n        description: Lago Generate a Customer Payment Provider Checkout URL\n        inputParameters:\n        - name: external_customer_id\n\
  \          in: path\n          type: string\n          required: true\n          description: The customer external unique identifier (provided by your own application).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: createevent\n        method: POST\n        description: Lago Send usage events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallevents\n        method: GET\n        description: Lago List all events\n        inputParameters:\n        - name: code\n          in: query\n          type: string\n          description: Filter events by its code.\n        - name: timestamp_from\n          in: query\n          type: string\n          description: Filter events by timestamp starting from a specific date.\n        - name: timestamp_to\n\
  \          in: query\n          type: string\n          description: Filter events by timestamp up to a specific date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-batch\n      path: /events/batch\n      operations:\n      - name: createbatchevents\n        method: POST\n        description: Lago Batch multiple events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-estimate-fees\n      path: /events/estimate_fees\n      operations:\n      - name: eventestimatefees\n        method: POST\n        description: Lago Estimate fees for a pay in advance charge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-transaction-id\n      path: /events/{transaction_id}\n      operations:\n      - name: findevent\n\
  \        method: GET\n        description: Lago Retrieve a specific event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fees\n      path: /fees\n      operations:\n      - name: findallfees\n        method: GET\n        description: Lago List all fees\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Filter results by fee's currency.\n        - name: fee_type\n          in: query\n          type: string\n          description: The fee type. Possible values are `add-on`, `charge`, `credit` or `subscription`.\n        - name: billable_metric_code\n          in: query\n          type: string\n          description: Filter results by the `code` of the billable metric attached to the fee. Only applies to `charge` types.\n        - name: payment_status\n          in: query\n          type: string\n          description: Indicates\
  \ the payment status of the fee. It represents the current status of the payment associated\n            with the fee. The possible values for this field are `pendin\n        - name: created_at_from\n          in: query\n          type: string\n          description: Filter results created after creation date and time in UTC.\n        - name: created_at_to\n          in: query\n          type: string\n          description: Filter results created before creation date and time in UTC.\n        - name: succeeded_at_from\n          in: query\n          type: string\n          description: Filter results with payment success after creation date and time in UTC.\n        - name: succeeded_at_to\n          in: query\n          type: string\n          description: Filter results with payment success after creation date and time in UTC.\n        - name: failed_at_from\n          in: query\n          type: string\n          description: Filter results with payment failure after creation date and\
  \ time in UTC.\n        - name: failed_at_to\n          in: query\n          type: string\n          description: Filter results with payment failure after creation date and time in UTC.\n        - name: refunded_at_from\n          in: query\n          type: string\n          description: Filter results with payment refund after creation date and time in UTC.\n        - name: refunded_at_to\n          in: query\n          type: string\n          description: Filter results with payment refund after creation date and time in UTC.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fees-lago-id\n      path: /fees/{lago_id}\n      operations:\n      - name: findfee\n        method: GET\n        description: Lago Retrieve a specific fee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefee\n        method:\
  \ PUT\n        description: Lago Update a fee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefee\n        method: DELETE\n        description: Lago Delete a fee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      operations:\n      - name: createinvoice\n        method: POST\n        description: Lago Create a one-off invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findallinvoices\n        method: GET\n        description: Lago List all invoices\n        inputParameters:\n        - name: issuing_date_from\n          in: query\n          type: string\n          description: Filter invoices starting from a specific date.\n        - name: issuing_date_to\n        \
  \  in: query\n          type: string\n          description: Filter invoices up to a specific date.\n        - name: status\n          in: query\n          type: string\n          description: Filter invoices by status. Possible values are `draft` or `finalized`.\n        - name: payment_status\n          in: query\n          type: string\n          description: Filter invoices by payment status. Possible values are `pending`, `failed` or `succeeded`.\n        - name: payment_overdue\n          in: query\n          type: boolean\n          description: Filter invoices by payment_overdue. Possible values are `true` or `false`.\n        - name: search_term\n          in: query\n          type: string\n          description: Search invoices by id, number, customer name, customer external_id or customer email.\n        - name: currency\n          in: query\n          type: string\n          description: Filter invoices by currency in. Possible values ISO 4217 currency codes.\n        - name:\
  \ payment_dispute_lost\n          in: query\n          type: boolean\n          description: Filter invoices with a payment dispute lost. Possible values are `true` or `false`.\n        - name: invoice_type\n          in: query\n          type: string\n          description: Filter invoices by invoice type. Possible values are `subscription`, `add_on`, `credit`, `one_off`\n            or `advance_charges`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id\n      path: /invoices/{lago_id}\n      operations:\n      - name: updateinvoice\n        method: PUT\n        description: Lago Update an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: findinvoice\n        method: GET\n        description: Lago Retrieve an invoice\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-download\n      path: /invoices/{lago_id}/download\n      operations:\n      - name: downloadinvoice\n        method: POST\n        description: Lago Download an invoice PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-finalize\n      path: /invoices/{lago_id}/finalize\n      operations:\n      - name: finalizeinvoice\n        method: PUT\n        description: Lago Finalize a draft invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-lose-dispute\n      path: /invoices/{lago_id}/lose_dispute\n      operations:\n      - name: losedisputeinvoice\n        method: POST\n        description: Lago Mark an invoice payment dispute as lost\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-refresh\n      path: /invoices/{lago_id}/refresh\n      operations:\n      - name: refreshinvoice\n        method: PUT\n        description: Lago Refresh a draft invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-retry\n      path: /invoices/{lago_id}/retry\n      operations:\n      - name: retryinvoice\n        method: POST\n        description: Lago Retry generation of a failed invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-payment-url\n      path: /invoices/{lago_id}/payment_url\n      operations:\n      - name: invoicepaymenturl\n        method: POST\n        description: Lago Generate a payment URL\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-retry-payment\n      path: /invoices/{lago_id}/retry_payment\n      operations:\n      - name: retrypayment\n        method: POST\n        description: Lago Retry an invoice payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-lago-id-void\n      path: /invoices/{lago_id}/void\n      operations:\n      - name: voidinvoice\n        method: POST\n        description: Lago Void an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lago-rest\n    description: REST adapter for Lago API documentation.\n    resources:\n    - path: /add_ons\n      name: createaddon\n      operations:\n      - method: POST\n        name: createaddon\n        description:\
  \ Lago Create an add-on\n        call: lago.createaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add_ons\n      name: findalladdons\n      operations:\n      - method: GET\n        name: findalladdons\n        description: Lago List all add-ons\n        call: lago.findalladdons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add_ons/{code}\n      name: updateaddon\n      operations:\n      - method: PUT\n        name: updateaddon\n        description: Lago Update an add-on\n        call: lago.updateaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add_ons/{code}\n      name: findaddon\n      operations:\n      - method: GET\n        name: findaddon\n        description: Lago Retrieve an add-on\n        call: lago.findaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add_ons/{code}\n      name: destroyaddon\n     \
  \ operations:\n      - method: DELETE\n        name: destroyaddon\n        description: Lago Delete an add-on\n        call: lago.destroyaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/gross_revenue\n      name: findallgrossrevenues\n      operations:\n      - method: GET\n        name: findallgrossrevenues\n        description: Lago List gross revenue\n        call: lago.findallgrossrevenues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/invoice_collection\n      name: findallinvoicecollections\n      operations:\n      - method: GET\n        name: findallinvoicecollections\n        description: Lago List of finalized invoices\n        call: lago.findallinvoicecollections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/invoiced_usage\n      name: findallinvoicedusages\n      operations:\n      - method: GET\n        name: findallinvoicedusages\n\
  \        description: Lago List usage revenue\n        call: lago.findallinvoicedusages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/mrr\n      name: findallmrrs\n      operations:\n      - method: GET\n        name: findallmrrs\n        description: Lago List MRR\n        call: lago.findallmrrs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/overdue_balance\n      name: findalloverduebalances\n      operations:\n      - method: GET\n        name: findalloverduebalances\n        description: Lago List overdue balance\n        call: lago.findalloverduebalances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applied_coupons\n      name: applycoupon\n      operations:\n      - method: POST\n        name: applycoupon\n        description: Lago Apply a coupon to a customer\n        call: lago.applycoupon\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /applied_coupons\n      name: findallappliedcoupons\n      operations:\n      - method: GET\n        name: findallappliedcoupons\n        description: Lago List all applied coupons\n        call: lago.findallappliedcoupons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billable_metrics\n      name: createbillablemetric\n      operations:\n      - method: POST\n        name: createbillablemetric\n        description: Lago Create a billable metric\n        call: lago.createbillablemetric\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billable_metrics\n      name: findallbillablemetrics\n      operations:\n      - method: GET\n        name: findallbillablemetrics\n        description: Lago List all billable metrics\n        call: lago.findallbillablemetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billable_metrics/evaluate_expression\n\
  \      name: evaluatebillablemetricexpression\n      operations:\n      - method: POST\n        name: evaluatebillablemetricexpression\n        description: Lago Evaluate an expression for a billable metric\n        call: lago.evaluatebillablemetricexpression\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billable_metrics/{code}\n      name: updatebillablemetric\n      operations:\n      - method: PUT\n        name: updatebillablemetric\n        description: Lago Update a billable metric\n        call: lago.updatebillablemetric\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billable_metrics/{code}\n      name: destroybillablemetric\n      operations:\n      - method: DELETE\n        name: destroybillablemetric\n        description: Lago Delete a billable metric\n        call: lago.destroybillablemetric\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billable_metrics/{code}\n\
  \      name: findbillablemetric\n      operations:\n      - method: GET\n        name: findbillablemetric\n        description: Lago Retrieve a billable metric\n        call: lago.findbillablemetric\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /coupons\n      name: createcoupon\n      operations:\n      - method: POST\n        name: createcoupon\n        description: Lago Create a coupon\n        call: lago.createcoupon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /coupons\n      name: findallcoupons\n      operations:\n      - method: GET\n        name: findallcoupons\n        description: Lago List all coupons\n        call: lago.findallcoupons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /coupons/{code}\n      name: updatecoupon\n      operations:\n      - method: PUT\n        name: updatecoupon\n        description: Lago Update a coupon\n        call: lago.updatecoupon\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /coupons/{code}\n      name: findcoupon\n      operations:\n      - method: GET\n        name: findcoupon\n        description: Lago Retrieve a coupon\n        call: lago.findcoupon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /coupons/{code}\n      name: destroycoupon\n      operations:\n      - method: DELETE\n        name: destroycoupon\n        description: Lago Delete a coupon\n        call: lago.destroycoupon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credit_notes\n      name: createcreditnote\n      operations:\n      - method: POST\n        na\n\n# --- truncated at 32 KB (67 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/lago/refs/heads/main/capabilities/lago-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lago/refs/heads/main/capabilities/lago-capability.yaml
tags:
- Lago
- API
tools:
- description: Lago Create an add-on
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaddon
- description: Lago List all add-ons
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findalladdons
- description: Lago Update an add-on
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaddon
- description: Lago Retrieve an add-on
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findaddon
- description: Lago Delete an add-on
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: destroyaddon
- description: Lago List gross revenue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallgrossrevenues
- description: Lago List of finalized invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallinvoicecollections
- description: Lago List usage revenue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallinvoicedusages
- description: Lago List MRR
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallmrrs
- description: Lago List overdue balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findalloverduebalances
- description: Lago Apply a coupon to a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: applycoupon
- description: Lago List all applied coupons
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallappliedcoupons
- description: Lago Create a billable metric
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbillablemetric
- description: Lago List all billable metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallbillablemetrics
- description: Lago Evaluate an expression for a billable metric
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluatebillablemetricexpression
- description: Lago Update a billable metric
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebillablemetric
- description: Lago Delete a billable metric
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: destroybillablemetric
- description: Lago Retrieve a billable metric
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findbillablemetric
- description: Lago Create a coupon
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcoupon
- description: Lago List all coupons
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallcoupons
- description: Lago Update a coupon
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecoupon
- description: Lago Retrieve a coupon
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcoupon
- description: Lago Delete a coupon
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: destroycoupon
- description: Lago Create a credit note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcreditnote
- description: Lago List all credit notes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallcreditnotes
- description: Lago Update a credit note
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecreditnote
- description: Lago Retrieve a credit note
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcreditnote
- description: Lago Download a credit note PDF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: downloadcreditnote
- description: Lago Estimate amounts for a new credit note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: estimatecreditnote
- description: Lago Void available credit
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: voidcreditnote
- description: Lago Create a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomer
- description: Lago List all customers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallcustomers
- description: Lago Retrieve a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcustomer
- description: Lago Delete a customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: destroycustomer
- description: Lago Delete an applied coupon
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteappliedcoupon
- description: Lago Get a customer portal URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomerportalurl
- description: Lago Retrieve customer current usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcustomercurrentusage
- description: Lago Retrieve customer past usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallcustomerpastusage
- description: Lago Generate a Customer Payment Provider Checkout URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatecustomercheckouturl
- description: Lago Send usage events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createevent
- description: Lago List all events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallevents
- description: Lago Batch multiple events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbatchevents
- description: Lago Estimate fees for a pay in advance charge
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: eventestimatefees
- description: Lago Retrieve a specific event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findevent
- description: Lago List all fees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallfees
- description: Lago Retrieve a specific fee
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findfee
- description: Lago Update a fee
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefee
- description: Lago Delete a fee
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefee
- description: Lago Create a one-off invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinvoice
- description: Lago List all invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findallinvoices
- description: Lago Update an invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinvoice
- description: Lago Retrieve an invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findinvoice
- description: Lago Download an invoice PDF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: downloadinvoice
- description: Lago Finalize a draft invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: finalizeinvoice
- description: Lago Mark an invoice payment dispute as lost
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: losedisputeinvoice
- description: Lago Refresh a draft invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: refreshinvoice
- description: Lago Retry generation of a failed invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retryinvoice
- description: Lago Generate a payment URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invoicepaymenturl
- description: Lago Retry an invoice payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retrypayment
- description: Lago Void an invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: voidinvoice
---
