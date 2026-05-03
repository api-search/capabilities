---
categories: []
consumed_apis:
- traiana-trade-processing
- traiana-creditlink
- traiana-netlink
description: Unified workflow capability for post-trade lifecycle management combining Harmony Trade Processing, CreditLink, and NetLink APIs. Designed for back-office teams, risk managers, and operations staff managing cross-asset trade processing across FX, equities, equity derivatives, and ETD markets.
layout: capability
name: Traiana Post-Trade Processing
operations:
- description: List trades processed through the Harmony network.
  method: GET
  name: list-trades
  path: /v1/trades
- description: Submit a trade for post-trade processing.
  method: POST
  name: submit-trade
  path: /v1/trades
- description: List trade allocations.
  method: GET
  name: list-allocations
  path: /v1/allocations
- description: Submit a trade allocation.
  method: POST
  name: submit-allocation
  path: /v1/allocations
- description: List trade matching results.
  method: GET
  name: list-match-results
  path: /v1/match-results
- description: List credit limits.
  method: GET
  name: list-credit-limits
  path: /v1/credit-limits
- description: Create a new credit limit.
  method: POST
  name: create-credit-limit
  path: /v1/credit-limits
- description: Get current credit utilization.
  method: GET
  name: get-credit-utilization
  path: /v1/credit-utilization
- description: List netting sessions.
  method: GET
  name: list-netting-sessions
  path: /v1/netting-sessions
- description: Create a netting session.
  method: POST
  name: create-netting-session
  path: /v1/netting-sessions
- description: List settlement instructions.
  method: GET
  name: list-settlements
  path: /v1/settlements
- description: List compression runs.
  method: GET
  name: list-compression-runs
  path: /v1/compression-runs
- description: Create a new compression run.
  method: POST
  name: create-compression-run
  path: /v1/compression-runs
personas: []
provider_name: Traiana
provider_slug: traiana
search_terms:
- trade submission and lifecycle management.
- intraday netting sessions.
- settlement instruction management.
- list trades processed through the harmony network with filtering by asset class and status.
- submit a new trade for post-trade processing through the harmony network.
- list compression runs.
- list credit limits
- list credit breaches
- current credit utilization.
- foreign exchange
- get netting results
- list settlement instructions for payment and delivery scheduling.
- get results of a completed netting session showing net positions and settlement obligations.
- get credit utilization
- list credit limits.
- trade matching results.
- list trade matching results to monitor confirmation status.
- list allocations
- create an intraday netting session to reduce bilateral settlement obligations.
- initiate a trade compression run to reduce notional exposure and counterparty count.
- confirm trade
- get current credit utilization.
- create netting session
- list trades
- list settlement instructions.
- create credit limit
- trade compression
- list settlements
- list compression runs
- risk management
- get details of a specific trade including its matching status and lifecycle state.
- credit risk
- list credit limit breach events for risk oversight.
- create a netting session.
- list trade matching results.
- list trades processed through the harmony network.
- list trade allocations.
- submit a trade for post-trade processing.
- list all credit limits across prime-brokered, cleared, and bilateral counterparty relationships.
- create a new compression run.
- trade allocation management.
- get current credit utilization showing available headroom across all counterparties.
- submit a trade allocation.
- credit limit management and monitoring.
- list netting sessions.
- submit allocation
- list match results
- trade compression runs.
- trade matching
- settlement
- netting
- create a new credit limit.
- fintech
- list netting sessions
- post-trade processing
- list trade allocations for block trade splitting and reporting.
- confirm a matched trade to complete the confirmation workflow.
- create compression run
- get trade
- submit trade
slug: post-trade-processing
source_filename: post-trade-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Traiana Post-Trade Processing\"\n  description: \"Unified workflow capability for post-trade lifecycle management combining Harmony Trade Processing, CreditLink, and NetLink APIs. Designed for back-office teams, risk managers, and operations staff managing cross-asset trade processing across FX, equities, equity derivatives, and ETD markets.\"\n  tags:\n    - Credit Risk\n    - Fintech\n    - Foreign Exchange\n    - Netting\n    - Post-Trade Processing\n    - Settlement\n    - Trade Compression\n    - Trade Matching\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRAIANA_API_KEY: TRAIANA_API_KEY\n\ncapability:\n  consumes:\n    - import: traiana-trade-processing\n      location: ./shared/harmony-trade-processing.yaml\n    - import: traiana-creditlink\n      location: ./shared/harmony-creditlink.yaml\n    - import: traiana-netlink\n      location: ./shared/harmony-netlink.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: traiana-post-trade-api\n      description: \"Unified REST API for Traiana post-trade processing, credit risk, netting, and settlement operations.\"\n      resources:\n        - path: /v1/trades\n          name: trades\n          description: \"Trade submission and lifecycle management.\"\n          operations:\n            - method: GET\n              name: list-trades\n              description: \"List trades processed through the Harmony network.\"\n              call: \"traiana-trade-processing.list-trades\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-trade\n              description: \"Submit a trade for post-trade processing.\"\n              call: \"traiana-trade-processing.submit-trade\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/allocations\n          name: allocations\n          description: \"Trade allocation management.\"\n          operations:\n            - method: GET\n              name: list-allocations\n              description: \"List trade allocations.\"\n              call: \"traiana-trade-processing.list-allocations\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-allocation\n              description: \"Submit a trade allocation.\"\n              call: \"traiana-trade-processing.submit-allocation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/match-results\n          name: match-results\n          description: \"Trade matching results.\"\n          operations:\n            - method: GET\n              name: list-match-results\n              description: \"List trade matching results.\"\n              call:\
  \ \"traiana-trade-processing.list-match-results\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/credit-limits\n          name: credit-limits\n          description: \"Credit limit management and monitoring.\"\n          operations:\n            - method: GET\n              name: list-credit-limits\n              description: \"List credit limits.\"\n              call: \"traiana-creditlink.list-credit-limits\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-credit-limit\n              description: \"Create a new credit limit.\"\n              call: \"traiana-creditlink.create-credit-limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/credit-utilization\n          name: credit-utilization\n          description: \"Current credit\
  \ utilization.\"\n          operations:\n            - method: GET\n              name: get-credit-utilization\n              description: \"Get current credit utilization.\"\n              call: \"traiana-creditlink.get-credit-utilization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/netting-sessions\n          name: netting-sessions\n          description: \"Intraday netting sessions.\"\n          operations:\n            - method: GET\n              name: list-netting-sessions\n              description: \"List netting sessions.\"\n              call: \"traiana-netlink.list-netting-sessions\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-netting-session\n              description: \"Create a netting session.\"\n              call: \"traiana-netlink.create-netting-session\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/settlements\n          name: settlements\n          description: \"Settlement instruction management.\"\n          operations:\n            - method: GET\n              name: list-settlements\n              description: \"List settlement instructions.\"\n              call: \"traiana-netlink.list-settlements\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/compression-runs\n          name: compression-runs\n          description: \"Trade compression runs.\"\n          operations:\n            - method: GET\n              name: list-compression-runs\n              description: \"List compression runs.\"\n              call: \"traiana-netlink.list-compression-runs\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-compression-run\n\
  \              description: \"Create a new compression run.\"\n              call: \"traiana-netlink.create-compression-run\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: traiana-post-trade-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Traiana post-trade processing, risk management, and settlement operations.\"\n      tools:\n        - name: list-trades\n          description: \"List trades processed through the Harmony network with filtering by asset class and status.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-trade-processing.list-trades\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: submit-trade\n          description: \"Submit a new trade for post-trade processing through the Harmony network.\"\n          hints:\n         \
  \   readOnly: false\n            idempotent: false\n          call: \"traiana-trade-processing.submit-trade\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-trade\n          description: \"Get details of a specific trade including its matching status and lifecycle state.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-trade-processing.get-trade\"\n          with:\n            tradeId: \"tools.tradeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: confirm-trade\n          description: \"Confirm a matched trade to complete the confirmation workflow.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"traiana-trade-processing.confirm-trade\"\n          with:\n            tradeId: \"tools.tradeId\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n\n        - name: list-allocations\n          description: \"List trade allocations for block trade splitting and reporting.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-trade-processing.list-allocations\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-match-results\n          description: \"List trade matching results to monitor confirmation status.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-trade-processing.list-match-results\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-credit-limits\n          description: \"List all credit limits across prime-brokered, cleared, and bilateral counterparty relationships.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-creditlink.list-credit-limits\"\
  \n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-credit-utilization\n          description: \"Get current credit utilization showing available headroom across all counterparties.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-creditlink.get-credit-utilization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-credit-breaches\n          description: \"List credit limit breach events for risk oversight.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-creditlink.list-credit-limit-breaches\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-netting-session\n          description: \"Create an intraday netting session to reduce bilateral settlement obligations.\"\n          hints:\n           \
  \ readOnly: false\n            idempotent: false\n          call: \"traiana-netlink.create-netting-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-netting-results\n          description: \"Get results of a completed netting session showing net positions and settlement obligations.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-netlink.get-netting-results\"\n          with:\n            sessionId: \"tools.sessionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-settlements\n          description: \"List settlement instructions for payment and delivery scheduling.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traiana-netlink.list-settlements\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name:\
  \ create-compression-run\n          description: \"Initiate a trade compression run to reduce notional exposure and counterparty count.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"traiana-netlink.create-compression-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/traiana/refs/heads/main/capabilities/post-trade-processing.yaml
