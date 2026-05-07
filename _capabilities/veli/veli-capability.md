---
categories: []
consumed_apis: []
description: The Veli API enables financial platforms and crypto exchanges to integrate automated investment strategies for their users. Partners retain custody and execution while Veli handles strategy logic, rebalancing signals, fee collection, and performance reporting for crypto portfolios.
layout: capability
name: Veli API
operations:
- description: Veli List Strategies
  method: GET
  name: liststrategies
  path: /strategies
- description: Veli Get Strategy
  method: GET
  name: getstrategy
  path: /strategies/{strategyId}
- description: Veli List Portfolios
  method: GET
  name: listportfolios
  path: /portfolios
- description: Veli Create Portfolio
  method: POST
  name: createportfolio
  path: /portfolios
- description: Veli Get Portfolio
  method: GET
  name: getportfolio
  path: /portfolios/{portfolioId}
- description: Veli Close Portfolio
  method: DELETE
  name: closeportfolio
  path: /portfolios/{portfolioId}
- description: Veli Get Positions
  method: GET
  name: getpositions
  path: /portfolios/{portfolioId}/positions
- description: Veli Rebalance Portfolio
  method: POST
  name: rebalanceportfolio
  path: /portfolios/{portfolioId}/rebalance
- description: Veli Get Performance
  method: GET
  name: getperformance
  path: /portfolios/{portfolioId}/performance
