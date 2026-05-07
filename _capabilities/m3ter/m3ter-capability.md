---
categories: []
consumed_apis: []
description: 'If you are using Postman, you can: - Use the **Download** button above to download the m3ter Open API spec JSON file and then import this file as the **m3ter API Collection** into your Workspace. See [Importing the m3ter Open API](https://www.m3ter.com/docs/guides/m3ter-apis/getting-started-with-api-calls#importing-the-m3ter-open-api) in our main user Documentation for details. - Copy this link: [m3ter-Template API Collection](https://www.datocms-assets.com/78893/1672846767-m3ter-template-api-collection-postman_collection.json) and use it to import the **m3ter-Template API Collection** into yo'
layout: capability
name: m3ter API
operations:
- description: Retrieve Debit Line Item
  method: GET
  name: getdebitlineitem
  path: /organizations/{orgId}/bills/{billId}/debitlineitems/{id}
- description: Update Debit Line Item
  method: PUT
  name: putdebitlineitem
  path: /organizations/{orgId}/bills/{billId}/debitlineitems/{id}
- description: Delete Debit Line Item
  method: DELETE
  name: deletedebitlineitem
  path: /organizations/{orgId}/bills/{billId}/debitlineitems/{id}
- description: Retrieve latest Bill
  method: GET
  name: getlatestbill
  path: /organizations/{orgId}/bills/latest/{accountId}
- description: List Debit Line Items
  method: GET
  name: listdebitlineitems
  path: /organizations/{orgId}/bills/{billId}/debitlineitems
- description: Create Debit Line Item
  method: POST
  name: postdebitlineitem
  path: /organizations/{orgId}/bills/{billId}/debitlineitems
- description: Retrieve Bill
  method: GET
  name: getbill
  path: /organizations/{orgId}/bills/{id}
- description: Delete Bill
  method: DELETE
  name: deletebill
  path: /organizations/{orgId}/bills/{id}
- description: Retrieve BalanceChargeSchedule
  method: GET
  name: getbalancechargeschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancechargeschedules/{id}
- description: Update BalanceChargeSchedule
  method: PUT
  name: updatebalancechargeschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancechargeschedules/{id}
- description: Delete BalanceChargeSchedule
  method: DELETE
  name: deletebalancechargeschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancechargeschedules/{id}
- description: List BalanceTransactionSchedule
  method: GET
  name: listbalancetransactionschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules
- description: Create BalanceTransactionSchedule
  method: POST
  name: createbalancetransactionschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules
- description: Retrieve Credit Line Item
  method: GET
  name: getcreditlineitem
  path: /organizations/{orgId}/bills/{billId}/creditlineitems/{id}
- description: Update Credit Line Item
  method: PUT
  name: putcreditlineitem
  path: /organizations/{orgId}/bills/{billId}/creditlineitems/{id}
- description: Delete Credit Line Item
  method: DELETE
  name: deletecreditlineitem
  path: /organizations/{orgId}/bills/{billId}/creditlineitems/{id}
- description: Cancel StatementJob
  method: POST
  name: cancelstatementjob
  path: /organizations/{orgId}/statementjobs/{id}/cancel
- description: Retrieve BalanceTransactionSchedule
  method: GET
  name: getbalancetransactionschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules/{id}
- description: Update BalanceTransactionSchedule
  method: PUT
  name: updatebalancetransactionschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules/{id}
- description: Delete BalanceTransactionSchedule
  method: DELETE
  name: deletebalancetransactionschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules/{id}
- description: Retrieve BillConfig
  method: GET
  name: getbillconfig
  path: /organizations/{orgId}/billconfig
- description: Update BillConfig
  method: PUT
  name: updatebillconfig
  path: /organizations/{orgId}/billconfig
- description: List Bills
  method: GET
  name: listbills
  path: /organizations/{orgId}/bills
- description: Update Bill Status
  method: PUT
  name: updatebillstatus
  path: /organizations/{orgId}/bills/{id}/status
