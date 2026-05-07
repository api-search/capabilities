---
categories: []
consumed_apis: []
description: REST API for Oracle Fusion Cloud Financials General Ledger, providing programmatic access to journal batches, journal entries, ledger balances, currency rates, chart of accounts filters, and budgetary control. The API supports creating, retrieving, updating, and deleting journal batches, viewing account balances for any account combination or account group, and managing currency conversion rates used across the financial system.
layout: capability
name: Oracle Financials General Ledger API
operations:
- description: Oracle Financials List journal batches
  method: GET
  name: listjournalbatches
  path: /fscmRestApi/resources/11.13.18.05/journalBatches
- description: Oracle Financials Get a journal batch
  method: GET
  name: getjournalbatch
  path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}
- description: Oracle Financials Update a journal batch
  method: PATCH
  name: updatejournalbatch
  path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}
- description: Oracle Financials Delete a journal batch
  method: DELETE
  name: deletejournalbatch
  path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}
- description: Oracle Financials List account balances
  method: GET
  name: listledgerbalances
  path: /fscmRestApi/resources/11.13.18.05/ledgerBalances
- description: Oracle Financials List currency rates
  method: GET
  name: listcurrencyrates
  path: /fscmRestApi/resources/11.13.18.05/currencyRates
- description: Oracle Financials Create a chart of accounts filter
  method: POST
  name: createchartofaccountsfilter
  path: /fscmRestApi/resources/11.13.18.05/chartOfAccountsFilters
- description: Oracle Financials List budgetary control results
  method: GET
  name: listbudgetarycontrolresults
  path: /fscmRestApi/resources/11.13.18.05/budgetaryControlResults
- description: Oracle Financials Create a budget transaction
  method: POST
  name: createbudgettransaction
  path: /fscmRestApi/resources/11.13.18.05/budgetaryControlBudgetTransactions
