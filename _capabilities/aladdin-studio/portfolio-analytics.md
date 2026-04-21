---
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
- Quantitative Researcher
- get risk
- get portfolio risk
- list data cloud datasets
- execute sql query against the aladdin data cloud snowflake database for large-scale portfolio analytics and data science workflows.
- portfolio risk analytics
- institutional portfolio manager monitoring holdings, performance, and risk across aladdin-managed portfolios.
- get positions
- asset management
- unified portfolio analytics combining graph api and data cloud for institutional portfolio managers and risk analysts
- list portfolios
- risk management
- execute sql query against data cloud
- get security reference data
- get portfolio
- data cloud
- financial
- investment management
- get security reference data from aladdin including classification attributes
- list aladdin portfolios accessible to the authenticated user
- portfolio management
- get current portfolio positions
- get security
- quant researcher building and backtesting models using aladdin data cloud for large-scale portfolio analytics.
- get details for a specific aladdin portfolio
- get portfolio risk analytics and factor exposures
- portfolio analytics
- list available datasets in the aladdin data cloud for analytics
- get risk analytics for an aladdin portfolio including tracking error, var, beta, volatility, and factor exposures computed by aladdin's risk engine.
- list available data cloud datasets
- execute query
- investment research and analyst insights
- portfolio management and discovery
- list datasets
- aladdin data cloud available datasets
- get current positions and holdings for an aladdin portfolio including market values, quantities, and weights by security.
- Risk Analyst
- portfolio metadata, positions, and performance tracking
- get portfolio positions
- query data cloud
- data cloud sql query execution
- list accessible aladdin portfolios
- risk analytics, factor exposures, and stress testing
- large-scale analytics on snowflake-based data warehouse
- security reference data
- Portfolio Manager
- risk analytics
- portfolio holdings and positions
- blackrock
- risk professional analyzing factor exposures, var, and stress test results for institutional portfolios using aladdin's risk engine.
- order management and execution workflows
- aladdin studio
slug: portfolio-analytics
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
