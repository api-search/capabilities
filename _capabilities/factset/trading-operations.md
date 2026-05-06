---
categories: []
consumed_apis: []
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
- list events
- list events.
- get security models.
- research
- list trading resources.
- investment analytics
- list issues
- market data
- refresh ib office data.
- get events
- get open marketplace.
- portfolio analytics
- trading operations.
- operations
- refresh ib office
- factset
- trading
- list support issues.
- get partner documents.
- financial data
- manage users
- list trading
- administration
- get partner docs
- get private markets
- get event calendar.
- manage user provisioning.
- financial
- get marketplace
- get private markets data.
- get security models
- event calendar.
slug: trading-operations
source_filename: trading-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Trading and Operations\n  description: Unified workflow for trading and operations including order management, private markets, event calendars, security\n    modeling, and user provisioning. Used by operations teams.\n  tags:\n  - FactSet\n  - Trading\n  - Operations\n  - Administration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n   \
  \   path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n\
  \    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name:\
  \ list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8091\n    namespace: trading-ops-api\n    description: Unified REST API for trading and operations.\n    resources:\n    - path: /v1/trading\n      name: trading\n    \
  \  description: Trading operations.\n      operations:\n      - method: GET\n        name: list-trading\n        description: List trading resources.\n        call: factset-trading.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Event calendar.\n      operations:\n      - method: GET\n        name: list-events\n        description: List events.\n        call: factset-events.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: trading-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted trading and operations.\n    tools:\n    - name: list-trading\n      description: List trading resources.\n      hints:\n        readOnly: true\n      call: factset-trading.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-private-markets\n      description: Get private markets data.\n\
  \      hints:\n        readOnly: true\n      call: factset-private.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-events\n      description: Get event calendar.\n      hints:\n        readOnly: true\n      call: factset-events.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-security-models\n      description: Get security models.\n      hints:\n        readOnly: true\n      call: factset-sec-model.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-issues\n      description: List support issues.\n      hints:\n        readOnly: true\n      call: factset-issues.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-users\n      description: Manage user provisioning.\n      hints:\n        readOnly: true\n      call: factset-scim.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refresh-ib-office\n\
  \      description: Refresh IB office data.\n      hints:\n        readOnly: true\n      call: factset-ib.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-marketplace\n      description: Get Open Marketplace.\n      hints:\n        readOnly: true\n      call: factset-marketplace.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-partner-docs\n      description: Get partner documents.\n      hints:\n        readOnly: true\n      call: factset-partners.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
