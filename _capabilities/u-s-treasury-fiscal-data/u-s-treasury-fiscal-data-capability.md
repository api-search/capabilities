---
categories: []
consumed_apis: []
description: The U.S. Treasury Fiscal Data API provides free, open access to federal financial data including national debt, interest rates, exchange rates, and detailed fiscal operations data. No authentication or API key is required. The API uses RESTful principles, accepts GET requests, and returns JSON responses with standardized pagination, filtering, sorting, and field selection across 80+ endpoints covering all major Treasury financial reports.
layout: capability
name: Treasury Fiscal Data API
operations:
- description: Treasury Fiscal Data Get Debt to the Penny
  method: GET
  name: getdebttopenny
  path: /v2/accounting/od/debt_to_penny
- description: Treasury Fiscal Data Get Treasury Reporting Rates of Exchange
  method: GET
  name: getratesofexchange
  path: /v1/accounting/od/rates_of_exchange
- description: Treasury Fiscal Data Get Average Interest Rates on U.S. Treasury Securities
  method: GET
  name: getavginterestrates
  path: /v2/accounting/od/avg_interest_rates
- description: Treasury Fiscal Data Get Daily Treasury Statement
  method: GET
  name: getdailytreasurystatement
  path: /v1/accounting/dts/dts_table_1
- description: Treasury Fiscal Data Get Monthly Treasury Statement Receipts and Outlays
  method: GET
  name: getmonthlytreasurystatement
  path: /v2/accounting/mts/mts_table_4
- description: Treasury Fiscal Data Get Savings Bond Redemption Tables
  method: GET
  name: getsavingsbondredemptiontables
  path: /v1/accounting/od/redemption_tables
- description: Treasury Fiscal Data Get Interest Expense on the Debt Outstanding
  method: GET
  name: getinterestexpensedebt
  path: /v2/accounting/od/interest_expense
- description: Treasury Fiscal Data Get Monthly Statement of the Public Debt
  method: GET
  name: getpublicdebtbysecuritytype
  path: /v1/accounting/od/mspd_table_1
- description: Treasury Fiscal Data Get Gift Contributions to Reduce the Public Debt
  method: GET
  name: getgiftcontributionsdebt
  path: /v1/accounting/od/gift_contributions
