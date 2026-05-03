---
api_specs:
- filename: treasury-fiscal-data-api-openapi.yaml
  format: yaml
  label: treasury-fiscal
  slug: treasury-fiscal
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/u-s-treasury-fiscal-data/refs/heads/main/openapi/treasury-fiscal-data-api-openapi.yaml
categories: []
consumed_apis:
- treasury-fiscal
description: Workflow capability for economists, policy analysts, financial journalists, and researchers to access U.S. Treasury federal financial data including national debt trends, exchange rates, interest rates, and Treasury financial statement data. Provides AI-assisted access to the Treasury Fiscal Data API for data analysis and visualization workflows.
layout: capability
name: Treasury Fiscal Data Intelligence
operations:
- description: Retrieve current and historical U.S. public debt outstanding.
  method: GET
  name: get-national-debt
  path: /v1/debt
- description: Retrieve official Treasury reporting rates of exchange by country and quarter.
  method: GET
  name: get-exchange-rates
  path: /v1/exchange-rates
- description: Retrieve monthly average interest rates for Treasury securities by type.
  method: GET
  name: get-interest-rates
  path: /v1/interest-rates
- description: Retrieve DTS data showing daily Treasury account activity.
  method: GET
  name: get-daily-treasury
  path: /v1/daily-treasury
- description: Retrieve MTS data showing monthly federal budget activity.
  method: GET
  name: get-monthly-treasury
  path: /v1/monthly-treasury
