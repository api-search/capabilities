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
- portfolio management and discovery
- list available datasets in the aladdin data cloud for analytics
- get security reference data
- get security reference data from aladdin including classification attributes
- Risk Analyst
- quant researcher building and backtesting models using aladdin data cloud for large-scale portfolio analytics.
- execute sql query against the aladdin data cloud snowflake database for large-scale portfolio analytics and data science workflows.
- risk professional analyzing factor exposures, var, and stress test results for institutional portfolios using aladdin's risk engine.
- Quantitative Researcher
- get portfolio
- portfolio risk analytics
- data cloud sql query execution
- investment management
- get security
- get portfolio risk analytics and factor exposures
- institutional portfolio manager monitoring holdings, performance, and risk across aladdin-managed portfolios.
- list accessible aladdin portfolios
- Portfolio Manager
- get portfolio positions
- get current positions and holdings for an aladdin portfolio including market values, quantities, and weights by security.
- execute query
- portfolio analytics
- get risk
- unified portfolio analytics combining graph api and data cloud for institutional portfolio managers and risk analysts
- query data cloud
- portfolio management
- blackrock
- asset management
- get risk analytics for an aladdin portfolio including tracking error, var, beta, volatility, and factor exposures computed by aladdin's risk engine.
- risk analytics, factor exposures, and stress testing
- large-scale analytics on snowflake-based data warehouse
- list datasets
- list data cloud datasets
- financial
- data cloud
- portfolio holdings and positions
- aladdin studio
- get details for a specific aladdin portfolio
- list available data cloud datasets
- investment research and analyst insights
- security reference data
- aladdin data cloud available datasets
- execute sql query against data cloud
- get portfolio risk
- risk analytics
- list aladdin portfolios accessible to the authenticated user
- order management and execution workflows
- get current portfolio positions
- risk management
- portfolio metadata, positions, and performance tracking
- list portfolios
- get positions
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
