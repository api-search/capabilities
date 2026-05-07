---
categories: []
consumed_apis: []
description: Workflow capability for automating OTC derivatives portfolio compression cycles via the triReduce API. Designed for derivatives operations teams, risk managers, and treasury systems that need to participate in multilateral compression cycles to reduce gross notional outstanding, lower counterparty risk, and optimize capital requirements under Basel III / CRR2.
layout: capability
name: Trioptima Portfolio Compression
operations:
- description: List available compression cycles, optionally filtered by status
  method: GET
  name: list-cycles
  path: /v1/cycles
- description: Get schedule, status, and participant count for a cycle
  method: GET
  name: get-cycle
  path: /v1/cycles/{cycleId}
- description: List trades submitted for a compression cycle
  method: GET
  name: list-trades
  path: /v1/cycles/{cycleId}/trades
- description: Submit trade population for compression
  method: POST
  name: submit-trades
  path: /v1/cycles/{cycleId}/trades
- description: Get submitted delta ladder risk constraints
  method: GET
  name: get-risk
  path: /v1/cycles/{cycleId}/risk
- description: Submit delta ladder risk constraints
  method: POST
  name: submit-risk
  path: /v1/cycles/{cycleId}/risk
- description: Get compression results including notional reduction and new trades
  method: GET
  name: get-results
  path: /v1/cycles/{cycleId}/results
- description: Confirm or reject compression results for settlement
  method: POST
  name: confirm-results
  path: /v1/cycles/{cycleId}/results