- description: Retrieve Bill Statement in JSON Format
  method: GET
  name: getbilljsonstatement
  path: /organizations/{orgId}/bills/{id}/statement/json
- description: List Line Items
  method: GET
  name: listbilllineitems
  path: /organizations/{orgId}/bills/{billId}/lineitems
- description: List Transactions
  method: GET
  name: listbalancetransactions
  path: /organizations/{orgId}/balances/{balanceId}/transactions
- description: Create Balance Transaction
  method: POST
  name: postbalancetransaction
  path: /organizations/{orgId}/balances/{balanceId}/transactions
- description: Retrieve Bills for an Account ID
  method: GET
  name: getallbillsforaccount
  path: /organizations/{orgId}/bills/accountid/{accountId}
- description: Preview ScheduledBalanceTransactions
  method: POST
  name: previewbalancetransactionschedule
  path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules/preview
- description: Retrieve Line Item
  method: GET
  name: getbilllineitem
  path: /organizations/{orgId}/bills/{billId}/lineitems/{id}
- description: Lock Bill
  method: PUT
  name: lockbill
  path: /organizations/{orgId}/bills/{id}/lock
- description: Approve Bills in Billing Period
  method: POST
  name: approveallbillsinbillingperiod
  path: /organizations/{orgId}/bills/billingperiod/{lastDateInBillingPeriod}/{billingFrequency}/approve
- description: List Charges
  method: GET
  name: listcharges
  path: /organizations/{orgId}/charges
- description: Create Charge
  method: POST
  name: createcharge
  path: /organizations/{orgId}/charges
- description: Get Balance Transactions Summary
  method: GET
  name: getbalancetransactionssummary
  path: /organizations/{orgId}/balances/{balanceId}/transactions/summary
- description: Retrieve BillJob
  method: GET
  name: getbilljob
  path: /organizations/{orgId}/billjobs/{id}
- description: List Balances
  method: GET
  name: listbalances
  path: /organizations/{orgId}/balances
- description: Create Balance
  method: POST
  name: postbalance
  path: /organizations/{orgId}/balances
- description: Get StatementJob
  method: GET
  name: getstatementjob
  path: /organizations/{orgId}/statementjobs/{id}
- description: Retrieve Bill Statement in CSV Format
  method: GET
  name: getbillcsvstatement
  path: /organizations/{orgId}/bills/{id}/statement/csv
- description: Create Bill Statement in CSV Format
  method: POST
  name: createbillcsvstatement
  path: /organizations/{orgId}/bills/{id}/statement/csv
- description: List BillJobs
  method: GET
  name: listbilljobs
  path: /organizations/{orgId}/billjobs
- description: Create BillJob
  method: POST
  name: createbilljob
  path: /organizations/{orgId}/billjobs
- description: Preview ScheduledBalanceCharges
  method: POST
  name: previewscheduledcharge
  path: /organizations/{orgId}/balances/{balanceId}/balancechargeschedules/preview
- description: List Line Items
  method: GET
  name: listlineitems
  path: /organizations/{orgId}/lineitems
- description: Retrieve Balance
  method: GET
  name: getbalance
  path: /organizations/{orgId}/balances/{id}
- description: Update Balance
  method: PUT
  name: putbalance
  path: /organizations/{orgId}/balances/{id}
- description: Delete Balance
  method: DELETE
  name: deletebalance
  path: /organizations/{orgId}/balances/{id}
- description: Cancel BillJob
  method: POST
  name: cancelbilljob
  path: /organizations/{orgId}/billjobs/{id}/cancel
- description: List CounterAdjustments
  method: GET
  name: listcounteradjustments
  path: /organizations/{orgId}/counteradjustments
- description: Create CounterAdjustment
  method: POST
  name: postcounteradjustment
  path: /organizations/{orgId}/counteradjustments
- description: Preview Bill
  method: POST
  name: previewbill
  path: /organizations/{orgId}/bills/preview
- description: Create Batch StatementJobs
  method: POST
  name: createstatementjobbatch
  path: /organizations/{orgId}/statementjobs/batch
