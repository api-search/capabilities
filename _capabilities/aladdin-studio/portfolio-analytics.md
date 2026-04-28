---
categories: []
consumed_apis:
- aladdin-graph
- aladdin-data-cloud
description: Workflow capability combining the Aladdin Graph API and Data Cloud API for institutional portfolio analytics. Provides portfolio managers, risk analysts, and quantitative researchers with unified access to positions, risk metrics, factor exposures, and large-scale analytics data.
layout: capability
name: Aladdin Studio Portfolio Analytics
operations:
- description: List accessible Aladdin portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Get current portfolio positions
  method: GET
  name: get-positions
  path: /v1/portfolios/{portfolioId}/positions
- description: Get portfolio risk analytics and factor exposures
  method: GET
  name: get-risk
  path: /v1/portfolios/{portfolioId}/risk
- description: Get security reference data
  method: GET
  name: get-security
  path: /v1/securities/{securityId}
- description: List available Data Cloud datasets
  method: GET
  name: list-datasets
  path: /v1/data-cloud/datasets
- description: Execute SQL query against Data Cloud
  method: POST
  name: execute-query
  path: /v1/data-cloud/query
personas: []
provider_name: Aladdin Studio
provider_slug: aladdin-studio
search_terms:
- portfolio management
- get current positions and holdings for an aladdin portfolio including market values, quantities, and weights by security.
- portfolio metadata, positions, and performance tracking
- list accessible aladdin portfolios
- get portfolio risk
- risk management
- risk analytics
- aladdin data cloud available datasets
- investment research and analyst insights
- portfolio risk analytics
- quant researcher building and backtesting models using aladdin data cloud for large-scale portfolio analytics.
- get security reference data from aladdin including classification attributes
- execute sql query against the aladdin data cloud snowflake database for large-scale portfolio analytics and data science workflows.
- unified portfolio analytics combining graph api and data cloud for institutional portfolio managers and risk analysts
- risk professional analyzing factor exposures, var, and stress test results for institutional portfolios using aladdin's risk engine.
- large-scale analytics on snowflake-based data warehouse
- portfolio holdings and positions
- asset management
- financial
- get portfolio
- blackrock
- security reference data
- Portfolio Manager
- get details for a specific aladdin portfolio
- investment management
- get portfolio positions
- institutional portfolio manager monitoring holdings, performance, and risk across aladdin-managed portfolios.
- get risk analytics for an aladdin portfolio including tracking error, var, beta, volatility, and factor exposures computed by aladdin's risk engine.
- data cloud sql query execution
- execute query
- get security reference data
- list available data cloud datasets
- portfolio management and discovery
- order management and execution workflows
- portfolio analytics
- list aladdin portfolios accessible to the authenticated user
- risk analytics, factor exposures, and stress testing
- get current portfolio positions
- list datasets
- query data cloud
- list data cloud datasets
- list available datasets in the aladdin data cloud for analytics
- data cloud
- get risk
- list portfolios
- get positions
- get security
- Risk Analyst
- aladdin studio
- Quantitative Researcher
- get portfolio risk analytics and factor exposures
- execute sql query against data cloud
slug: portfolio-analytics
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Aladdin Studio Portfolio Analytics\n  description: >-\n    Workflow capability combining the Aladdin Graph API and Data Cloud API for\n    institutional portfolio analytics. Provides portfolio managers, risk\n    analysts, and quantitative researchers with unified access to positions,\n    risk metrics, factor exposures, and large-scale analytics data.\n  tags:\n    - Aladdin Studio\n    - Portfolio Management\n    - Risk Analytics\n    - Investment Management\n    - Financial\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALADDIN_API_TOKEN: ALADDIN_API_TOKEN\n      ALADDIN_ADC_TOKEN: ALADDIN_ADC_TOKEN\n\ncapability:\n  consumes:\n    - import: aladdin-graph\n      location: ./shared/graph-api.yaml\n    - import: aladdin-data-cloud\n      location: ./shared/data-cloud-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aladdin-portfolio-analytics-api\n\
  \      description: Unified REST API for Aladdin portfolio analytics workflows.\n      resources:\n        - path: /v1/portfolios\n          name: portfolios\n          description: Portfolio management and discovery\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: List accessible Aladdin portfolios\n              call: \"aladdin-graph.list-portfolios\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}/positions\n          name: positions\n          description: Portfolio holdings and positions\n          operations:\n            - method: GET\n              name: get-positions\n              description: Get current portfolio positions\n              call: \"aladdin-graph.get-positions\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                asOfDate: \"rest.asOfDate\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}/risk\n          name: risk\n          description: Portfolio risk analytics\n          operations:\n            - method: GET\n              name: get-risk\n              description: Get portfolio risk analytics and factor exposures\n              call: \"aladdin-graph.get-risk\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                asOfDate: \"rest.asOfDate\"\n                model: \"rest.model\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/securities/{securityId}\n          name: securities\n          description: Security reference data\n          operations:\n            - method: GET\n              name: get-security\n              description: Get security reference data\n              call: \"aladdin-graph.get-security\"\n              with:\n             \
  \   securityId: \"rest.securityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-cloud/datasets\n          name: datasets\n          description: Aladdin Data Cloud available datasets\n          operations:\n            - method: GET\n              name: list-datasets\n              description: List available Data Cloud datasets\n              call: \"aladdin-data-cloud.list-datasets\"\n              with:\n                connectionId: \"rest.connectionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-cloud/query\n          name: queries\n          description: Data Cloud SQL query execution\n          operations:\n            - method: POST\n              name: execute-query\n              description: Execute SQL query against Data Cloud\n              call: \"aladdin-data-cloud.execute-query\"\n              with:\n     \
  \           connectionId: \"rest.connectionId\"\n                sql: \"rest.sql\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: aladdin-portfolio-analytics-mcp\n      transport: http\n      description: MCP server for AI-assisted portfolio analytics with Aladdin Studio.\n      tools:\n        - name: list-portfolios\n          description: List Aladdin portfolios accessible to the authenticated user\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aladdin-graph.list-portfolios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio\n          description: Get details for a specific Aladdin portfolio\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aladdin-graph.get-portfolio\"\n          with:\n            portfolioId: \"tools.portfolioId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio-positions\n          description: >-\n            Get current positions and holdings for an Aladdin portfolio including\n            market values, quantities, and weights by security.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aladdin-graph.get-positions\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            asOfDate: \"tools.asOfDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio-risk\n          description: >-\n            Get risk analytics for an Aladdin portfolio including tracking error,\n            VaR, beta, volatility, and factor exposures computed by Aladdin's risk engine.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aladdin-graph.get-risk\"\n          with:\n\
  \            portfolioId: \"tools.portfolioId\"\n            asOfDate: \"tools.asOfDate\"\n            model: \"tools.model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-security\n          description: Get security reference data from Aladdin including classification attributes\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aladdin-graph.get-security\"\n          with:\n            securityId: \"tools.securityId\"\n            idType: \"tools.idType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-cloud-datasets\n          description: List available datasets in the Aladdin Data Cloud for analytics\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aladdin-data-cloud.list-datasets\"\n          with:\n            connectionId: \"tools.connectionId\"\n            schema:\
  \ \"tools.schema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-data-cloud\n          description: >-\n            Execute SQL query against the Aladdin Data Cloud Snowflake database\n            for large-scale portfolio analytics and data science workflows.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aladdin-data-cloud.execute-query\"\n          with:\n            connectionId: \"tools.connectionId\"\n            sql: \"tools.sql\"\n            warehouse: \"tools.warehouse\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aladdin-studio/refs/heads/main/capabilities/portfolio-analytics.yaml
tags:
- Aladdin Studio
- Portfolio Management
- Risk Analytics
- Investment Management
- Financial
tools:
- description: List Aladdin portfolios accessible to the authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolios
- description: Get details for a specific Aladdin portfolio
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio
- description: Get current positions and holdings for an Aladdin portfolio including market values, quantities, and weights by security.
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio-positions
- description: Get risk analytics for an Aladdin portfolio including tracking error, VaR, beta, volatility, and factor exposures computed by Aladdin's risk engine.
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio-risk
- description: Get security reference data from Aladdin including classification attributes
  hints:
    openWorld: false
    readOnly: true
  name: get-security
- description: List available datasets in the Aladdin Data Cloud for analytics
  hints:
    openWorld: false
    readOnly: true
  name: list-data-cloud-datasets
- description: Execute SQL query against the Aladdin Data Cloud Snowflake database for large-scale portfolio analytics and data science workflows.
  hints:
    openWorld: true
    readOnly: true
  name: query-data-cloud
---
