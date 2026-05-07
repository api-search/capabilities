---
categories: []
consumed_apis: []
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
- get portfolio positions
- data cloud sql query execution
- portfolio management
- get current portfolio positions
- get risk analytics for an aladdin portfolio including tracking error, var, beta, volatility, and factor exposures computed by aladdin's risk engine.
- get current positions and holdings for an aladdin portfolio including market values, quantities, and weights by security.
- get details for a specific aladdin portfolio
- Quantitative Researcher
- list available data cloud datasets
- asset management
- query data cloud
- blackrock
- large-scale analytics on snowflake-based data warehouse
- portfolio analytics
- portfolio holdings and positions
- get security reference data
- list available datasets in the aladdin data cloud for analytics
- order management and execution workflows
- list portfolios
- unified portfolio analytics combining graph api and data cloud for institutional portfolio managers and risk analysts
- get security
- portfolio risk analytics
- get portfolio risk analytics and factor exposures
- Risk Analyst
- list accessible aladdin portfolios
- get portfolio
- institutional portfolio manager monitoring holdings, performance, and risk across aladdin-managed portfolios.
- aladdin data cloud available datasets
- execute sql query against the aladdin data cloud snowflake database for large-scale portfolio analytics and data science workflows.
- aladdin studio
- execute query
- get positions
- investment research and analyst insights
- security reference data
- risk professional analyzing factor exposures, var, and stress test results for institutional portfolios using aladdin's risk engine.
- risk management
- financial
- get risk
- get security reference data from aladdin including classification attributes
- quant researcher building and backtesting models using aladdin data cloud for large-scale portfolio analytics.
- risk analytics
- Portfolio Manager
- list datasets
- portfolio management and discovery
- risk analytics, factor exposures, and stress testing
- investment management
- portfolio metadata, positions, and performance tracking
- get portfolio risk
- list aladdin portfolios accessible to the authenticated user
- data cloud
- execute sql query against data cloud
- list data cloud datasets
slug: portfolio-analytics
source_filename: portfolio-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Aladdin Studio Portfolio Analytics\n  description: Workflow capability combining the Aladdin Graph API and Data Cloud API for institutional portfolio analytics.\n    Provides portfolio managers, risk analysts, and quantitative researchers with unified access to positions, risk metrics,\n    factor exposures, and large-scale analytics data.\n  tags:\n  - Aladdin Studio\n  - Portfolio Management\n  - Risk Analytics\n  - Investment Management\n  - Financial\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALADDIN_API_TOKEN: ALADDIN_API_TOKEN\n    ALADDIN_ADC_TOKEN: ALADDIN_ADC_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: aladdin-graph\n    baseUri: https://api.blackrock.com/v1\n    description: Aladdin Graph API for portfolio and risk data\n    authentication:\n      type: bearer\n      token: '{{env.ALADDIN_API_TOKEN}}'\n    resources:\n    - name: portfolios\n      path: /portfolios\n\
  \      description: Portfolio management operations\n      operations:\n      - name: list-portfolios\n        method: GET\n        description: List portfolios accessible to the authenticated user\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-portfolio\n        method: GET\n        description: Get portfolio details by ID\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: positions\n      path: /portfolios/{portfolioId}/positions\n      description: Portfolio position data\n      operations:\n      - name: get-positions\n        method: GET\n        description: Get current positions for a portfolio\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: asOfDate\n          in: query\n          type: string\n          required: false\n          description: Position date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: risk\n      path: /portfolios/{portfolioId}/risk\n      description: Portfolio risk analytics\n      operations:\n      - name: get-risk\n        method: GET\n        description: Get risk analytics for a portfolio\n        inputParameters:\n        - name: portfolioId\n   \
  \       in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: asOfDate\n          in: query\n          type: string\n          required: false\n          description: Risk calculation date\n        - name: model\n          in: query\n          type: string\n          required: false\n          description: Risk model identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: securities\n      path: /securities/{securityId}\n      description: Security reference data\n      operations:\n      - name: get-security\n        method: GET\n        description: Get security reference data\n        inputParameters:\n        - name: securityId\n          in: path\n          type: string\n          required: true\n          description: Security identifier\n        - name: idType\n          in: query\n          type: string\n          required:\
  \ false\n          description: Identifier type (ISIN, CUSIP, etc.)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: aladdin-data-cloud\n    baseUri: https://api.blackrock.com/adc/v1\n    description: Aladdin Data Cloud API for Snowflake-based analytics\n    authentication:\n      type: bearer\n      token: '{{env.ALADDIN_ADC_TOKEN}}'\n    resources:\n    - name: connections\n      path: /connections\n      description: Data Cloud connection management\n      operations:\n      - name: list-connections\n        method: GET\n        description: List available Data Cloud connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries\n      path: /connections/{connectionId}/query\n      description: SQL query execution\n      operations:\n      - name: execute-query\n        method: POST\n\
  \        description: Execute SQL query against Data Cloud\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sql: '{{tools.sql}}'\n            warehouse: '{{tools.warehouse}}'\n    - name: datasets\n      path: /connections/{connectionId}/datasets\n      description: Available datasets discovery\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List available datasets in the Data Cloud\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection identifier\n        - name: schema\n          in: query\n          type: string\n          required:\
  \ false\n          description: Snowflake schema filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aladdin-portfolio-analytics-api\n    description: Unified REST API for Aladdin portfolio analytics workflows.\n    resources:\n    - path: /v1/portfolios\n      name: portfolios\n      description: Portfolio management and discovery\n      operations:\n      - method: GET\n        name: list-portfolios\n        description: List accessible Aladdin portfolios\n        call: aladdin-graph.list-portfolios\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/positions\n      name: positions\n      description: Portfolio holdings and positions\n      operations:\n      - method: GET\n        name: get-positions\n        description: Get current portfolio positions\n        call: aladdin-graph.get-positions\n\
  \        with:\n          portfolioId: rest.portfolioId\n          asOfDate: rest.asOfDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/risk\n      name: risk\n      description: Portfolio risk analytics\n      operations:\n      - method: GET\n        name: get-risk\n        description: Get portfolio risk analytics and factor exposures\n        call: aladdin-graph.get-risk\n        with:\n          portfolioId: rest.portfolioId\n          asOfDate: rest.asOfDate\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/securities/{securityId}\n      name: securities\n      description: Security reference data\n      operations:\n      - method: GET\n        name: get-security\n        description: Get security reference data\n        call: aladdin-graph.get-security\n        with:\n          securityId: rest.securityId\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /v1/data-cloud/datasets\n      name: datasets\n      description: Aladdin Data Cloud available datasets\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List available Data Cloud datasets\n        call: aladdin-data-cloud.list-datasets\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-cloud/query\n      name: queries\n      description: Data Cloud SQL query execution\n      operations:\n      - method: POST\n        name: execute-query\n        description: Execute SQL query against Data Cloud\n        call: aladdin-data-cloud.execute-query\n        with:\n          connectionId: rest.connectionId\n          sql: rest.sql\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aladdin-portfolio-analytics-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted portfolio analytics with Aladdin Studio.\n    tools:\n    - name: list-portfolios\n      description: List Aladdin portfolios accessible to the authenticated user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aladdin-graph.list-portfolios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio\n      description: Get details for a specific Aladdin portfolio\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aladdin-graph.get-portfolio\n      with:\n        portfolioId: tools.portfolioId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio-positions\n      description: Get current positions and holdings for an Aladdin portfolio including market values, quantities, and weights\n        by security.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aladdin-graph.get-positions\n\
  \      with:\n        portfolioId: tools.portfolioId\n        asOfDate: tools.asOfDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio-risk\n      description: Get risk analytics for an Aladdin portfolio including tracking error, VaR, beta, volatility, and factor\n        exposures computed by Aladdin's risk engine.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aladdin-graph.get-risk\n      with:\n        portfolioId: tools.portfolioId\n        asOfDate: tools.asOfDate\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-security\n      description: Get security reference data from Aladdin including classification attributes\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aladdin-graph.get-security\n      with:\n        securityId: tools.securityId\n        idType: tools.idType\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-data-cloud-datasets\n      description: List available datasets in the Aladdin Data Cloud for analytics\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aladdin-data-cloud.list-datasets\n      with:\n        connectionId: tools.connectionId\n        schema: tools.schema\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-data-cloud\n      description: Execute SQL query against the Aladdin Data Cloud Snowflake database for large-scale portfolio analytics\n        and data science workflows.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aladdin-data-cloud.execute-query\n      with:\n        connectionId: tools.connectionId\n        sql: tools.sql\n        warehouse: tools.warehouse\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