- description: Retrieve CounterAdjustment
  method: GET
  name: getcounteradjustment
  path: /organizations/{orgId}/counteradjustments/{id}
- description: Update CounterAdjustment
  method: PUT
  name: putcounteradjustment
  path: /organizations/{orgId}/counteradjustments/{id}
- description: Delete CounterAdjustment
  method: DELETE
  name: deletecounteradjustment
  path: /organizations/{orgId}/counteradjustments/{id}
- description: Create Recalculation BillJob
  method: POST
  name: recalculatebilljob
  path: /organizations/{orgId}/billjobs/recalculate
- description: Retrieve Line Item Usage in JSON Format
  method: GET
  name: getbilllineitemjsonusage
  path: /organizations/{orgId}/bills/{billId}/lineitems/{id}/usage/json
- description: List Credit Line Items
  method: GET
  name: listcreditlineitems
  path: /organizations/{orgId}/bills/{billId}/creditlineitems
personas: []
provider_name: M3ter
provider_slug: m3ter
search_terms:
- createbalancetransactionschedule
- updatebalancetransactionschedule
- api
- listdebitlineitems
- list billjobs
- retrieve counteradjustment
- getbillcsvstatement
- preview scheduledbalancecharges
- update counteradjustment
- putbalance
- getcreditlineitem
- update balance
- get statementjob
- cancelbilljob
- create billjob
- listbalancetransactions
- listcounteradjustments
- deletebalance
- retrieve line item usage in json format
- deletebalancechargeschedule
- create charge
- listbills
- finops
- create counteradjustment
- deletedebitlineitem
- approve bills in billing period
- list charges
- list line items
- listcharges
- postdebitlineitem
- list balancetransactionschedule
- listbalancetransactionschedule
- listbalances
- getstatementjob
- delete credit line item
- updatebalancechargeschedule
- create balance
- usage-based billing
- putcreditlineitem
- list debit line items
- delete balancechargeschedule
- retrieve billjob
- retrieve credit line item
- cancel statementjob
- createbillcsvstatement
- update balancetransactionschedule
- getbilllineitem
- update credit line item
- create batch statementjobs
- listcreditlineitems
- getallbillsforaccount
- delete debit line item
- getbalancetransactionssummary
- retrieve balance
- metering
- retrieve bill statement in csv format
- createstatementjobbatch
- getbilljob
- create balancetransactionschedule
- postbalance
- m3ter
- deletebalancetransactionschedule
- postbalancetransaction
- getbillconfig
- list transactions
- delete balance
- getdebitlineitem
- retrieve balancechargeschedule
- get balance transactions summary
- listbilljobs
- update billconfig
- list balances
- updatebillconfig
- putcounteradjustment
- list counteradjustments
- billing
- update bill status
- list credit line items
- getbalancechargeschedule
- create recalculation billjob
- createcharge
- getbalancetransactionschedule
- saas
- cancel billjob
- previewbill
- deletebill
- approveallbillsinbillingperiod
- update debit line item
- retrieve debit line item
- preview scheduledbalancetransactions
- create bill statement in csv format
- delete bill
- previewscheduledcharge
- cancelstatementjob
- deletecreditlineitem
- create balance transaction
- retrieve billconfig
- preview bill
- retrieve balancetransactionschedule
- retrieve bills for an account id
- listlineitems
- getlatestbill
- postcounteradjustment
- lock bill
- delete counteradjustment
- create debit line item
- retrieve latest bill
- retrieve bill
- createbilljob
- recalculatebilljob
- update balancechargeschedule
- getbilllineitemjsonusage
- deletecounteradjustment
- pricing
- getbilljsonstatement
- list bills
- delete balancetransactionschedule
- listbilllineitems
- getbill
- retrieve bill statement in json format
- previewbalancetransactionschedule
- updatebillstatus
- getbalance
- lockbill
- putdebitlineitem
- retrieve line item
- getcounteradjustment
slug: m3ter-capability
source_filename: m3ter-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: m3ter API\n  description: 'If you are using Postman, you can: - Use the **Download** button above to download the m3ter Open API spec\n    JSON file and then import this file as the **m3ter API Collection** into your Workspace. See [Importing the m3ter Open\n    API](https://www.m3ter.com/docs/guides/m3ter-apis/getting-started-with-api-calls#importing-the-m3ter-open-api) in our\n    main user Documentation for details. - Copy this link: [m3ter-Template API Collection](https://www.datocms-assets.com/78893/1672846767-m3ter-template-api-collection-postman_collection.json)\n    and use it to import the **m3ter-Template API Collection** into yo'\n  tags:\n  - M3ter\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: m3ter\n    baseUri: https://api.m3ter.com\n    description: m3ter API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{M3TER_TOKEN}}'\n    resources:\n\
  \    - name: organizations-orgid-bills-billid-debitlineitems-\n      path: /organizations/{orgId}/bills/{billId}/debitlineitems/{id}\n      operations:\n      - name: getdebitlineitem\n        method: GET\n        description: Retrieve Debit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the Organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: UUID of the bill.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the debit line item to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putdebitlineitem\n        method: PUT\n     \
  \   description: Update Debit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the Organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: UUID of the bill.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the debit line item to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedebitlineitem\n        method: DELETE\n        description: Delete Debit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the Organization. The\
  \ Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: UUID of the bill.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: UUID of the debit line item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-latest-accountid\n      path: /organizations/{orgId}/bills/latest/{accountId}\n      operations:\n      - name: getlatestbill\n        method: GET\n        description: Retrieve latest Bill\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of\
  \ our service.\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Account for which the latest Bill should be retrieved.\n        - name: additional\n          in: query\n          type: array\n          description: Comma separated list of additional fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-billid-debitlineitems\n      path: /organizations/{orgId}/bills/{billId}/debitlineitems\n      operations:\n      - name: listdebitlineitems\n        method: GET\n        description: List Debit Line Items\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the Organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n\
  \        - name: billId\n          in: path\n          type: string\n          required: true\n          description: UUID of the bill.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of line items to retrieve per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: '`nextToken` for multi page retrievals.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postdebitlineitem\n        method: POST\n        description: Create Debit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the Organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n\
  \          description: UUID of the bill.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-id\n      path: /organizations/{orgId}/bills/{id}\n      operations:\n      - name: getbill\n        method: GET\n        description: Retrieve Bill\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Bill to retrieve.\n        - name: additional\n          in: query\n          type: array\n          description: Comma separated list of additional fields.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletebill\n        method: DELETE\n        description: Delete Bill\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Bill to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-balances-balanceid-balancech\n      path: /organizations/{orgId}/balances/{balanceId}/balancechargeschedules/{id}\n      operations:\n      - name: getbalancechargeschedule\n        method: GET\n        description: Retrieve BalanceChargeSchedule\n\
  \        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the BalanceChargeSchedule to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebalancechargeschedule\n        method: PUT\n        description: Update BalanceChargeSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description:\
  \ UUID of the balance\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the BalanceChargeSchedule to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebalancechargeschedule\n        method: DELETE\n        description: Delete BalanceChargeSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the BalanceChargeSchedule to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: organizations-orgid-balances-balanceid-balancetr\n      path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules\n      operations:\n      - name: listbalancetransactionschedule\n        method: GET\n        description: List BalanceTransactionSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of BalanceTransactionSchedules to retrieve per page\n        - name: nextToken\n          in: query\n          type: string\n          description: nextToken for multi page retrievals\n        - name: ids\n          in: query\n          type: array\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbalancetransactionschedule\n        method: POST\n        description: Create BalanceTransactionSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-billid-creditlineitems\n      path: /organizations/{orgId}/bills/{billId}/creditlineitems/{id}\n      operations:\n      - name: getcreditlineitem\n        method: GET\n        description: Retrieve Credit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n         \
  \ type: string\n          required: true\n          description: UUID of the organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: UUID of the Bill.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Credit line item to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putcreditlineitem\n        method: PUT\n        description: Update Credit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n\
  \          in: path\n          type: string\n          required: true\n          description: UUID of the bill.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the credit line item to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecreditlineitem\n        method: DELETE\n        description: Delete Credit Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: UUID of the bill.\n        - name: id\n          in: path\n          type: string\n          required: true\n   \
  \       description: UUID of the credit line item to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-statementjobs-id-cancel\n      path: /organizations/{orgId}/statementjobs/{id}/cancel\n      operations:\n      - name: cancelstatementjob\n        method: POST\n        description: Cancel StatementJob\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the StatementJob to cancel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: organizations-orgid-balances-balanceid-balancetr\n      path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules/{id}\n      operations:\n      - name: getbalancetransactionschedule\n        method: GET\n        description: Retrieve BalanceTransactionSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the BalanceTransactionSchedule to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebalancetransactionschedule\n        method: PUT\n        description:\
  \ Update BalanceTransactionSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the BalanceTransactionSchedule to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebalancetransactionschedule\n        method: DELETE\n        description: Delete BalanceTransactionSchedule\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type:\
  \ string\n          required: true\n          description: UUID of the balance\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The UUID of the BalanceTransactionSchedule to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-billconfig\n      path: /organizations/{orgId}/billconfig\n      operations:\n      - name: getbillconfig\n        method: GET\n        description: Retrieve BillConfig\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebillconfig\n\
  \        method: PUT\n        description: Update BillConfig\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization. The Organization represents your company as a direct customer of the m3ter\n            service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills\n      path: /organizations/{orgId}/bills\n      operations:\n      - name: listbills\n        method: GET\n        description: List Bills\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: pageSize\n          in: query\n          type: integer\n        \
  \  description: Specifies the maximum number of Bills to retrieve per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: The `nextToken` for multi-page retrievals. It is used to fetch the next page of Bills in a paginated\n            list.\n        - name: accountId\n          in: query\n          type: string\n          description: Optional filter. An Account ID - returns the Bills for the single specified Account.\n        - name: locked\n          in: query\n          type: boolean\n          description: Boolean flag specifying whether to include Bills with \"locked\" status. * **TRUE** - the list inlcudes\n            \"locked\" Bills. * **FALSE** - excludes \"locked\" Bills from\n        - name: excludeLineItems\n          in: query\n          type: boolean\n          description: Exclude Line Items\n        - name: includeBillTotal\n          in: query\n          type: boolean\n          description: Include Bill Total\n     \
  \   - name: status\n          in: query\n          type: string\n          description: Only include Bills having the given status\n        - name: billDate\n          in: query\n          type: string\n          description: The specific date in ISO 8601 format for which you want to retrieve Bills.\n        - name: billDateStart\n          in: query\n          type: string\n          description: Only include Bills with bill dates equal to or later than this date.\n        - name: billDateEnd\n          in: query\n          type: string\n          description: Only include Bills with bill dates earlier than this date.\n        - name: externalInvoiceDateStart\n          in: query\n          type: string\n          description: Only include Bills with external invoice dates equal to or later than this date.\n        - name: externalInvoiceDateEnd\n          in: query\n          type: string\n          description: Only include Bills with external invoice dates earlier than this date.\n\
  \        - name: ids\n          in: query\n          type: array\n          description: Optional filter. The list of Bill IDs to retrieve.\n        - name: billJobId\n          in: query\n          type: string\n          description: List Bill entities by the bill job that last calculated them.\n        - name: additional\n          in: query\n          type: array\n          description: Comma separated list of additional fields.\n        - name: billingFrequency\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-id-status\n      path: /organizations/{orgId}/bills/{id}/status\n      operations:\n      - name: updatebillstatus\n        method: PUT\n        description: Update Bill Status\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Bill whose status you want to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-id-statement-json\n      path: /organizations/{orgId}/bills/{id}/statement/json\n      operations:\n      - name: getbilljsonstatement\n        method: GET\n        description: Retrieve Bill Statement in JSON Format\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Bill for which you want to retrieve the Statement.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-billid-lineitems\n      path: /organizations/{orgId}/bills/{billId}/lineitems\n      operations:\n      - name: listbilllineitems\n        method: GET\n        description: List Line Items\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Bill\
  \ for which you want to list the line items.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Specifies the maximum number of line items to retrieve per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: The `nextToken` for multi-page retrievals. It is used to fetch the next page of line items in a paginated\n            list.\n        - name: additional\n          in: query\n          type: array\n          description: Comma separated list of additional fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-balances-balanceid-transacti\n      path: /organizations/{orgId}/balances/{balanceId}/transactions\n      operations:\n      - name: listbalancetransactions\n        method: GET\n        description: List Transactions\n        inputParameters:\n        - name: orgId\n     \
  \     in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) for your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) for the Balance whose Transactions you want to retrieve.\n        - name: pageSize\n          in: query\n          type: integer\n          description: The maximum number of transactions to return per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: '`nextToken` for multi page retrievals. A token for retrieving the next page of transactions. You''ll\n            get this from the response to your request.'\n        - name: transactionTypeId\n          in: query\n          type: string\n        - name: entityType\n          in: query\n          type: string\n\
  \        - name: entityId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postbalancetransaction\n        method: POST\n        description: Create Balance Transaction\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) for your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) for the Balance to which you want to add a transaction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-accountid-accountid\n      path: /organizations/{orgId}/bills/accountid/{accountId}\n\
  \      operations:\n      - name: getallbillsforaccount\n        method: GET\n        description: Retrieve Bills for an Account ID\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Specifies the maximum number of Bills to retrieve per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: The `nextToken` for multi-page retrievals. It is used to fetch the next page of Bills in a paginated\n            list.\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Account for which you want to retrieve Bills.\n      \
  \  - name: additional\n          in: query\n          type: array\n          description: Comma separated list of additional fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-balances-balanceid-balancetr\n      path: /organizations/{orgId}/balances/{balanceId}/balancetransactionschedules/preview\n      operations:\n      - name: previewbalancetransactionschedule\n        method: POST\n        description: Preview ScheduledBalanceTransactions\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: balanceId\n          in: path\n          type: string\n          required: true\n          description: UUID of the balance\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of BalanceTransactions to\
  \ retrieve per page\n        - name: nextToken\n          in: query\n          type: string\n          description: nextToken for multi page retrievals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-billid-lineitems-id\n      path: /organizations/{orgId}/bills/{billId}/lineitems/{id}\n      operations:\n      - name: getbilllineitem\n        method: GET\n        description: Retrieve Line Item\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the Bill containing the line item.\n        - name:\
  \ id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of the line item you want to retrieve.\n        - name: additional\n          in: query\n          type: array\n          description: Comma separated list of additional fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-id-lock\n      path: /organizations/{orgId}/bills/{id}/lock\n      operations:\n      - name: lockbill\n        method: PUT\n        description: Lock Bill\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \          description: The unique identifier (UUID) of the Bill to lock.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-bills-billingperiod-lastdate\n      path: /organizations/{orgId}/bills/billingperiod/{lastDateInBillingPeriod}/{billingFrequency}/approve\n      operations:\n      - name: approveallbillsinbillingperiod\n        method: POST\n        description: Approve Bills in Billing Period\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (UUID) of your Organization. The Organization represents your company as a direct\n            customer of our service.\n        - name: lastDateInBillingPeriod\n          in: path\n          type: string\n          required: true\n          description: The last date of the billing period for which you want to approve Bills.\
  \ This date defines the range\n            of Bills to be approved.\n        - name: billingFrequency\n          in: path\n          type: string\n          required: true\n          description: The billing frequency for the specified period. Valid options are daily, weekly, monthly, or annually.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-charges\n      path: /organizations/{orgId}/charges\n      operations:\n      - name: listcharges\n        method: GET\n        description: List Charges\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: UUID of the organization\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of Charges to retrieve per page\n        - name: nextToken\n          in: query\n          type: string\n          description:\
  \ nextToken for multi page retrievals\n        - name: accountId\n          in: query\n          type: string\n          description: List Charge items for the Account UUID\n        - name: entityType\n          in: query\n          type: string\n          description: List Charge items for the EntityType\n        - name: entityId\n          in: query\n          type: string\n          description: List Charge items for the Entity UUID\n        - name: billDate\n          in: query\n          type: string\n          description: List Charge items for the Bill Date\n        - name: ids\n          in: query\n          type: array\n          description: List of Charge UUIDs \n\n# --- truncated at 32 KB (129 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/m3ter/refs/heads/main/capabilities/m3ter-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/m3ter/refs/heads/main/capabilities/m3ter-capability.yaml
