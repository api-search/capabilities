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
- query data cloud
- portfolio holdings and positions
- list accessible aladdin portfolios
- portfolio management
- risk professional analyzing factor exposures, var, and stress test results for institutional portfolios using aladdin's risk engine.
- list datasets
- portfolio management and discovery
- get portfolio risk
- portfolio metadata, positions, and performance tracking
- investment management
- security reference data
- quant researcher building and backtesting models using aladdin data cloud for large-scale portfolio analytics.
- portfolio analytics
- get risk analytics for an aladdin portfolio including tracking error, var, beta, volatility, and factor exposures computed by aladdin's risk engine.
- list available datasets in the aladdin data cloud for analytics
- get details for a specific aladdin portfolio
- financial
- large-scale analytics on snowflake-based data warehouse
- list data cloud datasets
- get portfolio positions
- unified portfolio analytics combining graph api and data cloud for institutional portfolio managers and risk analysts
- get security
- institutional portfolio manager monitoring holdings, performance, and risk across aladdin-managed portfolios.
- data cloud
- list portfolios
- risk analytics, factor exposures, and stress testing
- get positions
- list aladdin portfolios accessible to the authenticated user
- Risk Analyst
- aladdin studio
- get current portfolio positions
- portfolio risk analytics
- order management and execution workflows
- execute sql query against the aladdin data cloud snowflake database for large-scale portfolio analytics and data science workflows.
- list available data cloud datasets
- investment research and analyst insights
- get security reference data from aladdin including classification attributes
- Portfolio Manager
- data cloud sql query execution
- blackrock
- execute sql query against data cloud
- get risk
- get portfolio
- risk analytics
- get portfolio risk analytics and factor exposures
- get security reference data
- Quantitative Researcher
- risk management
- asset management
- aladdin data cloud available datasets
- execute query
- get current positions and holdings for an aladdin portfolio including market values, quantities, and weights by security.
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