personas: []
provider_name: U.S. Treasury Fiscal Data
provider_slug: u-s-treasury-fiscal-data
search_terms:
- Researcher
- Financial Journalist
- retrieve mts data showing monthly federal budget activity.
- unified workflow for economists, policy analysts, financial journalists, and researchers to access u.s. treasury federal financial data for analysis and reporting.
- get treasury interest rates
- national debt
- academic or government economist analyzing federal fiscal trends, national debt trajectories, and interest rate impacts on the economy.
- retrieve official u.s. treasury foreign currency exchange rates used for federal reporting purposes. data updated quarterly. filter by country name or currency using the filter parameter (e.g., 'country:eq:japan'). covers approximately 170 countries.
- government or think-tank analyst using treasury fiscal data to assess budget policy proposals, deficit projections, and debt sustainability.
- federal government
- average interest rates on u.s. treasury securities.
- get national debt
- retrieve monthly average interest rates for treasury securities by type.
- monthly treasury statement budget receipts and outlays.
- retrieve monthly average interest rates for u.s. treasury securities by security type (bills, notes, bonds, tips, etc.). useful for tracking borrowing costs and monetary policy analysis. filter by security_desc to get rates for a specific security type.
- retrieve daily treasury statement (dts) data showing federal government cash flows including deposits, withdrawals, and account balances. the dts is published each business day by the bureau of the fiscal service. use filter to query by date or account type.
- get monthly treasury
- get monthly treasury statement
- federal government receipts, outlays, surplus/deficit from the monthly treasury statement
- treasury foreign currency exchange rates.
- interest rates and outstanding amounts for u.s. treasury bills, notes, bonds, and other securities
- government data
- Economist
- daily treasury statement account balances and transactions.
- total u.s. public debt outstanding including debt held by public and intragovernmental holdings
- exchange rates
- economics
- retrieve official treasury reporting rates of exchange by country and quarter.
- finance
- federal finance
- get interest rates
- Policy Analyst
- get daily treasury
- retrieve current and historical u.s. public debt outstanding.
- academic or policy researcher using treasury fiscal data for economic research, historical analysis, and quantitative studies.
- retrieve dts data showing daily treasury account activity.
- treasury
- reporter or journalist tracking daily debt figures, exchange rates, and treasury financial statements for news coverage and data stories.
- u.s. national debt data from the debt to the penny dataset.
- retrieve monthly treasury statement (mts) data with consolidated federal budget receipts, outlays, and surplus/deficit by classification. published monthly by the bureau of the fiscal service. essential for budget analysis and deficit tracking.
- get daily treasury statement
- federal or state budget analyst using treasury data for fiscal planning, appropriations analysis, and government financial reporting.
- get exchange rates
- retrieve current and historical u.s. national debt data from the treasury debt to the penny dataset. returns total public debt outstanding, debt held by the public, and intragovernmental holdings. data updated daily. use filter parameter like 'record_date:gte:2024-01-01' to limit results by date.
- official treasury foreign currency exchange rates for federal reporting purposes
- Budget Analyst
slug: fiscal-data-intelligence
source_filename: fiscal-data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Treasury Fiscal Data Intelligence\"\n  description: >-\n    Workflow capability for economists, policy analysts, financial journalists,\n    and researchers to access U.S. Treasury federal financial data including\n    national debt trends, exchange rates, interest rates, and Treasury\n    financial statement data. Provides AI-assisted access to the Treasury\n    Fiscal Data API for data analysis and visualization workflows.\n  tags:\n    - Treasury\n    - Federal Finance\n    - National Debt\n    - Exchange Rates\n    - Government Data\n    - Economics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: treasury-fiscal\n      location: ./shared/treasury-fiscal-data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: fiscal-intelligence-api\n      description: \"Unified REST API for Treasury fiscal data intelligence.\"\n      resources:\n        - path: /v1/debt\n\
  \          name: national-debt\n          description: \"U.S. national debt data from the Debt to the Penny dataset.\"\n          operations:\n            - method: GET\n              name: get-national-debt\n              description: \"Retrieve current and historical U.S. public debt outstanding.\"\n              call: \"treasury-fiscal.get-debt-to-penny\"\n              with:\n                fields: \"rest.fields\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n                page[number]: \"rest.page_number\"\n                page[size]: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/exchange-rates\n          name: exchange-rates\n          description: \"Treasury foreign currency exchange rates.\"\n          operations:\n            - method: GET\n              name: get-exchange-rates\n              description: \"Retrieve official Treasury reporting rates\
  \ of exchange by country and quarter.\"\n              call: \"treasury-fiscal.get-exchange-rates\"\n              with:\n                fields: \"rest.fields\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n                page[number]: \"rest.page_number\"\n                page[size]: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/interest-rates\n          name: interest-rates\n          description: \"Average interest rates on U.S. Treasury securities.\"\n          operations:\n            - method: GET\n              name: get-interest-rates\n              description: \"Retrieve monthly average interest rates for Treasury securities by type.\"\n              call: \"treasury-fiscal.get-avg-interest-rates\"\n              with:\n                fields: \"rest.fields\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n         \
  \       page[number]: \"rest.page_number\"\n                page[size]: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/daily-treasury\n          name: daily-treasury-statement\n          description: \"Daily Treasury Statement account balances and transactions.\"\n          operations:\n            - method: GET\n              name: get-daily-treasury\n              description: \"Retrieve DTS data showing daily Treasury account activity.\"\n              call: \"treasury-fiscal.get-daily-treasury-statement\"\n              with:\n                fields: \"rest.fields\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n                page[number]: \"rest.page_number\"\n                page[size]: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monthly-treasury\n        \
  \  name: monthly-treasury-statement\n          description: \"Monthly Treasury Statement budget receipts and outlays.\"\n          operations:\n            - method: GET\n              name: get-monthly-treasury\n              description: \"Retrieve MTS data showing monthly federal budget activity.\"\n              call: \"treasury-fiscal.get-monthly-treasury-statement\"\n              with:\n                fields: \"rest.fields\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n                page[number]: \"rest.page_number\"\n                page[size]: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: fiscal-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted federal fiscal data analysis using the Treasury Fiscal Data API.\"\n      tools:\n        - name: get-national-debt\n          description:\
  \ >-\n            Retrieve current and historical U.S. national debt data from the\n            Treasury Debt to the Penny dataset. Returns total public debt\n            outstanding, debt held by the public, and intragovernmental\n            holdings. Data updated daily. Use filter parameter like\n            'record_date:gte:2024-01-01' to limit results by date.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"treasury-fiscal.get-debt-to-penny\"\n          with:\n            fields: \"tools.fields\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            page[number]: \"tools.page_number\"\n            page[size]: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-exchange-rates\n          description: >-\n            Retrieve official U.S. Treasury foreign currency exchange rates\n            used for federal reporting purposes. Data\
  \ updated quarterly.\n            Filter by country name or currency using the filter parameter\n            (e.g., 'country:eq:Japan'). Covers approximately 170 countries.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"treasury-fiscal.get-exchange-rates\"\n          with:\n            fields: \"tools.fields\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            page[number]: \"tools.page_number\"\n            page[size]: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-treasury-interest-rates\n          description: >-\n            Retrieve monthly average interest rates for U.S. Treasury\n            securities by security type (Bills, Notes, Bonds, TIPS, etc.).\n            Useful for tracking borrowing costs and monetary policy analysis.\n            Filter by security_desc to get rates for a specific security type.\n     \
  \     hints:\n            readOnly: true\n            openWorld: true\n          call: \"treasury-fiscal.get-avg-interest-rates\"\n          with:\n            fields: \"tools.fields\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            page[number]: \"tools.page_number\"\n            page[size]: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-daily-treasury-statement\n          description: >-\n            Retrieve Daily Treasury Statement (DTS) data showing federal\n            government cash flows including deposits, withdrawals, and account\n            balances. The DTS is published each business day by the Bureau\n            of the Fiscal Service. Use filter to query by date or account type.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"treasury-fiscal.get-daily-treasury-statement\"\n          with:\n            fields:\
  \ \"tools.fields\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            page[number]: \"tools.page_number\"\n            page[size]: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-monthly-treasury-statement\n          description: >-\n            Retrieve Monthly Treasury Statement (MTS) data with consolidated\n            federal budget receipts, outlays, and surplus/deficit by\n            classification. Published monthly by the Bureau of the Fiscal\n            Service. Essential for budget analysis and deficit tracking.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"treasury-fiscal.get-monthly-treasury-statement\"\n          with:\n            fields: \"tools.fields\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            page[number]: \"tools.page_number\"\n            page[size]: \"tools.page_size\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/u-s-treasury-fiscal-data/refs/heads/main/capabilities/fiscal-data-intelligence.yaml
