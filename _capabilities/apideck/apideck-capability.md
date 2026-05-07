---
categories: []
consumed_apis: []
description: 'Welcome to the Accounting API. You can use this API to access all Accounting API endpoints. ## Base URL The base URL for all API requests is `https://unify.apideck.com` ## Headers Custom headers that are expected as part of the request. Note that [RFC7230](https://tools.ietf.org/html/rfc7230) states header names are case insensitive. | Name | Type | Required | Description | | --------------------- | ------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | | x-apideck-con'
layout: capability
name: Apideck Accounting API
operations:
- description: Apideck List Tax Rates
  method: GET
  name: taxratesall
  path: /accounting/tax-rates
- description: Apideck Create Tax Rate
  method: POST
  name: taxratesadd
  path: /accounting/tax-rates
- description: Apideck Get Tax Rate
  method: GET
  name: taxratesone
  path: /accounting/tax-rates/{id}
- description: Apideck Update Tax Rate
  method: PATCH
  name: taxratesupdate
  path: /accounting/tax-rates/{id}
- description: Apideck Delete Tax Rate
  method: DELETE
  name: taxratesdelete
  path: /accounting/tax-rates/{id}
- description: Apideck List Bills
  method: GET
  name: billsall
  path: /accounting/bills
- description: Apideck Create Bill
  method: POST
  name: billsadd
  path: /accounting/bills
- description: Apideck Get Bill
  method: GET
  name: billsone
  path: /accounting/bills/{id}
- description: Apideck Update Bill
  method: PATCH
  name: billsupdate
  path: /accounting/bills/{id}
- description: Apideck Delete Bill
  method: DELETE
  name: billsdelete
  path: /accounting/bills/{id}
- description: Apideck List Invoices
  method: GET
  name: invoicesall
  path: /accounting/invoices
- description: Apideck Create Invoice
  method: POST
  name: invoicesadd
  path: /accounting/invoices
- description: Apideck Get Invoice
  method: GET
  name: invoicesone
  path: /accounting/invoices/{id}
- description: Apideck Update Invoice
  method: PATCH
  name: invoicesupdate
  path: /accounting/invoices/{id}
- description: Apideck Delete Invoice
  method: DELETE
  name: invoicesdelete
  path: /accounting/invoices/{id}
- description: Apideck List Ledger Accounts
  method: GET
  name: ledgeraccountsall
  path: /accounting/ledger-accounts
- description: Apideck Create Ledger Account
  method: POST
  name: ledgeraccountsadd
  path: /accounting/ledger-accounts
- description: Apideck Get Ledger Account
  method: GET
  name: ledgeraccountsone
  path: /accounting/ledger-accounts/{id}
- description: Apideck Update Ledger Account
  method: PATCH
  name: ledgeraccountsupdate
  path: /accounting/ledger-accounts/{id}
- description: Apideck Delete Ledger Account
  method: DELETE
  name: ledgeraccountsdelete
  path: /accounting/ledger-accounts/{id}
- description: Apideck List Invoice Items
  method: GET
  name: invoiceitemsall
  path: /accounting/invoice-items
- description: Apideck Create Invoice Item
  method: POST
  name: invoiceitemsadd
  path: /accounting/invoice-items
- description: Apideck Get Invoice Item
  method: GET
  name: invoiceitemsone
  path: /accounting/invoice-items/{id}
- description: Apideck Update Invoice Item
  method: PATCH
  name: invoiceitemsupdate
  path: /accounting/invoice-items/{id}
- description: Apideck Delete Invoice Item
  method: DELETE
  name: invoiceitemsdelete
  path: /accounting/invoice-items/{id}
- description: Apideck List Credit Notes
  method: GET
  name: creditnotesall
  path: /accounting/credit-notes
- description: Apideck Create Credit Note
  method: POST
  name: creditnotesadd
  path: /accounting/credit-notes
- description: Apideck Get Credit Note
  method: GET
  name: creditnotesone
  path: /accounting/credit-notes/{id}
- description: Apideck Update Credit Note
  method: PATCH
  name: creditnotesupdate
  path: /accounting/credit-notes/{id}