personas: []
provider_name: Veli
provider_slug: veli
search_terms:
- rebalanceportfolio
- getpositions
- defi
- portfolio management
- getstrategy
- veli get strategy
- api
- liststrategies
- closeportfolio
- crypto
- veli close portfolio
- finance
- investment
- veli get portfolio
- veli rebalance portfolio
- veli list portfolios
- veli get performance
- getperformance
- createportfolio
- veli create portfolio
- listportfolios
- veli get positions
- veli
- veli list strategies
- getportfolio
slug: veli-capability
source_filename: veli-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Veli API\n  description: The Veli API enables financial platforms and crypto exchanges to integrate automated investment strategies\n    for their users. Partners retain custody and execution while Veli handles strategy logic, rebalancing signals, fee collection,\n    and performance reporting for crypto portfolios.\n  tags:\n  - Veli\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: veli\n    baseUri: https://api.veli.io/v1\n    description: Veli API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{VELI_TOKEN}}'\n    resources:\n    - name: strategies\n      path: /strategies\n      operations:\n      - name: liststrategies\n        method: GET\n        description: Veli List Strategies\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: 'Filter by strategy category: index, theme,\
  \ or custom'\n        - name: risk\n          in: query\n          type: string\n          description: 'Filter by risk level: conservative, moderate, aggressive'\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: strategies-strategyid\n      path: /strategies/{strategyId}\n      operations:\n      - name: getstrategy\n        method: GET\n        description: Veli Get Strategy\n        inputParameters:\n        - name: strategyId\n          in: path\n          type: string\n          required: true\n          description: Strategy identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios\n      path: /portfolios\n      operations:\n      - name: listportfolios\n\
  \        method: GET\n        description: Veli List Portfolios\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n          description: Filter portfolios by end-user ID\n        - name: strategyId\n          in: query\n          type: string\n          description: Filter portfolios by strategy\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createportfolio\n        method: POST\n        description: Veli Create Portfolio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios-portfolioid\n      path: /portfolios/{portfolioId}\n      operations:\n      - name: getportfolio\n        method: GET\n        description: Veli\
  \ Get Portfolio\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: closeportfolio\n        method: DELETE\n        description: Veli Close Portfolio\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios-portfolioid-positions\n      path: /portfolios/{portfolioId}/positions\n      operations:\n      - name: getpositions\n        method: GET\n        description: Veli Get Positions\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios-portfolioid-rebalance\n      path: /portfolios/{portfolioId}/rebalance\n      operations:\n      - name: rebalanceportfolio\n        method: POST\n        description: Veli Rebalance Portfolio\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios-portfolioid-performance\n      path: /portfolios/{portfolioId}/performance\n      operations:\n      - name: getperformance\n        method: GET\n        description: Veli Get Performance\n        inputParameters:\n        - name: portfolioId\n          in:\
  \ path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: period\n          in: query\n          type: string\n          description: 'Time period: 1d, 7d, 1m, 3m, 1y, all'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: veli-rest\n    description: REST adapter for Veli API.\n    resources:\n    - path: /strategies\n      name: liststrategies\n      operations:\n      - method: GET\n        name: liststrategies\n        description: Veli List Strategies\n        call: veli.liststrategies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /strategies/{strategyId}\n      name: getstrategy\n      operations:\n      - method: GET\n        name: getstrategy\n        description: Veli Get Strategy\n        call: veli.getstrategy\n        with:\n          strategyId:\
  \ rest.strategyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolios\n      name: listportfolios\n      operations:\n      - method: GET\n        name: listportfolios\n        description: Veli List Portfolios\n        call: veli.listportfolios\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolios\n      name: createportfolio\n      operations:\n      - method: POST\n        name: createportfolio\n        description: Veli Create Portfolio\n        call: veli.createportfolio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolios/{portfolioId}\n      name: getportfolio\n      operations:\n      - method: GET\n        name: getportfolio\n        description: Veli Get Portfolio\n        call: veli.getportfolio\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolios/{portfolioId}\n\
  \      name: closeportfolio\n      operations:\n      - method: DELETE\n        name: closeportfolio\n        description: Veli Close Portfolio\n        call: veli.closeportfolio\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolios/{portfolioId}/positions\n      name: getpositions\n      operations:\n      - method: GET\n        name: getpositions\n        description: Veli Get Positions\n        call: veli.getpositions\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolios/{portfolioId}/rebalance\n      name: rebalanceportfolio\n      operations:\n      - method: POST\n        name: rebalanceportfolio\n        description: Veli Rebalance Portfolio\n        call: veli.rebalanceportfolio\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /portfolios/{portfolioId}/performance\n      name: getperformance\n      operations:\n      - method: GET\n        name: getperformance\n        description: Veli Get Performance\n        call: veli.getperformance\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: veli-mcp\n    transport: http\n    description: MCP adapter for Veli API for AI agent use.\n    tools:\n    - name: liststrategies\n      description: Veli List Strategies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: veli.liststrategies\n      with:\n        category: tools.category\n        risk: tools.risk\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: category\n        type: string\n        description: 'Filter by strategy category: index, theme, or custom'\n\
  \      - name: risk\n        type: string\n        description: 'Filter by risk level: conservative, moderate, aggressive'\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstrategy\n      description: Veli Get Strategy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: veli.getstrategy\n      with:\n        strategyId: tools.strategyId\n      inputParameters:\n      - name: strategyId\n        type: string\n        description: Strategy identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listportfolios\n      description: Veli List Portfolios\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: veli.listportfolios\n      with:\n        userId:\
  \ tools.userId\n        strategyId: tools.strategyId\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: userId\n        type: string\n        description: Filter portfolios by end-user ID\n      - name: strategyId\n        type: string\n        description: Filter portfolios by strategy\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createportfolio\n      description: Veli Create Portfolio\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: veli.createportfolio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getportfolio\n      description: Veli Get Portfolio\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: veli.getportfolio\n\
  \      with:\n        portfolioId: tools.portfolioId\n      inputParameters:\n      - name: portfolioId\n        type: string\n        description: Portfolio identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: closeportfolio\n      description: Veli Close Portfolio\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: veli.closeportfolio\n      with:\n        portfolioId: tools.portfolioId\n      inputParameters:\n      - name: portfolioId\n        type: string\n        description: Portfolio identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpositions\n      description: Veli Get Positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: veli.getpositions\n      with:\n        portfolioId: tools.portfolioId\n      inputParameters:\n      - name: portfolioId\n\
  \        type: string\n        description: Portfolio identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rebalanceportfolio\n      description: Veli Rebalance Portfolio\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: veli.rebalanceportfolio\n      with:\n        portfolioId: tools.portfolioId\n      inputParameters:\n      - name: portfolioId\n        type: string\n        description: Portfolio identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getperformance\n      description: Veli Get Performance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: veli.getperformance\n      with:\n        portfolioId: tools.portfolioId\n        period: tools.period\n      inputParameters:\n      - name: portfolioId\n        type: string\n        description: Portfolio\
  \ identifier\n        required: true\n      - name: period\n        type: string\n        description: 'Time period: 1d, 7d, 1m, 3m, 1y, all'\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    VELI_TOKEN: VELI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veli/refs/heads/main/capabilities/veli-capability.yaml
tags:
- Veli
- API
tools:
- description: Veli List Strategies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststrategies
- description: Veli Get Strategy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstrategy
- description: Veli List Portfolios
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listportfolios
- description: Veli Create Portfolio
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createportfolio
- description: Veli Get Portfolio
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getportfolio
- description: Veli Close Portfolio
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: closeportfolio
- description: Veli Get Positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpositions
- description: Veli Rebalance Portfolio
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rebalanceportfolio
- description: Veli Get Performance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperformance
---