tags:
- Treasury
- Federal Finance
- National Debt
- Exchange Rates
- Government Data
- Economics
tools:
- description: Retrieve current and historical U.S. national debt data from the Treasury Debt to the Penny dataset. Returns total public debt outstanding, debt held by the public, and intragovernmental holdings. Data updated daily. Use filter parameter like 'record_date:gte:2024-01-01' to limit results by date.
  hints:
    openWorld: true
    readOnly: true
  name: get-national-debt
- description: Retrieve official U.S. Treasury foreign currency exchange rates used for federal reporting purposes. Data updated quarterly. Filter by country name or currency using the filter parameter (e.g., 'country:eq:Japan'). Covers approximately 170 countries.
  hints:
    openWorld: true
    readOnly: true
  name: get-exchange-rates
- description: Retrieve monthly average interest rates for U.S. Treasury securities by security type (Bills, Notes, Bonds, TIPS, etc.). Useful for tracking borrowing costs and monetary policy analysis. Filter by security_desc to get rates for a specific security type.
  hints:
    openWorld: true
    readOnly: true
  name: get-treasury-interest-rates
- description: Retrieve Daily Treasury Statement (DTS) data showing federal government cash flows including deposits, withdrawals, and account balances. The DTS is published each business day by the Bureau of the Fiscal Service. Use filter to query by date or account type.
  hints:
    openWorld: true
    readOnly: true
  name: get-daily-treasury-statement
- description: Retrieve Monthly Treasury Statement (MTS) data with consolidated federal budget receipts, outlays, and surplus/deficit by classification. Published monthly by the Bureau of the Fiscal Service. Essential for budget analysis and deficit tracking.
  hints:
    openWorld: true
    readOnly: true
  name: get-monthly-treasury-statement
---
