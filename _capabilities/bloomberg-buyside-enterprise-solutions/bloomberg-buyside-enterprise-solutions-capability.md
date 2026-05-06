---
categories: []
consumed_apis: []
description: Access to Bloomberg's analytics engine for fixed income, derivatives, and multi-asset calculations including scenario analysis, stress testing, yield curve construction, and pricing models. Part of Bloomberg's buy-side enterprise solutions for institutional investors.
layout: capability
name: Bloomberg Buyside Enterprise Solutions Bloomberg Analytics API
operations:
- description: Bloomberg Buyside Enterprise Solutions Calculate fixed income analytics
  method: POST
  name: calculatefixedincome
  path: /v1/fixed-income/calculate
- description: Bloomberg Buyside Enterprise Solutions Get fixed income cash flows
  method: POST
  name: getfixedincomecashflows
  path: /v1/fixed-income/cashflows
- description: Bloomberg Buyside Enterprise Solutions Price a derivative instrument
  method: POST
  name: pricederivative
  path: /v1/derivatives/price
- description: Bloomberg Buyside Enterprise Solutions Calculate option Greeks
  method: POST
  name: calculategreeks
  path: /v1/derivatives/greeks
- description: Bloomberg Buyside Enterprise Solutions Run scenario analysis
  method: POST
  name: analyzescenario
  path: /v1/scenarios/analyze
- description: Bloomberg Buyside Enterprise Solutions Run stress test
  method: POST
  name: runstresstest
  path: /v1/stress-tests/run
- description: Bloomberg Buyside Enterprise Solutions List predefined stress scenarios
  method: GET
  name: liststressscenarios
  path: /v1/stress-tests/scenarios
- description: Bloomberg Buyside Enterprise Solutions List available yield curves
  method: GET
  name: listyieldcurves
  path: /v1/yield-curves
- description: Bloomberg Buyside Enterprise Solutions Get yield curve data
  method: GET
  name: getyieldcurve
  path: /v1/yield-curves/{curveId}
- description: Bloomberg Buyside Enterprise Solutions Evaluate security prices
  method: POST
  name: evaluatesecurities
  path: /v1/pricing/evaluate
