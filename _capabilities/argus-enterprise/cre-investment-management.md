---
consumed_apis:
- argusenterprise
description: Unified capability for commercial real estate investment management using ARGUS Enterprise. Combines property valuation, cash flow modeling, lease management, portfolio analytics, and reporting for Asset Managers and Portfolio Managers.
layout: capability
name: ARGUS Enterprise CRE Investment Management
operations:
- description: List all commercial properties
  method: GET
  name: list-properties
  path: /v1/properties
- description: Get property details and current metrics
  method: GET
  name: get-property
  path: /v1/properties
- description: List all real estate portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: List property valuations
  method: GET
  name: list-valuations
  path: /v1/valuations
- description: List all leases
  method: GET
  name: list-leases
  path: /v1/leases
- description: Get property cash flow projections
  method: GET
  name: get-cashflows
  path: /v1/properties/{id}/cashflows
personas: []
provider_name: ARGUS Enterprise
provider_slug: argus-enterprise
search_terms:
- list current and historical property valuations
- property valuation and appraisal
- commercial property investment and management
- altus group
- list all commercial properties
- Portfolio Manager
- get property cashflows
- Asset Manager
- commercial property management
- list all real estate portfolios
- list properties
- investment management
- get cash flow projections for a commercial property
- get cashflows
- list all leases
- commercial real estate
- cash flow projections
- list commercial real estate properties with current status and metrics
- valuation
- manages individual commercial real estate assets
- list real estate portfolios with aggregate performance metrics
- multi-asset portfolio analytics and reporting
- cash flow modeling
- argus enterprise
- get property details and current metrics
- get property cash flow projections
- oversees a portfolio of commercial real estate assets
- list portfolios
- asset management
- get property
- property valuations
- list property valuations
- list leases
- portfolio management
- list valuations
- lease management
- get detailed information about a commercial property including valuation and occupancy
- complete commercial real estate investment management workflow
- list lease records with tenant and expiry information
slug: cre-investment-management
tags:
- ARGUS Enterprise
- Commercial Real Estate
- Investment Management
- Portfolio Management
- Valuation
tools:
- description: List commercial real estate properties with current status and metrics
  hints:
    openWorld: true
    readOnly: true
  name: list-properties
- description: Get detailed information about a commercial property including valuation and occupancy
  hints:
    readOnly: true
  name: get-property
- description: List real estate portfolios with aggregate performance metrics
  hints:
    openWorld: true
    readOnly: true
  name: list-portfolios
- description: List current and historical property valuations
  hints:
    openWorld: true
    readOnly: true
  name: list-valuations
- description: List lease records with tenant and expiry information
  hints:
    openWorld: true
    readOnly: true
  name: list-leases
- description: Get cash flow projections for a commercial property
  hints:
    readOnly: true
  name: get-property-cashflows
---