personas: []
provider_name: Trioptima
provider_slug: trioptima
search_terms:
- get details for a specific compression cycle
- get submitted delta ladder risk constraints
- submit trade population for compression
- submit delta ladder risk constraints
- list available trireduce compression cycles. filter by status (open, submission, optimization, completed) or type (cleared, bilateral) to find cycles relevant to the participant.
- submit risk constraints
- get compression results
- confirm results
- confirm acceptance of compression results to proceed to settlement. all cycle participants must confirm before terminations and new trades are processed. set confirmed=false to reject with an optional comment.
- list trades submitted for a compression cycle
- get results
- risk constraint management
- submit trades for compression
- get cycle
- portfolio compression
- get the delta ladder risk constraints submitted for a compression cycle.
- list available compression cycles, optionally filtered by status
- trade submission and review
- list cycles
- osttra
- list submitted trades
- cme group
- list compression cycles
- submit trades
- reconciliation
- derivatives
- financial services
- get schedule, status, and participant count for a cycle
- list trades submitted by the participant for a given compression cycle.
- confirm or reject compression results for settlement
- post-trade services
- list trades
- get compression results including notional reduction and new trades
- compression results and settlement confirmation
- get compression results for a completed cycle including notional reduction percentage, list of terminated trades, and replacement trades created by the optimization algorithm.
- submit or replace the participant's trade population for a compression cycle. provide an array of trades with uti, notional, currency, maturity, fixed rate, pay/receive direction, and clearing house.
- get risk constraints
- get cycle details
- get risk
- get full details for a specific compression cycle including submission deadline, optimization date, settlement date, and participant count.
- confirm compression results
- capital optimization
- submit delta ladder (dv01 by tenor bucket) risk constraints for a compression cycle. the optimization algorithm will preserve the aggregate risk profile within the specified tolerances.
- compression
- submit risk
- risk management
- discover and monitor compression cycles
slug: portfolio-compression
source_filename: portfolio-compression.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trioptima Portfolio Compression\n  description: Workflow capability for automating OTC derivatives portfolio compression cycles via the triReduce API. Designed\n    for derivatives operations teams, risk managers, and treasury systems that need to participate in multilateral compression\n    cycles to reduce gross notional outstanding, lower counterparty risk, and optimize capital requirements under Basel III\n    / CRR2.\n  tags:\n  - Capital Optimization\n  - Compression\n  - Derivatives\n  - Financial Services\n  - Post-Trade Services\n  - Risk Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRIREDUCE_OAUTH_TOKEN: TRIREDUCE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: trireduce\n    baseUri: https://rates.trireduce.com/api/v1\n    description: triReduce portfolio compression API for OTC derivatives\n    authentication:\n      type: bearer\n      token: '{{env.TRIREDUCE_OAUTH_TOKEN}}'\n\
  \    resources:\n    - name: cycles\n      path: /cycles\n      description: Compression cycle discovery and management\n      operations:\n      - name: list-cycles\n        method: GET\n        description: List available compression cycles filtered by status and type\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by cycle status (open, submission, optimization, completed)\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by cycle type (cleared, bilateral)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cycle\n        method: GET\n        description: Get detailed information about a specific compression cycle\n        inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n    \
  \      required: true\n          description: Unique cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cycle-trades\n      path: /cycles/{cycleId}/trades\n      description: Trade submission and retrieval for compression cycles\n      operations:\n      - name: list-cycle-trades\n        method: GET\n        description: List trades submitted for a compression cycle\n        inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n          required: true\n          description: Compression cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-cycle-trades\n        method: POST\n        description: Submit trade population for a compression cycle\n        inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n\
  \          required: true\n          description: Compression cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            trades: '{{tools.trades}}'\n    - name: cycle-risk\n      path: /cycles/{cycleId}/risk\n      description: Risk data management for compression cycles\n      operations:\n      - name: get-cycle-risk\n        method: GET\n        description: Get risk data submitted for a compression cycle\n        inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n          required: true\n          description: Compression cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-cycle-risk\n        method: POST\n        description: Submit delta ladder risk constraints for compression\n   \
  \     inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n          required: true\n          description: Compression cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            currency: '{{tools.currency}}'\n            deltaLadder: '{{tools.delta_ladder}}'\n    - name: cycle-results\n      path: /cycles/{cycleId}/results\n      description: Compression results and confirmation\n      operations:\n      - name: get-cycle-results\n        method: GET\n        description: Get compression results including terminations and new trades\n        inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n          required: true\n          description: Compression cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: confirm-cycle-results\n        method: POST\n        description: Confirm or reject compression results\n        inputParameters:\n        - name: cycleId\n          in: path\n          type: string\n          required: true\n          description: Compression cycle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            confirmed: '{{tools.confirmed}}'\n            comment: '{{tools.comment}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: portfolio-compression-api\n    description: Unified REST API for automating OTC derivatives portfolio compression with triReduce.\n    resources:\n    - path: /v1/cycles\n      name: cycles\n      description: Discover and monitor compression cycles\n      operations:\n      - method: GET\n        name: list-cycles\n        description: List available\
  \ compression cycles, optionally filtered by status\n        call: trireduce.list-cycles\n        with:\n          status: rest.status\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cycles/{cycleId}\n      name: cycle\n      description: Get details for a specific compression cycle\n      operations:\n      - method: GET\n        name: get-cycle\n        description: Get schedule, status, and participant count for a cycle\n        call: trireduce.get-cycle\n        with:\n          cycleId: rest.cycleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cycles/{cycleId}/trades\n      name: trades\n      description: Trade submission and review\n      operations:\n      - method: GET\n        name: list-trades\n        description: List trades submitted for a compression cycle\n        call: trireduce.list-cycle-trades\n        with:\n          cycleId: rest.cycleId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-trades\n        description: Submit trade population for compression\n        call: trireduce.submit-cycle-trades\n        with:\n          cycleId: rest.cycleId\n          trades: rest.body.trades\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cycles/{cycleId}/risk\n      name: risk\n      description: Risk constraint management\n      operations:\n      - method: GET\n        name: get-risk\n        description: Get submitted delta ladder risk constraints\n        call: trireduce.get-cycle-risk\n        with:\n          cycleId: rest.cycleId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-risk\n        description: Submit delta ladder risk constraints\n        call: trireduce.submit-cycle-risk\n        with:\n          cycleId: rest.cycleId\n          currency: rest.body.currency\n\
  \          delta_ladder: rest.body.deltaLadder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cycles/{cycleId}/results\n      name: results\n      description: Compression results and settlement confirmation\n      operations:\n      - method: GET\n        name: get-results\n        description: Get compression results including notional reduction and new trades\n        call: trireduce.get-cycle-results\n        with:\n          cycleId: rest.cycleId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: confirm-results\n        description: Confirm or reject compression results for settlement\n        call: trireduce.confirm-cycle-results\n        with:\n          cycleId: rest.cycleId\n          confirmed: rest.body.confirmed\n          comment: rest.body.comment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: portfolio-compression-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted OTC derivatives portfolio compression automation.\n    tools:\n    - name: list-compression-cycles\n      description: List available triReduce compression cycles. Filter by status (open, submission, optimization, completed)\n        or type (cleared, bilateral) to find cycles relevant to the participant.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trireduce.list-cycles\n      with:\n        status: tools.status\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cycle-details\n      description: Get full details for a specific compression cycle including submission deadline, optimization date, settlement\n        date, and participant count.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trireduce.get-cycle\n      with:\n        cycleId: tools.cycleId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-submitted-trades\n      description: List trades submitted by the participant for a given compression cycle.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trireduce.list-cycle-trades\n      with:\n        cycleId: tools.cycleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-trades-for-compression\n      description: Submit or replace the participant's trade population for a compression cycle. Provide an array of trades\n        with UTI, notional, currency, maturity, fixed rate, pay/receive direction, and clearing house.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trireduce.submit-cycle-trades\n      with:\n        cycleId: tools.cycleId\n        trades: tools.trades\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-risk-constraints\n      description: Get the delta ladder risk constraints\
  \ submitted for a compression cycle.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trireduce.get-cycle-risk\n      with:\n        cycleId: tools.cycleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-risk-constraints\n      description: Submit delta ladder (DV01 by tenor bucket) risk constraints for a compression cycle. The optimization algorithm\n        will preserve the aggregate risk profile within the specified tolerances.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trireduce.submit-cycle-risk\n      with:\n        cycleId: tools.cycleId\n        currency: tools.currency\n        delta_ladder: tools.delta_ladder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-compression-results\n      description: Get compression results for a completed cycle including notional reduction percentage, list of terminated\n       \
  \ trades, and replacement trades created by the optimization algorithm.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trireduce.get-cycle-results\n      with:\n        cycleId: tools.cycleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: confirm-compression-results\n      description: Confirm acceptance of compression results to proceed to settlement. All cycle participants must confirm\n        before terminations and new trades are processed. Set confirmed=false to reject with an optional comment.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: trireduce.confirm-cycle-results\n      with:\n        cycleId: tools.cycleId\n        confirmed: tools.confirmed\n        comment: tools.comment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trioptima/refs/heads/main/capabilities/portfolio-compression.yaml