personas: []
provider_name: Oracle Financials
provider_slug: oracle-financials
search_terms:
- getjournalbatch
- expense management
- accounting
- financials
- general ledger
- listjournalbatches
- accounts payable
- api
- accounts receivable
- oracle financials list account balances
- oracle financials list budgetary control results
- oracle financials create a chart of accounts filter
- financial management
- listcurrencyrates
- oracle financials list journal batches
- updatejournalbatch
- oracle financials get a journal batch
- oracle financials create a budget transaction
- oracle financials delete a journal batch
- oracle financials list currency rates
- createbudgettransaction
- cash management
- oracle financials update a journal batch
- listbudgetarycontrolresults
- erp
- deletejournalbatch
- oracle
- createchartofaccountsfilter
- listledgerbalances
slug: oracle-financials-capability
source_filename: oracle-financials-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Financials General Ledger API\n  description: REST API for Oracle Fusion Cloud Financials General Ledger, providing programmatic access to journal batches,\n    journal entries, ledger balances, currency rates, chart of accounts filters, and budgetary control. The API supports creating,\n    retrieving, updating, and deleting journal batches, viewing account balances for any account combination or account group,\n    and managing currency conversion rates used across the financial system.\n  tags:\n  - Oracle\n  - Financials\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-financials\n    baseUri: https://servername.oraclecloud.com\n    description: Oracle Financials General Ledger API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_FINANCIALS_TOKEN}}'\n    resources:\n    - name: fscmrestapi-resources-11-13-18-05-journalbatches\n\
  \      path: /fscmRestApi/resources/11.13.18.05/journalBatches\n      operations:\n      - name: listjournalbatches\n        method: GET\n        description: Oracle Financials List journal batches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-journalbatches\n      path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}\n      operations:\n      - name: getjournalbatch\n        method: GET\n        description: Oracle Financials Get a journal batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatejournalbatch\n        method: PATCH\n        description: Oracle Financials Update a journal batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejournalbatch\n\
  \        method: DELETE\n        description: Oracle Financials Delete a journal batch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-ledgerbalances\n      path: /fscmRestApi/resources/11.13.18.05/ledgerBalances\n      operations:\n      - name: listledgerbalances\n        method: GET\n        description: Oracle Financials List account balances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-currencyrates\n      path: /fscmRestApi/resources/11.13.18.05/currencyRates\n      operations:\n      - name: listcurrencyrates\n        method: GET\n        description: Oracle Financials List currency rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-chartofaccount\n\
  \      path: /fscmRestApi/resources/11.13.18.05/chartOfAccountsFilters\n      operations:\n      - name: createchartofaccountsfilter\n        method: POST\n        description: Oracle Financials Create a chart of accounts filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-budgetarycontr\n      path: /fscmRestApi/resources/11.13.18.05/budgetaryControlResults\n      operations:\n      - name: listbudgetarycontrolresults\n        method: GET\n        description: Oracle Financials List budgetary control results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-budgetarycontr\n      path: /fscmRestApi/resources/11.13.18.05/budgetaryControlBudgetTransactions\n      operations:\n      - name: createbudgettransaction\n        method: POST\n  \
  \      description: Oracle Financials Create a budget transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-financials-rest\n    description: REST adapter for Oracle Financials General Ledger API.\n    resources:\n    - path: /fscmRestApi/resources/11.13.18.05/journalBatches\n      name: listjournalbatches\n      operations:\n      - method: GET\n        name: listjournalbatches\n        description: Oracle Financials List journal batches\n        call: oracle-financials.listjournalbatches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}\n      name: getjournalbatch\n      operations:\n      - method: GET\n        name: getjournalbatch\n        description: Oracle Financials Get a journal batch\n        call: oracle-financials.getjournalbatch\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}\n      name: updatejournalbatch\n      operations:\n      - method: PATCH\n        name: updatejournalbatch\n        description: Oracle Financials Update a journal batch\n        call: oracle-financials.updatejournalbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/journalBatches/{JeBatchId}\n      name: deletejournalbatch\n      operations:\n      - method: DELETE\n        name: deletejournalbatch\n        description: Oracle Financials Delete a journal batch\n        call: oracle-financials.deletejournalbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/ledgerBalances\n      name: listledgerbalances\n      operations:\n      - method: GET\n        name: listledgerbalances\n        description:\
  \ Oracle Financials List account balances\n        call: oracle-financials.listledgerbalances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/currencyRates\n      name: listcurrencyrates\n      operations:\n      - method: GET\n        name: listcurrencyrates\n        description: Oracle Financials List currency rates\n        call: oracle-financials.listcurrencyrates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/chartOfAccountsFilters\n      name: createchartofaccountsfilter\n      operations:\n      - method: POST\n        name: createchartofaccountsfilter\n        description: Oracle Financials Create a chart of accounts filter\n        call: oracle-financials.createchartofaccountsfilter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/budgetaryControlResults\n  \
  \    name: listbudgetarycontrolresults\n      operations:\n      - method: GET\n        name: listbudgetarycontrolresults\n        description: Oracle Financials List budgetary control results\n        call: oracle-financials.listbudgetarycontrolresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/budgetaryControlBudgetTransactions\n      name: createbudgettransaction\n      operations:\n      - method: POST\n        name: createbudgettransaction\n        description: Oracle Financials Create a budget transaction\n        call: oracle-financials.createbudgettransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-financials-mcp\n    transport: http\n    description: MCP adapter for Oracle Financials General Ledger API for AI agent use.\n    tools:\n    - name: listjournalbatches\n      description: Oracle Financials List journal\
  \ batches\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-financials.listjournalbatches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjournalbatch\n      description: Oracle Financials Get a journal batch\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-financials.getjournalbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatejournalbatch\n      description: Oracle Financials Update a journal batch\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-financials.updatejournalbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejournalbatch\n      description: Oracle Financials Delete a journal batch\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n\
  \      call: oracle-financials.deletejournalbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listledgerbalances\n      description: Oracle Financials List account balances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-financials.listledgerbalances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcurrencyrates\n      description: Oracle Financials List currency rates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-financials.listcurrencyrates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchartofaccountsfilter\n      description: Oracle Financials Create a chart of accounts filter\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-financials.createchartofaccountsfilter\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listbudgetarycontrolresults\n      description: Oracle Financials List budgetary control results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-financials.listbudgetarycontrolresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbudgettransaction\n      description: Oracle Financials Create a budget transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-financials.createbudgettransaction\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORACLE_FINANCIALS_TOKEN: ORACLE_FINANCIALS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-financials/refs/heads/main/capabilities/oracle-financials-capability.yaml
tags:
- Oracle
- Financials
- API
tools:
- description: Oracle Financials List journal batches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjournalbatches
- description: Oracle Financials Get a journal batch
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjournalbatch
- description: Oracle Financials Update a journal batch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejournalbatch
- description: Oracle Financials Delete a journal batch
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejournalbatch
- description: Oracle Financials List account balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listledgerbalances
- description: Oracle Financials List currency rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcurrencyrates
- description: Oracle Financials Create a chart of accounts filter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchartofaccountsfilter
- description: Oracle Financials List budgetary control results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbudgetarycontrolresults
- description: Oracle Financials Create a budget transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbudgettransaction
---