tags:
- Credit Risk
- Fintech
- Foreign Exchange
- Netting
- Post-Trade Processing
- Settlement
- Trade Compression
- Trade Matching
tools:
- description: List trades processed through the Harmony network with filtering by asset class and status.
  hints:
    idempotent: true
    readOnly: true
  name: list-trades
- description: Submit a new trade for post-trade processing through the Harmony network.
  hints:
    idempotent: false
    readOnly: false
  name: submit-trade
- description: Get details of a specific trade including its matching status and lifecycle state.
  hints:
    idempotent: true
    readOnly: true
  name: get-trade
- description: Confirm a matched trade to complete the confirmation workflow.
  hints:
    idempotent: false
    readOnly: false
  name: confirm-trade
- description: List trade allocations for block trade splitting and reporting.
  hints:
    idempotent: true
    readOnly: true
  name: list-allocations
- description: List trade matching results to monitor confirmation status.
  hints:
    idempotent: true
    readOnly: true
  name: list-match-results
- description: List all credit limits across prime-brokered, cleared, and bilateral counterparty relationships.
  hints:
    idempotent: true
    readOnly: true
  name: list-credit-limits
- description: Get current credit utilization showing available headroom across all counterparties.
  hints:
    idempotent: true
    readOnly: true
  name: get-credit-utilization
- description: List credit limit breach events for risk oversight.
  hints:
    idempotent: true
    readOnly: true
  name: list-credit-breaches
- description: Create an intraday netting session to reduce bilateral settlement obligations.
  hints:
    idempotent: false
    readOnly: false
  name: create-netting-session
- description: Get results of a completed netting session showing net positions and settlement obligations.
  hints:
    idempotent: true
    readOnly: true
  name: get-netting-results
- description: List settlement instructions for payment and delivery scheduling.
  hints:
    idempotent: true
    readOnly: true
  name: list-settlements
- description: Initiate a trade compression run to reduce notional exposure and counterparty count.
  hints:
    idempotent: false
    readOnly: false
  name: create-compression-run
---