tags:
- Capital Optimization
- Compression
- Derivatives
- Financial Services
- Post-Trade Services
- Risk Management
tools:
- description: List available triReduce compression cycles. Filter by status (open, submission, optimization, completed) or type (cleared, bilateral) to find cycles relevant to the participant.
  hints:
    openWorld: false
    readOnly: true
  name: list-compression-cycles
- description: Get full details for a specific compression cycle including submission deadline, optimization date, settlement date, and participant count.
  hints:
    openWorld: false
    readOnly: true
  name: get-cycle-details
- description: List trades submitted by the participant for a given compression cycle.
  hints:
    openWorld: false
    readOnly: true
  name: list-submitted-trades
- description: Submit or replace the participant's trade population for a compression cycle. Provide an array of trades with UTI, notional, currency, maturity, fixed rate, pay/receive direction, and clearing house.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-trades-for-compression
- description: Get the delta ladder risk constraints submitted for a compression cycle.
  hints:
    openWorld: false
    readOnly: true
  name: get-risk-constraints
- description: Submit delta ladder (DV01 by tenor bucket) risk constraints for a compression cycle. The optimization algorithm will preserve the aggregate risk profile within the specified tolerances.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-risk-constraints
- description: Get compression results for a completed cycle including notional reduction percentage, list of terminated trades, and replacement trades created by the optimization algorithm.
  hints:
    openWorld: false
    readOnly: true
  name: get-compression-results
- description: Confirm acceptance of compression results to proceed to settlement. All cycle participants must confirm before terminations and new trades are processed. Set confirmed=false to reject with an optional comment.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: confirm-compression-results
---
