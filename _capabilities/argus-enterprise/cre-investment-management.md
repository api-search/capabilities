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
- manages individual commercial real estate assets
- lease management
- oversees a portfolio of commercial real estate assets
- list all leases
- get cashflows
- list all real estate portfolios
- list current and historical property valuations
- list all commercial properties
- multi-asset portfolio analytics and reporting
- list property valuations
- list commercial real estate properties with current status and metrics
- list leases
- commercial property management
- cash flow projections
- list real estate portfolios with aggregate performance metrics
- get property cash flow projections
- argus enterprise
- list portfolios
- cash flow modeling
- investment management
- list valuations
- commercial property investment and management
- get property details and current metrics
- valuation
- get property cashflows
- list properties
- Portfolio Manager
- property valuations
- get detailed information about a commercial property including valuation and occupancy
- Asset Manager
- get cash flow projections for a commercial property
- altus group
- asset management
- complete commercial real estate investment management workflow
- property valuation and appraisal
- list lease records with tenant and expiry information
- get property
- commercial real estate
- portfolio management
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