- description: Apideck Delete Credit Note
  method: DELETE
  name: creditnotesdelete
  path: /accounting/credit-notes/{id}
- description: Apideck List Customers
  method: GET
  name: customersall
  path: /accounting/customers
- description: Apideck Create Customer
  method: POST
  name: customersadd
  path: /accounting/customers
- description: Apideck Get Customer
  method: GET
  name: customersone
  path: /accounting/customers/{id}
- description: Apideck Update Customer
  method: PATCH
  name: customersupdate
  path: /accounting/customers/{id}
- description: Apideck Delete Customer
  method: DELETE
  name: customersdelete
  path: /accounting/customers/{id}
- description: Apideck List Suppliers
  method: GET
  name: suppliersall
  path: /accounting/suppliers
- description: Apideck Create Supplier
  method: POST
  name: suppliersadd
  path: /accounting/suppliers
- description: Apideck Get Supplier
  method: GET
  name: suppliersone
  path: /accounting/suppliers/{id}
- description: Apideck Update Supplier
  method: PATCH
  name: suppliersupdate
  path: /accounting/suppliers/{id}
- description: Apideck Delete Supplier
  method: DELETE
  name: suppliersdelete
  path: /accounting/suppliers/{id}
- description: Apideck List Payments
  method: GET
  name: paymentsall
  path: /accounting/payments
- description: Apideck Create Payment
  method: POST
  name: paymentsadd
  path: /accounting/payments
- description: Apideck Get Payment
  method: GET
  name: paymentsone
  path: /accounting/payments/{id}
- description: Apideck Update Payment
  method: PATCH
  name: paymentsupdate
  path: /accounting/payments/{id}
- description: Apideck Delete Payment
  method: DELETE
  name: paymentsdelete
  path: /accounting/payments/{id}
- description: Apideck List Refunds
  method: GET
  name: refundsall
  path: /accounting/refunds
- description: Apideck Create Refund
  method: POST
  name: refundsadd
  path: /accounting/refunds
- description: Apideck Get Refund
  method: GET
  name: refundsone
  path: /accounting/refunds/{id}
- description: Apideck Update Refund
  method: PATCH
  name: refundsupdate
  path: /accounting/refunds/{id}
- description: Apideck Delete Refund
  method: DELETE
  name: refundsdelete
  path: /accounting/refunds/{id}
- description: Apideck Get company info
  method: GET
  name: companyinfoone
  path: /accounting/company-info
- description: Apideck List companies
  method: GET
  name: companiesall
  path: /accounting/companies
- description: Apideck Get BalanceSheet
  method: GET
  name: balancesheetone
  path: /accounting/balance-sheet
- description: Apideck Get Profit and Loss
  method: GET
  name: profitandlossone
  path: /accounting/profit-and-loss
- description: Apideck List Journal Entries
  method: GET
  name: journalentriesall
  path: /accounting/journal-entries
- description: Apideck Create Journal Entry
  method: POST
  name: journalentriesadd
  path: /accounting/journal-entries
- description: Apideck Get Journal Entry
  method: GET
  name: journalentriesone
  path: /accounting/journal-entries/{id}
- description: Apideck Update Journal Entry
  method: PATCH
  name: journalentriesupdate
  path: /accounting/journal-entries/{id}
- description: Apideck Delete Journal Entry
  method: DELETE
  name: journalentriesdelete
  path: /accounting/journal-entries/{id}
- description: Apideck List Purchase Orders
  method: GET
  name: purchaseordersall
  path: /accounting/purchase-orders
