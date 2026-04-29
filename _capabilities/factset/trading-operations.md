---
categories: []
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
- get events
- operations
- get partner docs
- investment analytics
- get marketplace
- manage user provisioning.
- trading operations.
- event calendar.
- get private markets
- financial
- get partner documents.
- list events
- list trading
- financial data
- manage users
- refresh ib office data.
- get security models
- administration
- list events.
- get security models.
- get private markets data.
- portfolio analytics
- get event calendar.
- list support issues.
- factset
- get open marketplace.
- market data
- trading
- refresh ib office
- research
- list issues
- list trading resources.
slug: trading-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Trading and Operations\"\n  description: \"Unified workflow for trading and operations including order management, private markets, event calendars, security modeling, and user provisioning. Used by operations teams.\"\n  tags:\n    - FactSet\n    - Trading\n    - Operations\n    - Administration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-trading\n      location: ./shared/trading.yaml\n    - import: factset-private\n      location: ./shared/private-markets.yaml\n    - import: factset-events\n      location: ./shared/event-calendar.yaml\n    - import: factset-sec-model\n      location: ./shared/security-modeling.yaml\n    - import: factset-issues\n      location: ./shared/issue-tracker.yaml\n    - import: factset-scim\n      location: ./shared/procure-to-pay-api-scim.yaml\n\
  \    - import: factset-ib\n      location: ./shared/investment-banking-office-refresh.yaml\n    - import: factset-marketplace\n      location: ./shared/open-marketplace.yaml\n    - import: factset-partners\n      location: ./shared/open-partners-documents.yaml\n\n  exposes:\n    - type: rest\n      port: 8091\n      namespace: trading-ops-api\n      description: \"Unified REST API for trading and operations.\"\n      resources:\n        - path: /v1/trading\n          name: trading\n          description: \"Trading operations.\"\n          operations:\n            - method: GET\n              name: list-trading\n              description: \"List trading resources.\"\n              call: \"factset-trading.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Event calendar.\"\n          operations:\n            - method: GET\n              name: list-events\n\
  \              description: \"List events.\"\n              call: \"factset-events.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: trading-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted trading and operations.\"\n      tools:\n        - name: list-trading\n          description: \"List trading resources.\"\n          hints:\n            readOnly: true\n          call: \"factset-trading.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-private-markets\n          description: \"Get private markets data.\"\n          hints:\n            readOnly: true\n          call: \"factset-private.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-events\n          description: \"Get event calendar.\"\n          hints:\n      \
  \      readOnly: true\n          call: \"factset-events.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-security-models\n          description: \"Get security models.\"\n          hints:\n            readOnly: true\n          call: \"factset-sec-model.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-issues\n          description: \"List support issues.\"\n          hints:\n            readOnly: true\n          call: \"factset-issues.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-users\n          description: \"Manage user provisioning.\"\n          hints:\n            readOnly: true\n          call: \"factset-scim.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refresh-ib-office\n          description: \"Refresh IB office\
  \ data.\"\n          hints:\n            readOnly: true\n          call: \"factset-ib.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-marketplace\n          description: \"Get Open Marketplace.\"\n          hints:\n            readOnly: true\n          call: \"factset-marketplace.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-partner-docs\n          description: \"Get partner documents.\"\n          hints:\n            readOnly: true\n          call: \"factset-partners.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/trading-operations.yaml
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
