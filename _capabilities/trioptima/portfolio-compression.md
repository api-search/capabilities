---
categories: []
consumed_apis:
- trireduce
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
- derivatives
- submit risk constraints
- get risk constraints
- get compression results for a completed cycle including notional reduction percentage, list of terminated trades, and replacement trades created by the optimization algorithm.
- submit or replace the participant's trade population for a compression cycle. provide an array of trades with uti, notional, currency, maturity, fixed rate, pay/receive direction, and clearing house.
- confirm compression results
- submit delta ladder (dv01 by tenor bucket) risk constraints for a compression cycle. the optimization algorithm will preserve the aggregate risk profile within the specified tolerances.
- capital optimization
- get details for a specific compression cycle
- submit risk
- confirm results
- list available trireduce compression cycles. filter by status (open, submission, optimization, completed) or type (cleared, bilateral) to find cycles relevant to the participant.
- get schedule, status, and participant count for a cycle
- confirm acceptance of compression results to proceed to settlement. all cycle participants must confirm before terminations and new trades are processed. set confirmed=false to reject with an optional comment.
- compression results and settlement confirmation
- portfolio compression
- get cycle details
- confirm or reject compression results for settlement
- get the delta ladder risk constraints submitted for a compression cycle.
- financial services
- get cycle
- list trades
- osttra
- list trades submitted by the participant for a given compression cycle.
- list available compression cycles, optionally filtered by status
- list compression cycles
- submit trade population for compression
- compression
- risk management
- cme group
- get full details for a specific compression cycle including submission deadline, optimization date, settlement date, and participant count.
- reconciliation
- discover and monitor compression cycles
- get submitted delta ladder risk constraints
- risk constraint management
- list trades submitted for a compression cycle
- list submitted trades
- trade submission and review
- submit delta ladder risk constraints
- get compression results including notional reduction and new trades
- list cycles
- submit trades for compression
- get risk
- post-trade services
- get compression results
- submit trades
- get results
slug: portfolio-compression
source_filename: portfolio-compression.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trioptima Portfolio Compression\"\n  description: >-\n    Workflow capability for automating OTC derivatives portfolio compression cycles\n    via the triReduce API. Designed for derivatives operations teams, risk managers,\n    and treasury systems that need to participate in multilateral compression cycles\n    to reduce gross notional outstanding, lower counterparty risk, and optimize\n    capital requirements under Basel III / CRR2.\n  tags:\n    - Capital Optimization\n    - Compression\n    - Derivatives\n    - Financial Services\n    - Post-Trade Services\n    - Risk Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRIREDUCE_OAUTH_TOKEN: TRIREDUCE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: trireduce\n      location: ./shared/trireduce-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: portfolio-compression-api\n      description:\
  \ \"Unified REST API for automating OTC derivatives portfolio compression with triReduce.\"\n      resources:\n        - path: /v1/cycles\n          name: cycles\n          description: \"Discover and monitor compression cycles\"\n          operations:\n            - method: GET\n              name: list-cycles\n              description: \"List available compression cycles, optionally filtered by status\"\n              call: \"trireduce.list-cycles\"\n              with:\n                status: \"rest.status\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cycles/{cycleId}\n          name: cycle\n          description: \"Get details for a specific compression cycle\"\n          operations:\n            - method: GET\n              name: get-cycle\n              description: \"Get schedule, status, and participant count for a cycle\"\n              call: \"trireduce.get-cycle\"\
  \n              with:\n                cycleId: \"rest.cycleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cycles/{cycleId}/trades\n          name: trades\n          description: \"Trade submission and review\"\n          operations:\n            - method: GET\n              name: list-trades\n              description: \"List trades submitted for a compression cycle\"\n              call: \"trireduce.list-cycle-trades\"\n              with:\n                cycleId: \"rest.cycleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-trades\n              description: \"Submit trade population for compression\"\n              call: \"trireduce.submit-cycle-trades\"\n              with:\n                cycleId: \"rest.cycleId\"\n                trades: \"rest.body.trades\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cycles/{cycleId}/risk\n          name: risk\n          description: \"Risk constraint management\"\n          operations:\n            - method: GET\n              name: get-risk\n              description: \"Get submitted delta ladder risk constraints\"\n              call: \"trireduce.get-cycle-risk\"\n              with:\n                cycleId: \"rest.cycleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-risk\n              description: \"Submit delta ladder risk constraints\"\n              call: \"trireduce.submit-cycle-risk\"\n              with:\n                cycleId: \"rest.cycleId\"\n                currency: \"rest.body.currency\"\n                delta_ladder: \"rest.body.deltaLadder\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/cycles/{cycleId}/results\n          name: results\n          description: \"Compression results and settlement confirmation\"\n          operations:\n            - method: GET\n              name: get-results\n              description: \"Get compression results including notional reduction and new trades\"\n              call: \"trireduce.get-cycle-results\"\n              with:\n                cycleId: \"rest.cycleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: confirm-results\n              description: \"Confirm or reject compression results for settlement\"\n              call: \"trireduce.confirm-cycle-results\"\n              with:\n                cycleId: \"rest.cycleId\"\n                confirmed: \"rest.body.confirmed\"\n                comment: \"rest.body.comment\"\n              outputParameters:\n                - type: object\n      \
  \            mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: portfolio-compression-mcp\n      transport: http\n      description: \"MCP server for AI-assisted OTC derivatives portfolio compression automation.\"\n      tools:\n        - name: list-compression-cycles\n          description: >-\n            List available triReduce compression cycles. Filter by status (open,\n            submission, optimization, completed) or type (cleared, bilateral) to\n            find cycles relevant to the participant.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trireduce.list-cycles\"\n          with:\n            status: \"tools.status\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cycle-details\n          description: >-\n            Get full details for a specific compression cycle including submission\n            deadline, optimization\
  \ date, settlement date, and participant count.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trireduce.get-cycle\"\n          with:\n            cycleId: \"tools.cycleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-submitted-trades\n          description: \"List trades submitted by the participant for a given compression cycle.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trireduce.list-cycle-trades\"\n          with:\n            cycleId: \"tools.cycleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-trades-for-compression\n          description: >-\n            Submit or replace the participant's trade population for a compression\n            cycle. Provide an array of trades with UTI, notional, currency, maturity,\n            fixed rate, pay/receive\
  \ direction, and clearing house.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"trireduce.submit-cycle-trades\"\n          with:\n            cycleId: \"tools.cycleId\"\n            trades: \"tools.trades\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-risk-constraints\n          description: \"Get the delta ladder risk constraints submitted for a compression cycle.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trireduce.get-cycle-risk\"\n          with:\n            cycleId: \"tools.cycleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-risk-constraints\n          description: >-\n            Submit delta ladder (DV01 by tenor bucket) risk constraints for a\n            compression cycle. The optimization algorithm will preserve\
  \ the\n            aggregate risk profile within the specified tolerances.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"trireduce.submit-cycle-risk\"\n          with:\n            cycleId: \"tools.cycleId\"\n            currency: \"tools.currency\"\n            delta_ladder: \"tools.delta_ladder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-compression-results\n          description: >-\n            Get compression results for a completed cycle including notional reduction\n            percentage, list of terminated trades, and replacement trades created\n            by the optimization algorithm.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trireduce.get-cycle-results\"\n          with:\n            cycleId: \"tools.cycleId\"\n          outputParameters:\n            - type: object\n     \
  \         mapping: \"$.\"\n        - name: confirm-compression-results\n          description: >-\n            Confirm acceptance of compression results to proceed to settlement.\n            All cycle participants must confirm before terminations and new trades\n            are processed. Set confirmed=false to reject with an optional comment.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"trireduce.confirm-cycle-results\"\n          with:\n            cycleId: \"tools.cycleId\"\n            confirmed: \"tools.confirmed\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