personas: []
provider_name: Apideck
provider_slug: apideck
search_terms:
- companiesall
- apideck list companies
- billsall
- suppliersdelete
- apideck update refund
- apideck create journal entry
- apideck update ledger account
- ledgeraccountsupdate
- apideck get payment
- api
- ledgeraccountsadd
- apideck get invoice item
- companyinfoone
- refundsupdate
- apideck get journal entry
- apideck delete invoice
- paymentsupdate
- apideck create customer
- balancesheetone
- apideck delete journal entry
- apideck delete tax rate
- apideck get credit note
- customersall
- billsupdate
- invoiceitemsone
- apideck create refund
- apideck create ledger account
- apideck update payment
- refundsadd
- billsone
- integrations
- billsadd
- apideck create invoice item
- apideck update customer
- invoicesall
- apideck delete customer
- paymentsdelete
- apideck list credit notes
- ledgeraccountsdelete
- apideck list suppliers
- apideck delete refund
- apideck update invoice item
- apideck update invoice
- customersupdate
- apideck get balancesheet
- apideck list tax rates
- apideck list payments
- taxratesdelete
- apideck list bills
- apideck list purchase orders
- apideck create payment
- suppliersupdate
- journalentriesdelete
- customersone
- purchaseordersall
- apideck get profit and loss
- apideck get tax rate
- apideck delete ledger account
- suppliersadd
- apideck create tax rate
- creditnotesadd
- ledgeraccountsall
- paymentsone
- journalentriesadd
- apideck delete supplier
- apideck get company info
- unified api
- apideck list ledger accounts
- suppliersone
- apideck create credit note
- journalentriesone
- apideck create bill
- apideck create supplier
- invoicesdelete
- taxratesupdate
- apideck delete bill
- apideck list invoice items
- refundsdelete
- apideck create invoice
- apideck update journal entry
- journalentriesupdate
- creditnotesall
- paymentsall
- apideck get supplier
- apideck update credit note
- apideck delete credit note
- ledgeraccountsone
- apideck list invoices
- invoiceitemsadd
- journalentriesall
- invoicesupdate
- paymentsadd
- refundsall
- invoiceitemsdelete
- apideck delete invoice item
- apideck update bill
- apideck update supplier
- refundsone
- apideck get refund
- creditnotesupdate
- profitandlossone
- apideck list journal entries
- apideck list refunds
- customersdelete
- apideck
- creditnotesone
- customersadd
- invoiceitemsupdate
- invoicesone
- suppliersall
- apideck list customers
- taxratesone
- invoicesadd
- apideck get bill
- apideck get ledger account
- apideck get customer
- apideck get invoice
- apideck delete payment
- billsdelete
- apideck update tax rate
- taxratesall
- creditnotesdelete
- invoiceitemsall
- taxratesadd
slug: apideck-capability
source_filename: apideck-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apideck Accounting API\n  description: 'Welcome to the Accounting API. You can use this API to access all Accounting API endpoints. ## Base URL The\n    base URL for all API requests is `https://unify.apideck.com` ## Headers Custom headers that are expected as part of the\n    request. Note that [RFC7230](https://tools.ietf.org/html/rfc7230) states header names are case insensitive. | Name | Type\n    | Required | Description | | --------------------- | ------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------\n    | | x-apideck-con'\n  tags:\n  - Apideck\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: apideck\n    baseUri: https://unify.apideck.com\n    description: Apideck Accounting API HTTP API.\n    authentication:\n      type: apikey\n     \
  \ in: header\n      name: Authorization\n      value: '{{APIDECK_TOKEN}}'\n    resources:\n    - name: accounting-tax-rates\n      path: /accounting/tax-rates\n      operations:\n      - name: taxratesall\n        method: GET\n        description: Apideck List Tax Rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: taxratesadd\n        method: POST\n        description: Apideck Create Tax Rate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-tax-rates-id\n      path: /accounting/tax-rates/{id}\n      operations:\n      - name: taxratesone\n        method: GET\n        description: Apideck Get Tax Rate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: taxratesupdate\n        method: PATCH\n        description:\
  \ Apideck Update Tax Rate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: taxratesdelete\n        method: DELETE\n        description: Apideck Delete Tax Rate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-bills\n      path: /accounting/bills\n      operations:\n      - name: billsall\n        method: GET\n        description: Apideck List Bills\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: billsadd\n        method: POST\n        description: Apideck Create Bill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-bills-id\n      path: /accounting/bills/{id}\n      operations:\n      - name: billsone\n\
  \        method: GET\n        description: Apideck Get Bill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: billsupdate\n        method: PATCH\n        description: Apideck Update Bill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: billsdelete\n        method: DELETE\n        description: Apideck Delete Bill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-invoices\n      path: /accounting/invoices\n      operations:\n      - name: invoicesall\n        method: GET\n        description: Apideck List Invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoicesadd\n        method: POST\n        description:\
  \ Apideck Create Invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-invoices-id\n      path: /accounting/invoices/{id}\n      operations:\n      - name: invoicesone\n        method: GET\n        description: Apideck Get Invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoicesupdate\n        method: PATCH\n        description: Apideck Update Invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoicesdelete\n        method: DELETE\n        description: Apideck Delete Invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-ledger-accounts\n      path: /accounting/ledger-accounts\n   \
  \   operations:\n      - name: ledgeraccountsall\n        method: GET\n        description: Apideck List Ledger Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ledgeraccountsadd\n        method: POST\n        description: Apideck Create Ledger Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-ledger-accounts-id\n      path: /accounting/ledger-accounts/{id}\n      operations:\n      - name: ledgeraccountsone\n        method: GET\n        description: Apideck Get Ledger Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ledgeraccountsupdate\n        method: PATCH\n        description: Apideck Update Ledger Account\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: ledgeraccountsdelete\n        method: DELETE\n        description: Apideck Delete Ledger Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-invoice-items\n      path: /accounting/invoice-items\n      operations:\n      - name: invoiceitemsall\n        method: GET\n        description: Apideck List Invoice Items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoiceitemsadd\n        method: POST\n        description: Apideck Create Invoice Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-invoice-items-id\n      path: /accounting/invoice-items/{id}\n      operations:\n      - name: invoiceitemsone\n        method:\
  \ GET\n        description: Apideck Get Invoice Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoiceitemsupdate\n        method: PATCH\n        description: Apideck Update Invoice Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invoiceitemsdelete\n        method: DELETE\n        description: Apideck Delete Invoice Item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-credit-notes\n      path: /accounting/credit-notes\n      operations:\n      - name: creditnotesall\n        method: GET\n        description: Apideck List Credit Notes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creditnotesadd\n\
  \        method: POST\n        description: Apideck Create Credit Note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-credit-notes-id\n      path: /accounting/credit-notes/{id}\n      operations:\n      - name: creditnotesone\n        method: GET\n        description: Apideck Get Credit Note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creditnotesupdate\n        method: PATCH\n        description: Apideck Update Credit Note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creditnotesdelete\n        method: DELETE\n        description: Apideck Delete Credit Note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ accounting-customers\n      path: /accounting/customers\n      operations:\n      - name: customersall\n        method: GET\n        description: Apideck List Customers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: customersadd\n        method: POST\n        description: Apideck Create Customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-customers-id\n      path: /accounting/customers/{id}\n      operations:\n      - name: customersone\n        method: GET\n        description: Apideck Get Customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: customersupdate\n        method: PATCH\n        description: Apideck Update Customer\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n      - name: customersdelete\n        method: DELETE\n        description: Apideck Delete Customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-suppliers\n      path: /accounting/suppliers\n      operations:\n      - name: suppliersall\n        method: GET\n        description: Apideck List Suppliers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suppliersadd\n        method: POST\n        description: Apideck Create Supplier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-suppliers-id\n      path: /accounting/suppliers/{id}\n      operations:\n      - name: suppliersone\n        method: GET\n        description: Apideck\
  \ Get Supplier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suppliersupdate\n        method: PATCH\n        description: Apideck Update Supplier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suppliersdelete\n        method: DELETE\n        description: Apideck Delete Supplier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-payments\n      path: /accounting/payments\n      operations:\n      - name: paymentsall\n        method: GET\n        description: Apideck List Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: paymentsadd\n        method: POST\n        description: Apideck Create Payment\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-payments-id\n      path: /accounting/payments/{id}\n      operations:\n      - name: paymentsone\n        method: GET\n        description: Apideck Get Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: paymentsupdate\n        method: PATCH\n        description: Apideck Update Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: paymentsdelete\n        method: DELETE\n        description: Apideck Delete Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-refunds\n      path: /accounting/refunds\n      operations:\n      - name: refundsall\n \
  \       method: GET\n        description: Apideck List Refunds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refundsadd\n        method: POST\n        description: Apideck Create Refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-refunds-id\n      path: /accounting/refunds/{id}\n      operations:\n      - name: refundsone\n        method: GET\n        description: Apideck Get Refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refundsupdate\n        method: PATCH\n        description: Apideck Update Refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refundsdelete\n        method: DELETE\n      \
  \  description: Apideck Delete Refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-company-info\n      path: /accounting/company-info\n      operations:\n      - name: companyinfoone\n        method: GET\n        description: Apideck Get company info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-companies\n      path: /accounting/companies\n      operations:\n      - name: companiesall\n        method: GET\n        description: Apideck List companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-balance-sheet\n      path: /accounting/balance-sheet\n      operations:\n      - name: balancesheetone\n        method: GET\n        description: Apideck Get BalanceSheet\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-profit-and-loss\n      path: /accounting/profit-and-loss\n      operations:\n      - name: profitandlossone\n        method: GET\n        description: Apideck Get Profit and Loss\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-journal-entries\n      path: /accounting/journal-entries\n      operations:\n      - name: journalentriesall\n        method: GET\n        description: Apideck List Journal Entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: journalentriesadd\n        method: POST\n        description: Apideck Create Journal Entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: accounting-journal-entries-id\n      path: /accounting/journal-entries/{id}\n      operations:\n      - name: journalentriesone\n        method: GET\n        description: Apideck Get Journal Entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: journalentriesupdate\n        method: PATCH\n        description: Apideck Update Journal Entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: journalentriesdelete\n        method: DELETE\n        description: Apideck Delete Journal Entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-purchase-orders\n      path: /accounting/purchase-orders\n      operations:\n      - name: purchaseordersall\n        method: GET\n        description: Apideck List\
  \ Purchase Orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apideck-rest\n    description: REST adapter for Apideck Accounting API.\n    resources:\n    - path: /accounting/tax-rates\n      name: taxratesall\n      operations:\n      - method: GET\n        name: taxratesall\n        description: Apideck List Tax Rates\n        call: apideck.taxratesall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/tax-rates\n      name: taxratesadd\n      operations:\n      - method: POST\n        name: taxratesadd\n        description: Apideck Create Tax Rate\n        call: apideck.taxratesadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/tax-rates/{id}\n      name: taxratesone\n      operations:\n      - method: GET\n        name: taxratesone\n        description:\
  \ Apideck Get Tax Rate\n        call: apideck.taxratesone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/tax-rates/{id}\n      name: taxratesupdate\n      operations:\n      - method: PATCH\n        name: taxratesupdate\n        description: Apideck Update Tax Rate\n        call: apideck.taxratesupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/tax-rates/{id}\n      name: taxratesdelete\n      operations:\n      - method: DELETE\n        name: taxratesdelete\n        description: Apideck Delete Tax Rate\n        call: apideck.taxratesdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/bills\n      name: billsall\n      operations:\n      - method: GET\n        name: billsall\n        description: Apideck List Bills\n        call: apideck.billsall\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /accounting/bills\n      name: billsadd\n      operations:\n      - method: POST\n        name: billsadd\n        description: Apideck Create Bill\n        call: apideck.billsadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/bills/{id}\n      name: billsone\n      operations:\n      - method: GET\n        name: billsone\n        description: Apideck Get Bill\n        call: apideck.billsone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/bills/{id}\n      name: billsupdate\n      operations:\n      - method: PATCH\n        name: billsupdate\n        description: Apideck Update Bill\n        call: apideck.billsupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/bills/{id}\n      name: billsdelete\n      operations:\n      - method: DELETE\n        name: billsdelete\n        description: Apideck Delete Bill\n        call: apideck.billsdelete\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoices\n      name: invoicesall\n      operations:\n      - method: GET\n        name: invoicesall\n        description: Apideck List Invoices\n        call: apideck.invoicesall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoices\n      name: invoicesadd\n      operations:\n      - method: POST\n        name: invoicesadd\n        description: Apideck Create Invoice\n        call: apideck.invoicesadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoices/{id}\n      name: invoicesone\n      operations:\n      - method: GET\n        name: invoicesone\n        description: Apideck Get Invoice\n        call: apideck.invoicesone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoices/{id}\n      name: invoicesupdate\n      operations:\n\
  \      - method: PATCH\n        name: invoicesupdate\n        description: Apideck Update Invoice\n        call: apideck.invoicesupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoices/{id}\n      name: invoicesdelete\n      operations:\n      - method: DELETE\n        name: invoicesdelete\n        description: Apideck Delete Invoice\n        call: apideck.invoicesdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/ledger-accounts\n      name: ledgeraccountsall\n      operations:\n      - method: GET\n        name: ledgeraccountsall\n        description: Apideck List Ledger Accounts\n        call: apideck.ledgeraccountsall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/ledger-accounts\n      name: ledgeraccountsadd\n      operations:\n      - method: POST\n        name: ledgeraccountsadd\n        description: Apideck Create\
  \ Ledger Account\n        call: apideck.ledgeraccountsadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/ledger-accounts/{id}\n      name: ledgeraccountsone\n      operations:\n      - method: GET\n        name: ledgeraccountsone\n        description: Apideck Get Ledger Account\n        call: apideck.ledgeraccountsone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/ledger-accounts/{id}\n      name: ledgeraccountsupdate\n      operations:\n      - method: PATCH\n        name: ledgeraccountsupdate\n        description: Apideck Update Ledger Account\n        call: apideck.ledgeraccountsupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/ledger-accounts/{id}\n      name: ledgeraccountsdelete\n      operations:\n      - method: DELETE\n        name: ledgeraccountsdelete\n        description: Apideck Delete Ledger Account\n        call:\
  \ apideck.ledgeraccountsdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoice-items\n      name: invoiceitemsall\n      operations:\n      - method: GET\n        name: invoiceitemsall\n        description: Apideck List Invoice Items\n        call: apideck.invoiceitemsall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoice-items\n      name: invoiceitemsadd\n      operations:\n      - method: POST\n        name: invoiceitemsadd\n        description: Apideck Create Invoice Item\n        call: apideck.invoiceitemsadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoice-items/{id}\n      name: invoiceitemsone\n      operations:\n      - method: GET\n        name: invoiceitemsone\n        description: Apideck Get Invoice Item\n        call: apideck.invoiceitemsone\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /accounting/invoice-items/{id}\n      name: invoiceitemsupdate\n      operations:\n      - method: PATCH\n        name: invoiceitemsupdate\n        description: Apideck Update Invoice Item\n        call: apideck.invoiceitemsupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/invoice-items/{id}\n      name: invoiceitemsdelete\n      operations:\n      - method: DELETE\n        name: invoiceitemsdelete\n        description: Apideck Delete Invoice Item\n        call: apideck.invoiceitemsdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/credit-notes\n      name: creditnotesall\n      operations:\n      - method: GET\n        name: creditnotesall\n        description: Apideck List Credit Notes\n        call: apideck.creditnotesall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/credit-notes\n      name: creditnotesadd\n\
  \      operations:\n      - method: POST\n        name: creditnotesadd\n        description: Apideck Create Credit Note\n        call: apideck.creditnotesadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/credit-notes/{id}\n      name: creditnotesone\n      operations:\n      - method: GET\n        name: creditnotesone\n        description: Apideck Get Credit Note\n        call: apideck.creditnotesone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/credit-notes/{id}\n      name: creditnotesupdate\n      operations:\n      - method: PATCH\n        name: creditnotesupdate\n        description: Apideck Update Credit Note\n        call: apideck.creditnotesupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/credit-notes/{id}\n      name: creditnotesdelete\n      operations:\n      - method: DELETE\n        name: creditnotesdelete\n    \
  \    description: Apideck Delete Credit Note\n        call: apideck.creditnotesdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/customers\n      name: customersall\n      operations:\n      - method: GET\n        name: customersall\n        description: Apideck List Customers\n        call: apideck.customersall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/customers\n      name: customersadd\n      operations:\n      - method: POST\n        name: customersadd\n        description: Apideck Create Customer\n        call: apideck.customersadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/customers/{id}\n      name: customersone\n      operations:\n      - method: GET\n        name: customersone\n        description: Apideck Get Customer\n        call: apideck.customersone\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /accounting/customers/{id}\n      name: customersupdate\n      operations:\n      - method: PATCH\n        name: customersupdate\n        description: Apideck Update Customer\n        call: apideck.customersupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/customers/{id}\n      name: customersdelete\n      operations:\n      - method: DELETE\n        name: customersdelete\n        description: Apideck Delete Customer\n        call: apideck.customersdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/suppliers\n      name: suppliersall\n      operations:\n      - method: GET\n        name: suppliersall\n        description: Apideck List Suppliers\n        call: apideck.suppliersall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/suppliers\n      name: suppliersadd\n      operations:\n      - method:\
  \ POST\n        name: suppliersadd\n        description: Apideck Create Supplier\n        call: apideck.suppliersadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/suppliers/{id}\n      name: suppliersone\n      operations:\n      - method: GET\n        name: suppliersone\n        description: Apideck Get Supplier\n        call: apideck.suppliersone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/suppliers/{id}\n      name: suppliersupdate\n      operations:\n      - method: PATCH\n        name: suppliersupdate\n        description: Apideck Update Supplier\n        call: apideck.suppliersupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/suppliers/{id}\n      name: suppliersdelete\n      operations:\n      - method: DELETE\n        name: suppliersdelete\n        description: Apideck Delete Supplier\n        call: apideck.suppliersdelete\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/payments\n      name: paymentsall\n      operations:\n      - method: GET\n        name: paymentsall\n        description: Apideck List Payments\n        call: apideck.paymentsall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/payments\n      name: paymentsadd\n      operations:\n      - method: POST\n        name: paymentsadd\n        description: Apideck Create Payment\n        call: apideck.paymentsadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/payments/{id}\n      name: paymentsone\n      operations:\n      - method: GET\n        name: paymentsone\n        description: Apideck Get Payment\n        call: apideck.paymentsone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/payments/{id}\n      name: paymentsupdate\n      operations:\n\
  \      - method: PATCH\n        name: paymentsupdate\n        description: Apideck Update Payment\n        call: apideck.paymentsupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/payments/{id}\n      name: paymentsdelete\n      operations:\n      - method: DELETE\n        name: paymentsdelete\n        description: Apideck Delete Payment\n        call: apideck.paymentsdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/refunds\n      name: refundsall\n      operations:\n      - method: GET\n        name: refundsall\n        description: Apideck List Refunds\n        call: apideck.refundsall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/refunds\n      name: refundsadd\n      operations:\n      - method: POST\n        name: refundsadd\n        description: Apideck Create Refund\n        call: apideck.refundsadd\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounting/refunds/{id}\n      name: refundsone\n      operations:\n      - method: GET\n        name: refundsone\n        description: Apideck Get Refund\n        call: apideck.refundsone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/refunds/{id}\n      name: refundsupdate\n      operations:\n      - method: PATCH\n        name: refundsupdate\n        description: Apideck Update Refund\n        call: apideck.refundsupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/refunds/{id}\n      name: refundsdelete\n      operations:\n      - method: DELETE\n        name: refundsdelete\n        description: Apideck Delete Refund\n        call: apideck.refundsdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/company-info\n      name: companyinfoone\n      operations:\n      -\
  \ method: GET\n        name: companyinfoone\n        description: Apideck Get company info\n        call: apideck.companyinfoone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/companies\n      name: companiesall\n      operations:\n      - method: GET\n        name: companiesall\n        description: Apideck List companies\n        call: apideck.companiesall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/balance-sheet\n      name: balancesheetone\n      operations:\n      - method: GET\n        name: balancesheetone\n        description: Apideck Get BalanceSheet\n        call: apideck.balancesheetone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/profit-and-loss\n      name: profitandlossone\n      operations:\n      - method: GET\n        name: profitandlossone\n        description: Apideck Get Profit and Loss\n        call: apideck.profitandlossone\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/journal-entries\n      name: journalentriesall\n      operations:\n      - method: GET\n        name: journalentriesall\n        description: Apideck List Journal Entries\n        call: apideck.journalentriesall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/journal-entries\n      name: journalentriesadd\n      operations:\n      - method: POST\n        name: journalentriesadd\n        description: Apideck Create Journal Entry\n        call: apideck.journalentriesadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounting/journal-entries/{id}\n      name: journalentriesone\n      operations:\n      - method: GET\n        name: journalentriesone\n        descriptio\n\n# --- truncated at 32 KB (48 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/apideck/refs/heads/main/capabilities/apideck-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apideck/refs/heads/main/capabilities/apideck-capability.yaml
