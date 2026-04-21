---
consumed_apis:
- factset-trading
- factset-private
- factset-events
- factset-sec-model
- factset-issues
- factset-scim
- factset-ib
- factset-marketplace
- factset-partners
description: Unified workflow for trading and operations including order management, private markets, event calendars, security modeling, and user provisioning. Used by operations teams.
layout: capability
name: FactSet Trading and Operations
operations:
- description: List trading resources.
  method: GET
  name: list-trading
  path: /v1/trading
- description: List events.
  method: GET
  name: list-events
  path: /v1/events
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- refresh ib office data.
- list trading resources.
- list trading
- get marketplace
- trading operations.
- investment analytics
- list issues
- list events.
- financial
- refresh ib office
- trading
- operations
- event calendar.
- research
- get partner documents.
- list support issues.
- portfolio analytics
- administration
- market data
- get security models
- get private markets data.
- manage users
- manage user provisioning.
- list events
- get events
- get open marketplace.
- get security models.
- factset
- financial data
- get event calendar.
- get partner docs
- get private markets
slug: trading-operations
tags:
- FactSet
- Trading
- Operations
- Administration
tools:
- description: List trading resources.
  hints:
    readOnly: true
  name: list-trading
- description: Get private markets data.
  hints:
    readOnly: true
  name: get-private-markets
- description: Get event calendar.
  hints:
    readOnly: true
  name: get-events
- description: Get security models.
  hints:
    readOnly: true
  name: get-security-models
- description: List support issues.
  hints:
    readOnly: true
  name: list-issues
- description: Manage user provisioning.
  hints:
    readOnly: true
  name: manage-users
- description: Refresh IB office data.
  hints:
    readOnly: true
  name: refresh-ib-office
- description: Get Open Marketplace.
  hints:
    readOnly: true
  name: get-marketplace
- description: Get partner documents.
  hints:
    readOnly: true
  name: get-partner-docs
---