personas: []
provider_name: U.S. Treasury Fiscal Data
provider_slug: u-s-treasury-fiscal-data
search_terms:
- getpublicdebtbysecuritytype
- economics
- federal or state budget analyst using treasury data for fiscal planning, appropriations analysis, and government financial reporting.
- getavginterestrates
- academic or government economist analyzing federal fiscal trends, national debt trajectories, and interest rate impacts on the economy.
- getdebttopenny
- treasury fiscal data get monthly treasury statement receipts and outlays
- national debt
- getgiftcontributionsdebt
- interest rates and outstanding amounts for u.s. treasury bills, notes, bonds, and other securities
- treasury fiscal data get daily treasury statement
- official treasury foreign currency exchange rates for federal reporting purposes
- reporter or journalist tracking daily debt figures, exchange rates, and treasury financial statements for news coverage and data stories.
- finance
- government or think-tank analyst using treasury fiscal data to assess budget policy proposals, deficit projections, and debt sustainability.
- treasury fiscal data get average interest rates on u.s. treasury securities
- exchange rates
- treasury fiscal data get savings bond redemption tables
- fiscal
- treasury fiscal data get gift contributions to reduce the public debt
- Policy Analyst
- treasury
- Budget Analyst
- federal government receipts, outlays, surplus/deficit from the monthly treasury statement
- treasury fiscal data get interest expense on the debt outstanding
- academic or policy researcher using treasury fiscal data for economic research, historical analysis, and quantitative studies.
- api
- Financial Journalist
- total u.s. public debt outstanding including debt held by public and intragovernmental holdings
- getsavingsbondredemptiontables
- Economist
- data
- federal government
- Researcher
- treasury fiscal data get treasury reporting rates of exchange
- getratesofexchange
- treasury fiscal data get debt to the penny
- getdailytreasurystatement
- getmonthlytreasurystatement
- unified workflow for economists, policy analysts, financial journalists, and researchers to access u.s. treasury federal financial data for analysis and reporting.
- treasury fiscal data get monthly statement of the public debt
- getinterestexpensedebt
slug: u-s-treasury-fiscal-data-capability
source_filename: u-s-treasury-fiscal-data-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Treasury Fiscal Data API\n  description: The U.S. Treasury Fiscal Data API provides free, open access to federal financial data including national debt,\n    interest rates, exchange rates, and detailed fiscal operations data. No authentication or API key is required. The API\n    uses RESTful principles, accepts GET requests, and returns JSON responses with standardized pagination, filtering, sorting,\n    and field selection across 80+ endpoints covering all major Treasury financial reports.\n  tags:\n  - U\n  - S\n  - Treasury\n  - Fiscal\n  - Data\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: u-s-treasury-fiscal-data\n    baseUri: https://api.fiscaldata.treasury.gov/services/api/fiscal_service\n    description: Treasury Fiscal Data API HTTP API.\n    resources:\n    - name: v2-accounting-od-debt-to-penny\n      path: /v2/accounting/od/debt_to_penny\n      operations:\n\
  \      - name: getdebttopenny\n        method: GET\n        description: Treasury Fiscal Data Get Debt to the Penny\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-accounting-od-rates-of-exchange\n      path: /v1/accounting/od/rates_of_exchange\n      operations:\n      - name: getratesofexchange\n        method: GET\n        description: Treasury Fiscal Data Get Treasury Reporting Rates of Exchange\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-accounting-od-avg-interest-rates\n      path: /v2/accounting/od/avg_interest_rates\n      operations:\n      - name: getavginterestrates\n        method: GET\n        description: Treasury Fiscal Data Get Average Interest Rates on U.S. Treasury Securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: v1-accounting-dts-dts-table-1\n      path: /v1/accounting/dts/dts_table_1\n      operations:\n      - name: getdailytreasurystatement\n        method: GET\n        description: Treasury Fiscal Data Get Daily Treasury Statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-accounting-mts-mts-table-4\n      path: /v2/accounting/mts/mts_table_4\n      operations:\n      - name: getmonthlytreasurystatement\n        method: GET\n        description: Treasury Fiscal Data Get Monthly Treasury Statement Receipts and Outlays\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-accounting-od-redemption-tables\n      path: /v1/accounting/od/redemption_tables\n      operations:\n      - name: getsavingsbondredemptiontables\n        method: GET\n        description: Treasury Fiscal\
  \ Data Get Savings Bond Redemption Tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-accounting-od-interest-expense\n      path: /v2/accounting/od/interest_expense\n      operations:\n      - name: getinterestexpensedebt\n        method: GET\n        description: Treasury Fiscal Data Get Interest Expense on the Debt Outstanding\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-accounting-od-mspd-table-1\n      path: /v1/accounting/od/mspd_table_1\n      operations:\n      - name: getpublicdebtbysecuritytype\n        method: GET\n        description: Treasury Fiscal Data Get Monthly Statement of the Public Debt\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-accounting-od-gift-contributions\n      path:\
  \ /v1/accounting/od/gift_contributions\n      operations:\n      - name: getgiftcontributionsdebt\n        method: GET\n        description: Treasury Fiscal Data Get Gift Contributions to Reduce the Public Debt\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: u-s-treasury-fiscal-data-rest\n    description: REST adapter for Treasury Fiscal Data API.\n    resources:\n    - path: /v2/accounting/od/debt_to_penny\n      name: getdebttopenny\n      operations:\n      - method: GET\n        name: getdebttopenny\n        description: Treasury Fiscal Data Get Debt to the Penny\n        call: u-s-treasury-fiscal-data.getdebttopenny\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/od/rates_of_exchange\n      name: getratesofexchange\n      operations:\n      - method: GET\n        name: getratesofexchange\n \
  \       description: Treasury Fiscal Data Get Treasury Reporting Rates of Exchange\n        call: u-s-treasury-fiscal-data.getratesofexchange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/accounting/od/avg_interest_rates\n      name: getavginterestrates\n      operations:\n      - method: GET\n        name: getavginterestrates\n        description: Treasury Fiscal Data Get Average Interest Rates on U.S. Treasury Securities\n        call: u-s-treasury-fiscal-data.getavginterestrates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/dts/dts_table_1\n      name: getdailytreasurystatement\n      operations:\n      - method: GET\n        name: getdailytreasurystatement\n        description: Treasury Fiscal Data Get Daily Treasury Statement\n        call: u-s-treasury-fiscal-data.getdailytreasurystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/accounting/mts/mts_table_4\n\
  \      name: getmonthlytreasurystatement\n      operations:\n      - method: GET\n        name: getmonthlytreasurystatement\n        description: Treasury Fiscal Data Get Monthly Treasury Statement Receipts and Outlays\n        call: u-s-treasury-fiscal-data.getmonthlytreasurystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/od/redemption_tables\n      name: getsavingsbondredemptiontables\n      operations:\n      - method: GET\n        name: getsavingsbondredemptiontables\n        description: Treasury Fiscal Data Get Savings Bond Redemption Tables\n        call: u-s-treasury-fiscal-data.getsavingsbondredemptiontables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/accounting/od/interest_expense\n      name: getinterestexpensedebt\n      operations:\n      - method: GET\n        name: getinterestexpensedebt\n        description: Treasury Fiscal Data Get Interest Expense on the Debt\
  \ Outstanding\n        call: u-s-treasury-fiscal-data.getinterestexpensedebt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/od/mspd_table_1\n      name: getpublicdebtbysecuritytype\n      operations:\n      - method: GET\n        name: getpublicdebtbysecuritytype\n        description: Treasury Fiscal Data Get Monthly Statement of the Public Debt\n        call: u-s-treasury-fiscal-data.getpublicdebtbysecuritytype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/od/gift_contributions\n      name: getgiftcontributionsdebt\n      operations:\n      - method: GET\n        name: getgiftcontributionsdebt\n        description: Treasury Fiscal Data Get Gift Contributions to Reduce the Public Debt\n        call: u-s-treasury-fiscal-data.getgiftcontributionsdebt\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: u-s-treasury-fiscal-data-mcp\n\
  \    transport: http\n    description: MCP adapter for Treasury Fiscal Data API for AI agent use.\n    tools:\n    - name: getdebttopenny\n      description: Treasury Fiscal Data Get Debt to the Penny\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getdebttopenny\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getratesofexchange\n      description: Treasury Fiscal Data Get Treasury Reporting Rates of Exchange\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getratesofexchange\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getavginterestrates\n      description: Treasury Fiscal Data Get Average Interest Rates on U.S. Treasury Securities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getavginterestrates\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdailytreasurystatement\n      description: Treasury Fiscal Data Get Daily Treasury Statement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getdailytreasurystatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmonthlytreasurystatement\n      description: Treasury Fiscal Data Get Monthly Treasury Statement Receipts and Outlays\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getmonthlytreasurystatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsavingsbondredemptiontables\n      description: Treasury Fiscal Data Get Savings Bond Redemption Tables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getsavingsbondredemptiontables\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinterestexpensedebt\n      description: Treasury Fiscal Data Get Interest Expense on the Debt Outstanding\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getinterestexpensedebt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpublicdebtbysecuritytype\n      description: Treasury Fiscal Data Get Monthly Statement of the Public Debt\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getpublicdebtbysecuritytype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgiftcontributionsdebt\n      description: Treasury Fiscal Data Get Gift Contributions to Reduce the Public Debt\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: u-s-treasury-fiscal-data.getgiftcontributionsdebt\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/u-s-treasury-fiscal-data/refs/heads/main/capabilities/u-s-treasury-fiscal-data-capability.yaml
tags:
- U
- S
- Treasury
- Fiscal
- Data
- API
tools:
- description: Treasury Fiscal Data Get Debt to the Penny
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdebttopenny
- description: Treasury Fiscal Data Get Treasury Reporting Rates of Exchange
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getratesofexchange
- description: Treasury Fiscal Data Get Average Interest Rates on U.S. Treasury Securities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getavginterestrates
- description: Treasury Fiscal Data Get Daily Treasury Statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdailytreasurystatement
- description: Treasury Fiscal Data Get Monthly Treasury Statement Receipts and Outlays
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmonthlytreasurystatement
- description: Treasury Fiscal Data Get Savings Bond Redemption Tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsavingsbondredemptiontables
- description: Treasury Fiscal Data Get Interest Expense on the Debt Outstanding
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinterestexpensedebt
- description: Treasury Fiscal Data Get Monthly Statement of the Public Debt
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpublicdebtbysecuritytype
- description: Treasury Fiscal Data Get Gift Contributions to Reduce the Public Debt
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgiftcontributionsdebt
---
