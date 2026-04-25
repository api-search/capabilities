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
- get partner documents.
- list issues
- portfolio analytics
- list trading resources.
- investment analytics
- administration
- event calendar.
- get private markets data.
- manage users
- get marketplace
- list trading
- operations
- get security models
- get partner docs
- trading operations.
- factset
- trading
- market data
- list events.
- research
- list events
- get private markets
- refresh ib office
- list support issues.
- get events
- get open marketplace.
- financial
- refresh ib office data.
- get event calendar.
- financial data
- get security models.
- manage user provisioning.
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