personas: []
provider_name: Bloomberg Buyside Enterprise Solutions
provider_slug: bloomberg-buyside-enterprise-solutions
search_terms:
- runstresstest
- bloomberg buyside enterprise solutions calculate option greeks
- listyieldcurves
- bloomberg buyside enterprise solutions list available yield curves
- pricederivative
- bloomberg buyside enterprise solutions run scenario analysis
- evaluatesecurities
- market data
- analytics
- financial services
- calculatefixedincome
- buy-side
- bloomberg buyside enterprise solutions get fixed income cash flows
- portfolio management
- bloomberg
- bloomberg buyside enterprise solutions evaluate security prices
- enterprise solutions
- enterprise
- analyzescenario
- bloomberg buyside enterprise solutions run stress test
- trading
- solutions
- buyside
- getyieldcurve
- api
- bloomberg buyside enterprise solutions calculate fixed income analytics
- calculategreeks
- bloomberg buyside enterprise solutions price a derivative instrument
- bloomberg buyside enterprise solutions get yield curve data
- asset management
- getfixedincomecashflows
- liststressscenarios
- bloomberg buyside enterprise solutions list predefined stress scenarios
slug: bloomberg-buyside-enterprise-solutions-capability
source_filename: bloomberg-buyside-enterprise-solutions-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bloomberg Buyside Enterprise Solutions Bloomberg Analytics API\n  description: Access to Bloomberg's analytics engine for fixed income, derivatives, and multi-asset calculations including\n    scenario analysis, stress testing, yield curve construction, and pricing models. Part of Bloomberg's buy-side enterprise\n    solutions for institutional investors.\n  tags:\n  - Bloomberg\n  - Buyside\n  - Enterprise\n  - Solutions\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bloomberg-buyside-enterprise-solutions\n    baseUri: https://api.bloomberg.com/analytics\n    description: Bloomberg Buyside Enterprise Solutions Bloomberg Analytics API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BLOOMBERG_BUYSIDE_ENTERPRISE_SOLUTIONS_TOKEN}}'\n    resources:\n    - name: v1-fixed-income-calculate\n      path: /v1/fixed-income/calculate\n      operations:\n   \
  \   - name: calculatefixedincome\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Calculate fixed income analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-fixed-income-cashflows\n      path: /v1/fixed-income/cashflows\n      operations:\n      - name: getfixedincomecashflows\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Get fixed income cash flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-derivatives-price\n      path: /v1/derivatives/price\n      operations:\n      - name: pricederivative\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Price a derivative instrument\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: v1-derivatives-greeks\n      path: /v1/derivatives/greeks\n      operations:\n      - name: calculategreeks\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Calculate option Greeks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scenarios-analyze\n      path: /v1/scenarios/analyze\n      operations:\n      - name: analyzescenario\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Run scenario analysis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-stress-tests-run\n      path: /v1/stress-tests/run\n      operations:\n      - name: runstresstest\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Run stress test\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: v1-stress-tests-scenarios\n      path: /v1/stress-tests/scenarios\n      operations:\n      - name: liststressscenarios\n        method: GET\n        description: Bloomberg Buyside Enterprise Solutions List predefined stress scenarios\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: Filter by scenario category\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-yield-curves\n      path: /v1/yield-curves\n      operations:\n      - name: listyieldcurves\n        method: GET\n        description: Bloomberg Buyside Enterprise Solutions List available yield curves\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Filter\
  \ by currency (ISO 4217)\n        - name: type\n          in: query\n          type: string\n          description: Filter by curve type\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-yield-curves-curveid\n      path: /v1/yield-curves/{curveId}\n      operations:\n      - name: getyieldcurve\n        method: GET\n        description: Bloomberg Buyside Enterprise Solutions Get yield curve data\n        inputParameters:\n        - name: curveId\n          in: path\n          type: string\n          required: true\n          description: Yield curve identifier\n        - name: asOfDate\n          in: query\n          type: string\n          description: Curve date (defaults to most recent)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ v1-pricing-evaluate\n      path: /v1/pricing/evaluate\n      operations:\n      - name: evaluatesecurities\n        method: POST\n        description: Bloomberg Buyside Enterprise Solutions Evaluate security prices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bloomberg-buyside-enterprise-solutions-rest\n    description: REST adapter for Bloomberg Buyside Enterprise Solutions Bloomberg Analytics API.\n    resources:\n    - path: /v1/fixed-income/calculate\n      name: calculatefixedincome\n      operations:\n      - method: POST\n        name: calculatefixedincome\n        description: Bloomberg Buyside Enterprise Solutions Calculate fixed income analytics\n        call: bloomberg-buyside-enterprise-solutions.calculatefixedincome\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fixed-income/cashflows\n \
  \     name: getfixedincomecashflows\n      operations:\n      - method: POST\n        name: getfixedincomecashflows\n        description: Bloomberg Buyside Enterprise Solutions Get fixed income cash flows\n        call: bloomberg-buyside-enterprise-solutions.getfixedincomecashflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/derivatives/price\n      name: pricederivative\n      operations:\n      - method: POST\n        name: pricederivative\n        description: Bloomberg Buyside Enterprise Solutions Price a derivative instrument\n        call: bloomberg-buyside-enterprise-solutions.pricederivative\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/derivatives/greeks\n      name: calculategreeks\n      operations:\n      - method: POST\n        name: calculategreeks\n        description: Bloomberg Buyside Enterprise Solutions Calculate option Greeks\n        call: bloomberg-buyside-enterprise-solutions.calculategreeks\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scenarios/analyze\n      name: analyzescenario\n      operations:\n      - method: POST\n        name: analyzescenario\n        description: Bloomberg Buyside Enterprise Solutions Run scenario analysis\n        call: bloomberg-buyside-enterprise-solutions.analyzescenario\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stress-tests/run\n      name: runstresstest\n      operations:\n      - method: POST\n        name: runstresstest\n        description: Bloomberg Buyside Enterprise Solutions Run stress test\n        call: bloomberg-buyside-enterprise-solutions.runstresstest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stress-tests/scenarios\n      name: liststressscenarios\n      operations:\n      - method: GET\n        name: liststressscenarios\n        description: Bloomberg Buyside Enterprise Solutions List\
  \ predefined stress scenarios\n        call: bloomberg-buyside-enterprise-solutions.liststressscenarios\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/yield-curves\n      name: listyieldcurves\n      operations:\n      - method: GET\n        name: listyieldcurves\n        description: Bloomberg Buyside Enterprise Solutions List available yield curves\n        call: bloomberg-buyside-enterprise-solutions.listyieldcurves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/yield-curves/{curveId}\n      name: getyieldcurve\n      operations:\n      - method: GET\n        name: getyieldcurve\n        description: Bloomberg Buyside Enterprise Solutions Get yield curve data\n        call: bloomberg-buyside-enterprise-solutions.getyieldcurve\n        with:\n          curveId: rest.curveId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing/evaluate\n      name: evaluatesecurities\n\
  \      operations:\n      - method: POST\n        name: evaluatesecurities\n        description: Bloomberg Buyside Enterprise Solutions Evaluate security prices\n        call: bloomberg-buyside-enterprise-solutions.evaluatesecurities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bloomberg-buyside-enterprise-solutions-mcp\n    transport: http\n    description: MCP adapter for Bloomberg Buyside Enterprise Solutions Bloomberg Analytics API for AI agent use.\n    tools:\n    - name: calculatefixedincome\n      description: Bloomberg Buyside Enterprise Solutions Calculate fixed income analytics\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.calculatefixedincome\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfixedincomecashflows\n      description: Bloomberg Buyside Enterprise Solutions\
  \ Get fixed income cash flows\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.getfixedincomecashflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pricederivative\n      description: Bloomberg Buyside Enterprise Solutions Price a derivative instrument\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.pricederivative\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: calculategreeks\n      description: Bloomberg Buyside Enterprise Solutions Calculate option Greeks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.calculategreeks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analyzescenario\n      description:\
  \ Bloomberg Buyside Enterprise Solutions Run scenario analysis\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.analyzescenario\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runstresstest\n      description: Bloomberg Buyside Enterprise Solutions Run stress test\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.runstresstest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststressscenarios\n      description: Bloomberg Buyside Enterprise Solutions List predefined stress scenarios\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-buyside-enterprise-solutions.liststressscenarios\n      with:\n        category: tools.category\n        limit: tools.limit\n      inputParameters:\n\
  \      - name: category\n        type: string\n        description: Filter by scenario category\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listyieldcurves\n      description: Bloomberg Buyside Enterprise Solutions List available yield curves\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-buyside-enterprise-solutions.listyieldcurves\n      with:\n        currency: tools.currency\n        type: tools.type\n        limit: tools.limit\n      inputParameters:\n      - name: currency\n        type: string\n        description: Filter by currency (ISO 4217)\n      - name: type\n        type: string\n        description: Filter by curve type\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getyieldcurve\n      description:\
  \ Bloomberg Buyside Enterprise Solutions Get yield curve data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-buyside-enterprise-solutions.getyieldcurve\n      with:\n        curveId: tools.curveId\n        asOfDate: tools.asOfDate\n      inputParameters:\n      - name: curveId\n        type: string\n        description: Yield curve identifier\n        required: true\n      - name: asOfDate\n        type: string\n        description: Curve date (defaults to most recent)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: evaluatesecurities\n      description: Bloomberg Buyside Enterprise Solutions Evaluate security prices\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-buyside-enterprise-solutions.evaluatesecurities\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BLOOMBERG_BUYSIDE_ENTERPRISE_SOLUTIONS_TOKEN:\
  \ BLOOMBERG_BUYSIDE_ENTERPRISE_SOLUTIONS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloomberg-buyside-enterprise-solutions/refs/heads/main/capabilities/bloomberg-buyside-enterprise-solutions-capability.yaml
tags:
- Bloomberg
- Buyside
- Enterprise
- Solutions
- API
tools:
- description: Bloomberg Buyside Enterprise Solutions Calculate fixed income analytics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: calculatefixedincome
- description: Bloomberg Buyside Enterprise Solutions Get fixed income cash flows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getfixedincomecashflows
- description: Bloomberg Buyside Enterprise Solutions Price a derivative instrument
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pricederivative
- description: Bloomberg Buyside Enterprise Solutions Calculate option Greeks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: calculategreeks
- description: Bloomberg Buyside Enterprise Solutions Run scenario analysis
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analyzescenario
- description: Bloomberg Buyside Enterprise Solutions Run stress test
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runstresstest
- description: Bloomberg Buyside Enterprise Solutions List predefined stress scenarios
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststressscenarios
- description: Bloomberg Buyside Enterprise Solutions List available yield curves
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listyieldcurves
- description: Bloomberg Buyside Enterprise Solutions Get yield curve data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getyieldcurve
- description: Bloomberg Buyside Enterprise Solutions Evaluate security prices
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluatesecurities
---