tags:
- Apideck
- API
tools:
- description: Apideck List Tax Rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: taxratesall
- description: Apideck Create Tax Rate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: taxratesadd
- description: Apideck Get Tax Rate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: taxratesone
- description: Apideck Update Tax Rate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: taxratesupdate
- description: Apideck Delete Tax Rate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: taxratesdelete
- description: Apideck List Bills
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: billsall
- description: Apideck Create Bill
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: billsadd
- description: Apideck Get Bill
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: billsone
- description: Apideck Update Bill
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: billsupdate
- description: Apideck Delete Bill
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: billsdelete
- description: Apideck List Invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: invoicesall
- description: Apideck Create Invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invoicesadd
- description: Apideck Get Invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: invoicesone
- description: Apideck Update Invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invoicesupdate
- description: Apideck Delete Invoice
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: invoicesdelete
- description: Apideck List Ledger Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ledgeraccountsall
- description: Apideck Create Ledger Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ledgeraccountsadd
- description: Apideck Get Ledger Account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ledgeraccountsone
- description: Apideck Update Ledger Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ledgeraccountsupdate
- description: Apideck Delete Ledger Account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: ledgeraccountsdelete
- description: Apideck List Invoice Items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: invoiceitemsall
- description: Apideck Create Invoice Item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invoiceitemsadd
- description: Apideck Get Invoice Item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: invoiceitemsone
- description: Apideck Update Invoice Item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invoiceitemsupdate
- description: Apideck Delete Invoice Item
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: invoiceitemsdelete
- description: Apideck List Credit Notes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: creditnotesall
- description: Apideck Create Credit Note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creditnotesadd
- description: Apideck Get Credit Note
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: creditnotesone
- description: Apideck Update Credit Note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creditnotesupdate
- description: Apideck Delete Credit Note
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: creditnotesdelete
- description: Apideck List Customers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: customersall
- description: Apideck Create Customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: customersadd
- description: Apideck Get Customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: customersone
- description: Apideck Update Customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: customersupdate
- description: Apideck Delete Customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: customersdelete
- description: Apideck List Suppliers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: suppliersall
- description: Apideck Create Supplier
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: suppliersadd
- description: Apideck Get Supplier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: suppliersone
- description: Apideck Update Supplier
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: suppliersupdate
- description: Apideck Delete Supplier
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: suppliersdelete
- description: Apideck List Payments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paymentsall
- description: Apideck Create Payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: paymentsadd
- description: Apideck Get Payment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paymentsone
- description: Apideck Update Payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: paymentsupdate
- description: Apideck Delete Payment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: paymentsdelete
- description: Apideck List Refunds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: refundsall
- description: Apideck Create Refund
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refundsadd
- description: Apideck Get Refund
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: refundsone
- description: Apideck Update Refund
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refundsupdate
- description: Apideck Delete Refund
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: refundsdelete
- description: Apideck Get company info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: companyinfoone
- description: Apideck List companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: companiesall
- description: Apideck Get BalanceSheet
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: balancesheetone
- description: Apideck Get Profit and Loss
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: profitandlossone
- description: Apideck List Journal Entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: journalentriesall
- description: Apideck Create Journal Entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: journalentriesadd
- description: Apideck Get Journal Entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: journalentriesone
- description: Apideck Update Journal Entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: journalentriesupdate
- description: Apideck Delete Journal Entry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: journalentriesdelete
- description: Apideck List Purchase Orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: purchaseordersall
---