tags:
- M3ter
- API
tools:
- description: Retrieve Debit Line Item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdebitlineitem
- description: Update Debit Line Item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putdebitlineitem
- description: Delete Debit Line Item
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedebitlineitem
- description: Retrieve latest Bill
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatestbill
- description: List Debit Line Items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdebitlineitems
- description: Create Debit Line Item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdebitlineitem
- description: Retrieve Bill
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbill
- description: Delete Bill
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebill
- description: Retrieve BalanceChargeSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalancechargeschedule
- description: Update BalanceChargeSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebalancechargeschedule
- description: Delete BalanceChargeSchedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebalancechargeschedule
- description: List BalanceTransactionSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbalancetransactionschedule
- description: Create BalanceTransactionSchedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbalancetransactionschedule
- description: Retrieve Credit Line Item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcreditlineitem
- description: Update Credit Line Item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putcreditlineitem
- description: Delete Credit Line Item
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecreditlineitem
- description: Cancel StatementJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelstatementjob
- description: Retrieve BalanceTransactionSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalancetransactionschedule
- description: Update BalanceTransactionSchedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebalancetransactionschedule
- description: Delete BalanceTransactionSchedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebalancetransactionschedule
- description: Retrieve BillConfig
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbillconfig
- description: Update BillConfig
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebillconfig
- description: List Bills
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbills
- description: Update Bill Status
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebillstatus
- description: Retrieve Bill Statement in JSON Format
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbilljsonstatement
- description: List Line Items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbilllineitems
- description: List Transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbalancetransactions
- description: Create Balance Transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postbalancetransaction
- description: Retrieve Bills for an Account ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallbillsforaccount
- description: Preview ScheduledBalanceTransactions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: previewbalancetransactionschedule
- description: Retrieve Line Item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbilllineitem
- description: Lock Bill
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: lockbill
- description: Approve Bills in Billing Period
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approveallbillsinbillingperiod
- description: List Charges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcharges
- description: Create Charge
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcharge
- description: Get Balance Transactions Summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalancetransactionssummary
- description: Retrieve BillJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbilljob
- description: List Balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbalances
- description: Create Balance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postbalance
- description: Get StatementJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatementjob
- description: Retrieve Bill Statement in CSV Format
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbillcsvstatement
- description: Create Bill Statement in CSV Format
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbillcsvstatement
- description: List BillJobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbilljobs
- description: Create BillJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbilljob
- description: Preview ScheduledBalanceCharges
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: previewscheduledcharge
- description: List Line Items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlineitems
- description: Retrieve Balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalance
- description: Update Balance
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putbalance
- description: Delete Balance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebalance
- description: Cancel BillJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelbilljob
- description: List CounterAdjustments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcounteradjustments
- description: Create CounterAdjustment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postcounteradjustment
- description: Preview Bill
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: previewbill
- description: Create Batch StatementJobs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstatementjobbatch
- description: Retrieve CounterAdjustment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcounteradjustment
- description: Update CounterAdjustment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putcounteradjustment
- description: Delete CounterAdjustment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecounteradjustment
- description: Create Recalculation BillJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recalculatebilljob
- description: Retrieve Line Item Usage in JSON Format
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbilllineitemjsonusage
- description: List Credit Line Items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcreditlineitems
---
