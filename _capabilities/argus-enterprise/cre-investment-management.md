---
categories: []
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
- list all real estate portfolios
- multi-asset portfolio analytics and reporting
- list all commercial properties
- investment management
- property valuation and appraisal
- list lease records with tenant and expiry information
- oversees a portfolio of commercial real estate assets
- list valuations
- get property details and current metrics
- portfolio management
- get property cash flow projections
- Asset Manager
- Portfolio Manager
- altus group
- commercial property management
- list portfolios
- commercial real estate
- cash flow modeling
- list current and historical property valuations
- get property
- property valuations
- argus enterprise
- valuation
- list property valuations
- complete commercial real estate investment management workflow
- list all leases
- list real estate portfolios with aggregate performance metrics
- list leases
- list properties
- get property cashflows
- get cashflows
- lease management
- get detailed information about a commercial property including valuation and occupancy
- manages individual commercial real estate assets
- asset management
- get cash flow projections for a commercial property
- list commercial real estate properties with current status and metrics
- commercial property investment and management
- cash flow projections
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
